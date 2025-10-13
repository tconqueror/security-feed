# Mạng botnet quy mô lớn nhiều quốc gia nhắm vào dịch vụ RDP ở US

![Mạng botnet quy mô lớn nhiều quốc gia nhắm vào dịch vụ RDP ở US](https://www.bleepstatic.com/content/hl-images/2023/11/01/botnet-kill-switch.jpg)

Một mạng botnet quy mô lớn đang nhắm mục tiêu các dịch vụ Remote Desktop Protocol (RDP) ở United States từ hơn 100.000 địa chỉ IP.

Chiến dịch bắt đầu vào ngày 8 tháng Mười và dựa trên nguồn gốc của các IP, các nhà nghiên cứu tin rằng các cuộc tấn công được khởi xướng bởi một botnet đa quốc gia.

RDP là một giao thức mạng cho phép kết nối từ xa và điều khiển các hệ thống Windows. Nó thường được sử dụng bởi các quản trị viên, nhân viên hỗ trợ kỹ thuật và người làm việc từ xa.

Kẻ tấn công thường quét các cổng RDP mở hoặc cố gắng brute-force đăng nhập, khai thác lỗ hổng, hoặc thực hiện các tấn công dựa trên thời gian phản hồi.

Trong trường hợp này, các nhà nghiên cứu tại nền tảng giám sát mối đe doạ GreyNoise nhận thấy rằng botnet dựa vào hai loại tấn công liên quan đến RDP:

1. **RD Web Access timing attacks** – Thăm dò các endpoint RD Web Access và đo sự khác biệt thời gian phản hồi trong các luồng xác thực ẩn danh để suy ra tên người dùng hợp lệ
2. **RDP web client login enumeration** – Tương tác với luồng đăng nhập của RDP Web Client để liệt kê tài khoản người dùng bằng cách quan sát sự khác biệt về hành vi và phản hồi của máy chủ

GreyNoise phát hiện chiến dịch sau một đột biến lưu lượng bất thường từ Brazil, tiếp theo là hoạt động tương tự từ địa lý rộng hơn, bao gồm Argentina, Iran, China, Mexico, Russia, South Africa và Ecuador.

Công ty cho biết danh sách đầy đủ các quốc gia có thiết bị bị xâm nhập trong botnet vượt quá 100.

![Đột biến hoạt động bất thường từ Brazil](https://www.bleepstatic.com/images/news/u/1220909/2025/October/brazilspike.jpg)

**Đột biến hoạt động bất thường từ Brazil**  
_Nguồn: GreyNoise_

Gần như tất cả các địa chỉ IP đều chia sẻ một dấu vân TCP chung, và mặc dù có những biến thể trong (Maximum Segment Size), các [nhà nghiên cứu tin rằng](https://www.greynoise.io/blog/botnet-launches-coordinated-rdp-attack-wave) điều này là do các cụm tạo thành botnet.

Để phòng thủ trước hoạt động này, các quản trị hệ thống được khuyến nghị chặn các địa chỉ IP khởi xướng các cuộc tấn công và kiểm tra nhật ký để tìm các hoạt động dò xét RDP đáng ngờ.

Như một khuyến nghị chung, kết nối remote desktop không nên được để lộ ra internet công cộng và [thêm VPN](https://learn.microsoft.com/en-us/windows-server/remote/remote-desktop-services/remotepc/remote-desktop-allow-outside-access?source=recommendations#use-a-vpn) và xác thực đa yếu tố ([MFA](https://learn.microsoft.com/en-us/windows-server/remote/remote-desktop-services/rds-plan-mfa)) sẽ tăng thêm một lớp bảo vệ.