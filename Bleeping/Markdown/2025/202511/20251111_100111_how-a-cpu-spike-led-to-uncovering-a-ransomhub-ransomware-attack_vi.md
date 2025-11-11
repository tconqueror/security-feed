# Cách một đột biến CPU dẫn tới phát hiện một cuộc tấn công mã độc RansomHub

![Pháp y kỹ thuật số](https://www.bleepstatic.com/content/posts/2025/11/10/varonis-header-detection.jpg)

Varonis gần đây đã giúp một khách hàng phát hiện thấy một đột biến hoạt động CPU trên một máy chủ trong môi trường của họ, nơi một rà soát sơ bộ thiết bị tiết lộ một cuộc xâm phạm đang diễn ra bởi một tác nhân mối đe dọa phức tạp mà sau này chúng tôi ghi nhận là các cộng tác viên của [RansomHub](https://www.varonis.com/blog/ransomhub?hsLang=en). 

Trong vòng 48 giờ tiếp theo, đội của chúng tôi đã làm việc chặt chẽ với khách hàng để điều tra, săn tìm, chứa chấp và khắc phục mối đe dọa trước khi nó có thể phát triển thành mã độc tống tiền.

Nhờ khả năng can thiệp tiên tiến của đội, chúng tôi đã bảo vệ mạng của khách hàng mà không gây gián đoạn kinh doanh nào. Tiếp tục đọc để xem sự việc bắt đầu như thế nào.

## **Truy cập ban đầu**

Sự cố bắt đầu khi một người dùng tải xuống và sau đó thực thi một tệp mà họ được dẫn dắt tin rằng là một bản cập nhật trình duyệt hợp lệ. Trong trường hợp này, đó là một payload JavaScript độc hại.

![Initial execution of the malicious payload from a user click](https://www.bleepstatic.com/images/news/security/v/varonis/cpu-utilization-to-ransomware/initial-execution.png)

**Thực thi ban đầu của payload độc hại từ một cú nhấp của người dùng**

Việc tải xuống khởi động một chuỗi các hoạt động trinh sát tự động và điều khiển từ xa ban đầu, bao gồm liệt kê người dùng và máy tính trong Active Directory, truy vấn các thông tin hệ thống cục bộ quan trọng, săn tìm thông tin xác thực trong bộ nhớ, và nhiều kỹ thuật phát hiện khác.

Trong vài phút, phần mềm độc hại giai đoạn hai được triển khai dưới dạng một Scheduled Task lặp lại để duy trì truy cập. Sau đó, một bản phân phối Python hợp lệ được tải xuống vào %LOCALAPPDATA%ConnectedDevicesPlatform, cùng với một tập lệnh Python được mã hóa hoạt động như một SOCKS proxy với cơ sở hạ tầng kẻ tấn công, phơi bày mạng công ty trực tiếp trên Internet.

![Downloading a legitimate Python distribution to %LOCALAPPDATA%\ConnectedDevicesPlatform](https://www.bleepstatic.com/images/news/security/v/varonis/cpu-utilization-to-ransomware/downloading-pythong.png)

**Downloading a legitimate Python distribution to %LOCALAPPDATA%\\ConnectedDevicesPlatform**

**Installing additional Python packages from the Python distribution located at %LOCALAPPDATA%\\ConnectedDevicesPlatform**

**Installation of a Scheduled Task as a Persistence mechanism on a compromised endpoint**

Tập lệnh được mã hóa được bảo vệ bởi một routine giải nén gồm 10 lớp mã hóa đa giai đoạn, mỗi giai đoạn giải nén giai đoạn tiếp theo cùng với các thành phần khác.

Mỗi cấp của quá trình giải mã có tên biến được ngẫu nhiên hóa nhằm chống lại các cố gắng giải nén. Ngoài ra, mỗi giai đoạn cố gắng triển khai các kỹ thuật chống phân tích cơ bản, bao gồm phát hiện VM, phát hiện Debug và phát hiện Process Tracing.

**Đoạn mã của phần mềm độc hại Python được đóng gói nhằm chạy ẩn và tự giải nén nhiều lần**

[Our team wrote an unpacking routine for this specific variant](https://github.com/joeavanzato/socgholish%5Fc2%5Funpacker) to assist us in retrieving the final payload in plaintext. If you are a Varonis customer and need help with this task, please [contact our IR team](https://www.varonis.com/company/contact?hsLang=en).

Payload cuối cùng là một SOCKS proxy được thiết kế để tạo điều kiện giao tiếp giữa các điểm cuối của kẻ tấn công và hạ tầng mạng nội bộ bằng cách sử dụng máy chủ bị xâm phạm như một điểm chuyển tiếp.

Ngoài ra, đội pháp chứng của chúng tôi ghi nhận rằng tác nhân này đã thao túng tất cả chữ ký email được lưu tại $env:APPDATA\\Microsoft\\Signatures bằng cách nhúng một tham chiếu hình ảnh độc hại vào cuối.

**Thao túng chữ ký Email**

Loại thay đổi này sẽ không bị người dùng cuối chú ý. Tuy nhiên, nó có thể được sử dụng trên các client dễ bị tổn thương để buộc [một lần xác thực NTLM và dẫn đến thu thập thêm thông tin xác thực.](https://www.morphisec.com/blog/5-ntlm-vulnerabilities-unpatched-privilege-escalation-threats-in-microsoft/#:~:text=Imagine%20receiving%20an%20email%20from%20an%20untrusted)

## [Tải báo cáo Varonis 2025 State of Data Security](https://info.varonis.com/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Đội của chúng tôi đã phân tích dữ liệu từ 1.000 môi trường CNTT thực tế và phát hiện rằng không tổ chức nào là miễn dịch hoàn toàn trước xâm phạm.

Thực tế, 99% tổ chức có dữ liệu nhạy cảm bị phơi bày mà có thể dễ dàng bị lộ ra bởi AI.

[Read the report](https://info.varonis.com/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## **Khám phá**

Sau khi xâm nhập ban đầu vào endpoint, kẻ tấn công ngay lập tức bắt đầu săn tìm thông tin xác thực và cơ hội nâng quyền trong mạng của khách hàng. Điều này bao gồm quét chia sẻ mạng để tìm tài liệu chứa thông tin xác thực như RDP/. Như được hiển thị dưới đây, các tệp OVPN, KeePass Vaults, và các phần mở rộng hoặc tên tệp khác thường chứa dữ liệu xác thực.

**PowerShell được khởi chạy bởi TA để săn tìm các tệp thường chứa thông tin xác thực**

Lệnh trên được khởi chạy trên tất cả các chia sẻ mạng được gắn vào thiết bị như một phần của giai đoạn trinh sát tự động bởi phần mềm độc hại. Ngoài ra, mối đe dọa cố gắng xác định thông tin xác thực được lưu trong trình duyệt bằng cách phân tích các cơ sở dữ liệu local state cho Chrome và Edge. Đoạn mã dưới đây thể hiện các cố gắng của họ sử dụng Data Protection API (DPAPI) để giải mã mật khẩu lưu trong trình duyệt từ các tệp, bao gồm:

* $env:LOCALAPPDATA\\(Google|Microsoft)\\(Chrome|Edge)\\User Data\\Default\\Login Data
* $env:LOCALAPPDATA\\(Google|Microsoft)\\(Chrome|Edge)\\\\User Data\\Local State

**Threat Actor abusing DPAPI to extract stored browser credentials**

## **Nâng quyền**

Tại thời điểm này, mối đe dọa đã có truy cập mạng trực tiếp vào môi trường thông qua một đường hầm mạng và điều khiển trực tiếp thiết bị bị xâm phạm ban đầu. Phân tích của chúng tôi xác định rằng kẻ tấn công bắt đầu kiểm soát một tài khoản Domain Admin khoảng bốn giờ sau khi xâm nhập ban đầu.

Bên cạnh việc săn khắp mạng để xác định các thiết bị bị xâm phạm, chúng tôi điều tra chính xác cách thức nâng quyền này xảy ra để phong tỏa mọi cấu hình sai hoặc các khu vực yếu kém trong tư thế bảo mật.

Khoảng hai giờ sau khi xâm phạm ban đầu, tài khoản ADFS của khách hàng này được quan sát xác thực từ workstation bị xâm nhập vào một read-only Domain Controller, nơi nó sau đó có đặc quyền quản trị, được chỉ ra bởi tham số Elevated Token bên trong sự kiện xác thực 4624 liên quan.

**Một mẫu sự kiện xác thực được thiết lập sử dụng đặc quyền Administrative**

Phiên đăng nhập này cũng sở hữu quyền SeTcbPrivilege, một phân công quyền nguy hiểm cho phép người được cấp mạo danh bất kỳ người dùng nào khác trong môi trường, bao gồm Domain Admins hoặc SYSTEM.

**Hoạt động đăng nhập đáng ngờ với phân công quyền cao bắt nguồn từ một thiết bị bị xâm phạm**

Không lâu sau đó, chúng tôi quan sát thấy mối đe dọa bắt đầu lạm dụng nhiều tài khoản Domain Admin. Do lượng telemetry hạn chế, chúng tôi không thể xác định chính xác phương pháp leo thang. 

Chúng tôi đã tiến hành kiểm toán môi trường Active Directory của khách hàng và xác định một vài vấn đề chính có thể đã cung cấp bề mặt tấn công cho việc leo thang.

Một trong những phát hiện quan trọng là các chứng chỉ được cấu hình sai trong Certificate Services (AD CS) có thể cho phép leo thang đặc quyền thông qua [ESC1](https://www.semperis.com/blog/esc1-attack-explained/). AD CS bị cấu hình sai cực kỳ nguy hiểm vì nó thường cho phép người dùng thông thường nâng quyền lên Domain Administrator với rất ít kháng cự.

Chúng tôi tin rằng tác nhân đã nhận ra điều này và lợi dụng lỗi cấu hình để lấy quyền truy cập vào nhiều tài khoản có đặc quyền cao, bao gồm cả người dùng Domain Admin. Việc leo thang nhanh từ người dùng bình thường lên quản trị viên này xảy ra chưa đầy bốn giờ sau cú nhấp vào tệp độc hại ban đầu, cho thấy cần phải hành động càng sớm càng tốt khi phát hiện mối đe dọa.

## **Khám phá bổ sung**

Khi kẻ tấn công có đặc quyền, họ bắt đầu đi khám phá khắp mạng. Một trong những việc đầu tiên họ làm là nhắm vào laptop thuộc về domain admins. Để làm điều này, họ đảm bảo RDP được bật và cho phép trên các máy liên quan thông qua tương tác dịch vụ từ xa và registry. Sau đó, họ truy cập tương tác vào thiết bị sau khi đảm bảo không còn ai khác đang đăng nhập, như được minh họa dưới đây.

**Cấu hình và khởi động truy cập từ xa qua sc.exe**

Tác nhân còn lạm dụng reg.exe và netsh.exe để cấu hình các thiết lập registry phù hợp để cho phép kết nối từ xa và đảm bảo cổng 3389 được mở trên các thiết bị mục tiêu. Sau đó, quser được dùng để kiểm tra người dùng đang đăng nhập.

Khi xác định được một thiết bị không có người dùng, TA triển khai thêm các script thu thập thông tin và thông tin đăng nhập trong một tệp batch trên endpoints. Các script này ngay lập tức bị xóa sau khi thực thi, như hiển thị dưới đây.

**Kiểm tra người dùng đang đăng nhập, triển khai một scheduled task từ xa, sau đó kết nối tới các thiết bị mục tiêu**

**Ví dụ cho thấy TA tạo, thực thi, rồi xóa Scheduled Tasks được thiết kế để thu thập dữ liệu từ các thiết bị mục tiêu**

Bên cạnh các kỹ thuật khám phá tiêu chuẩn như lạm dụng ping, nltest, net, qwinsta, v.v., mối đe dọa còn làm điều gì đó khiến chúng tôi ngạc nhiên — họ sử dụng các bản cài đặt Word, Visio, và Excel để mở các tệp cụ thể quan tâm về kiến trúc nội bộ, mạng và môi trường máy chủ của khách hàng.

Chúng tôi thấy điều này độc đáo vì loại dữ liệu này thường bị lấy offline để phân tích. Tuy nhiên, tác nhân này đã mở các tệp từ các server bị xâm phạm với các tiện ích Microsoft Office được cài đặt, cho chúng tôi khả năng hiển thị cao về động cơ và quy trình của họ.

Ví dụ các tệp được mở bao gồm:

* ESXi Host Cheat Sheets
* Azure VM Networking Solutions
* Server Readmes
* Thông tin chung về kiến trúc/ cơ sở dữ liệu của khách hàng

Hoạt động này có chủ đích và có mục tiêu rõ ràng và chỉ là một ví dụ cho thấy mức độ mà các tác nhân đe dọa sẵn sàng đi tới. Giám sát truy cập dữ liệu là điều tối quan trọng cho tư thế an ninh và mức độ chấp nhận rủi ro của bất kỳ công ty nào.

## **Rò rỉ dữ liệu**

Khoảng 24 giờ sau khi xâm phạm ban đầu, kẻ tấn công đã thành công đạt được Domain Admin, triển khai nhiều cơ chế duy trì truy cập khắp môi trường, liệt kê gần như toàn bộ Active Directory, và thực hiện khám phá mạng và tệp mở rộng.

Hài lòng với tiến độ, mối đe dọa đã triển khai AzCopy, một công cụ tương tác với Microsoft Azure Storage Account. Như minh họa dưới đây, mối đe dọa đã dùng công cụ này để thực hiện rò rỉ dữ liệu hàng loạt trên một vài thư mục mục tiêu.

**TA Abuse of AzCopy for data exfiltration – excluding specific files by extension and date to find recent data of interest**

**Tăng các sự kiện File Access tương quan với hoạt động rò rỉ**
**Trung bình, người dùng này đọc 1k tệp mỗi ngày, và vào ngày rò rỉ, gần 270k, tạo ra các cảnh báo tương ứng trong Varonis**

Hoạt động rò rỉ dữ liệu là nguyên nhân gây ra đột biến CPU ban đầu và thu hút sự chú ý của khách hàng. Ngay sau đó, đội của chúng tôi xác định được cơ chế duy trì truy cập của mối đe dọa và các IOC liên quan và tổ chức một cuộc ngắt kết nối chung với khách hàng để đảm bảo mọi truy cập độc hại bị cắt đồng thời trên toàn mạng. Điều này cho phép khách hàng có thời gian để khắc phục và đảm bảo mối đe dọa không tiến triển thành mã độc tống tiền.

Phân tích các tactics, techniques, and procedures (TTPs) và các Indicators of Compromise (IOCs) liên quan đã liên kết cuộc xâm nhập này với các cộng tác viên của nhóm [RansomHub](https://www.varonis.com/blog/ransomhub?hsLang=en) sử dụng phần mềm độc hại [SocGhoulish](https://www.trendmicro.com/en%5Fus/research/25/c/socgholishs-intrusion-techniques-facilitate-distribution-of-rans.html) cho các hoạt động truy cập ban đầu.

May mắn thay, dịch vụ can thiệp của chúng tôi đã giúp khách hàng này diệt trừ hoàn toàn mối đe dọa mà không làm gián đoạn hoạt động kinh doanh. Nếu sự việc này bị bỏ qua thậm chí vài giờ nữa, mã độc tống tiền rất có thể đã được triển khai khắp môi trường của khách hàng.

_Sponsored and written by [Varonis](https://info.varonis.com/en/interceptor-demo?hsLang=en&utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._