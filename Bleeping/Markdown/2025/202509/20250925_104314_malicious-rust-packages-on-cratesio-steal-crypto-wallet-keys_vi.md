# Các gói Rust độc hại trên Crates.io đánh cắp khóa ví tiền điện tử

![Các gói Rust độc hại trên Crates.io đánh cắp khóa ví tiền điện tử](https://www.bleepstatic.com/content/hl-images/2024/04/09/Rust-headpic-red.jpg)

Hai gói độc hại với gần 8.500 lượt tải từ kho crate chính thức của Rust đã quét hệ thống của các nhà phát triển để đánh cắp khóa riêng tư tiền điện tử và các bí mật khác.

Các crate Rust được phân phối qua một registry trung tâm tại [Crates.io](https://crates.io/), tương đương với npm dành cho JavaScript, PyPI cho Python, và Ruby Gems cho Ruby.

Các crate độc hại, có tên _faster\_log_ và _async\_println_, được xuất bản trên nền tảng vào ngày 25 tháng 5 và đã được tải xuống lần lượt 7.200 và 1.200 lần.

Các nhà nghiên cứu tại công ty bảo mật mã nguồn Socket phát hiện các crate độc hại và báo cáo chúng với Crate.io. Nền tảng đã gỡ cả hai và đình chỉ các tài khoản xuất bản, 'rustguruman' và 'dumbnbased', vào ngày 24 tháng 9.

## Nhắm vào các bí mật tiền điện tử

Socket giải thích trong một [báo cáo](http://socket.dev/blog/two-malicious-rust-crates-impersonate-popular-logger-to-steal-wallet-keys) rằng hai crate này giả mạo crate hợp pháp ‘fast\_log’, sao chép file README, metadata kho lưu trữ, và giữ lại chức năng logging của dự án thật để giảm bớt nghi ngờ.

![Sao chép dự án hợp pháp để giảm nghi ngờ](https://www.bleepstatic.com/images/news/u/1220909/2025/September/impersonation.jpg)

**Sao chép dự án hợp pháp để giảm nghi ngờ**  
_Nguồn: Socket_

Kẻ tấn công lợi dụng chức năng đóng gói file log để quét thông tin nhạy cảm.

Một payload ẩn trong các crate độc hại được thực thi tại runtime để quét môi trường của nạn nhân và mã nguồn dự án để tìm các loại mục sau:

* Chuỗi hex trông giống khóa riêng tư Ethereum
* Chuỗi Base58 giống khóa/địa chỉ Solana
* mảng byte trong ngoặc có thể ẩn khóa hoặc seed

Khi mã tìm thấy khớp, nó đóng gói cùng với đường dẫn tệp và số dòng và gửi dữ liệu ra ngoài tới một địa chỉ Cloudflare Worker cố định (_mainnet\[.\]solana-rpc-pool\[.\]workers\[.\]dev_).

Socket xác nhận rằng endpoint này hoạt động và chấp nhận các yêu cầu POST trong quá trình kiểm tra của họ, lưu ý rằng host này không phải là endpoint RPC chính thức của Solana.

Crate.io [lưu ý trong thông báo của họ](https://blog.rust-lang.org/2025/09/24/crates.io-malicious-crates-fasterlog-and-asyncprintln/) rằng các crate độc hại không có crate phụ thuộc hạ nguồn trên nền tảng, và hai nhà xuất bản bị cấm không gửi dự án nào khác, nên cuộc tấn công hiện đã được dọn dẹp.

![Các crate độc hại xuất hiện trong kết quả tìm kiếm cho dự án hợp pháp](https://www.bleepstatic.com/images/news/u/1220909/2025/September/search-results.jpg)

**Các crate độc hại xuất hiện trong kết quả tìm kiếm cho dự án hợp pháp**  
_Nguồn: Socket_

Các nhà phát triển đã tải xuống bất kỳ crate nào trong hai crate này cần thực hiện dọn dẹp hệ thống và chuyển tài sản kỹ thuật số của họ sang ví mới để ngăn chặn việc bị đánh cắp.

Trước khi tải một crate Rust, các nhà phát triển nên xác minh uy tín của nhà xuất bản. Một biện pháp phòng ngừa khác là kiểm tra kỹ hướng dẫn build để đảm bảo chúng không tự động lấy các gói độc hại.