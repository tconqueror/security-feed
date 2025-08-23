# Google kiện nhằm phá vỡ botnet BadBox 2.0 lây nhiễm 10 triệu thiết bị

![Thiết bị Android](https://www.bleepstatic.com/content/hl-images/2024/12/19/android-malware-botnet.jpg)

Google đã đệ đơn kiện các điều hành viên ẩn danh của botnet phần mềm độc hại Android BadBox 2.0, cáo buộc họ thực hiện một kế hoạch gian lận quảng cáo toàn cầu nhằm vào các nền tảng quảng cáo của công ty.

Botnet phần mềm độc hại BadBox 2.0 là một hoạt động tội phạm mạng sử dụng các thiết bị Android Open Source Project (AOSP) bị lây nhiễm, bao gồm TV thông minh, hộp phát trực tuyến và các thiết bị kết nối khác thiếu các biện pháp bảo mật, chẳng hạn như Google Play Protect.

Các thiết bị này bị lây nhiễm hoặc do các tác nhân mối đe dọa mua các thiết bị AOSP giá rẻ, sửa đổi hệ điều hành để bao gồm phần mềm độc hại BadBox 2, và sau đó bán lại trực tuyến, hoặc bằng cách lừa người dùng tải xuống và cài đặt các ứng dụng độc hại trên thiết bị của họ chứa phần mềm độc hại.

Phần mềm độc hại trở thành một cổng sau kết nối với máy chủ chỉ huy và kiểm soát (C2) do các kẻ tấn công điều hành, nơi nó nhận lệnh để thực hiện trên thiết bị.

Một khi đã bị xâm phạm, các thiết bị trở thành một phần của botnet BadBox 2.0, nơi chúng được biến thành các proxy dân cư được bán cho các tội phạm mạng khác mà không có sự biết đến của các nạn nhân hoặc được sử dụng để thực hiện gian lận quảng cáo.

Đơn kiện của Google chủ yếu tập trung vào thành phần gian lận quảng cáo, mà botnet thường thực hiện đối với các nền tảng quảng cáo của công ty.

Gian lận quảng cáo này được thực hiện theo ba cách:

* **Kết xuất quảng cáo ẩn**: Các ứng dụng giả mạo "em sinh đôi độc ác" được cài đặt âm thầm trên các thiết bị bị lây nhiễm để tải quảng cáo ẩn ở nền trên các trang web do kẻ tấn công kiểm soát có quảng cáo Google, tạo ra doanh thu quảng cáo gian lận cho hoạt động.
* **Trang web trò chơi dựa trên web**: Các bot được hướng dẫn để mở trình duyệt web vô hình và chơi các trò chơi bị lừa đảo nhanh chóng kích hoạt lượt xem quảng cáo Google. Mỗi lượt xem quảng cáo tạo ra doanh thu cho các tài khoản nhà xuất bản do kẻ tấn công kiểm soát.
* **Gian lận nhấp chuột quảng cáo tìm kiếm**: Các bot được hướng dẫn thực hiện các truy vấn tìm kiếm trên các trang web do kẻ tấn công điều hành sử dụng AdSense for Search, tạo ra doanh thu quảng cáo từ các quảng cáo hiển thị trong kết quả tìm kiếm được truy xuất.

Vào tháng 12 năm 2024, [botnet BadBox ban đầu đã bị phá vỡ bởi Đức](https://www.bleepingcomputer.com/news/security/germany-blocks-badbox-malware-loaded-on-30-000-android-devices/) sau khi quốc gia này chặn giao tiếp giữa các thiết bị bị lây nhiễm và cơ sở hạ tầng chỉ huy và kiểm soát (C2) bằng cách chặn các truy vấn DNS.

Tuy nhiên, điều đó không ngăn cản hoạt động tội phạm, bởi vì các tác nhân mối đe dọa đã nhanh chóng phát động BadBox 2.0, mà giờ đây được cho là đã [lây nhiễm hơn 10 triệu thiết bị Android](https://www.bleepingcomputer.com/news/security/fbi-badbox-20-android-malware-infects-millions-of-consumer-devices/) tính đến tháng 4 năm 2025\. [Đơn kiện](http://legacy.www.documentcloud.org/documents/26001727-google-badbox2-complaint/) của Google cho biết rằng có hơn 170,000 thiết bị bị lây nhiễm chỉ riêng tại bang New York.

Đơn kiện của Google cho biết họ đã ngừng hàng nghìn tài khoản nhà xuất bản liên kết với hoạt động này, nhưng cảnh báo rằng botnet tiếp tục phát triển và gây ra rủi ro an ninh mạng ngày càng tăng.

"Nếu kế hoạch BadBox 2.0 không bị phá vỡ, nó sẽ tiếp tục sinh sôi," Google cảnh báo.

"Doanh nghiệp BadBox 2.0 sẽ tiếp tục tạo ra doanh thu, sẽ sử dụng số tiền thu được để mở rộng phạm vi, sản xuất các thiết bị mới và phần mềm độc hại mới để thúc đẩy hoạt động tội phạm của mình, và Google sẽ buộc phải tiếp tục tiêu tốn nguồn lực tài chính đáng kể để điều tra và chống lại hoạt động gian lận của Doanh nghiệp."

Bởi vì các bị cáo không rõ danh tính và được cho là cư trú ở Trung Quốc, Google đang theo đuổi bồi thường theo Đạo luật Gian lận và Lạm dụng Máy tính và Đạo luật các tổ chức có ảnh hưởng và tham nhũng (RICO).

Công ty tìm kiếm bồi thường thiệt hại và một lệnh cấm vĩnh viễn để giải tán cơ sở hạ tầng phần mềm độc hại và ngăn chặn việc lây lan thêm của phần mềm độc hại.

Kèm theo đơn kiện là danh sách hơn 100 miền internet là một phần của cơ sở hạ tầng hoạt động tội phạm mạng.