# SonicWall cảnh báo về phiên bản NetExtender bị trojan hóa đánh cắp đăng nhập VPN

![SonicWall](https://www.bleepstatic.com/content/hl-images/2022/05/13/SonicWall.jpeg)

SonicWall đang cảnh báo khách hàng rằng các tác nhân đe dọa đang phân phối phiên bản NetExtender SSL VPN client bị trojan hóa nhằm đánh cắp thông tin xác thực VPN.

Phần mềm giả mạo này được phát hiện bởi các nhà nghiên cứu của SonicWall và Microsoft Threat Intelligence (MSTIC), bắt chước phiên bản chính thức NetExtender v10.3.2.27, phiên bản mới nhất hiện có.

Tệp cài đặt độc hại được lưu trữ trên một trang web giả mạo được làm cho có vẻ hợp pháp, khiến người truy cập nghĩ rằng họ đang tải phần mềm từ SonicWall.

Mặc dù tệp cài đặt không được ký số bởi SonicWall, nhưng nó được ký bởi "CITYLIGHT MEDIA PRIVATE LIMITED," cho phép nó vượt qua các biện pháp phòng ngừa cơ bản.

![Chữ ký số trên tệp đã bị sửa đổi](https://www.bleepstatic.com/images/news/u/1220909/2025/June/signature.jpg)

**Chữ ký số trên tệp đã bị sửa đổi**  
_Nguồn: SonicWall_

Mục tiêu của ứng dụng bị trojan hóa là ăn cắp cấu hình VPN và thông tin tài khoản và phát tán chúng đến kẻ tấn công.

SonicWall NetExtender là một VPN client truy cập từ xa cho phép người dùng kết nối một cách an toàn với mạng nội bộ của tổ chức từ các vị trí xa.

Nó được thiết kế đặc biệt để hoạt động với các thiết bị SonicWall SSL VPN và tường lửa, và thường được sử dụng bởi nhân viên từ xa của các doanh nghiệp nhỏ đến vừa, quản trị viên CNTT và nhà thầu thuộc nhiều loại hình ngành nghề khác nhau.

SonicWall và Microsoft phát hiện hai tệp nhị phân đã bị sửa đổi của sản phẩm họ đang phân phối bởi các trang web giả mạo độc hại.

Một tệp **NeService.exe** đã được sửa đổi với logic xác thực của nó được vá để vượt qua kiểm tra chứng chỉ số và tệp **NetExtender.exe**, đã được sửa đổi để đánh cắp dữ liệu.

"Mã bổ sung đã được thêm vào để gửi thông tin cấu hình VPN tới một máy chủ từ xa với địa chỉ IP 132.196.198.163 qua cổng 8080," giải thích [thông báo của SonicWall](https://www.sonicwall.com/blog/threat-actors-modify-and-re-create-commercial-software-to-steal-users-information).

"Khi thông tin chi tiết cấu hình VPN được nhập và nút 'Kết nối' được nhấp, mã độc thực hiện xác thực riêng của nó trước khi gửi dữ liệu đến máy chủ từ xa. Thông tin cấu hình bị đánh cắp bao gồm tên người dùng, mật khẩu, miền, và nhiều hơn nữa."

![Các sửa đổi trên tệp 'NetExtender.exe'](https://www.bleepstatic.com/images/news/u/1220909/2025/June/code.jpg)

**Mã độc trên tệp 'NetExtender.exe'**  
_Nguồn: SonicWall_

SonicWall khuyến cáo rằng người dùng chỉ nên tải phần mềm từ các cổng chính thức tại sonicwall.com và mysonicwall.com.

Các công cụ bảo mật của công ty và Microsoft Defender hiện phát hiện và chặn các tệp cài đặt độc hại, mặc dù các công cụ bảo mật khác có thể không phát hiện được.

Thường thì, người dùng bị chuyển hướng đến các trang web giả mạo cung cấp các tệp cài đặt bị trojan hóa thông qua quảng cáo độc hại, SEO poisoning, tin nhắn trực tiếp, bài đăng trên diễn đàn, và video trên YouTube hoặc TikTok.

Khi tải phần mềm, hãy sử dụng trang web chính thức của nhà cung cấp và bỏ qua tất cả các kết quả quảng cáo. Ngoài ra, hãy luôn quét các tệp tải xuống trên một AV cập nhật trước khi thực thi chúng trên thiết bị của bạn.