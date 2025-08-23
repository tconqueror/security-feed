# Thiết kế các playbook cho Đội Xanh với Wazuh để đáp ứng sự cố chủ động

![Wazuh header](https://www.bleepstatic.com/content/posts/2025/06/08/blue-team-header.png)

Trong lĩnh vực an ninh mạng, Các Đội Xanh chịu trách nhiệm bảo vệ môi trường CNTT của một tổ chức, bao gồm mạng, đầu cuối, ứng dụng và dữ liệu khỏi nhiều loại mối đe dọa khác nhau. Vai trò của họ không chỉ là bảo vệ tài sản CNTT; họ còn đảm bảo sự liên tục hoạt động, theo dõi hoạt động độc hại và phản ứng với các sự cố trong thời gian thực. Để hoạt động hiệu quả, các đội này dựa vào các quy trình có cấu trúc được gọi là playbook.

Playbook của Đội Xanh là hướng dẫn chi tiết phác thảo cách xác định, cách ly và khôi phục các sự cố an ninh cụ thể. Các playbook này giúp đảm bảo rằng các phản ứng sự cố nhất quán, kịp thời và phù hợp với các chính sách tổ chức và yêu cầu quy định, từ đó tối thiểu hóa tác động của các cuộc tấn công mạng. Chúng bao gồm các yêu cầu tiên quyết cụ thể, quy trình làm việc, danh sách kiểm tra và các bước điều tra cho nhiều kịch bản sự cố khác nhau.

## Các yếu tố chính của playbook Đội Xanh

Khi mỗi tổ chức có thể tùy chỉnh các playbook của mình để phù hợp với môi trường cụ thể của họ, một số quy trình nhất định là cần thiết để phản ứng hiệu quả với các trường hợp sự cố:

* **Yêu cầu tiên quyết:** Các yêu cầu cơ bản phải có trước khi bắt đầu điều tra. Điều này bao gồm việc có các công cụ bảo mật phù hợp, vai trò xác định, quy tắc phát hiện và logic cảnh báo liên quan, giữa các yếu tố khác.
* **Quy trình làm việc:** Chuỗi các bước hợp lý được thực hiện trong quá trình phản ứng sự cố. Nó thường theo một mô hình cho thấy cách một sự cố được phát hiện, leo thang, phân loại, cách ly và đã được giải quyết.
* **Danh sách kiểm tra:** Danh sách các nhiệm vụ được sử dụng để theo dõi và xác minh từng bước trong quy trình làm việc, đảm bảo rằng tất cả các hành động cần thiết được thực hiện để giảm thiểu và khôi phục một sự cố một cách hiệu quả.
* **Cards điều tra:** Hướng dẫn từng bước cụ thể được thiết kế cho các trường hợp sự cố và vector tấn công khác nhau. Mỗi playcard nên bao gồm nguồn nhật ký, chỉ số bị xâm phạm (IoC), các kỹ thuật MITRE ATT&CK liên quan, các hoạt động cách ly và phục hồi.

Tại cốt lõi của các playbook này là Phản ứng Sự cố (IR), quy trình chính thức để phát hiện, điều tra và giảm thiểu các sự cố bảo mật. Các playbook thực hiện IR bằng cách dịch các quy trình cấp cao thành các bước có thể hành động cho các mối đe dọa cụ thể, khiến chúng trở thành những công cụ cần thiết cho các hoạt động bảo mật hiệu quả.

### Các trường hợp sự cố được bao phủ bởi playbook Đội Xanh

Các playbook Đội Xanh được thiết kế để phản ứng với các cuộc tấn công mối đe dọa khác nhau. Một số trường hợp sự cố thông thường bao gồm:

* Các nỗ lực đăng nhập brute-force qua SSH, RDP hoặc cổng web.
* Nhiễm malware và thay đổi tệp không được phép.
* Mối đe dọa nội bộ và hành vi người dùng bất thường.
* Tăng đặc quyền và thực thi quy trình đáng ngờ trên các đầu cuối.
* Các nỗ lực xuất dữ liệu thông qua hoạt động mạng bất thường.
* Các cuộc tấn công ứng dụng web, bao gồm tải lên web shell và cố gắng khai thác.

Bằng cách ánh xạ từng trường hợp sử dụng với một chiến lược phản ứng được xác định trước, các Đội Xanh có thể hành động nhanh chóng, giảm thời gian phản ứng trung bình (MTTR) và giới hạn thiệt hại tiềm ẩn.

## [Tăng cường Playbooks Đội Xanh của bạn với Wazuh](https://wazuh.com/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer)

Khám phá tiềm năng đầy đủ của hoạt động Đội Xanh của bạn. Tìm hiểu cách Wazuh, một nền tảng bảo mật mã nguồn mở, nâng cao khả năng phát hiện mối đe dọa theo thời gian thực, đáp ứng tự động và quản lý sự cố toàn diện cho các kịch bản tấn công khác nhau.

Tăng cường khả năng phòng thủ mạng của bạn hôm nay!

[Tìm hiểu thêm về Wazuh](https://wazuh.com/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer)

## Hiểu vai trò của Wazuh trong các playbook Đội Xanh

Phản ứng sự cố hiệu quả đòi hỏi các công cụ cung cấp giám sát an ninh theo thời gian thực, phản ứng tự động và phát hiện mối đe dọa dựa trên tương quan. [Wazuh](https://wazuh.com/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer), một nền tảng bảo mật miễn phí và mã nguồn mở, cung cấp những khả năng này, cho phép các đội an ninh phát hiện, phân tích và phản ứng với các sự cố một cách hiệu quả.

Wazuh hợp nhất các chức năng của Quản lý Thông tin và Sự kiện Bảo mật (SIEM) với các khả năng Phát hiện và Phản ứng Mở rộng (XDR). Các khả năng của nó cho phép phân tích và tương quan dữ liệu an ninh trên nhiều đầu cuối và môi trường khác nhau, bao gồm hạ tầng tại chỗ, đám mây và hybrid. Khả năng phát hiện mối đe dọa theo thời gian thực, phân tích nhật ký và giám sát tính toàn vẹn tệp làm cho nó trở thành một tài sản quan trọng cho Các Đội Xanh. Những tính năng này làm cho nó trở nên vô giá trong tất cả bốn giai đoạn chính của vòng đời phản ứng sự cố.

![Bốn giai đoạn của vòng đời phản ứng sự cố](https://www.bleepstatic.com/images/news/security/w/wazuh/blue-team-playbook/four-phases.jpg)

Phản ứng sự cố (IR) bao gồm một cách tiếp cận có cấu trúc mà bao gồm chuẩn bị, phát hiện, phân tích, cách ly, tiêu diệt, phục hồi và các hoạt động sau sự cố để ghi lại bài học đã học. Bằng cách tích hợp Wazuh vào vòng đời phản ứng sự cố, các tổ chức có thể đạt được các điều sau:

* Phát hiện theo thời gian thực thông qua phân tích nhật ký tập trung và giám sát tính toàn vẹn tệp.
* Cảnh báo tự động dựa trên các quy tắc tùy chỉnh để kích hoạt các phản ứng.
* Giám sát hành vi của đầu cuối, máy chủ và môi trường đám mây.
* Các hành động phản ứng sự cố tích hợp để cách ly và cô lập các mối đe dọa.
* Các tính năng báo cáo tuân thủ và kiểm toán cho tài liệu sau sự cố.

### Tích hợp Wazuh vào playbook Đội Xanh của bạn

Các ví dụ playbook sau đây cho thấy cách Wazuh có thể được áp dụng cho các kịch bản mối đe dọa thực tế, thể hiện vai trò của nó trong phát hiện và phản ứng qua các vector tấn công khác nhau:

#### Playbook 1: Trích xuất thông tin danh tính trên một đầu cuối Windows

Trích xuất thông tin danh tính là một kỹ thuật phổ biến sau khai thác mà các kẻ tấn công sử dụng để thu thập thông tin tài khoản được lưu trong bộ nhớ hoặc hive registry. Những thông tin này sau đó có thể được sử dụng cho chuyển động bên và truy cập không có quyền vào thông tin hạn chế. Wazuh giúp phát hiện hành vi này trên các đầu cuối Windows bằng cách tận dụng các nhật ký sự kiện bảo mật, nhật ký Sysmon và các mô-đun giám sát quy trình.

Wazuh có thể được cấu hình để theo dõi truy cập đáng ngờ vào `lsass.exe`, các truy vấn registry đến `SAM` hoặc `SECURITY` hives, và việc thực thi bất thường các công cụ trích xuất thông tin như Mimikatz. Cảnh báo được tạo ra bằng cách sử dụng các quy tắc được xác định trước liên quan đến mối quan hệ giữa quy trình cha-con, các tham số dòng lệnh và các mẫu IoC đã biết.

Ví dụ, các quy tắc Wazuh theo mặc định có thể [phát hiện sự lạm dụng Impacket](https://wazuh.com/blog/detecting-impacket-with-wazuh/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) chống lại các đầu cuối Windows được theo dõi. Impacket là một bộ sưu tập các tập lệnh dựa trên Python được thiết kế để thao túng các giao thức mạng và khai thác các dịch vụ Windows.

Khi các công cụ tấn công Impacket như `secretsdump.py` được thực thi trên một đại lý Wazuh, Wazuh ngay lập tức phát hiện hoạt động này. Sau đó, nó kích hoạt các cảnh báo hiển thị trên bảng điều khiển Wazuh để các nhà phân tích an ninh xem xét và phản ứng.

![Hình 1: Cảnh báo trên bảng điều khiển Wazuh từ việc thực thi secretsdump.py.](https://www.bleepstatic.com/images/news/security/w/wazuh/blue-team-playbook/wazuh-alerts.png)

**Hình 1: Cảnh báo trên bảng điều khiển Wazuh từ việc thực thi secretsdump.py**

#### Playbook 2: Web shell trên một máy chủ web bị xâm phạm

Web shell là các tập lệnh độc hại cho phép các yếu tố đe dọa duy trì quyền truy cập liên tục vào các máy chủ web bị xâm phạm và khởi chạy các cuộc tấn công bổ sung. Các tác nhân đe dọa ưa thích kỹ thuật này để tạo ra các cửa hậu trong môi trường của nạn nhân của họ.

Wazuh phát hiện web shells bằng cách sử dụng sự kết hợp của giám sát tính toàn vẹn tệp (FIM) và khả năng phát hiện mối đe dọa. Các Đội Xanh có thể cấu hình Wazuh để theo dõi các thư mục có nguy cơ cao và đánh dấu các việc tạo hoặc sửa đổi tệp không được phép có thể chỉ ra sự hiện diện của một web shell. Wazuh FIM tạo ra các cảnh báo bất cứ khi nào có thay đổi xảy ra trong các đường dẫn được chỉ định, cho phép phát hiện sớm sự can thiệp trong các đầu cuối được giám sát.

Ngoài việc theo dõi sự thay đổi tệp, Wazuh còn bao gồm các quy tắc tích hợp sẵn giúp phát hiện hoạt động đáng ngờ trên các máy chủ web. Các quy tắc này đánh dấu hành vi như thực thi các tập lệnh không chuẩn hoặc sử dụng các phương thức HTTP không mong đợi. Các Đội Xanh cũng có thể tạo các quy tắc tùy chỉnh để phát hiện hành vi malware cụ thể.

Dưới đây là một quy tắc bổ sung viết để kích hoạt cảnh báo khi quản lý Wazuh phát hiện các tệp được sửa đổi trong các thư mục được giám sát với chữ ký web shell PHP:

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

Quy tắc sau kiểm tra các tệp đã sửa đổi cho các chức năng PHP đáng ngờ thường được sử dụng trong web shells. Trường `changed_content` đại diện cho nội dung của tệp đã sửa đổi, mà Wazuh quét để tìm các mẫu như `eval`, `exec` và `base64_decode`. Khi phù hợp, nó kích hoạt một cảnh báo độ nghiêm trọng cao và ánh xạ hành vi đến các kỹ thuật MITRE ATT&CK liên quan.

#### Playbook 3: Xuất dữ liệu đáng ngờ

Xuất dữ liệu có thể khó phát hiện, đặc biệt khi các kẻ tấn công tận dụng các công cụ hợp pháp để di chuyển dữ liệu và tránh bị phát hiện. Kỹ thuật này, được gọi là Living Off the Land (LOTL), liên quan đến việc lạm dụng các tiện ích hệ điều hành bản địa, khiến các hoạt động độc hại hòa lẫn với các hoạt động bình thường. Wazuh hỗ trợ giám sát hoạt động mạng, theo dõi thực thi lệnh và kiểm toán truy cập tệp để phát hiện các hoạt động xuất dữ liệu bất thường.

Bằng cách theo dõi lịch sử lệnh, chuyển dữ liệu lớn, hoặc các công cụ như `scp`, `curl` hoặc `netcat`, Wazuh cảnh báo các nhóm đến các việc chuyển dữ liệu có khối lượng cao hoặc điểm đến không bình thường. Wazuh cũng sử dụng tính năng GeoIP để đánh dấu các kết nối từ và đến các vị trí đáng ngờ, giúp bạn phát hiện và tăng cường các nỗ lực xuất dữ liệu trong thời gian thực.

Bài viết trên blog về [phát hiện xuất dữ liệu được thực hiện bằng các công cụ LOTL](https://wazuh.com/blog/detecting-data-exfiltration-using-living-off-the-land-tools-with-wazuh/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) mô phỏng các kịch bản xuất dữ liệu khác nhau và cách chúng có thể được phát hiện bằng cách sử dụng Wazuh.

Nó chứng minh cách Wazuh có thể giám sát các lệnh được thực thi qua PowerShell, Command Prompt, và các tiện ích Windows tích hợp để xác định các chuyển dữ liệu đáng ngờ. Bằng cách thu thập và phân tích nhật ký sự kiện, các đại lý Wazuh có thể phát hiện các chỉ số như việc sử dụng `certutil`, `bitsadmin` và `curl` cho việc di chuyển dữ liệu trái phép.

Các quy tắc và bộ giải mã tùy chỉnh có thể tạo ra cảnh báo khi các công cụ này bị lạm dụng, giúp Các Đội Xanh phản ứng nhanh chóng với các nỗ lực xuất dữ liệu.

**Hình 2: Wazuh sử dụng các quy tắc tùy chỉnh để kích hoạt cảnh báo khi dịch vụ BITS bị lạm dụng**

#### Playbook 4: Cuộc tấn công brute-force đăng nhập

Brute-forcing là một vector tấn công phổ biến mà các kẻ tấn công sử dụng để có được quyền truy cập trái phép vào các đầu cuối và dịch vụ. Các dịch vụ như SSH trên các đầu cuối Linux và RDP trên Windows thường dễ bị tấn công brute-force. Wazuh phát hiện các cuộc tấn công brute-force bằng cách tương quan nhiều sự kiện thất bại xác thực trên các đầu cuối được giám sát. Trên các đầu cuối Linux, nó xác định những tấn công này theo mặc định bằng cách phân tích các nhật ký xác thực như `/var/log/auth.log` bằng cách sử dụng khả năng phát hiện dữ liệu nhật ký.

Các bộ giải mã Wazuh phân tích dữ liệu nhật ký thô từ các dịch vụ xác thực để lấy thông tin có cấu trúc về các nỗ lực đăng nhập thất bại. Điều này bao gồm các chi tiết như địa chỉ IP nguồn, tên người dùng và dấu thời gian. Sau khi được giải mã, các quy tắc tương quan Wazuh phân tích dữ liệu này để phát hiện các mẫu thất bại nhanh chóng hoặc lặp đi lặp lại từ cùng một địa chỉ IP, dẫn đến cảnh báo về các cuộc tấn công brute-force tiềm năng.

Khi ngưỡng cảnh báo được xác định được đáp ứng, Wazuh sử dụng khả năng [Phản hồi Chủ động](https://documentation.wazuh.com/current/user-manual/capabilities/active-response/ar-use-cases/blocking-ssh-brute-force.html?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) của nó để chạy các tập lệnh nhằm thực hiện hành động trên các kích hoạt nhất định. Ví dụ, Wazuh có thể kích hoạt phản hồi chủ động để chặn địa chỉ IP gây rối bằng cách sử dụng các quy tắc tường lửa như `iptables`.

Bài viết trên blog về việc giám sát [Rapid SCADA với Wazuh](https://wazuh.com/blog/monitoring-rapid-scada-with-wazuh/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) minh họa cách các nỗ lực đăng nhập brute-force đối với hệ thống điều khiển công nghiệp có thể được phát hiện bằng cách sử dụng khả năng phân tích dữ liệu nhật ký. Wazuh giám sát các nhật ký xác thực từ các hệ thống Rapid SCADA, phân tích các sự kiện cho thấy nhiều thất bại trong các nỗ lực đăng nhập. Các quy tắc tùy chỉnh xác định các mẫu bất thường, chẳng hạn như nhiều thất bại trong một khoảng thời gian ngắn.

Các quy tắc này tạo ra cảnh báo nổi bật hoạt động tiềm năng brute-force, cho phép các đội an ninh phản ứng nhanh chóng. Bằng cách phân tích dữ liệu nhật ký từ các hệ thống SCADA, Wazuh cho phép phát hiện sớm các nỗ lực truy cập trái phép và các điều bất thường khác trong các môi trường điều khiển công nghiệp.

**Hình 3: Wazuh phát hiện các nỗ lực brute-force sau nhiều nỗ lực xác thực thất bại**

### Tích hợp Wazuh với các công cụ an ninh khác

Để xây dựng các playbook Đội Xanh hiệu quả, các tổ chức cần các công cụ không chỉ phát hiện mối đe dọa mà còn làm việc liền mạch trong một hệ sinh thái an ninh rộng hơn. Wazuh hỗ trợ điều này bằng cách tích hợp với một loạt các công cụ bên ngoài trong toàn bộ vòng đời phản ứng sự cố:

* **Nền tảng SOAR** như TheHive và Shuffle giúp tự động hóa quản lý trường hợp và đơn giản hóa việc thực hiện các playbook phản ứng sự cố.
* **Dữ liệu tình báo mối đe dọa**, bao gồm VirusTotal, AlienVault OTX và AbuseIPDB, làm phong phú thêm dữ liệu cảnh báo với ngữ cảnh bên ngoài, giúp phân loại nhanh hơn và thông tin hơn.
* **Hệ thống ticketing** như Jira tích hợp với Wazuh để tạo điều kiện cho việc theo dõi sự cố hiệu quả, phân công công việc và giao tiếp trong nhóm.
* **Nền tảng đám mây** như AWS, Azure và GCP có thể được Wazuh giám sát để phát hiện các vấn đề cấu hình, hoạt động bất thường và các vi phạm bảo mật tiềm tàng trong các khối lượng công việc đám mây.

## Kết luận

Mỗi playbook này làm nổi bật tính linh hoạt của Wazuh để hỗ trợ các hoạt động Đội Xanh. Cho dù phản ứng với một cuộc tấn công thu thập thông tin xác thực hay phát hiện một vị trí bám chặt thông qua một web shell, Wazuh cung cấp cho các nhà phòng thủ các công cụ để hành động nhanh chóng, được hỗ trợ bởi cơ sở dữ liệu các quy tắc phát hiện mối đe dọa do cộng đồng phát triển và các tích hợp mã nguồn mở.

Tìm hiểu thêm về Wazuh bằng cách kiểm tra [tài liệu](https://documentation.wazuh.com/current/index.html?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) của họ và tham gia [cộng đồng](https://wazuh.com/community/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) của các chuyên gia để được hỗ trợ. 

_Được tài trợ và viết bởi [Wazuh](https://wazuh.com/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer)._