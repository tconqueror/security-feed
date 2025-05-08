# FBI: Các bộ định tuyến hết tuổi thọ bị hack để tạo mạng proxy tội phạm mạng

![FBI](https://www.bleepstatic.com/content/hl-images/2022/12/16/FBI__headpic.jpg)

FBI cảnh báo rằng các tác nhân đe dọa đang triển khai phần mềm độc hại trên các bộ định tuyến hết tuổi thọ (EoL) để chuyển đổi chúng thành các proxy được bán trên các mạng 5Socks và Anyproxy.

Các thiết bị này, được phát hành cách đây nhiều năm và không còn nhận cập nhật bảo mật từ các nhà cung cấp của chúng, dễ bị tấn công bên ngoài lợi dụng các lỗ hổng công khai để tiêm phần mềm độc hại tồn tại lâu dài.

Khi bị xâm phạm, chúng sẽ được thêm vào các botnet proxy dân cư mà điều hướng lưu lượng độc hại. Trong nhiều trường hợp, các proxy này được sử dụng bởi các tội phạm mạng để tiến hành các hoạt động độc hại hoặc tấn công mạng.

"Với mạng 5Socks và Anyproxy, tội phạm đang bán quyền truy cập vào các bộ định tuyến bị xâm phạm như là các proxy để khách hàng có thể mua và sử dụng," [giải thích thông báo khẩn của FBI](https://www.ic3.gov/CSA/2025/250507.pdf).

"Các proxy này có thể được sử dụng bởi các tác nhân đe dọa để làm mờ danh tính hoặc vị trí của họ."

Thông báo liệt kê các mẫu Linksys và Cisco EoL sau đây là mục tiêu phổ biến:

* Linksys E1200, E2500, E1000, E4200, E1500, E300, E3200, E1550
* Linksys WRT320N, WRT310N, WRT610N
* Cradlepoint E100
* Cisco M10

FBI cảnh báo rằng các tác nhân có sự hỗ trợ từ nhà nước Trung Quốc đã khai thác các lỗ hổng đã biết (n-day) trong các bộ định tuyến này để [tiến hành các chiến dịch gián điệp bí mật](https://www.bleepingcomputer.com/news/security/state-hackers-turn-to-massive-orb-proxy-networks-to-evade-detection/), bao gồm các hoạt động nhắm mục tiêu vào cơ sở hạ tầng quan trọng của Hoa Kỳ.

Trong một [thông cáo liên quan](https://www.ic3.gov/PSA/2025/PSA250507), cơ quan xác nhận rằng nhiều bộ định tuyến này bị nhiễm một biến thể của phần mềm độc hại "TheMoon", cho phép các tác nhân đe dọa cấu hình chúng làm proxy.

"Các bộ định tuyến hết tuổi thọ đã bị xâm phạm bởi các tác nhân mạng sử dụng các biến thể của botnet TheMoon," thông báo của FBI cho biết.

"Gần đây, một số bộ định tuyến đã hết tuổi thọ, với chức năng quản trị từ xa được bật, được xác định là đã bị xâm phạm bởi một biến thể mới của phần mềm độc hại TheMoon. Phần mềm độc hại này cho phép các tác nhân mạng cài đặt proxy trên các bộ định tuyến của nạn nhân mà họ không hay biết và thực hiện tội phạm mạng một cách ẩn danh."

Khi bị xâm phạm, các bộ định tuyến kết nối với các máy chủ chỉ huy và kiểm soát (C2) để nhận lệnh thực hiện, chẳng hạn như quét và xâm nhập các thiết bị dễ bị tấn công trên Internet.

FBI cho biết các proxy sau đó được sử dụng để tránh bị phát hiện trong quá trình đánh cắp tiền điện tử, các hoạt động thuê tội phạm mạng, và các hoạt động bất hợp pháp khác.

Những dấu hiệu phổ biến của sự xâm nhập của botnet bao gồm gián đoạn kết nối mạng, quá nhiệt, suy giảm hiệu suất, thay đổi cấu hình, xuất hiện người dùng quản trị bất hợp pháp, và lưu lượng mạng không bình thường.

Cách tốt nhất để giảm thiểu rủi ro nhiễm botnet là thay thế các bộ định tuyến hết tuổi thọ bằng các mẫu mới hơn, được hỗ trợ tích cực.

Nếu điều đó không thể xảy ra, hãy áp dụng bản cập nhật firmware mới nhất cho mẫu thiết bị của bạn, lấy từ cổng tải xuống chính thức của nhà cung cấp, thay đổi thông tin đăng nhập tài khoản quản trị mặc định, và tắt các bảng quản trị từ xa.

FBI đã chia sẻ các chỉ báo của sự xâm phạm liên quan đến phần mềm độc hại được cài đặt trên các thiết bị EoL.