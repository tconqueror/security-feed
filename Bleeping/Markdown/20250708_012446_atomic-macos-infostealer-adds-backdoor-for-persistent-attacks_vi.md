# Atomic macOS infostealer thêm backdoor cho các cuộc tấn công kéo dài

![Atomic macOS infostealer thêm backdoor cho các cuộc tấn công kéo dài](https://www.bleepstatic.com/content/hl-images/2023/09/11/apple_triangle.jpg)

Nhà phân tích phần mềm độc hại đã phát hiện một phiên bản mới của Atomic macOS info-stealer (còn được gọi là 'AMOS') đi kèm với một backdoor, cho phép tin tặc truy cập liên tục vào các hệ thống đã bị xâm nhập.

Phần bổ sung mới cho phép thực hiện các lệnh từ xa tuỳ ý, nó sống sót sau khi khởi động lại và cho phép duy trì quyền kiểm soát trên các máy chủ bị nhiễm một cách vô thời hạn.

Bộ phận an ninh mạng của MacPaw, Moonlock, đã phân tích backdoor trong phần mềm độc hại Atomic sau một mẹo từ nhà nghiên cứu độc lập [g0njxa](https://x.com/g0njxa), một người quan sát gần gũi hoạt động của infostealer.

" Các chiến dịch phần mềm độc hại AMOS đã đạt tới hơn 120 quốc gia, với Hoa Kỳ, Pháp, Ý, Vương quốc Anh và Canada là những nước bị ảnh hưởng nhiều nhất," các nhà nghiên cứu cho biết.

"Phiên bản có backdoor của Atomic macOS Stealer giờ đây có khả năng truy cập đầy đủ vào hàng nghìn thiết bị Mac trên toàn thế giới."

![Luồng mẫu Unique Atomic stealer](https://www.bleepstatic.com/images/news/u/1220909/2025/July/samples.jpg)

**Luồng mẫu Unique Atomic stealer**  
_Nguồn: Moonlock_

## Tiến hóa của Atomic stealer

Atomic stealer, [được ghi nhận lần đầu vào tháng 4 năm 2023](https://www.bleepingcomputer.com/news/security/new-atomic-macos-info-stealing-malware-targets-50-crypto-wallets/), là một hoạt động phần mềm độc hại-dưới-dạng-dịch-vụ (MaaS) được quảng bá trên các kênh Telegram với mức phí đăng ký lên tới 1.000 đô la mỗi tháng. Nó nhắm mục tiêu vào các tệp macOS, các tiện ích mở rộng cryptocurrency và mật khẩu người dùng lưu trên trình duyệt web.

Vào tháng 11 năm 2023, nó đã hỗ trợ [mở rộng đầu tiên của 'ClearFake'](https://www.bleepingcomputer.com/news/security/atomic-stealer-malware-strikes-macos-via-fake-browser-updates/) cho macOS, trong khi vào tháng 9 năm 2024, nó đã được phát hiện trong một chiến dịch quy mô lớn bởi nhóm tội phạm mạng '[Marko Polo](https://www.bleepingcomputer.com/news/security/global-infostealer-malware-operation-targets-crypto-users-gamers/),' những người đã triển khai trên các máy tính Apple.

Moonlock báo cáo rằng Atomic gần đây đã chuyển từ các kênh phân phối rộng rãi như các trang web phần mềm miễn phí sang việc lừa đảo nhắm vào các chủ sở hữu cryptocurrency, cũng như mời phỏng vấn việc làm cho các freelancer.

Phiên bản được phân tích của phần mềm độc hại đi kèm với một backdoor nhúng, sử dụng LaunchDaemons để sống sót sau khi khởi động lại trên macOS, theo dõi nạn nhân dựa trên ID và cơ sở hạ tầng chỉ huy và kiểm soát mới.

![Tiến hóa của Atomic stealer](https://www.bleepstatic.com/images/news/u/1220909/2025/July/evolution.jpg)

**Tiến hóa của Atomic stealer**  
_Nguồn: Moonlock_

## Một backdoor vào Mac của bạn

Tập tin thực thi backdoor chính là một nhị phân có tên '.helper', được tải xuống và lưu trữ trong thư mục chính của nạn nhân như một tệp ẩn sau khi nhiễm, [các nhà nghiên cứu cho biết](http://moonlock.com/amos-backdoor-persistent-access).

Một tập tin kịch bản gói bền vững có tên '.agent' (cũng ẩn) chạy '.helper' trong một vòng lặp với tư cách người dùng đã đăng nhập, trong khi một LaunchDaemon (com.finder.helper) được cài đặt qua AppleScript đảm bảo rằng '.agent' được thực thi khi khởi động hệ thống.

Hành động này được thực hiện với quyền hạn cao hơn bằng cách sử dụng mật khẩu của người dùng bị đánh cắp trong giai đoạn nhiễm ban đầu dưới một lý do sai lệch. Phần mềm độc hại có thể sau đó thực thi các lệnh và thay đổi quyền sở hữu của PLIST LaunchDaemon thành 'root:wheel' (cấp superuser trên macOS).

**Chuỗi thực thi backdoor**  
_Nguồn: Moonlock_

Backdoor cho phép các kẻ tấn công thực hiện các lệnh từ xa, ghi lại các gõ phím, giới thiệu các tải trọng bổ sung, hoặc khám phá khả năng di chuyển theo chiều ngang.

Để tránh bị phát hiện, backdoor kiểm tra các môi trường sandbox hoặc máy ảo bằng cách sử dụng 'system\_profiler' và cũng có tính năng làm mờ chuỗi.

Tiến hóa của phần mềm độc hại Atomic cho thấy rằng người dùng macOS ngày càng trở thành mục tiêu hấp dẫn hơn và các chiến dịch độc hại nhắm đến họ đang ngày càng tinh vi hơn.