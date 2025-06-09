# Thiết kế playbook cho Blue Team với Wazuh nhằm phòng thủ chủ động trong an ninh mạng

![Wazuh header](https://www.bleepstatic.com/content/posts/2025/06/08/blue-team-header.png)

Trong an ninh mạng, Blue Teams chịu trách nhiệm bảo vệ môi trường CNTT của tổ chức, bao gồm mạng, điểm cuối, ứng dụng và dữ liệu chống lại nhiều loại mối đe dọa khác nhau. Vai trò của họ không chỉ giới hạn trong việc bảo vệ tài sản CNTT; họ còn bảo đảm tính liên tục của hoạt động, giám sát hoạt động độc hại và phản ứng với các sự cố trong thời gian thực. Để hoạt động hiệu quả, các đội này phụ thuộc vào các quy trình có cấu trúc được gọi là playbooks.

Playbook của Blue Team là một hướng dẫn chi tiết phác thảo cách xác định, ngăn chặn và xử lý các sự cố bảo mật cụ thể. Các playbook này giúp đảm bảo rằng việc phản ứng với sự cố nhất quán, kịp thời và phù hợp với các chính sách tổ chức cũng như yêu cầu quy định, cuối cùng là giảm thiểu tác động của các cuộc tấn công mạng. Chúng bao gồm các yêu cầu tiên quyết, quy trình làm việc, danh sách kiểm tra và các bước điều tra cho các tình huống sự cố khác nhau.

## Các yếu tố chính của playbook Blue Team

Mặc dù mỗi tổ chức có thể tùy chỉnh playbook của mình để phù hợp với môi trường cụ thể, nhưng một số quy trình là cần thiết để phản ứng hiệu quả với các tình huống sự cố:

* **Yêu cầu tiên quyết:** Các yêu cầu nền tảng cần có trước khi bắt đầu một cuộc điều tra. Điều này bao gồm việc có công cụ bảo mật phù hợp, vai trò được xác định, các quy tắc phát hiện liên quan và logic cảnh báo, giữa những yếu tố khác.
* **Quy trình làm việc:** Trình tự logic của các bước thực hiện trong quá trình đáp ứng sự cố. Nó thường tuân theo một mô hình cho thấy cách phát hiện, nâng cấp, phân loại, ngăn chặn và giải quyết một sự cố.
* **Danh sách kiểm tra:** Một danh sách các nhiệm vụ được sử dụng để theo dõi và xác nhận từng bước trong quy trình làm việc, đảm bảo rằng tất cả các hành động cần thiết đều được thực hiện để giảm thiểu và xử lý một sự cố một cách hiệu quả.
* **Thẻ điều tra:** Các hướng dẫn chi tiết từng bước được điều chỉnh cho các tình huống sự cố cụ thể và các vectơ tấn công khác nhau. Mỗi thẻ nên bao gồm các nguồn log, chỉ số xâm phạm (IoC), các kỹ thuật MITRE ATT&CK liên quan, hoạt động ngăn chặn và phục hồi.

Tại lõi của các playbook này là Quy trình phản ứng sự cố (IR), quy trình chính thức về việc phát hiện, điều tra và giảm thiểu các sự cố bảo mật. Playbooks triển khai IR bằng cách chuyển đổi các quy trình cấp cao thành các bước có thể hành động cho các mối đe dọa cụ thể, làm cho chúng trở thành công cụ thiết yếu cho các hoạt động bảo mật hiệu quả.

### Các tình huống sự cố được đề cập bởi playbook Blue Team

Playbook của Blue Team được thiết kế để phản ứng với các cuộc tấn công bằng nhiều loại mối đe dọa khác nhau. Một số tình huống sự cố phổ biến bao gồm:

* Nỗ lực đăng nhập brute-force qua SSH, RDP hoặc cổng web.
* Các cuộc tấn công phần mềm độc hại và thay đổi tệp trái phép.
* Các mối đe dọa từ bên trong và hành vi người dùng bất thường.
* Tăng đặc quyền và các thực thi quy trình đáng ngờ trên các điểm cuối.
* Các nỗ lực xuất dữ liệu qua hoạt động mạng bất thường.
* Các cuộc tấn công ứng dụng web, bao gồm việc tải lên web shell và các nỗ lực khai thác.

Bằng cách ánh xạ mỗi tình huống sử dụng đến một chiến lược phản ứng được định sẵn, Blue Teams có thể hành động nhanh chóng, giảm thời gian trung bình để phản ứng (MTTR) và giới hạn thiệt hại tiềm ẩn.

## [Củng cố playbook của Blue Team với Wazuh](https://wazuh.com/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer)

Khám phá tiềm năng hoàn toàn của các hoạt động của Blue Team của bạn. Khám phá cách Wazuh, một nền tảng an ninh mã nguồn mở, cung cấp khả năng phát hiện mối đe dọa trong thời gian thực, phản ứng tự động và quản lý sự cố toàn diện cho nhiều kịch bản tấn công khác nhau.

Nâng cao khả năng phòng thủ mạng của bạn ngay hôm nay!

[Tìm hiểu thêm về Wazuh](https://wazuh.com/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer)

## Hiểu vai trò của Wazuh trong playbooks Blue Team

Phản ứng sự cố hiệu quả yêu cầu các công cụ cung cấp giám sát an ninh thời gian thực, phản ứng tự động và phát hiện mối đe dọa dựa trên tương quan. [Wazuh](https://wazuh.com/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer), một nền tảng an ninh miễn phí và mã nguồn mở, cung cấp những khả năng này, cho phép các đội an ninh phát hiện, phân tích và phản ứng với các sự cố một cách hiệu quả.

Wazuh thống nhất các chức năng của Quản lý thông tin và sự kiện bảo mật (SIEM) với các khả năng Phát hiện và Phản ứng Mở rộng (XDR). Các khả năng của nó cho phép phân tích và tương quan dữ liệu an ninh trên các điểm cuối và môi trường đa dạng, bao gồm cơ sở hạ tầng tại chỗ, đám mây và lai. Khả năng phát hiện mối đe dọa trong thời gian thực, phân tích log và giám sát tính toàn vẹn tệp của nó khiến nó trở thành một tài sản quan trọng đối với các đội Blue. Những tính năng này khiến nó không thể thiếu trong tất cả bốn giai đoạn chính của chu trình phản ứng sự cố.

![Bốn giai đoạn chu kỳ phản ứng sự cố](https://www.bleepstatic.com/images/news/security/w/wazuh/blue-team-playbook/four-phases.jpg)

Phản ứng sự cố (IR) bao gồm một cách tiếp cận có cấu trúc bao gồm chuẩn bị, phát hiện, phân tích, ngăn chặn, tiêu diệt, phục hồi và các hoạt động sau sự cố để rút ra bài học. Bằng cách tích hợp Wazuh vào chu trình phản ứng sự cố, các tổ chức có thể đạt được các điều sau:

* Phát hiện trong thời gian thực thông qua phân tích log tập trung và giám sát tính toàn vẹn tệp.
* Cảnh báo tự động dựa trên các quy tắc tùy chỉnh để kích hoạt phản ứng.
* Giám sát hành vi của các điểm cuối, máy chủ và môi trường đám mây.
* Các hành động phản ứng sự cố tích hợp để ngăn chặn và cách ly các mối đe dọa.
* Các tính năng báo cáo tuân thủ và kiểm toán cho tài liệu sau sự cố.

### Tích hợp Wazuh vào playbook của bạn

Các ví dụ về playbook dưới đây minh họa cách Wazuh có thể được áp dụng vào các tình huống mối đe dọa trong thế giới thực, thể hiện vai trò của nó trong việc phát hiện và phản ứng với các vectơ tấn công đa dạng:

#### Playbook 1: Trích xuất thông tin đăng nhập trên điểm cuối Windows

Trích xuất thông tin đăng nhập là một kỹ thuật phổ biến sau khi khai thác mà kẻ tấn công sử dụng để thu thập thông tin tài khoản được lưu trữ trong bộ nhớ hoặc registry hives. Những thông tin này có thể được sử dụng tiếp theo cho việc di chuyển ngang và truy cập trái phép vào thông tin bị hạn chế. Wazuh giúp phát hiện hành vi này trên các điểm cuối Windows bằng cách sử dụng các log sự kiện bảo mật, log Sysmon và các mô-đun giám sát quá trình.

Wazuh có thể được cấu hình để giám sát các quyền truy cập đáng ngờ đến `lsass.exe`, các truy vấn registry đến các hive `SAM` hoặc `SECURITY`, và việc thực thi bất thường của các công cụ trích xuất thông tin đăng nhập như Mimikatz. Các cảnh báo được tạo ra bằng cách sử dụng các quy tắc đã được định nghĩa trước liên quan đến mối quan hệ quá trình cha-con, các đối số dòng lệnh và các mẫu IoC đã biết.

Ví dụ, các quy tắc có sẵn của Wazuh có thể [phát hiện lạm dụng Impacket](https://wazuh.com/blog/detecting-impacket-with-wazuh/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) chống lại các điểm cuối Windows được giám sát. Impacket là một bộ sưu tập các tập lệnh dựa trên Python được thiết kế để thao tác với các giao thức mạng và khai thác các dịch vụ Windows.

Khi các công cụ tấn công Impacket như `secretsdump.py` được thực thi trên một agent Wazuh, Wazuh ngay lập tức phát hiện hoạt động này và kích hoạt các cảnh báo hiển thị trên bảng điều khiển Wazuh cho các nhà phân tích an ninh xem xét và phản ứng.

![Hình 1: Cảnh báo trên bảng điều khiển Wazuh từ việc thực hiện secretsdump.py.](https://www.bleepstatic.com/images/news/security/w/wazuh/blue-team-playbook/wazuh-alerts.png)

**Hình 1: Cảnh báo trên bảng điều khiển Wazuh từ việc thực hiện secretsdump.py**

#### Playbook 2: Web shell trên một máy chủ web đã bị xâm nhập

Web shell là các tập lệnh độc hại cho phép các tác nhân đe dọa duy trì quyền truy cập liên tục trên các máy chủ web đã bị xâm nhập và thực hiện các cuộc tấn công bổ sung. Các tác nhân đe dọa thích kỹ thuật này để tạo ra các cửa hậu trong môi trường của nạn nhân.

Wazuh phát hiện web shell bằng cách sử dụng sự kết hợp giữa giám sát tính toàn vẹn tệp (FIM) và các khả năng phát hiện mối đe dọa. Các đội Blue có thể cấu hình Wazuh để giám sát các thư mục có nguy cơ cao và đánh dấu các tệp được tạo hoặc sửa đổi trái phép có thể chỉ ra sự tồn tại của một web shell. Wazuh FIM tạo ra cảnh báo bất cứ khi nào có sự thay đổi trong các đường dẫn được xác định, cho phép phát hiện sớm việc can thiệp trong các điểm cuối được giám sát.

Ngoài việc giám sát các thay đổi tệp, Wazuh bao gồm các quy tắc tích hợp giúp phát hiện các hoạt động đáng ngờ trên máy chủ web. Các quy tắc này đánh dấu các hành vi như thực thi các tập lệnh không tiêu chuẩn hoặc sử dụng các phương thức HTTP không mong đợi. Các đội Blue cũng có thể tạo các quy tắc tùy chỉnh để phát hiện hành vi độc hại cụ thể.

Dưới đây là một quy tắc bổ sung được viết để kích hoạt cảnh báo khi quản lý Wazuh phát hiện các tệp được sửa đổi trong các thư mục được giám sát có chữ ký web shell PHP:

```
<group>
<rule id="100502" level="15">
    <if_sid>100501</if_sid>
    <field name="changed_content" type="pcre2">(?i)passthru|exec|eval|shell_exec|assert|str_rot13|system|phpinfo|base64_decode|chmod|mkdir|fopen|fclose|readfile|show_source|proc_open|pcntl_exec|execute|WScript.Shell|WScript.Network|FileSystemObject|Adodb.stream</field>
    <description>[File Modification]: File $(file) contains a web shell</description>
    <mitre>
      <id>T1105</id>
      <id>T1505.003</id>
    </mitre>
  </rule>
</group>
```

Quy tắc này kiểm tra các tệp đã sửa đổi để tìm các hàm PHP đáng ngờ thường được sử dụng trong web shell. Trường `changed_content` đại diện cho nội dung của tệp đã sửa đổi, mà Wazuh quét để tìm các mẫu như `eval`, `exec`, và `base64_decode`. Khi có sự khớp, nó tạo ra một cảnh báo mức độ cao và ánh xạ hành vi này đến các kỹ thuật MITRE ATT&CK liên quan.

#### Playbook 3: Xuất dữ liệu đáng ngờ

Việc xuất dữ liệu có thể rất khó phát hiện, đặc biệt là khi kẻ tấn công lợi dụng các công cụ hợp pháp để di chuyển dữ liệu và tránh sự phát hiện. Kỹ thuật này, được gọi là Living Off the Land (LOTL), liên quan đến việc lạm dụng các tiện ích hệ điều hành bản địa, làm cho các hoạt động độc hại hòa quyện với các hoạt động bình thường. Wazuh hỗ trợ giám sát hoạt động mạng, theo dõi lệnh thực thi, và kiểm toán truy cập tệp để phát hiện các hoạt động bất thường ra ngoài.

Bằng cách giám sát lịch sử shell, các chuyển giao tệp lớn, hoặc các công cụ như `scp`, `curl`, hoặc `netcat`, Wazuh cảnh báo các nhóm về các chuyển giao khối lượng lớn hoặc các đích đáng ngờ. Wazuh cũng sử dụng tính năng GeoIP để đánh dấu các kết nối từ và đến các vị trí nghi ngờ, giúp bạn phát hiện và tăng cường các nỗ lực xuất dữ liệu trong thời gian thực.

Bài viết trên blog về [phát hiện việc xuất dữ liệu thực hiện bằng các công cụ LOTL](https://wazuh.com/blog/detecting-data-exfiltration-using-living-off-the-land-tools-with-wazuh/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) mô phỏng nhiều tình huống xuất dữ liệu khác nhau và cách chúng có thể được phát hiện bằng Wazuh.

Nó chứng tỏ cách Wazuh có thể giám sát các lệnh được thực thi qua PowerShell, Command Prompt và các tiện ích Windows tích hợp để xác định các chuyển giao tệp đáng ngờ. Bằng cách thu thập và phân tích các log sự kiện, các agent Wazuh có thể phát hiện các chỉ số như việc sử dụng `certutil`, `bitsadmin`, và `curl` cho việc di chuyển dữ liệu không được phép.

Các quy tắc và bộ giải mã tùy chỉnh có thể tạo cảnh báo khi những công cụ này bị lạm dụng, giúp các đội Blue nhanh chóng phản ứng với các nỗ lực xuất dữ liệu.

**Hình 2: Wazuh sử dụng các quy tắc tùy chỉnh để kích hoạt cảnh báo khi dịch vụ BITS bị lạm dụng**

#### Playbook 4: Tấn công đăng nhập brute-force

Brute-forcing là một vectơ tấn công phổ biến mà các tác nhân đe dọa sử dụng để có quyền truy cập trái phép vào các điểm cuối và dịch vụ. Các dịch vụ như SSH trên các điểm cuối Linux và RDP trên Windows thường dễ bị tấn công brute-force. Wazuh phát hiện các cuộc tấn công brute-force bằng cách tương quan nhiều sự kiện thất bại xác thực trên các điểm cuối được giám sát. Trên các điểm cuối Linux, nó xác định các cuộc tấn công này theo kiểu sẵn có bằng cách phân tích các log xác thực như `/var/log/auth.log` sử dụng khả năng phát hiện dữ liệu log.

Các bộ giải mã của Wazuh phân tích dữ liệu log thô từ các dịch vụ xác thực để trích xuất thông tin có cấu trúc về các nỗ lực đăng nhập thất bại. Điều này bao gồm các chi tiết như địa chỉ IP nguồn, tên người dùng, và thời gian. Khi các dữ liệu được giải mã, các quy tắc tương quan Wazuh phân tích dữ liệu này để phát hiện các mẫu thất bại nhanh chóng hoặc lập đi lập lại từ cùng một địa chỉ IP, kích hoạt cảnh báo cho các cuộc tấn công brute-force tiềm tàng.

Khi ngưỡng cảnh báo được định nghĩa được đáp ứng, Wazuh sử dụng các khả năng [Phản ứng Chủ động](https://documentation.wazuh.com/current/user-manual/capabilities/active-response/ar-use-cases/blocking-ssh-brute-force.html?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) để thực thi các tập lệnh nhằm thực hiện hành động trên một số kích hoạt. Ví dụ, Wazuh có thể kích hoạt một phản ứng chủ động để chặn địa chỉ IP vi phạm bằng cách sử dụng các quy tắc tường lửa như `iptables`.

Bài viết trên blog về việc giám sát [Rapid SCADA với Wazuh](https://wazuh.com/blog/monitoring-rapid-scada-with-wazuh/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) minh họa cách các nỗ lực đăng nhập brute-force chống lại các hệ thống điều khiển công nghiệp có thể được phát hiện bằng cách sử dụng khả năng phân tích dữ liệu log. Wazuh giám sát các log xác thực từ các hệ thống Rapid SCADA, phân tích các sự kiện chỉ ra các nỗ lực đăng nhập thất bại lặp lại. Các quy tắc tùy chỉnh nhận diện các mẫu bất thường, chẳng hạn như nhiều thất bại trong một khung thời gian ngắn.

Những quy tắc này tạo ra các cảnh báo mà làm nổi bật hoạt động brute-force tiềm tàng, cho phép các đội an ninh phản ứng nhanh chóng. Bằng cách phân tích dữ liệu log từ các hệ thống SCADA, Wazuh cho phép phát hiện sớm các nỗ lực truy cập trái phép và các bất thường khác trong môi trường điều khiển công nghiệp.

**Hình 3: Wazuh phát hiện các nỗ lực brute-force sau nhiều nỗ lực xác thực thất bại**

### Tích hợp Wazuh với các công cụ an ninh khác

Để xây dựng các playbook của Blue Team hiệu quả, các tổ chức cần các công cụ không chỉ phát hiện các mối đe dọa mà còn hoạt động một cách liền mạch trong một hệ sinh thái bảo mật rộng lớn hơn. Wazuh hỗ trợ điều này bằng cách tích hợp với một loạt công cụ bên ngoài trên toàn bộ chu trình phản ứng sự cố:

* **Nền tảng SOAR** như TheHive và Shuffle giúp tự động hóa quản lý vụ án và tối ưu hóa việc thực thi các playbook phản ứng sự cố.
* **Các nguồn thông tin mối đe dọa**, bao gồm VirusTotal, AlienVault OTX và AbuseIPDB, làm phong phú thêm dữ liệu cảnh báo với ngữ cảnh bên ngoài, giúp việc phân tích và triage nhanh hơn và thông minh hơn.
* **Hệ thống theo dõi** như Jira tích hợp với Wazuh để tạo điều kiện cho việc theo dõi sự cố hiệu quả, phân công, và giao tiếp giữa các nhóm.
* **Các nền tảng đám mây** như AWS, Azure, và GCP có thể được giám sát bởi Wazuh để phát hiện các vấn đề cấu hình, hoạt động bất thường, và các vi phạm bảo mật tiềm ẩn trong các khối lượng công việc đám mây.

## Kết luận

Mỗi playbook này làm nổi bật khả năng thích ứng của Wazuh để hỗ trợ các hoạt động của Blue Team. Dù phản ứng với một cuộc tấn công thu thập thông tin đăng nhập hay phát hiện một dấu chân liên tục thông qua một web shell, Wazuh cung cấp cho những người bảo vệ các công cụ để hành động nhanh chóng, được hỗ trợ bởi cơ sở dữ liệu các quy tắc phát hiện mối đe dọa do cộng đồng điều hành và các tích hợp mã nguồn mở.

Tìm hiểu thêm về Wazuh bằng cách kiểm tra [tài liệu](https://documentation.wazuh.com/current/index.html?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) của họ và tham gia [cộng đồng](https://wazuh.com/community/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) của các chuyên gia để nhận hỗ trợ.

_Được tài trợ và viết bởi [Wazuh](https://wazuh.com/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer)._