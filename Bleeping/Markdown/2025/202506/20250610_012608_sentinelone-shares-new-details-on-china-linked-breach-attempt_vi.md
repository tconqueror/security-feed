# SentinelOne chia sẻ chi tiết mới về nỗ lực xâm phạm liên quan đến Trung Quốc

![Tin tặc Trung Quốc](https://www.bleepstatic.com/content/hl-images/2025/03/05/chinese-hacker-flag.jpg)

SentinelOne đã chia sẻ thêm chi tiết về một cuộc tấn công chuỗi cung ứng bị thất bại của các tin tặc Trung Quốc thông qua một công ty dịch vụ CNTT và logistics, quản lý logistics phần cứng cho công ty an ninh mạng.

SentinelOne là nhà cung cấp giải pháp bảo vệ đầu cuối (EDR/XDR) của Mỹ, bảo vệ cơ sở hạ tầng quan trọng ở nước này và nhiều doanh nghiệp lớn.

Nó là một mục tiêu có giá trị cao cho các tác nhân nhà nước, vì việc xâm nhập có thể là bàn đạp để truy cập vào các mạng doanh nghiệp hạ nguồn và có cái nhìn sâu sắc vào khả năng phát hiện để phát triển các phương pháp né tránh.

SentinelLabs [đã báo cáo lần đầu tiên](https://www.sentinelone.com/labs/top-tier-target-what-it-takes-to-defend-a-cybersecurity-company-from-todays-adversaries/) về cuộc tấn công được cố gắng vào tháng Tư, với một báo cáo mới hôm nay mô tả cuộc tấn công như một phần của một chiến dịch rộng hơn nhắm vào hơn 70 thực thể trên toàn cầu từ tháng 6 năm 2024 đến tháng 3 năm 2025.

![Mục tiêu của chiến dịch](https://www.bleepstatic.com/images/news/u/1220909/2025/June/victims.jpg)

**Mục tiêu của chiến dịch**  
_Nguồn: SentinelLabs_

Các mục tiêu bao gồm các tổ chức trong lĩnh vực chính phủ, viễn thông, truyền thông, tài chính, sản xuất, nghiên cứu và CNTT.

Chiến dịch được chia thành hai cụm. Cụm đầu tiên là 'PurpleHaze', thuộc về APT15 và UNC5174, diễn ra trong khoảng thời gian từ tháng 9 đến tháng 10 năm 2024.

SentinelOne đã trở thành mục tiêu của cả hai cụm, một lần để trinh sát và một lần để xâm phạm chuỗi cung ứng.

![Cuộc tấn công PurpleHaze và ShadowPad đối với SentinelOne](https://www.bleepstatic.com/images/news/u/1220909/2025/June/purple-hz.jpg)

**Cuộc tấn công PurpleHaze (bên trái) và ShadowPad (bên phải) đối với SentinelOne**  
_Nguồn: SentinelLabs_

SentinelOne nghi ngờ rằng các tác nhân đe dọa trong cả hai chiến dịch đã khai thác các lỗ hổng trong các thiết bị mạng bị lộ, bao gồm Ivanti Cloud Service Appliances và các gateway Check Point.

"Chúng tôi nghi ngờ rằng vector truy cập ban đầu phổ biến nhất liên quan đến việc khai thác các thiết bị gateway Check Point, nhất quán với [nghiên cứu trước đó](https://www.orangecyberdefense.com/global/blog/cert-news/meet-nailaolocker-a-ransomware-distributed-in-europe-by-shadowpad-and-plugx-backdoors) về chủ đề này," [báo cáo của SentinelLabs](https://www.sentinelone.com/labs/follow-the-smoke-china-nexus-threat-actors-hammer-at-the-doors-of-top-tier-targets/).

"Chúng tôi cũng đã quan sát thấy những giao tiếp đến các máy chủ C2 ShadowPad có nguồn gốc từ Fortinet Fortigate, Microsoft IIS, SonicWall và CrushFTP, cho thấy khả năng xâm phạm các hệ thống này."

## Các chiến dịch PurpleHaze và ShadowPad

Làn sóng tấn công PurpleHaze đã cố gắng xâm nhập vào SentinelOne vào tháng 10 năm 2024, nơi các tác nhân đe dọa đã thực hiện quét trên các máy chủ lộ diện trên internet của công ty qua cổng 443, nhằm mục đích xác định các dịch vụ có thể truy cập.

Các tác nhân đe dọa đã đăng ký các tên miền giả mạo như cơ sở hạ tầng của SentinelOne, chẳng hạn như sentinelxdr\[.\]us và secmailbox\[.\]us.

Dựa trên bằng chứng từ các mục tiêu khác, bao gồm một chính phủ Nam Á, các cuộc tấn công thành công đã sử dụng backdoor GOREshell, đã được cài đặt trên các điểm cuối lộ diện trên mạng bằng cách sử dụng các lỗ hổng zero-day.

Cụm hoạt động gần đây hơn là 'ShadowPad', được thực hiện bởi APT41 từ tháng 6 năm 2024 đến tháng 3 năm 2025.

Các tác nhân đe dọa đã cố gắng thực hiện một cuộc tấn công chuỗi cung ứng vào SentinelOne vào đầu năm 2025, nơi APT41 đã sử dụng phần mềm độc hại ShadowPad, bị che giấu qua ScatterBrain, chống lại một công ty dịch vụ CNTT và logistics làm việc với công ty an ninh mạng.

Các kẻ tấn công đã gửi phần mềm độc hại đến mục tiêu qua PowerShell, sử dụng một độ trễ 60 giây để né tránh các môi trường sandbox. Phần mềm độc hại sau đó đã lập lịch khởi động lại hệ thống sau 30 phút để xóa dấu vết trong bộ nhớ.

Tiếp theo, các tin tặc triển khai framework truy cập từ xa mã nguồn mở 'Nimbo-C2' để cung cấp một loạt các [khả năng từ xa](https://github.com/itaymigdal/Nimbo-C2?tab=readme-ov-file#features), bao gồm chụp màn hình, thực thi lệnh PowerShell, thao tác tập tin, bỏ qua UAC và hơn thế nữa.

Các kẻ tấn công cũng sử dụng một script exfiltration dựa trên PowerShell, thực hiện tìm kiếm đệ quy các tài liệu nhạy cảm của người dùng, lưu trữ chúng trong một kho lưu trữ 7-Zip được khóa bằng mật khẩu và gửi chúng ra ngoài.

**Script exfiltration dữ liệu PowerShell**  
_Nguồn: SentinelLabs_

SentinelOne nhận xét rằng các mục tiêu của các tác nhân đe dọa vẫn chưa rõ ràng, nhưng một cuộc xâm phạm chuỗi cung ứng là kịch bản có khả năng xảy ra nhất.

Công ty an ninh mạng đã kiểm tra kỹ lưỡng tài sản của mình và báo cáo rằng không có xâm phạm nào được phát hiện trên phần mềm hoặc phần cứng của SentinelOne.

"Bài viết này làm nổi bật mối đe dọa liên tục mà các tác nhân gián điệp mạng liên quan đến Trung Quốc đặt ra đối với một loạt các ngành công nghiệp và tổ chức khu vực công, bao gồm cả các nhà cung cấp an ninh mạng," SentinelOne kết luận.

"Các hoạt động được chi tiết trong nghiên cứu này phản ánh sự quan tâm mạnh mẽ mà các tác nhân này dành cho chính các tổ chức được giao nhiệm vụ bảo vệ cơ sở hạ tầng kỹ thuật số."