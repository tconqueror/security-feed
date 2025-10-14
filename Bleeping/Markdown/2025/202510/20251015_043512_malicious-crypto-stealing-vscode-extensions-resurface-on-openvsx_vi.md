# Tiện ích mở rộng VSCode độc hại đánh cắp tiền mã hóa tái xuất trên OpenVSX

![Tiện ích mở rộng VSCode độc hại đánh cắp tiền mã hóa tái xuất trên OpenVSX](https://www.bleepstatic.com/content/hl-images/2023/08/04/package-container.jpg)

Một tác nhân đe dọa có tên TigerJack liên tục nhắm mục tiêu vào các nhà phát triển bằng các tiện ích mở rộng độc hại được xuất bản trên marketplace Visual Code (VSCode) của Microsoft và registry OpenVSX để đánh cắp tiền mã hóa và cấy backdoor.

Hai trong số các tiện ích mở rộng đó, bị gỡ khỏi VSCode sau khi đạt 17.000 lượt tải, vẫn còn xuất hiện trên OpenVSX. Hơn nữa, TigerJack còn tái xuất bản cùng mã độc dưới các tên mới trên marketplace VSCode.

OpenVSX là một marketplace tiện ích mở rộng mã nguồn mở do cộng đồng duy trì, hoạt động như một lựa chọn thay thế cho nền tảng của Microsoft, cung cấp một registry độc lập, trung lập với nhà cung cấp.

Nó cũng là marketplace mặc định cho các trình soạn thảo tương thích VSCode phổ biến bị hạn chế về kỹ thuật hoặc pháp lý so với VSCode, bao gồm [Cursor](https://www.bleepingcomputer.com/news/security/malicious-vscode-extension-in-cursor-ide-led-to-500k-crypto-theft/) và Windsurf.

Chiến dịch này được phát hiện bởi các nhà nghiên cứu tại Koi Security và đã phân phối ít nhất 11 tiện ích mở rộng VSCode độc hại kể từ đầu năm.

Hai trong số các tiện ích bị loại khỏi marketplace VSCode có tên _C++ Playground_ và _HTTP Format_, và đã được đưa trở lại nền tảng thông qua các tài khoản mới, theo các nhà nghiên cứu.

Khi khởi chạy, C++ Playground đăng ký một listener (‘onDidChangeTextDocument’) cho các tệp C++ để gửi trộm mã nguồn đến nhiều điểm cuối bên ngoài. Listener này được kích hoạt khoảng 500 mili-giây sau khi chỉnh sửa để bắt ký tự gần như theo thời gian thực.

Theo Koi Security, HTTP Format hoạt động như quảng cáo nhưng lén chạy một trình khai thác CoinIMP ở chế độ nền, sử dụng thông tin đăng nhập và cấu hình được mã hóa cứng để đào tiền mã hóa bằng sức mạnh xử lý của máy chủ.

Trình khai thác dường như không thực hiện bất kỳ hạn chế nào về việc sử dụng tài nguyên, tận dụng toàn bộ sức mạnh tính toán cho hoạt động của nó.

![Miner active on the host](https://www.bleepstatic.com/images/news/u/1220909/2025/October/cpu.jpg)

**Trình khai thác hoạt động trên máy chủ**  
_Source: Koi Security_

Một loại khác của các tiện ích mở rộng độc hại từ TigerJack (_cppplayground_, _httpformat_, và _pythonformat_) lấy mã JavaScript từ một địa chỉ cố định được gán trong mã và thực thi nó trên máy chủ.

Địa chỉ từ xa (ab498.pythonanywhere.com/static/in4.js) được polling mỗi 20 phút, cho phép thực thi mã tùy ý mà không cần cập nhật tiện ích mở rộng.

![Malicious function](https://www.bleepstatic.com/images/news/u/1220909/2025/October/function.jpg)

**Chức năng độc hại**  
_Source: Koi Security_

Các nhà nghiên cứu bình luận rằng, khác với kẻ đánh cắp mã nguồn và trình khai thác tiền mã hóa, loại thứ ba này nguy hiểm hơn nhiều, vì chúng có chức năng mở rộng.

“TigerJack có thể đẩy bất kỳ payload độc hại nào một cách động mà không cần cập nhật tiện ích mở rộng — đánh cắp thông tin đăng nhập và khóa API, triển khai ransomware, sử dụng máy phát triển bị xâm phạm làm điểm vào mạng doanh nghiệp, chèn backdoor vào dự án của bạn, hoặc giám sát hoạt động của bạn theo thời gian thực.” – Koi Security

**Tiện ích độc hại bị gỡ khỏi VSCode (bên trái) nhưng vẫn có trên OpenVSX (bên phải)**  
_Source: Koi Security_

Các nhà nghiên cứu cho biết TigerJack là “một hoạt động đa tài khoản có phối hợp” ngụy trang dưới ảo giác của các nhà phát triển độc lập với hồ sơ đáng tin cậy như các repository trên GitHub, thương hiệu, danh sách tính năng chi tiết, và tên tiện ích giống với các công cụ hợp pháp.

Koi Security đã báo cáo phát hiện của họ cho OpenVSX, nhưng người duy trì registry chưa phản hồi tính đến thời điểm xuất bản và hai tiện ích đó vẫn có thể tải xuống.

Các nhà phát triển sử dụng nền tảng để lấy phần mềm được khuyến nghị chỉ tải xuống các gói từ các nhà xuất bản đáng tin cậy và có uy tín.