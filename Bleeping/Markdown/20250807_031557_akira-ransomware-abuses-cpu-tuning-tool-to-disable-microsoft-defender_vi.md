# Ransomware Akira lợi dụng công cụ tinh chỉnh CPU để vô hiệu hóa Microsoft Defender

![Tin tặc đang nhìn vào một hộp](https://www.bleepstatic.com/content/hl-images/2024/05/07/hacker-box.jpg)

Ransomware Akira đang lợi dụng một trình điều khiển Intel CPU hợp pháp để tắt Microsoft Defender trong các cuộc tấn công từ các công cụ bảo mật và EDR chạy trên các máy mục tiêu.

Trình điều khiển bị lạm dụng là 'rwdrv.sys' (được sử dụng bởi ThrottleStop), mà các tác nhân đe dọa đăng ký như một dịch vụ để có được quyền truy cập cấp kernel.

Trình điều khiển này có thể được sử dụng để tải một trình điều khiển thứ hai, 'hlpdrv.sys', một công cụ độc hại thao tác Windows Defender để tắt các bảo vệ của nó.

Đây là một cuộc tấn công 'Mang Theo Trình Điều Khiển Có Lỗi Của Chính Bạn' (BYOVD), trong đó các tác nhân đe dọa sử dụng các trình điều khiển hợp pháp đã ký mà có những lỗ hổng hoặc điểm yếu đã biết có thể bị lạm dụng để đạt được cấp bậc quyền. Trình điều khiển này sau đó được sử dụng để tải một công cụ độc hại vô hiệu hóa Microsoft Defender.

"Trình điều khiển thứ hai, hlpdrv.sys, cũng được đăng ký như một dịch vụ. Khi được thực thi, nó sửa đổi các thiết lập DisableAntiSpyware của Windows Defender tại \\REGISTRY\\MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows Defender\\DisableAntiSpyware," [các nhà nghiên cứu giải thích](https://www.guidepointsecurity.com/blog/gritrep-akira-sonicwall/).

"Phần mềm độc hại thực hiện điều này thông qua việc thực thi regedit.exe."

Chiến thuật này đã được Guidepoint Security quan sát, với báo cáo thấy việc lạm dụng lặp đi lặp lại trình điều khiển rwdrv.sys trong các cuộc tấn công ransomware Akira kể từ ngày 15 tháng 7 năm 2025.

"Chúng tôi đang đánh dấu hành vi này vì sự phổ biến của nó trong các trường hợp phản ứng sự cố ransomware Akira gần đây. Chỉ thị có độ tin cậy cao này có thể được sử dụng để phát hiện chủ động và tìm kiếm mối đe dọa hồi tố," báo cáo tiếp tục.

Để hỗ trợ các nhà bảo vệ phát hiện và chặn các cuộc tấn công này, Guidepoint Security đã cung cấp một quy tắc YARA cho hlpdrv.sys, cũng như các chỉ dẫn hoàn chỉnh về các bằng chứng bị xâm phạm (IoCs) cho cả hai trình điều khiển, tên dịch vụ và đường dẫn file nơi chúng bị hạ.

## Các cuộc tấn công Akira vào SonicWall SSLVPN

Ransomware Akira gần đây đã liên quan đến các cuộc tấn công vào VPN của SonicWall bằng cách sử dụng một lỗ hổng chưa biết.

Guidepoint Security cho biết họ không thể xác nhận hoặc bác bỏ việc khai thác một lỗ hổng zero-day trong các VPN của SonicWall bởi các nhà điều hành ransomware Akira.

Đáp lại các báo cáo về hoạt động tấn công gia tăng, [SonicWall đã khuyên](https://www.bleepingcomputer.com/news/security/sonicwall-urges-admins-to-disable-sslvpn-amid-rising-attacks/) vô hiệu hóa hoặc hạn chế SSLVPN, thực thi xác thực đa yếu tố (MFA), bật bảo vệ Botnet/Geo-IP và xóa các tài khoản không sử dụng.

Trong khi đó, [Báo cáo DFIR](https://thedfirreport.com/2025/08/05/from-bing-search-to-ransomware-bumblebee-and-adaptixc2-deliver-akira/) đã công bố một phân tích về các cuộc tấn công ransomware Akira gần đây, làm nổi bật việc sử dụng trình tải malware Bumblebee được cung cấp qua các trình cài đặt MSI bị nhiễm độc của các công cụ phần mềm CNTT.

Một ví dụ liên quan đến việc tìm kiếm "ManageEngine OpManager" trên Bing, nơi SEO poisoning đã chuyển hướng nạn nhân đến trang web độc hại opmanager\[.\]pro.

![Trang web độc hại bắt đầu một cuộc tấn công Akira](https://www.bleepstatic.com/images/news/u/1220909/2025/July/website(1).jpg)

**Trang web độc hại bắt đầu một cuộc tấn công Akira**  
_Đã có nguồn: Báo cáo DFIR_

Bumblebee được khởi động thông qua DLL sideloading, và khi liên lạc C2 được thiết lập, nó hạ AdaptixC2 để có quyền truy cập lâu dài.

Các kẻ tấn công sau đó thực hiện việc thu thập thông tin nội bộ, tạo ra các tài khoản đặc quyền và khai thác dữ liệu bằng FileZilla, đồng thời duy trì quyền truy cập thông qua RustDesk và các đường hầm SSH.

Sau khoảng 44 giờ, payload chính của ransomware Akira (locker.exe) được triển khai để mã hóa các hệ thống trên các miền.

Cho đến khi tình hình VPN SonicWall được giải quyết, các quản trị viên hệ thống nên theo dõi các hoạt động liên quan đến Akira và áp dụng các bộ lọc và chặn khi các chỉ thị xuất hiện từ nghiên cứu bảo mật.

Cũng rất được khuyên nên chỉ tải phần mềm từ các trang chính thức và gương, vì các trang giả mạo đã trở thành một nguồn phổ biến gây ra phần mềm độc hại.