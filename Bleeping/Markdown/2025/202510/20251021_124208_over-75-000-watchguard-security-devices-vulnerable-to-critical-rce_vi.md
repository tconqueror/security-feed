# Hơn 75.000 thiết bị bảo mật WatchGuard dễ bị RCE nghiêm trọng

![Hơn 75,000 thiết bị bảo mật WatchGuard dễ bị RCE nghiêm trọng](https://www.bleepstatic.com/content/hl-images/2025/09/18/WatchGuard.jpg)

Gần 76.000 thiết bị bảo mật mạng WatchGuard Firebox đang được phơi bày trên web công cộng và vẫn dễ bị khai thác bởi một lỗ hổng nghiêm trọng (CVE-2025-9242) có thể cho phép kẻ tấn công từ xa thực thi mã mà không cần xác thực.

Thiết bị Firebox hoạt động như một trung tâm phòng thủ chính kiểm soát lưu lượng giữa mạng nội bộ và mạng bên ngoài, cung cấp bảo vệ thông qua quản lý chính sách, dịch vụ bảo mật, VPN và khả năng hiển thị thời gian thực thông qua WatchGuard Cloud.

Các quét từ The Shadowserver Foundation hiện cho thấy có 75.835 [Firebox bị lỗ hổng](https://x.com/Shadowserver/status/1979902019696509099) trên toàn thế giới, phần lớn ở Châu Âu và Bắc Mỹ.

Cụ thể, Hoa Kỳ đứng đầu danh sách với 24.500 điểm cuối, tiếp theo là Germany (7.300), Italy (6.800), United Kingdom (5.400), Canada (4.100) và France (2.000).

[![Heatmap of vulnerable Firebox devices](https://www.bleepstatic.com/images/news/u/1220909/2025/October/map.jpg)](https://x.com/Shadowserver/status/1979902019696509099) 

**Bản đồ nhiệt của các thiết bị Firebox bị lỗ hổng**  
_Nguồn: The Shadowserver Foundation_

WatchGuard [đã công bố CVE-2025-9242](https://www.bleepingcomputer.com/news/security/watchguard-warns-of-critical-vulnerability-in-firebox-firewalls/) trong một bản tin bảo mật vào ngày 17 tháng 9 và đánh giá lỗ hổng này có mức độ nghiêm trọng critical với điểm số 9.3. Vấn đề bảo mật là một out-of-bounds write trong Fireware OS quá trình 'iked', thứ xử lý đàm phán IKEv2 VPN.

Lỗ hổng có thể bị khai thác mà không cần xác thực bằng cách gửi các gói IKEv2 được tạo khéo léo đến các endpoint Firebox dễ bị tổn thương, ép thiết bị ghi dữ liệu vào các vùng nhớ ngoài ý muốn.

Chỉ ảnh hưởng tới các thiết bị Firebox sử dụng IKEv2 VPN với các dynamic gateway peers, trên các phiên bản 11.10.2 through 11.12.4_Update1, 12.0 through 12.11.3, và 2025.1

Nhà cung cấp đề xuất nâng cấp lên một trong các phiên bản sau:

* 2025.1.1
* 12.11.4
* 12.5.13
* 12.3.1_Update3 (B722811)

Người dùng cần biết rằng phiên bản 11.x đã đến cuối vòng đời hỗ trợ và sẽ không nhận các bản cập nhật bảo mật. Khuyến nghị cho họ là chuyển sang phiên bản vẫn được hỗ trợ.

Đối với các thiết bị chỉ được cấu hình với Branch Office VPNs tới các static gateway peers, nhà cung cấp chỉ tới tài liệu về việc bảo đảm kết nối sử dụng các giao thức IPSec và IKEv2 như một giải pháp tạm thời.

Vào ngày 19 tháng 10, The Shadowserver Foundation phát hiện 75.955 tường lửa Firebox dễ bị tấn công. Một phát ngôn viên nói với BleepingComputer rằng việc quét hiện tại được coi là đáng tin cậy, và các con số này phản ánh các triển khai thực tế chứ chưa phải honeypot.

Mặc dù chưa có báo cáo về khai thác tích cực CVE-2025-9242, các quản trị viên chưa áp dụng bản cập nhật bảo mật được khuyến cáo cài đặt bản vá càng sớm càng tốt.