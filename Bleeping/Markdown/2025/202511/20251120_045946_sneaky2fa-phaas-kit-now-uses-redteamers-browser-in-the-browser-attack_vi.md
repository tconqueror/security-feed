# Bộ công cụ Sneaky2FA PhaaS giờ sử dụng kỹ thuật Browser-in-the-Browser của redteamers

![Bộ công cụ Sneaky2FA PhaaS giờ sử dụng kỹ thuật Browser-in-the-Browser của redteamers](https://www.bleepstatic.com/content/hl-images/2022/08/23/phishing-hook.jpg)

Bộ kit lừa đảo phishing-as-a-service (PhaaS) Sneaky2FA đã thêm khả năng browser-in-the-browser (BitB) được sử dụng trong các cuộc tấn công để đánh cắp thông tin đăng nhập Microsoft và các phiên hoạt động.

Sneaky2FA là một nền tảng PhaaS được sử dụng rộng rãi hiện nay, cùng với Tycoon2FA và Mamba2FA, tất cả đều chủ yếu nhắm vào tài khoản Microsoft 365.

Bộ kit này đã nổi tiếng với các cuộc tấn công dựa trên SVG và các chiến thuật attacker-in-the-middle (AitM), nơi quá trình xác thực được proxy tới dịch vụ hợp pháp thông qua một trang lừa đảo chuyển tiếp các token phiên hợp lệ cho kẻ tấn công.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Theo một báo cáo từ Push Security, Sneaky2FA hiện đã thêm một cửa sổ bật lên BitB bắt chước cửa sổ đăng nhập Microsoft hợp pháp. Để tăng tính lừa đảo, trang đăng nhập giả điều chỉnh động theo hệ điều hành và trình duyệt của nạn nhân.

Kẻ tấn công đánh cắp thông tin đăng nhập và token phiên hoạt động có thể xác thực vào tài khoản của nạn nhân, ngay cả khi bảo vệ xác thực hai yếu tố (2FA) đang kích hoạt.

BitB là một kỹ thuật lừa đảo do nhà nghiên cứu mr.d0x phát triển vào năm 2022 và kể từ đó đã được các tác nhân đe dọa áp dụng trong các cuộc tấn công thực tế nhắm vào Facebook và Steam accounts, cùng các dịch vụ khác.

Trong cuộc tấn công, người dùng truy cập một trang web do kẻ tấn công kiểm soát sẽ thấy một cửa sổ pop-up trình duyệt giả với biểu mẫu đăng nhập.

Mẫu cho cửa sổ bật lên là một iframe mô phỏng biểu mẫu xác thực của các dịch vụ hợp lệ và có thể được tùy chỉnh với URL và tiêu đề cửa sổ cụ thể.

Bởi vì cửa sổ giả hiển thị thanh địa chỉ URL với tên miền chính thức của dịch vụ mục tiêu, nó trông giống như một cửa sổ OAuth đáng tin cậy.

Trong trường hợp của Sneaky2FA, nạn nhân mở một liên kết lừa đảo trên ‘_previewdoc[.]com_’ và phải vượt qua kiểm tra bot Cloudflare Turnstile trước khi họ được yêu cầu đăng nhập bằng Microsoft để xem một tài liệu.

![Lời nhắc lừa đảo dẫn tới phishing](https://www.bleepstatic.com/images/news/u/1220909/2025/November/adobe.jpg)

**Lời nhắc lừa đảo dẫn tới phishing**  
_Nguồn: Push Security_

Nếu chọn tùy chọn “Sign in with Microsoft”, cửa sổ BitB giả sẽ được hiển thị, có thanh địa chỉ Microsoft giả, được thay đổi kích thước và định dạng phù hợp cho Edge trên Windows hoặc Safari trên macOS.

Bên trong cửa sổ giả, Sneaky2FA tải trang phishing Microsoft bằng reverse-proxy của mình, vì vậy nó lợi dụng luồng đăng nhập thực tế để đánh cắp cả thông tin đăng nhập tài khoản và token phiên thông qua hệ thống AitM của nó.

**Cửa sổ giả**  
_Nguồn: Push Security_

Về cơ bản, BitB được sử dụng như một lớp lừa thị giác trên đỉnh các khả năng AitM hiện có của Sneaky2FA, tăng thêm tính chân thực cho chuỗi tấn công.

Bộ kit lừa đảo này cũng sử dụng cơ chế tải có điều kiện, gửi bot và các nhà nghiên cứu đến một trang an toàn.

Push Security báo cáo rằng những trang phishing này được thiết kế với mục tiêu né tránh, và chúng có khả năng không kích hoạt cảnh báo khi được truy cập.

“HTML và JavaScript của các trang Sneaky2FA bị obfuscate nặng để né tránh việc phát hiện tĩnh và so khớp mẫu, chẳng hạn như chia nhỏ văn bản giao diện người dùng bằng các thẻ vô hình, nhúng nền và các phần tử giao diện dưới dạng hình ảnh đã được mã hóa thay vì văn bản, và các thay đổi khác mà người dùng không nhìn thấy, nhưng khiến các công cụ quét khó nhận diện trang,” các nhà nghiên cứu giải thích.

Một cách để xác định liệu một biểu mẫu đăng nhập bật lên có xác thực hay không là thử kéo nó ra ngoài cửa sổ trình duyệt gốc. Điều này không thể thực hiện được với một iframe vì nó liên kết với cửa sổ cha của nó.

Ngoài ra, một cửa sổ bật lên hợp pháp xuất hiện trên thanh tác vụ như một phiên bản trình duyệt riêng biệt.

Hỗ trợ cho BitB đã được thấy với một dịch vụ PhaaS khác có tên Raccoon0365/Storm-2246, dịch vụ này đã bị gián đoạn gần đây bởi Microsoft và Cloudflare sau khi nó đánh cắp hàng nghìn thông tin đăng nhập Microsoft 365.