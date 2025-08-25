# Ứng dụng Android độc hại với 19 triệu lượt cài đặt đã bị xóa khỏi Google Play

![Ứng dụng Android độc hại với 19 triệu lượt cài đặt đã bị xóa khỏi Google Play](https://www.bleepstatic.com/content/hl-images/2024/05/03/Android-2.jpg)

Bảy mươi bảy ứng dụng Android độc hại với hơn 19 triệu lượt cài đặt đã phát tán nhiều gia đình phần mềm độc hại đến người dùng Google Play.

Cuộc xâm nhập phần mềm độc hại này được phát hiện bởi nhóm [Zscaler's ThreatLabs](https://www.zscaler.com/blogs/security-research/android-document-readers-and-deception-tracking-latest-updates-anatsa) trong khi đang điều tra một làn sóng lây nhiễm mới với trojan ngân hàng Anatsa (Tea Bot) nhắm vào các thiết bị Android.

Trong khi hầu hết các ứng dụng độc hại (hơn 66%) bao gồm các thành phần adware, phần mềm độc hại Android phổ biến nhất là Joker, mà các nhà nghiên cứu đã phát hiện trong gần 25% số ứng dụng đã phân tích.

Khi phần mềm độc hại Joker được cài đặt trên thiết bị, nó có thể đọc và gửi tin nhắn văn bản, chụp ảnh màn hình, thực hiện cuộc gọi điện thoại và đánh cắp danh bạ, truy cập thông tin thiết bị và đăng ký người dùng cho các dịch vụ trả phí.

Một tỷ lệ nhỏ hơn của các ứng dụng bao gồm maskware, một thuật ngữ được sử dụng để định nghĩa một ứng dụng độc hại ngụy trang thành một cái gì đó không gây nghi ngờ.

Loại phần mềm độc hại này có thể giả mạo như một ứng dụng hợp pháp hoạt động như đã quảng cáo. Tuy nhiên, nó thực hiện các hoạt động độc hại trong nền, chẳng hạn như đánh cắp thông tin xác thực, thông tin ngân hàng hoặc dữ liệu nhạy cảm khác (vị trí, SMS). Tội phạm mạng cũng có thể sử dụng maskware để phát tán các phần mềm độc hại khác.

Các nhà nghiên cứu của Zscaler cũng phát hiện một biến thể của phần mềm độc hại Joker có tên là Harly, mà đóng vai trò như một ứng dụng hợp pháp có mã độc ẩn sâu hơn trong mã để tránh bị phát hiện trong quá trình xem xét.

![](https://cms.zscaler.com/cdn-cgi/image/format=auto/sites/default/files/images/blogs/anatsa_2025_figure_5_0.png)

Chú thích

Trong một báo cáo vào tháng Ba, [các nhà nghiên cứu của Human Security](https://www.humansecurity.com/learn/blog/satori-perpectives-tracking-the-ongoing-evolution-of-harly-trojan-android-fraud/) cho biết Harly có thể ẩn mình trong các ứng dụng phổ biến, như trò chơi, hình nền, đèn pin và trình chỉnh sửa ảnh.

### Trojan Anatsa tiếp tục phát triển

Theo Zscaler, phiên bản mới nhất của trojan ngân hàng Anatsa đã mở rộng hơn nữa phạm vi nhắm mục tiêu của nó, tăng số lượng ứng dụng ngân hàng và tiền ảo lên 831, từ 650 trước đó, mà nó cố gắng đánh cắp dữ liệu từ.

Các nhà điều hành phần mềm độc hại sử dụng một ứng dụng được gọi là 'Document Reader – File Manager' như một cái bẫy, mà chỉ tải xuống payload độc hại Anatsa sau khi cài đặt, để tránh sự kiểm tra mã của Google.

![Ứng dụng Trojan Anatsa trên Google Play](https://www.bleepstatic.com/images/news/u/1220909/2025/August/play.jpg)

**Ứng dụng Trojan Anatsa trên Google Play**  
_Nguồn: Zscaler_

Chiến dịch mới nhất đã chuyển từ tải mã động DEX từ xa được sử dụng trong quá khứ sang cài đặt payload trực tiếp, giải nén từ các tệp JSON và sau đó xóa chúng.

Về mặt né tránh, nó sử dụng các tệp APK bị lỗi để phá vỡ phân tích tĩnh, giải mã chuỗi dựa trên DES trong thời gian thực và phát hiện giả lập. Tên gói và các giá trị hash cũng được thay đổi theo định kỳ.

**Phát hiện giả lập (bên trái) và lấy payload (bên phải)**  
_Nguồn: Zscaler_

Về khả năng, Anatsa lạm dụng quyền Accessibility trên Android để tự cấp cho nó các quyền rộng rãi.

Nó lấy các trang lừa đảo từ máy chủ của nó cho hơn 831 ứng dụng, giờ đây cũng bao gồm Đức và Hàn Quốc, trong khi một mô-đun keylogger cũng được thêm vào để lấy dữ liệu chung.

Chiến dịch Anatsa mới nhất này theo sau một làn sóng gần đây khác được phát hiện bởi ThreatFabric vào tháng Bảy, nơi trojan đã len lỏi vào Google Play với lớp vỏ của một trình xem PDF, đạt được hơn [50.000 lượt tải về](https://www.bleepingcomputer.com/news/security/android-malware-anatsa-infiltrates-google-play-to-target-us-banks/).

Các chiến dịch Anatsa cũ hơn bao gồm một cuộc tấn công vào trình đọc PDF và mã QR vào tháng 5 năm 2024 đạt được [70.000 lần lây nhiễm](https://www.bleepingcomputer.com/news/security/over-90-malicious-android-apps-with-55m-installs-found-on-google-play/), một cuộc tấn công vào Cleaner điện thoại và PDF vào tháng 2 năm 2024 với [150.000 lượt tải về](https://www.bleepingcomputer.com/news/security/anatsa-android-malware-downloaded-150-000-times-via-google-play/), và một cuộc tấn công trình xem PDF khác vào tháng 3 năm 2023 đạt được [30.000 lượt cài đặt](https://www.bleepingcomputer.com/news/security/anatsa-android-trojan-now-steals-banking-info-from-users-in-us-uk/).

## Làn sóng ứng dụng độc hại trên Google Play

Ngoài các ứng dụng Anatsa độc hại, Zscaler phát hiện lần này, hầu hết đều là gia đình adware, tiếp theo là 'Joker,' 'Harly,' và nhiều loại maskware khác.

"ThreatLabz đã xác định được sự gia tăng mạnh mẽ các ứng dụng adware trên Google Play Store cùng với phần mềm độc hại, như Joker, Harly và các trojan ngân hàng như Anatsa," giải thích nhà nghiên cứu của Zscaler Himanshu Sharma.

"Mặt khác, đã có sự sụt giảm rõ rệt ở các gia đình phần mềm độc hại như Facestealer và Coper."

Các công cụ và ứng dụng cá nhân hóa chiếm hơn một nửa số chiêu trò được sử dụng để phát tán các ứng dụng đó, vì vậy hai danh mục này, cùng với giải trí, nhiếp ảnh và thiết kế, nên được coi là có rủi ro cao.

Tổng cộng, 77 ứng dụng độc hại, bao gồm cả các ứng dụng chứa Anatsa, đã được tải xuống 19 triệu lần từ Google Play.

Zscaler báo cáo rằng Google đã xóa tất cả các ứng dụng độc hại mà họ phát hiện lần này khỏi Play Store sau khi báo cáo của họ.

Người dùng Android phải đảm bảo dịch vụ Play Protect của họ hoạt động trên thiết bị để đánh dấu các ứng dụng độc hại để xóa bỏ.

Trong trường hợp lây nhiễm trojan Anatsa, cần thực hiện các bước riêng với ngân hàng để bảo vệ các tài khoản hoặc thông tin xác thực ngân hàng điện tử có thể bị xâm phạm.

Để giảm thiểu rủi ro từ các phần mềm độc hại trên Google Play, chỉ nên tin tưởng các nhà phát hành uy tín, đọc ít nhất một vài đánh giá của người dùng và chỉ cấp quyền hạn trực tiếp liên quan đến chức năng cốt lõi của ứng dụng.