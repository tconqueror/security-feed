# PyPI vô hiệu hóa các token bị đánh cắp trong cuộc tấn công chuỗi cung ứng GhostAction

![PyPi](https://www.bleepstatic.com/content/hl-images/2025/09/18/PyPi.jpg)

Nhóm Python Software Foundation đã vô hiệu hóa tất cả các token PyPI bị đánh cắp trong cuộc tấn công chuỗi cung ứng GhostAction vào đầu tháng Chín, xác nhận rằng các tác nhân đe dọa không lợi dụng chúng để phát hành phần mềm độc hại.

Những token này được sử dụng để phát hành gói trên Python Package Index (PyPI), một kho phần mềm đóng vai trò là nguồn mặc định cho các công cụ quản lý gói của Python và lưu trữ hàng trăm nghìn gói.

Như PyPI admin Mike Fiedler giải thích, một nhân viên GitGuardian đã báo cáo vào ngày 5 tháng 9 rằng các workflow GitHub Actions độc hại (như FastUUID) đã cố gắng rút cắp token PyPI tới một máy chủ từ xa. Một nhà nghiên cứu khác của GitGuardian đã gửi email cho PyPI Security với các phát hiện bổ sung cùng ngày, nhưng thông điệp của họ đã vào thư mục spam, làm chậm phản ứng sự cố cho đến ngày 10 tháng 9.

Ngay khi phát hiện toàn bộ quy mô của cuộc tấn công chuỗi cung ứng, GitGuardian đã mở các issue trên GitHub trong hơn 570 kho lưu trữ bị ảnh hưởng và thông báo cho các nhóm an ninh của GitHub, npm và PyPI.

Nhiều người duy trì dự án đã xoay vòng các token PyPI của họ, hoàn tác các thay đổi trong workflow actions, hoặc loại bỏ các workflow bị ảnh hưởng sau khi được GitGuardian thông báo về sự cố. Trong khi nhóm PyPI không tìm thấy bằng chứng về các kho PyPI bị xâm phạm trong quá trình điều tra, họ đã vô hiệu hóa tất cả các token phát hành bị ảnh hưởng và liên hệ với chủ sở hữu dự án để hỗ trợ bảo đảm tài khoản của họ.

Tuy nhiên, GitGuardian ước tính vào thời điểm đó rằng [over 3,3000 secrets were stolen](https://www.bleepingcomputer.com/news/security/hackers-steal-3-325-secrets-in-ghostaction-github-supply-chain-attack/) trong chiến dịch GhostAction, bao gồm token PyPI, npm, DockerHub, GitHub, và Cloudflare API, cũng như khóa truy cập AWS và thông tin đăng nhập cơ sở dữ liệu.

"Phân tích này tiết lộ các token bị xâm phạm trên nhiều hệ sinh thái gói khác nhau, bao gồm Rust crates và npm packages," GitGuardian cho biết. "Một số công ty được phát hiện đã có toàn bộ danh mục SDK của họ bị xâm phạm, với các workflow độc hại ảnh hưởng đồng thời tới các kho mã Python, Rust, JavaScript và Go của họ."

![Secrets compromised in the GhostAction campaign](https://www.bleepstatic.com/images/news/u/1220909/2025/September/secrets.jpg)

_Secrets compromised in the GhostAction campaign (GitGuardian)_

Vào thứ Ba, Fiedler khuyên những người duy trì gói PyPI sử dụng GitHub Actions nên thay thế các token tồn tại lâu bằng các token Trusted Publishers ngắn hạn, điều này sẽ phòng thủ chống lại loại tấn công này. Fiedler cũng thúc giục họ [đăng nhập vào tài khoản của họ](https://pypi.org/manage/account/) và xem lại [lịch sử bảo mật của họ](https://pypi.org/manage/account/#account-events) để tìm bất kỳ hoạt động đáng ngờ nào.

"Sau khi xác nhận rằng không có tài khoản PyPI nào bị xâm phạm, vào ngày 15 tháng 9 tôi đã liên hệ với những người duy trì các dự án bị ảnh hưởng để thông báo cho họ về tình huống, cho họ biết rằng các token của họ đã bị vô hiệu hóa, và khuyến nghị sử dụng Trusted Publishers với GitHub Actions để giúp bảo vệ các dự án của họ trong tương lai," [Fiedler said](https://blog.pypi.org/posts/2025-09-16-github-actions-token-exfiltration/).

"Kẻ tấn công đã nhắm tới nhiều loại kho lưu trữ, nhiều trong số đó có token PyPI được lưu trữ như GitHub secrets, sửa đổi workflow của họ để gửi các token đó tới các máy chủ bên ngoài. Mặc dù kẻ tấn công đã rút cắp thành công một số token, dường như họ không sử dụng chúng trên PyPI."

Vào tháng Tám, kẻ tấn công đã lợi dụng một workflow GitHub Actions có lỗi được sử dụng bởi kho Nx (một hệ thống build và công cụ quản lý monorepo rất phổ biến) như một phần của một cuộc tấn công chuỗi cung ứng khác (được gọi là s1ngularity), vốn ảnh hưởng tới 2.180 tài khoản và 7.200 kho lưu trữ.

Một tháng trước đó, Python Software Foundation cũng cảnh báo người dùng rằng một chiến dịch lừa đảo đang cố gắng đánh cắp thông tin đăng nhập của họ bằng cách sử dụng một trang web giả Python Package Index (PyPI).