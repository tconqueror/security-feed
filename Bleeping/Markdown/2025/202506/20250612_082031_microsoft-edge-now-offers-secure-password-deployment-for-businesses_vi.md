# Microsoft Edge hiện cung cấp triển khai mật khẩu an toàn cho doanh nghiệp

![Microsoft Edge](https://www.bleepstatic.com/content/hl-images/2025/06/12/Microsoft-Edge.jpg)

Microsoft đã thông báo rằng một tính năng mới của Edge cho phép nhân viên chia sẻ mật khẩu an toàn hơn trong môi trường doanh nghiệp đã có sẵn cho mọi đối tượng sử dụng.

Được biết đến với tên gọi triển khai mật khẩu an toàn, tính năng này sẽ có sẵn cho người dùng Microsoft Edge for Business bắt đầu từ tuần này, giảm thiểu rủi ro truy cập trái phép bằng cách đảm bảo rằng nhân viên không vô tình chia sẻ mật khẩu với những người nhận không mong muốn.

Tính năng này có sẵn cho các gói Microsoft 365 Business Premium, E3 và E5 và yêu cầu vai trò quản trị Edge hoặc quản trị toàn cầu.

"Nhiều tổ chức hiện nay, nhân viên thường chia sẻ mật khẩu qua giấy ghi chú hoặc email. Điều này không chỉ phơi bày thông tin đăng nhập nhạy cảm với những người nhận không mong muốn, mà còn làm tăng rủi ro cho việc những mật khẩu này bị chuyển tiếp hoặc lạm dụng," [Microsoft cho biết](https://blogs.windows.com/msedgedev/2025/06/11/introducing-secure-password-deployment-in-microsoft-edge-for-business/).

"Triển khai mật khẩu an toàn cho phép các quản trị viên triển khai mật khẩu được mã hóa chia sẻ cho một nhóm người dùng trong tổ chức của họ. Với tính năng này, người dùng sẽ nhận được mật khẩu đã được triển khai trên thiết bị của họ và có thể đăng nhập một cách dễ dàng vào các trang web."

Triển khai mật khẩu an toàn là một phần của dịch vụ quản lý Microsoft Edge trong trung tâm quản trị Microsoft 365, cho phép các quản trị viên cấu hình cài đặt trình duyệt bằng cách sử dụng các chính sách để triển khai mật khẩu được mã hóa cho các nhóm người dùng cụ thể.

![Triển khai mật khẩu an toàn trong trung tâm quản trị M365](https://www.bleepstatic.com/images/news/u/1109292/2025/M365-admin-center-secure-password-deployment.jpg)

_Triển khai mật khẩu an toàn trong trung tâm quản trị M365 (Microsoft)_

Tính năng này mở rộng trải nghiệm Autofill tích hợp sẵn với giao diện trực quan cho phép các quản trị viên thêm, cập nhật và thu hồi thông tin đăng nhập.

Khi đã được triển khai bởi các quản trị viên, các mật khẩu sẽ tự động xuất hiện trong hồ sơ làm việc Edge của người dùng trên các thiết bị Windows được quản lý, sẵn sàng cho việc tự động điền vào các trang web tương ứng và cho phép trải nghiệm đăng nhập an toàn.

Mặc dù có thể truy cập được trong Edge, nhưng những mật khẩu này không thể được xem, chỉnh sửa, xóa (trừ khi được phép bởi trang web), hoặc xuất từ trình quản lý mật khẩu.

Trong khi vẫn còn các cách để truy cập vào các mật khẩu bằng cách sử dụng công cụ phát triển của trình duyệt web, các quản trị viên có thể hạn chế quyền truy cập vào chúng bằng cách sử dụng [chính sách DeveloperToolsAvailability](https://learn.microsoft.com/deployedge/microsoft-edge-browser-policies/developertoolsavailability).

![Trình quản lý mật khẩu Edge](https://www.bleepstatic.com/images/news/u/1109292/2025/Edge_password_manager.jpg)

_Trình quản lý mật khẩu Edge (Microsoft)_

Các mật khẩu được mã hóa bằng Microsoft Information Protection SDK, và việc mã hóa này được liên kết với các danh tính Entra, đảm bảo rằng quyền truy cập được tự động thi hành dựa trên các chính sách tổ chức mà không cần quản lý khóa thủ công.

"Sự tích hợp này mang sức mạnh của nền tảng bảo vệ dữ liệu của Microsoft trực tiếp vào trải nghiệm Quản lý Edge, mang lại cho các quản trị viên một cách tiếp cận liền mạch để triển khai các thông tin đăng nhập một cách an toàn đồng thời phù hợp với các nguyên tắc Zero Trust và yêu cầu tuân thủ," Microsoft bổ sung.

"Bằng cách nhúng Protection SDK trực tiếp vào Edge for Business, chúng tôi mở rộng khả năng bảo vệ dữ liệu của Microsoft đến tận điểm cuối—đảm bảo rằng thông tin nhạy cảm được bảo vệ từ cấu hình đến tiêu thụ."

Để bắt đầu sử dụng triển khai mật khẩu an toàn, các quản trị viên trước tiên phải truy cập dịch vụ [quản lý Edge](https://admin.microsoft.com/#/Edge/Overview) trong trung tâm quản trị Microsoft 365 và sau đó chọn một chính sách cấu hình hiện có hoặc tạo một chính sách mới.