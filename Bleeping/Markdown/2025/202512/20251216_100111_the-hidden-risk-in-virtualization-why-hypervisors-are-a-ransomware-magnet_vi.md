# Rủi ro ẩn trong ảo hóa: Tại sao Hypervisors lại thu hút Ransomware

![Tin tặc nhìn màn hình máy tính](https://www.bleepstatic.com/content/posts/2025/12/14/huntress-header-image.jpg)

_Tác giả: Dray Agha, Senior Manager, Hunt & Response, tại Huntress Labs_

Hypervisors là xương sống của các môi trường ảo hóa hiện đại, nhưng khi bị xâm phạm, chúng có thể trở thành nhân tố khuếch đại sức mạnh cho kẻ tấn công. Một lần vi phạm ở lớp này có thể đặt hàng chục hoặc thậm chí hàng trăm máy ảo vào rủi ro cùng lúc. Khác với các endpoint truyền thống, hypervisors thường hoạt động với tầm nhìn và biện pháp bảo vệ hạn chế, có nghĩa là các công cụ bảo mật thông thường có thể bị mù trước một cuộc tấn công cho đến khi quá muộn.

Từ góc nhìn của chúng tôi trong SOC và hoạt động hunt tại Huntress, chúng tôi thấy các đối thủ ngày càng nhắm vào hypervisors để triển khai ransomware ở quy mô lớn. Cụ thể, trong năm 2025, dữ liệu trường hợp của Huntress cho thấy sự tăng vọt đáng kinh ngạc trong ransomware nhắm vào hypervisor: vai trò của nó trong mã hóa độc hại tăng từ chỉ 3% trong nửa đầu năm lên 25% cho đến hiện tại trong nửa sau.

Tác nhân chính thúc đẩy xu hướng này là nhóm ransomware Akira. Sự dịch chuyển này nhấn mạnh tầm quan trọng của việc làm cứng lớp hypervisor với độ nghiêm ngặt tương tự như áp dụng cho endpoints và servers.

Trong bài viết này, chúng tôi nêu ra các mối đe dọa đã quan sát được ngoài thực địa và cung cấp hướng dẫn thực tiễn để bảo mật hạ tầng hypervisor của bạn, từ việc vá lỗi và kiểm soát truy cập đến gia cố runtime và chiến lược phục hồi vững chắc.

## Hypervisors: Một Chiến Trường Mới trong Hoạt Động Ransomware

Trong vài tháng cuối của năm 2025, Huntress đã quan sát các đối thủ nhắm vào hypervisors nhằm cố gắng vượt qua các kiểm soát bảo mật endpoint và mạng.

Và điều này có lý: khi các nhà phòng thủ tiếp tục làm cứng endpoints và servers, các đối thủ ngày càng chuyển trọng tâm sang lớp hypervisor, nền tảng của hạ tầng ảo hóa — một Type 1 ("bare metal") hypervisor là nền tảng, được cài đặt trực tiếp trên phần cứng máy chủ, một Type 2 ("hosted") hypervisor là một ứng dụng nằm trên hệ điều hành máy tính thông thường của bạn. Sự chuyển dịch này tuân theo một kịch bản quen thuộc.

Chúng tôi đã thấy điều này với các cuộc tấn công vào các thiết bị VPN: các tác nhân đe dọa nhận ra rằng hệ điều hành chủ thường là sở hữu hoặc bị hạn chế, có nghĩa là các nhà phòng thủ không thể cài đặt các kiểm soát bảo mật quan trọng như EDR. Điều này tạo ra một lỗ hổng tầm nhìn đáng kể.

Nguyên lý tương tự áp dụng cho Type 1 hypervisors; chúng là mục tiêu tối ưu để "đổ bộ và mở rộng" nơi mà bảo mật endpoint truyền thống thường không thể tiếp cận.

Chúng tôi cũng đã quan sát nhiều trường hợp nơi các toán ransomware triển khai **ransomware payloads trực tiếp thông qua hypervisors**, bỏ qua hoàn toàn các biện pháp bảo vệ endpoint truyền thống.

Trong một số trường hợp, kẻ tấn công tận dụng các công cụ tích hợp sẵn như openssl để thực hiện mã hóa các volume của máy ảo, tránh cần tải lên các binary ransomware tùy chỉnh.

* Một khi đã ở trong mạng, kẻ tấn công thường pivot về phía hypervisors bằng cách sử dụng chứng thực nội bộ bị xâm phạm trong các môi trường nơi phân đoạn mạng không ngăn được việc di chuyển ngang tới trang quản lý hypervisor. Hành động này cấp cho họ quyền điều khiển nâng cao đối với nhiều hệ thống guest chỉ từ một giao diện quản lý duy nhất.
* Chúng tôi đã thấy việc lạm dụng các tiện ích quản lý Hyper-V để thay đổi cài đặt VM và làm suy yếu các tính năng bảo mật. Điều này bao gồm vô hiệu hóa các biện pháp phòng thủ endpoint, can thiệp vào virtual switches, và chuẩn bị VM để triển khai ransomware ở quy mô lớn.

![Fig 1: Extract from Huntress Platform detecting adversary manipulating Hyper-V](https://www.bleepstatic.com/images/news/security/h/huntress-labs/virtualization-ransomware/huntress-detection-timeline.jpg)

**Fig 1: Extract from Huntress Platform detecting adversary manipulating Hyper-V**

Sự dịch chuyển này nhấn mạnh một xu hướng ngày càng gia tăng và khó chịu: Kẻ tấn công đang nhắm vào hạ tầng điều khiển tất cả các host, và khi có quyền truy cập vào hypervisor, các đối thủ khuếch đại đáng kể tác động của cuộc xâm nhập.

## [Chia Sẻ Món Quà Bảo Mật](https://www.huntress.com/cybersecurity-education/cybersecurity-awareness/secure-the-holiday-spirit-from-cyber-attacks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-11-camp-sat-global-prospect-all-x-gift%5Fof%5Fsat&utm%5Fcontent=december&hnt=f2jcfqx6qjxf)

Tin tặc cũng thích kỳ nghỉ! Hãy chia sẻ Khóa Đào Tạo Nhận Thức Bảo Mật MIỄN PHÍ với gia đình & bạn bè để giữ an toàn.

Các bài học nhanh, vui nhộn để rèn luyện kiến thức mạng! Truy cập được kéo dài đến 1/31/26.

[Đăng Ký Miễn Phí](https://www.huntress.com/cybersecurity-education/cybersecurity-awareness/secure-the-holiday-spirit-from-cyber-attacks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-11-camp-sat-global-prospect-all-x-gift%5Fof%5Fsat&utm%5Fcontent=december&hnt=f2jcfqx6qjxf)

## Bảo đảm truy cập, thực thi nguyên tắc quyền tối thiểu, và tách biệt plane quản lý

Nếu kẻ tấn công có thể lấy được chứng thực quản trị cho hypervisor, họ có thể triển khai payloads ransomware ảnh hưởng đến mọi VM trên host. Ngoài ra, việc sử dụng tài khoản domain-joined (ví dụ, tài khoản Active Directory (AD)) cho ESXi làm tăng rủi ro di chuyển ngang.

Nên làm gì:

* **Sử dụng tài khoản ESXi cục bộ.** Tránh sử dụng tài khoản domain admin chung cho quản trị. Thay vào đó, tạo các tài khoản ESXi cục bộ chuyên dụng hoặc các tài khoản domain bị giới hạn chặt chẽ, được kiểm toán chỉ với các quyền cần thiết. Nếu một tài khoản domain admin bị xâm phạm, sự tách biệt này ngăn chặn việc truy cập trái phép ngay lập tức vào hypervisor và các máy ảo của nó.
* **Thực thi Xác thực đa yếu tố (MFA).** Đây là điều bắt buộc không thể thương lượng cho tất cả các hạ tầng quan trọng. Thực thi MFA cho các giao diện quản lý host và truy cập vCenter để bảo vệ chống lại việc đánh cắp chứng thực. Một kẻ tấn công có username và mật khẩu bị đánh cắp sẽ bị chặn, làm tăng đáng kể nỗ lực cần thiết để xâm phạm thành công. Biện pháp này cung cấp phòng thủ vững chắc chống lại các cuộc phishing và brute-force thông thường. **Sử dụng mật khẩu mạnh được lưu trữ trong kho mật khẩu an toàn.** Chứng thực ESXi nên có mật khẩu cực kỳ mạnh và chỉ được lưu trữ trong kho mật khẩu chuyên dụng, không bao giờ trong tài liệu chia sẻ hoặc các vị trí kém an toàn. Điều này ngăn chặn việc lộ chứng thực thông qua các vector tấn công phổ biến như file shares bị xâm phạm hoặc thực hành quản lý mật khẩu không an toàn.
* **Tách biệt mạng quản lý host.** Tách mạng quản lý hypervisor ra khỏi mạng sản xuất và mạng người dùng chung. Tạo một VLAN chuyên dụng hoặc đoạn mạng được tách biệt về mặt logic và/hoặc vật lý. Bằng cách giới hạn số lượng endpoint có thể thử kết nối với giao diện quản lý hypervisor, bạn giảm đáng kể bề mặt tấn công tiềm năng.
* **Triển khai jump box hoặc bastion server.** Để đảm bảo mọi truy cập quản trị đều được kiểm toán và kiểm soát, hãy triển khai một jump box hoặc bastion server mà admin IT phải truy cập trước khi pivot tới hypervisor. Cấu hình này loại bỏ các kết nối trực tiếp từ các workstation admin có thể kém an toàn. Jump box đóng vai trò là điểm kiểm tra được giám sát, cho phép ghi lại phiên, ghi tất cả các lệnh và thực thi chính sách bảo mật trước khi cấp quyền truy cập vào hạ tầng quan trọng.
* **Áp dụng nguyên tắc quyền tối thiểu (PoLP).** Giới hạn nghiêm ngặt quyền truy cập vào control plane (vCenter và các host riêng lẻ). Chỉ cấp các vai trò tối thiểu cần thiết cho các chức năng quản trị, như quản lý tài nguyên hoặc vá lỗi, cho cả quản trị viên con người và service accounts. Thực thi PoLP đảm bảo rằng một tài khoản bị xâm phạm không thể bị lợi dụng để thay đổi toàn bộ môi trường ảo hóa.
* **Hạn chế truy cập quản lý cho các thiết bị admin chuyên dụng.** Giới hạn quyền truy cập giao diện quản lý ESXi chỉ cho các thiết bị quản trị cụ thể có địa chỉ IP tĩnh. Điều này tạo thêm rào cản bằng cách đảm bảo chỉ các endpoint đã biết, được phép mới có thể thử kết nối tới hypervisor, giảm thêm bề mặt tấn công.

## Khoá chặt môi trường runtime của hypervisor và thực thi kiểm soát mã/thực thi

Một trong những rủi ro đặc thù với ransomware ở mức hypervisor là khi kẻ tấn công đã ở trên host, họ có thể chạy mã ở mức hypervisor, vượt qua các kiểm soát của guest-OS. Bạn cần làm cứng host để nó chỉ chạy mã đã được mong đợi, ký và các module tin cậy.

Nên làm gì:

* Bật cài đặt nâng cao của host **VMkernel.Boot.execInstalledOnly = TRUE** để chỉ các binary được cài đặt thông qua VIB có chữ ký mới có thể thực thi, điều này ngăn chặn các binary độc hại tùy chỉnh chạy trên host.
* Vô hiệu hóa/đóng các dịch vụ không cần thiết như SSH hoặc ESXi Shell khi không sử dụng; bật lockdown mode.

## Giữ hypervisor được vá, cập nhật, và giảm thiểu các bề mặt phơi nhiễm

Kẻ tấn công đang tích cực nhắm vào các host ESXi thông qua các lỗ hổng đã biết cho các hoạt động mã hóa hàng loạt. 0days và CVEs có thể không phải là nguyên nhân phổ biến nhất / thực tế cho việc xâm phạm, mà thường là các sơ hở trong phân đoạn bảo mật. Tuy nhiên, duy trì việc vá lỗi là điều sống còn.

Ví dụ, CVE-2024-37085 làm nổi bật rủi ro hypervisor này một cách hoàn hảo. Lỗ hổng này cho phép kẻ tấn công có đủ quyền AD bỏ qua xác thực và ngay lập tức chiếm quyền quản trị đầy đủ của một host ESXi, dẫn đến việc mã hóa hàng loạt tất cả các VM trong vài giây.

Kỹ thuật khai thác hoạt động vì các host ESXi dễ bị tấn công tự động cấp quyền admin đầy đủ cho nhóm 'ESX Admins' AD. Các tác nhân đe dọa chỉ cần tái tạo nhóm đó để ngay lập tức chiếm chìa khóa vương quốc.

Những xâm phạm ban đầu này thường bắt đầu với các giao diện quản lý chưa được vá hoặc các giao thức phơi nhiễm, như Service Location Protocol (SLP), vốn cung cấp một điểm vào với ít nỗ lực.

Nên làm gì:

* Duy trì danh mục tất cả các host ESXi (và các thành phần quản lý liên quan như vCenter) và mức vá lỗi của chúng.
* Ưu tiên cập nhật và bản vá bảo mật từ nhà cung cấp, đặc biệt cho các CVE liên quan đến hypervisor.
* Vô hiệu hóa hoặc giới hạn các dịch vụ bạn không cần hoặc đảm bảo chúng không bị phơi nhiễm ra bên ngoài. Service Location Protocol (SLP/port 427) đã bị các nhóm ransomware như ESXArgs lợi dụng và nên được vô hiệu hóa. Làm theo hướng dẫn khắc phục chính thức của VMware.
* Đảm bảo rằng các host ESXi không bị phơi nhiễm trực tiếp ra Internet cho mục đích quản lý. Sử dụng VPN, bastion hosts, hoặc mạng quản lý cô lập.

## Chiến lược sao lưu, snapshots bất biến và khả năng phục hồi nhanh

Ngay cả với các biện pháp phòng ngừa mạnh mẽ, rủi ro vẫn tồn tại. Lớp hypervisor có tác động cao; việc có phương án dự phòng là bắt buộc. Nhiều hướng dẫn nhấn mạnh rằng phục hồi là tuyến phòng thủ cuối cùng. Ransomware nhắm vào ESXi thường tìm cách mã hóa VMDKs và các file host; nếu không có bản sao lưu tốt, bạn có thể buộc phải trả tiền chuộc.

Nên làm gì:

* Áp dụng quy tắc sao lưu “3-2-1”: có ít nhất ba bản sao dữ liệu, trên hai loại phương tiện khác nhau, và một bản sao ngoài site/không thuộc mạng hypervisor.
* Sử dụng repository sao lưu hoặc snapshots bất biến để một khi dữ liệu được ghi thì không thể bị chỉnh sửa hoặc xoá bởi ransomware.
* Không kết nối repository sao lưu của bạn với Active Directory hoặc bất kỳ hệ thống quản lý danh tính tập trung nào. Thay vào đó, sử dụng các tài khoản cục bộ riêng biệt, không thuộc domain và chuyên dụng để ngăn một chứng thực AD bị xâm phạm làm cho ransomware lây trực tiếp tới vị trí sao lưu quan trọng của bạn.
* Đảm bảo sao lưu bao gồm ảnh VM đầy đủ và trạng thái hypervisor liên quan, để bạn có thể xây dựng lại nhanh chóng.
* Thử nghiệm sao lưu của bạn thường xuyên. Đừng chỉ xác nhận rằng bạn có thể mount một bản sao lưu và truy cập file, mà hãy đảm bảo hệ điều hành khởi động đầy đủ và bạn có thể đăng nhập bằng chứng thực đã biết.
* Thực hành các bài diễn tập phục hồi toàn diện ít nhất hàng năm. Các giả định dẫn tới thời gian gián đoạn lâu hơn. Một số cân nhắc bổ sung:  
   * Bạn đã thử nghiệm ở các vị trí offsite và/hoặc failover chưa?  
   * Bạn có thể xác nhận rằng các server của bạn có cấu hình mạng/kết nối đúng không? Bạn có thể truy cập các server failover này từ các endpoint sản xuất không?  
   * Firewall của site sao lưu/vị trí failover đã có sẵn các quy tắc allowlisting và firewall cần thiết để đảm bảo giao tiếp đúng từ các công cụ quan trọng, như EDR, RMM, và client VPN?

## Giám sát, phát hiện bất thường, và giả định bị xâm phạm (defense-in-depth)

Bởi vì lớp hypervisor thường ít được công cụ bảo mật endpoint truyền thống như EDR nhìn thấy, bạn cần một chiến lược phát hiện thay thế. Kẻ tấn công thường thực hiện các hành động như thay đổi mức chấp nhận VIB, bật SSH, vô hiệu hóa lockdown mode, hoặc tạo tài khoản admin mới, như những bước chuẩn bị cho việc triển khai payload ransomware.

Nếu không giám sát, bạn có thể chỉ phát hiện sự việc sau khi quá trình mã hóa đã hoàn tất.

Nên làm gì:

* Chuyển tiếp logs ESXi tới SIEM của bạn và tạo cảnh báo cho các sự kiện đáng ngờ chính (như đăng nhập root mới, bật dịch vụ, thay đổi VIB acceptance, unmount datastore).
* Giám sát cấu hình để phát hiện drift. Nếu bất kỳ host nào bị tắt lockdown mode, SSH bật, hoặc execInstalledOnly bị tắt, đánh dấu để xem xét.
* Ghi lại lưu lượng mạng quản lý. Hãy nhớ khi chúng tôi đề xuất đặt ESXi và các control plane hạ tầng quan trọng khác trên VLAN hoặc đoạn mạng riêng? Bây giờ là lúc tìm kiếm các IP nguồn bất thường truy cập giao diện quản lý hypervisor (lý tưởng là bạn chỉ cho phép lưu lượng từ jump server), nỗ lực di chuyển ngang, hoặc các mẫu IO datastore lớn phù hợp với việc mã hóa VM.
* Sử dụng tư duy zero-trust cho quản lý hypervisor, và giả định chứng thực có thể bị xâm phạm, rồi xây dựng cảnh báo tương ứng.
* Khác với các định dạng syslog truyền thống, ESXi phân tách logs theo các hoạt động cụ thể vào các file riêng biệt. Các file log quan trọng nhất để phát hiện và điều tra xâm phạm hypervisor là: **/var/log/auth.log** (sự kiện xác thực), **/var/log/hostd.log** (hoạt động host agent), **/var/log/shell.log** (lệnh ESXi shell), và **/var/log/vobd.log** (VMware observer daemon). Để biết hướng dẫn cấu hình log, xem Broadcom's documentation và Sygnia's ESXi defense strategies.

Khi hợp tác với nhà cung cấp SOC hoặc MDR bên thứ ba, hãy xem xét thiết lập mô hình trách nhiệm chia sẻ. Đối tác an ninh bên ngoài của bạn sẽ không có ngữ cảnh kinh doanh cần thiết để phân biệt giữa bảo trì nội bộ thường lệ và một kẻ xâm nhập đang phá cửa lúc 2 AM.

Sự phân biệt này là then chốt: SOC bên thứ ba được định vị tốt để phát hiện các việc xấu phổ quát, như chính việc thực thi ransomware. Để bổ sung, chúng tôi khuyến nghị đội an ninh nội bộ của bạn tập trung vào giám sát các mối đe dọa nội bộ và các hành động mà chỉ họ mới có thể đặt vào ngữ cảnh, như đăng nhập đêm muộn kèm theo việc bật SSH.

Để mô hình này thành công, các đội IT phải tuân thủ nghiêm ngặt quy trình kiểm soát thay đổi và thông báo tất cả các thay đổi hypervisor dự kiến cho bảo mật nội bộ. Điều này đảm bảo SOC biết trước mọi hoạt động dự kiến, giúp mọi bên tập trung nỗ lực vào nơi hiệu quả nhất.

## Kết luận

Bảo vệ các bare-metal hypervisors như ESXi khỏi ransomware đòi hỏi một cách tiếp cận nhiều lớp và chủ động. Từ việc vá lỗi và kiểm soát truy cập, qua gia cố runtime và sẵn sàng phục hồi, đến phát hiện và ghi log, bạn cần bao phủ mọi góc cạnh.

Nếu bạn cần hướng dẫn toàn diện hơn để chuẩn bị cho trường hợp xấu nhất, xem hướng dẫn của chúng tôi về Disaster Recovery Planning. Bây giờ là lúc tổ chức của bạn tự hỏi: lần cuối cùng chúng ta cập nhật và kiểm thử đầy đủ IRPs và DRPs là khi nào, đặc biệt xác nhận khả năng khôi phục và chạy tất cả các guest virtual machines?

Bất chấp nỗ lực phòng ngừa và phát hiện tốt nhất, các tổ chức cũng nên chuẩn bị cho khả năng xâm phạm thành công. Nếu bạn đang phản ứng với một môi trường ESXi bị xâm phạm, chúng tôi khuyên bạn xem xét hướng dẫn ESXi IR Guide. Hướng dẫn cung cấp thủ tục ứng phó sự cố chi tiết và các artifact pháp chứng, được điều chỉnh riêng cho môi trường ESXi.

Tận dụng Huntress, bạn có thể đã áp dụng nhiều biện pháp này ở tầng OS/endpoint; nhưng hypervisor đòi hỏi độ nghiêm ngặt tương tự (và thường hơn thế) vì tiềm năng gây tác động hàng loạt của nó.

Nếu bạn nhúng các hướng dẫn phòng thủ trong bài viết này vào môi trường và quy trình bảo mật của mình, bạn sẽ tăng đáng kể rào cản đối với các tác nhân ransomware.

## Duy trì Nhận Thức Tình Huống trong 2026—Đăng ký Tradecraft Tuesday

Tradecraft Tuesday cung cấp cho các chuyên gia an ninh mạng phân tích chuyên sâu về các tác nhân đe dọa mới nhất, vector tấn công và chiến lược giảm thiểu. Mỗi buổi hàng tuần bao gồm các bước đi kỹ thuật của các sự cố gần đây, phân tích xu hướng malware toàn diện, và các chỉ số xâm phạm (IOCs) cập nhật.

Người tham gia nhận được:

* Briefing chi tiết về các chiến dịch đe dọa mới nổi và các biến thể ransomware
* Phương pháp phòng thủ dựa trên bằng chứng và kỹ thuật khắc phục
* Tương tác trực tiếp với các nhà phân tích Huntress để lấy kinh nghiệm ứng phó sự cố
* Truy cập vào threat intelligence và hướng dẫn phát hiện có thể hành động

**[Register for Tradecraft Tuesday →](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-12-camp-multi-global-prospect-iis-x-3p%5Fblog&hnt=tjmscapixr9u)**

Nâng cao thế phòng thủ của bạn với thông tin tình báo thời gian thực và giáo dục kỹ thuật được thiết kế đặc biệt cho những người chịu trách nhiệm bảo vệ môi trường tổ chức của họ.

_Tài trợ và viết bởi Huntress Labs._