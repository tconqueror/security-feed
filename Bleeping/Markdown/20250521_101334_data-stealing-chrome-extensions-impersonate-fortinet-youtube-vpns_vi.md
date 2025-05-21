# Các tiện ích mở rộng Chrome đánh cắp dữ liệu giả mạo Fortinet, YouTube và VPN

![Chrome](https://www.bleepstatic.com/content/hl-images/2021/09/23/Chrome_flare.jpg)

Một chiến dịch trên Cửa hàng Web Google Chrome sử dụng hơn 100 tiện ích mở rộng trình duyệt độc hại, giả mạo các công cụ hợp pháp như VPN, trợ lý AI và tiện ích crypto, để đánh cắp cookie trình duyệt và thực thi các script từ xa một cách bí mật.

Các tiện ích mở rộng này cung cấp một số tính năng đã hứa hẹn, nhưng cũng kết nối với cơ sở hạ tầng của kẻ tấn công để đánh cắp thông tin người dùng hoặc nhận lệnh để thực thi. Ngoài ra, các tiện ích mở rộng độc hại trên Chrome còn có khả năng sửa đổi lưu lượng mạng để cung cấp quảng cáo, thực hiện chuyển hướng hoặc làm proxy.

Chiến dịch này được phát hiện bởi các nhà nghiên cứu bảo mật tại DomainTools, những người đã phát hiện ra hơn 100 tên miền giả mạo quảng bá các công cụ này đến người dùng không nghi ngờ, có thể thông qua malvertising.

Danh sách của DomainTools về [hơn 100 trang web độc hại](https://github.com/DomainTools/SecuritySnacks/blob/main/2025/DualFunction-Malware-Chrome-Extensions) bao gồm nhiều thương hiệu VPN giả mạo cũng như các nỗ lực giả mạo các thương hiệu hợp pháp như Fortinet, YouTube, DeepSeek AI và Calendly:

* earthvpn\[.\]top
* irontunnel\[.\]world và iron-tunnel\[.\]com
* raccoon-vpn\[.\]world
* orchid-vpn\[.\]com
* soul-vpn\[.\]com
* forti-vpn\[.\]com và fortivnp\[.\]com
* debank-extension\[.\]world và debank\[.\]sbs, debank\[.\]click
* youtube-vision\[.\]com và youtube-vision\[.\]world
* deepseek-ai\[.\]link
* calendlydaily\[.\]world, calendlydocker\[.\]com, calendly-director\[.\]com
* whale-alerts\[.\]org và whale-alert\[.\]life
* madgicxads\[.\]world và madgicx-plus\[.\]com
* similar-net\[.\]com
* workfront-plus\[.\]com
* flight-radar\[.\]life

Các trang web này bao gồm các nút "Thêm vào Chrome" liên kết đến các tiện ích mở rộng trình duyệt độc hại trên Cửa hàng Web Chrome, do đó tăng cường cảm giác hợp pháp.

![Trang web độc hại giả mạo khách hàng VPN Fortinet](https://www.bleepstatic.com/images/news/security/c/chrome-extensions/100-extensions/fortivpn.jpg)

**Trang web độc hại giả mạo khách hàng VPN Fortinet**  
_Nguồn: DomainTools_

Mặc dù Google đã xóa nhiều tiện ích mở rộng mà DomainTools xác định, BleepingComputer đã xác nhận rằng một số tiện ích vẫn còn trên Cửa hàng Web Chrome.

"Cửa hàng Web Chrome đã xóa nhiều tiện ích mở rộng độc hại của kẻ tấn công sau khi xác định malware," [các nhà nghiên cứu giải thích](https://dti.domaintools.com/dual-function-malware-chrome-extensions/).

"Tuy nhiên, sự kiên trì của kẻ tấn công và khoảng thời gian trễ trong việc phát hiện và xóa vẫn gây ra mối đe dọa cho người dùng tìm kiếm các công cụ tăng năng suất và cải tiến trình duyệt."

Trong khi mỗi tiện ích mở rộng thực hiện các chức năng khác nhau, chúng yêu cầu các quyền rủi ro cho phép chúng đánh cắp cookie, bao gồm cả mã thông báo phiên, thực hiện phishing dựa trên DOM và thực hiện chèn script động.

Ví dụ, tiện ích mở rộng "fortivpn" được sử dụng để đánh cắp cookie, hoạt động như một máy chủ proxy, sửa đổi lưu lượng mạng và chạy các script JavaScript tùy ý từ một máy chủ từ xa.

"Khi được lệnh, nó sử dụng chrome.cookies.getAll({}) để lấy tất cả cookie trình duyệt, nén chúng bằng pako, mã hóa bằng Base64 và gửi lại đến máy chủ backend infograph\[.\]top," báo cáo cho biết.

"Nó có thể được lệnh để thiết lập một kết nối WebSocket riêng biệt để hoạt động như một proxy mạng, có khả năng chuyển hướng lưu lượng người dùng qua các máy chủ độc hại. Đích proxy được cung cấp bởi lệnh backend và cũng thực hiện xử lý xác thực proxy."

Rủi ro phát sinh từ việc cài đặt các tiện ích mở rộng này bao gồm đánh cắp tài khoản, đánh cắp dữ liệu cá nhân và giám sát hoạt động duyệt web. Cuối cùng, chúng cung cấp cho kẻ tấn công một cửa sau trên trình duyệt bị nhiễm, do đó tiềm năng khai thác là rất lớn.

Các kẻ tấn công cũng có thể sử dụng cookie phiên bị đánh cắp để xâm phạm các thiết bị hoặc tài khoản VPN hợp pháp của công ty để truy cập vào các mạng doanh nghiệp, gây ra các cuộc tấn công thiệt hại nghiêm trọng hơn.

Để giảm thiểu rủi ro từ việc tải xuống các tiện ích mở rộng độc hại từ Cửa hàng Web Chrome, chỉ nên tin tưởng các nhà xuất bản đáng tin cậy với thành tích đã được chứng minh và xem xét các đánh giá của người dùng để tìm kiếm các dấu hiệu cảnh báo.

BleepingComputer đã liên hệ với Google để hỏi về những nỗ lực phát hiện của họ liên quan đến chiến dịch cụ thể này, nhưng chúng tôi đã không nhận được phản hồi trước thời điểm xuất bản.