# PhantomRaven tấn công làm ngập npm bằng các gói đánh cắp thông tin đăng nhập

![PhantomRaven tấn công làm ngập npm bằng các gói đánh cắp thông tin đăng nhập](https://www.bleepstatic.com/content/hl-images/2025/10/29/package-container.jpg)

Một chiến dịch đang hoạt động có tên ‘PhantomRaven’ đang nhắm vào các nhà phát triển bằng hàng chục gói npm độc hại, đánh cắp token xác thực, bí mật CI/CD và thông tin đăng nhập GitHub.

Hoạt động bắt đầu vào tháng Tám và đã triển khai 126 gói npm với hơn 86,000 lượt tải xuống.

Node Package Manager (NPM) là trình quản lý gói mặc định cho Node.js, được các nhà phát triển JavaScript sử dụng để chia sẻ và cài đặt mã có thể tái sử dụng dưới dạng các gói phân phối.

PhantomRaven được các nhà nghiên cứu tại [Koi Security](https://www.koi.ai/blog/phantomraven-npm-malware-hidden-in-invisible-dependencies) phát hiện và bao gồm các gói giả mạo dự án hợp pháp, nhiều gói trong số này là kết quả của các đề xuất do AI ảo tưởng tạo ra (“slopsquatting”).

Slopsquatting xảy ra khi các nhà phát triển yêu cầu LLMs đề xuất gói cho một dự án, và trợ lý AI khuyến nghị các tên gói không tồn tại nhưng trông hợp pháp.

Các nhà nghiên cứu cho biết một số gói độc hại mạo danh công cụ của GitLab hoặc Apache. Phần lớn vẫn còn trên nền tảng npm tại thời điểm viết bài.

## Tổng quan về cuộc tấn công

Các gói được sử dụng trong chiến dịch PhantomRaven lợi dụng một hệ thống remote dynamic dependencies (RDD) nơi chúng khai báo không có phụ thuộc nào, nhưng tự động tải payload từ các URL bên ngoài trong quá trình cài đặt.

![Mã khai báo không có phụ thuộc](https://www.bleepstatic.com/images/news/u/1220909/2025/October/dependency.jpg)

**Mã khai báo không có phụ thuộc**  
_Nguồn: Koi Security_

Cơ chế này tải các gói và thực thi chúng tự động khi chạy ‘npm install’, và không yêu cầu tương tác của người dùng.

Payload “side-loaded” thu thập hồ sơ thiết bị bị nhiễm để xác định mức độ giá trị của mục tiêu, và tìm kiếm địa chỉ email trong các biến môi trường của nạn nhân.

![Tìm kiếm địa chỉ email của nạn nhân](https://www.bleepstatic.com/images/news/u/1220909/2025/October/email(2).jpg)

**Tìm kiếm địa chỉ email của nạn nhân**  
_Nguồn: Koi Security_

Điều đáng lo ngại nhất, phần mềm độc hại thu thập token cho NPM, GitHub Actions, GitLab, Jenkins và CircleCI, có thể được sử dụng để đưa các thay đổi độc hại vào các dự án khác và có khả năng phát động các cuộc tấn công chuỗi cung ứng.

**Các bí mật bị nhắm mục tiêu trong môi trường bị xâm phạm**  
_Nguồn: Koi Security_

Theo Koi Security, các kẻ điều hành phía sau chiến dịch PhantomRaven sử dụng ba phương thức chiết xuất dữ liệu: HTTP GET requests với dữ liệu được mã hóa trong URL, HTTP POST requests với dữ liệu JSON, và thông qua kết nối WebSocket.

PhantomRaven đã né tránh phát hiện trong một thời gian dài nhờ remote dynamic dependencies, vốn không hiển thị qua phân tích tĩnh. Koi Security lưu ý rằng điều này cho phép các tác nhân mối đe dọa tinh vi tránh bị phát hiện.

Các nhà phát triển phần mềm nên đảm bảo rằng họ đang sử dụng các gói hợp pháp được xuất bản bởi các nhà cung cấp uy tín. Họ nên tránh tham khảo LLMs để gợi ý gói và kiểm tra kỹ kết quả tìm kiếm để phân biệt giữa các dự án chính thức và các dự án bị typosquatting.

Báo cáo của Koi Security bao gồm các chỉ số thỏa hiệp (IoCs) cho hạ tầng được sử dụng trong các cuộc tấn công PhantomRaven và danh sách đầy đủ các gói độc hại.