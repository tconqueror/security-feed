# Tiện ích mở rộng Solidity giả cho VSCode trên Open VSX chèn backdoor vào máy nhà phát triển

![Tiện ích mở rộng Solidity giả cho VSCode trên Open VSX chèn backdoor vào máy nhà phát triển](https://www.bleepstatic.com/content/hl-images/2024/08/28/hacker.jpg)

Một trojan truy cập từ xa mang tên SleepyDuck, ngụy trang dưới dạng tiện ích mở rộng Solidity nổi tiếng trong kho mã nguồn mở Open VSX, sử dụng một hợp đồng thông minh Ethereum để thiết lập kênh liên lạc với kẻ tấn công.

Open VSX là một registry do cộng đồng điều hành cho các extension tương thích với VS Code, rất được ưa chuộng ở các môi trường phát triển tích hợp (IDE) hỗ trợ AI như Cursor và Windsurf.

Tiện ích mở rộng vẫn xuất hiện trên Open VSX với tên 'juan-bianco.solidity-vlang', mặc dù có cảnh báo từ nền tảng, và đã được tải xuống hơn 53.000 lần.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Khi lần đầu được gửi lên vào ngày 31 tháng Mười, tiện ích này vô hại và chỉ nhận các khả năng độc hại qua một bản cập nhật vào ngày hôm sau, khi số lượt tải đã đạt 14.000.

Theo một báo cáo từ nền tảng bảo mật extension Secure Annex, một tính năng đáng chú ý trong SleepyDuck là việc sử dụng các hợp đồng Ethereum để cập nhật địa chỉ máy chủ command-and-control (C2) và đạt được khả năng tồn tại lâu dài.

Ngay cả khi máy chủ C2 mặc định tại _sleepyduck[.]xyz_ bị tắt, hợp đồng trên blockchain Ethereum cho phép phần mềm độc hại tiếp tục hoạt động.

Kể từ khi nó được gửi lên Open VSX với phiên bản 0.0.7 và cho đến phiên bản 0.1.3 được xuất bản vào ngày 2 tháng Mười Một, gói _juan-bianco.solidity-vlang_ đã được tải xuống 53.439 lần và chỉ có một đánh giá 5 sao duy nhất từ tác giả của nó.

![Malicious package on Open VSX](https://www.bleepstatic.com/images/news/u/1100723/FakeSolidity_OpenVSX.jpg)

**Gói độc hại trên Open VSX**  
_Nguồn: BleepingComputer_

Cần lưu ý rằng author of the malic

Mã độc được kích hoạt khi trình soạn thảo khởi động, khi một tệp Solidity được mở, hoặc khi người dùng chạy lệnh biên dịch Solidity.

Khi kích hoạt, nó tạo một tệp khóa để chỉ chạy một lần trên mỗi host và gọi một hàm giả ‘webpack.init()’ từ ‘extension.js’ để trông giống hợp pháp, nhưng thực tế nó tải một payload độc hại.

**Tệp webpack giả**  
_Nguồn: Secure Annex_

Theo Secure Annex, thành phần độc hại trong SleepyDuck thu thập dữ liệu hệ thống (hostname, username, MAC address và timezone) và thiết lập một sandbox thực thi lệnh.

Các nhà nghiên cứu cho biết rằng khi khởi tạo, phần mềm độc hại tìm nhà cung cấp Ethereum RPC nhanh nhất để đọc hợp đồng thông minh chứa thông tin C2, khởi động một instance sleepyduck, cập nhật với cấu hình hợp lệ hiện tại, và bắt đầu một vòng lặp polling.

Blockchain Ethereum được dùng cho độ dư thừa C2, vì vậy nếu máy chủ lệnh chính bị ngắt, phần mềm độc hại sẽ đọc các chỉ dẫn cập nhật trực tiếp từ blockchain, bao gồm địa chỉ máy chủ C2 mới hoặc các khoảng thời gian liên lạc được điều chỉnh.

**Hợp đồng thông minh được SleepyDuck sử dụng**  
_Nguồn: Secure Anex_

Các nhà nghiên cứu cũng cho biết hàm polling sẽ gửi dữ liệu về hệ thống dưới dạng một yêu cầu POST và kiểm tra "một lệnh để thực thi từ phản hồi."

Sự phổ biến ngày càng tăng của Open VSX đã đặt nền tảng này vào tầm ngắm của kẻ tấn công, nhận được nhiều submission độc hại nhắm vào các nhà phát triển không đề phòng.

Gần đây, nền tảng đã thông báo một loạt cải tiến bảo mật để làm cho nó an toàn hơn cho người dùng, bao gồm rút ngắn thời hạn token, thu hồi nhanh các thông tin đăng nhập bị rò rỉ, quét tự động và chia sẻ thông tin quan trọng với VS Code về các mối đe dọa mới xuất hiện.

Các nhà phát triển phần mềm nên thận trọng khi tải xuống các extension cho VS Code, chỉ tin tưởng các nhà phát hành có uy tín và các kho lưu trữ chính thức của họ.