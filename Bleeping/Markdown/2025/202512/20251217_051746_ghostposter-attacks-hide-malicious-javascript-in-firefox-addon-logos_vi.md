# GhostPoster tấn công: ẩn JavaScript độc hại trong logo tiện ích mở rộng Firefox

![GhostPoster attacks hide malicious JavaScript in Firefox addon logos](https://www.bleepstatic.com/content/hl-images/2025/05/29/firefox-header.jpg)

Một chiến dịch mới có tên 'GhostPoster' đang giấu mã JavaScript trong biểu tượng ảnh của các tiện ích mở rộng Firefox độc hại có hơn 50.000 lượt tải, nhằm theo dõi hoạt động trình duyệt và cài cửa hậu.

Mã độc cho phép kẻ điều khiển có quyền truy cập bền vững với đặc quyền cao vào trình duyệt, cho phép chúng chiếm đoạt liên kết affiliate, chèn mã theo dõi và thực hiện gian lận nhấp chuột và quảng cáo.

Đoạn script ẩn hoạt động như một trình tải (loader) lấy payload chính từ máy chủ từ xa. Để khiến quá trình khó bị phát hiện hơn, payload được truy xuất cố ý chỉ 1 lần trong 10 lần thử.

[![Wiz](https://www.bleepstatic.com/content/webinar-images/Action1-970x250-watch-now.jpg)](/mgo/72/) 

Các nhà nghiên cứu của Koi Security đã phát hiện chiến dịch GhostPoster và xác định 17 tiện ích mở rộng Firefox bị xâm nhập, những tiện ích này hoặc đọc logo PNG để trích xuất và thực thi trình tải malware, hoặc tải payload chính từ máy chủ của kẻ tấn công.

Cần lưu ý rằng các tiện ích độc hại thuộc các danh mục phổ biến sau:

1. free-vpn-forever
2. screenshot-saved-easy
3. weather-best-forecast
4. crxmouse-gesture
5. cache-fast-site-loader
6. freemp3downloader
7. google-translate-right-clicks
8. google-traductor-esp
9. world-wide-vpn
10. dark-reader-for-ff
11. translator-gbbd
12. i-like-weather
13. google-translate-pro-extension
14. 谷歌-翻译
15. libretv-watch-free-videos
16. ad-stop
17. right-click-google-translate

Các nhà nghiên cứu cho biết không phải tất cả tiện ích ở trên đều sử dụng cùng một chuỗi tải payload, nhưng tất cả đều thể hiện hành vi giống nhau và liên lạc với cùng một cơ sở hạ tầng.

Tiện ích FreeVPN Forever là mục mà Koi Security phân tích ban đầu sau khi công cụ AI của họ đánh dấu vì phân tích các byte thô của tệp ảnh logo để tìm một đoạn JavaScript được ẩn bằng kỹ thuật steganography.

![Malicious extension on the Firefox store](https://www.bleepstatic.com/images/news/u/1220909/2025/December/ext.jpg)

**Tiện ích độc hại trên cửa hàng Firefox**  
_Nguồn: Koi Security_

Trình tải JavaScript kích hoạt sau 48 giờ để lấy payload từ một domain được mã cứng (hardcoded). Một domain dự phòng thứ hai có sẵn nếu payload không được truy xuất từ domain đầu tiên.

Theo [Koi Security](https://www.koi.ai/blog/inside-ghostposter-how-a-png-icon-infected-50-000-firefox-browser-users), trình tải phần lớn nằm im và chỉ lấy payload 10% thời gian, khiến nó có khả năng né tránh phát hiện từ các công cụ giám sát lưu lượng.

Payload tải về bị làm mờ nặng bằng cách đổi chữ hoa/chữ thường và mã hóa base64. Một bộ mã giải giải mã nó và sau đó mã hóa XOR sử dụng khóa được dẫn xuất từ runtime ID của tiện ích mở rộng.

**Phân tích dữ liệu logo để tìm đoạn mã độc**  
_Nguồn: Koi Security_

Payload cuối cùng có các khả năng sau:

* Chiếm đoạt liên kết affiliate trên các trang thương mại điện tử lớn, chuyển hoa hồng về cho kẻ tấn công.
* Chèn mã theo dõi Google Analytics vào mọi trang người dùng truy cập.
* Loại bỏ các header bảo mật khỏi tất cả phản hồi HTTP.
* Vượt qua CAPTCHA bằng ba cơ chế khác nhau để né các biện pháp bảo vệ bot.
* Chèn các iframe vô hình để gian lận quảng cáo, gian lận nhấp chuột và theo dõi, sau đó tự xóa sau 15 giây.

Mặc dù mã độc không thu thập mật khẩu hay chuyển hướng người dùng tới các trang lừa đảo (phishing), nó vẫn đe dọa quyền riêng tư của người dùng.

Hơn nữa, do trình tải ẩn được GhostPoster sử dụng, chiến dịch có thể nhanh chóng trở nên nguy hiểm hơn nếu kẻ điều khiển quyết định triển khai một payload độc hại hơn.

Người dùng các tiện ích đã liệt kê được khuyến nghị gỡ bỏ chúng và nên cân nhắc đặt lại mật khẩu cho các tài khoản quan trọng.

Nhiều tiện ích độc hại vẫn còn có trên trang Add-Ons của Firefox vào thời điểm viết bài. BleepingComputer đã liên hệ với Mozilla về vấn đề này, nhưng một bình luận chưa có sẵn ngay lập tức.