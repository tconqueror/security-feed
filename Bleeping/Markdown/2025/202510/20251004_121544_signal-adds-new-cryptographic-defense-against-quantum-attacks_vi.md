# Signal thêm cơ chế mật mã mới chống lại các cuộc tấn công lượng tử

![Signal thêm cơ chế mật mã mới chống lại các cuộc tấn công lượng tử](https://www.bleepstatic.com/content/hl-images/2025/09/08/Signal.jpg)

Signal announced the introduction of Sparse Post-Quantum Ratchet (SPQR), một thành phần mật mã mới được thiết kế để chống lại các mối đe dọa từ điện toán lượng tử.

SPQR sẽ đóng vai trò như một cơ chế tiên tiến liên tục cập nhật các khóa mã hóa được sử dụng trong các cuộc trò chuyện và loại bỏ các khóa cũ.

Signal là một ứng dụng nhắn tin và gọi điện mã hóa đầu-cuối đa nền tảng do tổ chức phi lợi nhuận Signal Foundation quản lý, với khoảng người dùng hoạt động hàng tháng ước tính lên tới 100 triệu.

Thành phần mới đảm bảo forward secrecy và post-compromise security, đảm bảo rằng ngay cả trong trường hợp khóa bị xâm phạm hoặc đánh cắp, các tin nhắn tương lai trao đổi giữa các bên vẫn sẽ an toàn.

Về mặt mật mã, SPQR sử dụng post-quantum Key-Encapsulation Mechanisms (ML-KEM) thay cho elliptic-curve Diffie-Hellman, và có phân đoạn hiệu quả và erasure coding để xử lý kích thước khóa lớn mà không làm phình băng thông.

Signal đã sử dụng CRYSTALS-Kyber (một post-quantum KEM) cùng với một triển khai của Elliptic Curve Diffie-Hellman [kể từ 2023](https://www.bleepingcomputer.com/news/security/signal-adds-quantum-resistant-encryption-to-its-e2ee-messaging-protocol/) để bảo vệ chống lại các cuộc tấn công điện toán lượng tử có nguy cơ phá vỡ mã hóa hiện tại.

Tuy nhiên, SPQR được đặt bên trên hệ thống double ratchet hiện có, tạo nên cái mà Signal gọi là Triple Ratchet, hình thành một “khóa hỗn hợp” siêu an toàn.

“Khi bạn muốn gửi một tin nhắn, bạn hỏi cả Double Ratchet và SPQR ‘Khoá mã hóa nào tôi nên dùng cho tin nhắn tiếp theo?’ và cả hai sẽ cung cấp cho bạn một khóa,” [đọc thông báo của Signal](https://signal.org/blog/spqr/).

“Thay vì sử dụng trực tiếp một trong hai khóa, cả hai được đưa vào một hàm dẫn xuất khóa – một hàm đặc biệt nhận các đầu vào đủ ngẫu nhiên và tạo ra một khóa mật mã an toàn có độ dài theo nhu cầu của bạn. Điều này cho bạn một ‘khóa hỗn hợp’ mới có bảo mật lai.”

Hệ thống mới được thiết kế phối hợp với PQShield, AIST (Japan), và New York University, với nền tảng kỹ thuật dựa một phần trên các bài báo của USENIX 2025 và Eurocrypt 2025.

Thiết kế cũng đã được xác minh chính thức bằng ProVerif, và tính mạnh mẽ của triển khai Rust đã được kiểm tra bằng công cụ hax. Việc xác minh liên tục sẽ được áp dụng cho tất cả các bản dựng trong tương lai, đảm bảo các bằng chứng được tái tạo với mỗi thay đổi mã.

Signal cho biết việc triển khai SPQR trên nền tảng nhắn tin sẽ diễn ra dần dần, và người dùng không cần thực hiện hành động nào để nâng cấp ngoại trừ việc giữ cho client của họ được cập nhật lên phiên bản mới nhất.

Hệ thống mới sẽ tương thích ngược ở chừng mực khi một client hỗ trợ SPQR giao tiếp với người chưa hỗ trợ công nghệ này, mô hình bảo mật sẽ bị giảm cấp.

Khi SPQR được triển khai cho tất cả client, Signal sẽ bắt buộc sử dụng nó trên tất cả các phiên.