# Google Chrome sẽ cảnh báo người dùng trước khi mở các trang HTTP không an toàn

![Google Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Google thông báo hôm nay rằng trình duyệt web Chrome sẽ bắt đầu cảnh báo người dùng theo mặc định trước khi kết nối với các trang web công cộng không an toàn dùng HTTP, bắt đầu từ Chrome 154 vào tháng 10 năm 2026.

Google Chrome cũng có một [chế độ HTTPS-First tùy chọn](https://www.bleepingcomputer.com/news/security/google-chrome-will-add-https-first-mode-to-keep-your-data-safe/) từ năm 2021, tính năng này đã thêm cài đặt "Always Use Secure Connections" và cố gắng kết nối tới các trang web qua HTTPS (HyperText Transfer Protocol Secure), hiển thị một cảnh báo có thể bỏ qua nếu HTTPS không khả dụng.

Tuy nhiên, Google giờ sẽ bật tùy chọn này theo mặc định để đảm bảo người dùng chỉ truy cập các trang web qua HTTPS và luôn được bảo vệ khỏi các cuộc tấn công man-in-the-middle (MITM) cố gắng nghe lén hoặc thay đổi dữ liệu trao đổi với các máy chủ Internet qua giao thức HTTP không mã hóa.

"Một năm nữa, với bản phát hành Chrome 154 vào tháng 10 năm 2026, chúng tôi sẽ thay đổi cài đặt mặc định của Chrome để bật 'Always Use Secure Connections.' Điều này có nghĩa Chrome sẽ xin phép người dùng trước lần truy cập đầu tiên tới bất kỳ trang công cộng nào không dùng HTTPS," công ty cho biết.

"Khi các liên kết không sử dụng HTTPS, một kẻ tấn công có thể chiếm điều hướng và ép người dùng Chrome tải các tài nguyên do kẻ tấn công kiểm soát, và khiến người dùng tiếp xúc với phần mềm độc hại, khai thác có mục tiêu, hoặc các tấn công lừa đảo."

![Cảnh báo HTTP](https://www.bleepstatic.com/images/news/u/1109292/2025/HTTP-warning.png)

_Cảnh báo HTTP (Google)_

Như Google giải thích thêm, đối với tất cả các biến thể của cài đặt "Always Use Secure Connections" (nhắm vào trang riêng tư hoặc công cộng), Chrome sẽ không liên tục cảnh báo người dùng về một trang đó miễn là người dùng thường xuyên truy cập một trang không an toàn. Điều này có nghĩa thay vì cảnh báo người dùng ở 1 trong 50 lần điều hướng, Chrome sẽ chỉ cảnh báo khi họ mở một trang mới (hoặc hiếm khi truy cập) mà không dùng HTTPS.

Ngoài ra, người dùng sẽ có tùy chọn bật cảnh báo kết nối không an toàn chỉ cho các trang công cộng hoặc cho cả hai loại trang công cộng và riêng tư (bao gồm mạng nội bộ doanh nghiệp).

Điều quan trọng cần lưu ý là mặc dù các trang riêng tư vẫn có thể rủi ro, chúng thường được coi là ít nguy hiểm hơn các trang công cộng bởi vì có ít cơ hội hơn cho kẻ tấn công khai thác, và HTTP chỉ có thể bị lạm dụng bởi kẻ tấn công trong một bối cảnh hạn chế hơn, chẳng hạn như mạng cục bộ như Wi‑Fi gia đình của bạn hoặc trong môi trường công ty.

Tuy nhiên, ngay cả khi cả hai loại cảnh báo đều được bật, người dùng không nên bị làm phiền bởi quá nhiều thông báo, vì khoảng 95–99% tất cả các trang web đã áp dụng HTTPS, một mức tăng lớn so với tỉ lệ áp dụng khoảng 30–45% vào năm 2015.

![Secure connection settings](https://www.bleepstatic.com/images/news/u/1109292/2025/Secure%20connection%20settings.png)

_Cài đặt kết nối an toàn (Google)_

Trước khi bật nó theo mặc định cho tất cả người dùng, Chrome sẽ bật "Always Use Secure Connections" cho các trang công cộng cho hơn 1 tỷ người dùng sử dụng các bảo vệ Enhanced Safe Browsing vào tháng 4 năm 2026, khi Chrome 147 được phát hành.

"Mặc dù chúng tôi hy vọng và mong đợi rằng quá trình chuyển đổi này sẽ tương đối êm thấm đối với hầu hết người dùng, người dùng vẫn có thể tắt các cảnh báo bằng cách vô hiệu hóa cài đặt 'Always Use Secure Connections'," Google bổ sung.

"Nếu bạn là nhà phát triển trang web hoặc chuyên gia CNTT, và bạn có người dùng có thể bị ảnh hưởng bởi tính năng này, chúng tôi rất khuyến nghị bật cài đặt 'Always Use Secure Connections' ngay hôm nay để giúp xác định các trang mà bạn có thể cần làm việc để di chuyển."

Vào tháng 10 năm 2023, Google Chrome đã [thêm tính năng HTTPS-Upgrades](https://www.bleepingcomputer.com/news/google/google-chrome-now-auto-upgrades-to-secure-connections-for-all-users/) tự động nâng cấp các liên kết HTTP trong trang lên kết nối an toàn cho tất cả người dùng, đồng thời đảm bảo hồi tiếp nhanh về HTTP nếu cần.

Đầu tháng này, Google cũng cập nhật trình duyệt web của mình để [tự động thu hồi quyền thông báo](https://www.bleepingcomputer.com/news/google/google-chrome-to-revoke-notification-access-for-inactive-sites/) cho các trang không được truy cập gần đây, nhằm giảm quá tải cảnh báo.