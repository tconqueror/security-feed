# Tiện ích mở rộng độc hại trong Cursor IDE đã dẫn đến việc đánh cắp 500.000 USD tiền điện tử

![Cursor](https://www.bleepstatic.com/content/hl-images/2025/07/13/cursor-header.jpg)

Một tiện ích mở rộng giả cho trình biên tập mã Cursor AI IDE đã lây nhiễm các thiết bị bằng các công cụ truy cập từ xa và infostealers, dẫn đến một trường hợp đánh cắp 500.000 USD tiền điện tử từ một nhà phát triển tiền điện tử Nga.

Cursor AI IDE là một môi trường phát triển dựa trên trí tuệ nhân tạo được xây dựng trên Visual Studio Code của Microsoft. Nó bao gồm hỗ trợ cho Open VSX, một lựa chọn thay thế cho Visual Studio Marketplace, cho phép bạn cài đặt các tiện ích mở rộng tương thích với VSCode để mở rộng khả năng của phần mềm.

Kaspersky [báo cáo](https://securelist.com/open-source-package-for-cursor-ai-turned-into-a-crypto-heist/116908/) rằng họ đã được gọi để điều tra một sự cố an ninh mà một nhà phát triển Nga làm trong lĩnh vực tiền điện tử đã báo cáo rằng 500.000 USD trong tiền điện tử đã bị đánh cắp từ máy tính của anh ta. Máy tính không có phần mềm diệt virus cài đặt, nhưng được cho là sạch sẽ.

Georgy Kucherin, một nhà nghiên cứu an ninh của Kaspersky, nhận được một hình ảnh của ổ cứng của thiết bị và sau khi phân tích, đã phát hiện ra một tệp JavaScript độc hại có tên extension.js nằm trong thư mục .cursor/extensions.

Tiện ích mở rộng này có tên là "Solidity Language" và được xuất bản trên kho Open VSX, tuyên bố là công cụ làm nổi bật cú pháp cho việc làm việc với các hợp đồng thông minh Ethereum.

Mặc dù plugin này mạo danh tiện ích mở rộng làm nổi bật cú pháp [Solidity hợp pháp](https://open-vsx.org/extension/juanblanco/solidity), nhưng thực sự nó đã thực thi một tập lệnh PowerShell từ một máy chủ xa tại angelic\[.\]su để tải xuống các payload độc hại bổ sung.

![Tệp Extension.js thực thi tập lệnh PowerShell từ xa](https://www.bleepstatic.com/images/news/security/c/cursor/malicious-solidity-extension/extension-js-powershell.jpg)

**Tệp Extension.js thực thi tập lệnh PowerShell từ xa**  
_Nguồn: Kaspersky_

Tập lệnh PowerShell từ xa đã kiểm tra xem công cụ quản lý từ xa ScreenConnect đã được cài đặt hay chưa, và nếu chưa, đã thực thi một tập lệnh khác để cài đặt nó.

Khi ScreenConnect được cài đặt, các tác nhân đe dọa đã có quyền truy cập từ xa hoàn toàn vào máy tính của nhà phát triển. Sử dụng ScreenConnect, tác nhân đe dọa đã tải lên và thực thi các tệp VBScript được sử dụng để tải xuống các payload bổ sung cho thiết bị.

Tập lệnh cuối cùng trong cuộc tấn công đã tải xuống một tệp thực thi độc hại từ archive\[.\]org chứa một bộ tải được gọi là VMDetector, bộ tải này đã cài đặt:

* **Quasar RAT:** Một trojan truy cập từ xa có khả năng thực thi các lệnh trên các thiết bị.
* **PureLogs stealer:** Một phần mềm đánh cắp thông tin lấy cắp thông tin đăng nhập và cookie xác thực từ các trình duyệt web, cũng như lấy cắp ví tiền điện tử.

Theo Kaspersky, Open VSX cho thấy rằng tiện ích mở rộng này đã được tải xuống 54.000 lần trước khi bị gỡ bỏ vào ngày 2 tháng 7. Tuy nhiên, các nhà nghiên cứu tin rằng con số cài đặt này đã bị thổi phồng artificially để tạo ấn tượng hợp pháp.

Một ngày sau, các kẻ tấn công đã phát hành một phiên bản gần giống dưới tên "solidity", làm tăng số lượng cài đặt cho tiện ích mở rộng này lên gần hai triệu.

![Số lượng tải xuống bị thổi phồng cho các tiện ích mở rộng độc hại](https://www.bleepstatic.com/images/news/security/c/cursor/malicious-solidity-extension/malicious-solidity-language-extension.jpg)

**Số lượng tải xuống bị thổi phồng cho các tiện ích mở rộng độc hại**  
_Nguồn: Kaspersky_

Kaspersky cho biết các tác nhân đe dọa đã có thể xếp hạng tiện ích mở rộng của họ cao hơn tiện ích hợp pháp trong kết quả tìm kiếm Open VSX bằng cách lừa đảo thuật toán và thông qua số lượng cài đặt bị thổi phồng. Điều này khiến nạn nhân cài đặt tiện ích mở rộng độc hại, tưởng rằng đó là tiện ích hợp pháp.

Các nhà nghiên cứu đã tìm thấy các tiện ích mở rộng tương tự được xuất bản vào kho thị trường Visual Studio Code của Microsoft có tên "solaibot", "among-eth" và "blankebesxstnion", cũng thực thi một tập lệnh PowerShell để cài đặt ScreenConnect và infostealers.

Kaspersky cảnh báo rằng các nhà phát triển nên cẩn trọng khi tải xuống các gói và tiện ích mở rộng từ các kho mở vì chúng đã trở thành một nguồn lây nhiễm malware phổ biến.

"Các gói độc hại vẫn tiếp tục đặt ra một mối đe dọa đáng kể đối với ngành công nghiệp tiền điện tử. Nhiều dự án ngày nay phụ thuộc vào các công cụ mã nguồn mở tải xuống từ các kho gói," Kaspersky kết luận.

"Đáng tiếc, các gói từ những kho này thường là nguồn lây nhiễm malware. Do đó, chúng tôi khuyên bạn nên cực kỳ thận trọng khi tải xuống bất kỳ công cụ nào. Luôn luôn xác minh rằng gói mà bạn đang tải xuống không phải là giả."

"Nếu một gói không hoạt động như đã quảng cáo sau khi bạn cài đặt, hãy nghi ngờ và kiểm tra mã nguồn đã tải xuống."