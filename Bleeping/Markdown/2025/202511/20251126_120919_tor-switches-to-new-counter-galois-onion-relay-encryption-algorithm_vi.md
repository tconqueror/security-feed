# Tor chuyển sang thuật toán mã hóa relay Counter Galois Onion mới

![Tor chuyển sang thuật toán mã hóa relay Counter Galois Onion mới](https://www.bleepstatic.com/content/hl-images/2024/09/19/tor-logo.jpg)

Tor đã công bố cải thiện mã hóa và bảo mật cho lưu lượng mạch (circuit traffic) bằng cách thay thế thuật toán mã hóa relay tor1 cũ bằng một thiết kế mới có tên Counter Galois Onion (CGO).

Một lý do đằng sau quyết định này là nhằm làm cho mạng [more resilient](https://blog.torproject.org/introducing-cgo/) trước các cuộc tấn công chặn lưu lượng hiện đại có thể làm suy yếu bảo mật dữ liệu và phá hoại ẩn danh người dùng Tor.

Mạng Tor là một hệ thống toàn cầu gồm hàng nghìn relay tạo ra một mạch để các gói dữ liệu đi đến đích thông qua ba relay (entry, middle, và exit), mỗi nhảy thêm một lớp mã hóa (onion routing).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Người dùng Tor Browser, một phiên bản được gia cố của Firefox được xây dựng để duyệt mạng Tor, hưởng lợi từ onion routing này để giao tiếp riêng tư, chia sẻ hoặc truy cập thông tin ẩn danh, vượt kiểm duyệt, và tránh việc theo dõi ở cấp ISP.

Thông thường, Tor được sử dụng bởi những người bất đồng chính kiến, nhà hoạt động, người tố giác, nhà báo, nhà nghiên cứu, và nói chung là những người quan tâm đến quyền riêng tư, bao gồm cả tội phạm mạng tìm cách truy cập các chợ darknet.

Như Tor team giải thích trong một thông báo, tor1 được phát triển vào thời điểm mà mật mã học còn kém phát triển hơn ngày nay, và các tiêu chuẩn đã được cải thiện đáng kể kể từ đó.

Một vấn đề với thiết kế tor1 là nó sử dụng AES-CTR encryption mà không có xác thực từng chặng (hop-by-hop authentication), dẫn tới mã hóa relay có thể bị biến đổi (malleable). Điều này có nghĩa là kẻ thù có thể chỉnh sửa lưu lượng giữa các relay mà chúng kiểm soát và quan sát các thay đổi có thể dự đoán được — một cuộc tấn công gắn thẻ (tagging attack) thuộc lớp [internal covert channel](https://spec.torproject.org/proposals/344-protocol-info-leaks.html#11-highly-severe-internal-covert-channel-vectors) của các cuộc tấn công.

Một vấn đề khác là tor1 sử dụng partial forward secrecy bằng cách tái sử dụng cùng các khóa AES trong suốt vòng đời của một mạch, cho phép giải mã nếu khóa bị đánh cắp.

Mối quan ngại bảo mật thứ ba là tor1 sử dụng digest SHA-1 4-byte cho xác thực cell, khiến kẻ tấn công có xác suất một trên 4 tỷ để giả mạo một cell mà không bị phát hiện.

Tor project lưu ý rằng chỉ có cuộc tấn công đầu tiên trong danh sách là nghiêm trọng hơn, và hai ví dụ sau được đề cập "vì mục đích hoàn thiện."

## Introducing CGO

CGO giải quyết các vấn đề nêu trên. Nó được xây dựng trên một cấu trúc Rugged Pseudorandom Permutation (RPRP) gọi là UIV+, [do các nhà nghiên cứu mật mã học](https://eprint.iacr.org/2025/583) Jean Paul Degabriele, Alessandro Melloni, Jean-Pierre Münch, và Martijn Stam thiết kế.

Tor nói rằng hệ thống này đã được [verified](http://eprint.iacr.org/2025/2017) để đáp ứng các yêu cầu bảo mật cụ thể, bao gồm bảo vệ chống "tagging resistance, immediate forward secrecy, longer authentication tags, limited bandwidth overhead, relatively efficient operation, and modernized cryptography."

Cụ thể, CGO cải thiện các điểm sau so với Tor1:

* **Bảo vệ chống gắn thẻ (Tagging protection):** CGO sử dụng wide-block encryption và tag chaining, nên bất kỳ sửa đổi nào sẽ khiến toàn bộ cell và các cell tương lai không thể phục hồi, chặn các cuộc tấn công gắn thẻ.
* **Bảo mật tiến về trước (Forward secrecy):** CGO cập nhật khóa sau mỗi cell, vì vậy lưu lượng quá khứ không thể bị giải mã ngay cả khi khóa hiện tại bị lộ.
* **Xác thực mạnh hơn (Stronger authentication):** SHA-1 bị loại hoàn toàn khỏi mã hóa relay, và CGO sử dụng một bộ xác thực 16-byte, điều mà nhóm Tor bình luận là những gì “sensible people use.”
* **Tính toàn vẹn mạch (Circuit integrity):** CGO nối chuỗi T’ (encrypted tag) và N (initial nonce) qua các cell, nên mỗi cell phụ thuộc vào tất cả các cell trước đó, đảm bảo kháng giả mạo.

Tổng quan, CGO là một hệ thống mã hóa và xác thực hiện đại, dựa trên nghiên cứu, giải quyết nhiều vấn đề của Tor1 mà không gây thêm chi phí băng thông lớn.

Các người duy trì dự án nói rằng việc thêm CGO vào C Tor implementation và client viết bằng Rust, Arti, đang được tiến hành, và tính năng này được đánh dấu là experimental. Công việc còn chờ xử lý bao gồm thêm negotiation cho onion service và tối ưu hóa hiệu năng.

Người dùng Tor browser không cần làm gì để hưởng lợi từ CGO, vì thay đổi sẽ xảy ra tự động khi hệ thống mới có thể được triển khai đầy đủ. Tuy nhiên, một dòng thời gian cho khi nào nó sẽ trở thành tùy chọn mặc định chưa được cung cấp.