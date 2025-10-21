# TP-Link cảnh báo lỗ hổng tiêm lệnh nghiêm trọng trong các gateway Omada

![TP-Link cảnh báo lỗ hổng tiêm lệnh nghiêm trọng trong các gateway Omada](https://www.bleepstatic.com/content/hl-images/2025/09/04/TPLINK_Logo_2.jpg)

TP-Link đang cảnh báo về hai lỗ hổng tiêm lệnh trong các thiết bị gateway Omada có thể bị khai thác để thực thi các lệnh OS tùy ý.

Các gateway Omada được tiếp thị như các giải pháp full-stack (router, firewall, VPN gateway) cho các doanh nghiệp nhỏ và vừa, và ngày càng trở nên phổ biến.

Mặc dù hai vấn đề bảo mật dẫn đến cùng một kết quả khi bị kích hoạt, chỉ có một trong số chúng, được xác định là CVE-2025-6542 với mức độ nghiêm trọng critical 9.3, có thể bị khai thác bởi kẻ tấn công từ xa mà không cần xác thực.

Lỗ hổng thứ hai được theo dõi là CVE-2025-6541 và nhận điểm mức độ nghiêm trọng thấp hơn là 8.6. Tuy nhiên, nó chỉ có thể bị khai thác nếu kẻ tấn công có thể đăng nhập vào giao diện quản lý web.

“Một lệnh OS tùy ý có thể được thực thi trên các gateway Omada bởi người dùng có thể đăng nhập vào giao diện quản lý web hoặc bởi kẻ tấn công từ xa không xác thực,” đọc [TP-Link's advisory](https://support.omadanetworks.com/en/document/108455/).

“Kẻ tấn công có thể thực thi các lệnh tùy ý trên hệ điều hành nền tảng của thiết bị,” công ty bổ sung.

Rủi ro mà hai lỗ hổng này gây ra là đáng kể vì chúng có thể dẫn đến việc xâm phạm hoàn toàn, đánh cắp dữ liệu, di chuyển ngang và duy trì quyền truy cập lâu dài.

CVE-2025-6541 và CVE-2025-6542 ảnh hưởng tới 13 mẫu gateway Omada trong các phiên bản firmware được liệt kê dưới đây:

| **Mẫu sản phẩm bị ảnh hưởng** **Phiên bản bị ảnh hưởng** **Phiên bản đã sửa** ER8411 < 1.3.3 Build 20251013 Rel.44647 \>= 1.3.3 Build 20251013 Rel.44647 ER7412-M2 < 1.1.0 Build 20251015 Rel.63594 \>= 1.1.0 Build 20251015 Rel.63594 ER707-M2 < 1.3.1 Build 20251009 Rel.67687 \>= 1.3.1 Build 20251009 Rel.67687 ER7206 < 2.2.2 Build 20250724 Rel.11109 \>= 2.2.2 Build 20250724 Rel.11109 ER605 < 2.3.1 Build 20251015 Rel.78291 \>= 2.3.1 Build 20251015 Rel.78291 ER706W < 1.2.1 Build 20250821 Rel.80909 \>= 1.2.1 Build 20250821 Rel.80909 ER706W-4G < 1.2.1 Build 20250821 Rel.82492 \>= 1.2.1 Build 20250821 Rel.82492 ER7212PC < 2.1.3 Build 20251016 Rel.82571 \>= 2.1.3 Build 20251016 Rel.82571 G36 < 1.1.4 Build 20251015 Rel.84206 \>= 1.1.4 Build 20251015 Rel.84206 G611 < 1.2.2 Build 20251017 Rel.45512 \>= 1.2.2 Build 20251017 Rel.45512 FR365 < 1.1.10 Build 20250626 Rel.81746 \>= 1.1.10 Build 20250626 Rel.81746 FR205 < 1.0.3 Build 20251016 Rel.61376 \>= 1.0.3 Build 20251016 Rel.61376 FR307-M2 < 1.2.5 Build 20251015 Rel.76743 \>= 1.2.5 Build 20251015 Rel.76743 |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Nhà cung cấp đã phát hành các bản cập nhật firmware khắc phục hai vấn đề và khuyến nghị mạnh mẽ người dùng có thiết bị bị ảnh hưởng áp dụng các bản sửa và kiểm tra cấu hình sau khi nâng cấp để đảm bảo tất cả cài đặt vẫn như dự định.

Trong một [thông báo riêng](https://support.omadanetworks.com/us/document/108456/), TP-Link cảnh báo về hai lỗ hổng nghiêm trọng khác có thể cho phép tiêm lệnh xác thực và truy cập root trong một số điều kiện nhất định.

Lỗ hổng đầu tiên là CVE-2025-8750 (CVSS: 9.3), một lỗ hổng tiêm lệnh có thể bị khai thác bởi những kẻ tấn công nắm giữ mật khẩu admin để truy cập cổng web Omada.

Lỗ hổng còn lại là CVE-2025-7851 (CVSS: 8.7), có thể cho phép kẻ tấn công có được truy cập shell với quyền root trên hệ điều hành nền tảng, bị giới hạn trong các đặc quyền của Omada.

CVE-2025-7850 và CVE-2025-7851 ảnh hưởng tới tất cả các mẫu gateway Omada được liệt kê trong bảng ở trên. Cần lưu ý rằng bản phát hành firmware mới nhất khắc phục cả bốn lỗ hổng.