# TARmageddon lỗ hổng trong thư viện Rust bị bỏ hoang cho phép thực thi mã từ xa (RCE)

![Tin tặc](https://www.bleepstatic.com/content/hl-images/2024/05/07/hacker-box.jpg)

Một lỗ hổng mức độ nghiêm trọng cao trong thư viện async-tar viết bằng Rust hiện đã bị bỏ hoang và các fork của nó có thể bị khai thác để đạt được thực thi mã từ xa trên các hệ thống chạy phần mềm chưa được vá.

Được theo dõi là [CVE-2025-62518](https://nvd.nist.gov/vuln/detail/CVE-2025-62518), lỗi logic này phát sinh từ vấn đề mất đồng bộ cho phép kẻ tấn công không cần xác thực chèn thêm các mục lưu trữ trong quá trình giải nén tệp TAR.

Điều này xảy ra cụ thể khi xử lý các tệp TAR lồng nhau với các header ustar và PAX extended không khớp, khiến trình phân tích nhảy vào nội dung tệp và nhầm lẫn nó là header TAR, dẫn đến việc giải nén các tệp do kẻ tấn công cung cấp.

Edera, công ty an ninh mạng phát hiện lỗ hổng và đặt tên là [TARmageddon](https://edera.dev/stories/tarmageddon), giải thích rằng các tác nhân đe dọa có thể khai thác nó để ghi đè tệp trong các cuộc tấn công chuỗi cung ứng bằng cách thay thế tệp cấu hình và chiếm quyền backend xây dựng.

Lỗ hổng bảo mật này ảnh hưởng không chỉ các dự án sử dụng async-tar mà còn cả tokio-tar, một fork cực kỳ phổ biến với [hơn 7 triệu lượt tải trên crates.io](https://crates.io/crates/tokio-tar) và cũng đã bị bỏ hoang.

Mặc dù các fork đang được duy trì đã được [vá](https://github.com/edera-dev/cve-tarmageddon/tree/main/patches), Edera cho biết không thể ước tính chính xác tác động của lỗ hổng này do tính lan rộng của các fork, bao gồm cả tokio-tar.

"Due to the widespread nature of tokio-tar in various forms, it is not possible to truly quantify upfront the blast radius of this bug across the ecosystem," [said Edera](https://edera.dev/stories/tarmageddon).

"While the active forks have been successfully patched (see also Astral Security Advisory), this disclosure highlights a major systemic challenge: the highly downloaded tokio-tar remains unpatched."

Lỗ hổng TARmageddon ảnh hưởng nhiều dự án được sử dụng rộng rãi, bao gồm Binstalk, Astral's uv Python package manager, the wasmCloud universal application platform, liboxen, and the open-source testcontainers library.

Trong khi một số dự án hạ nguồn mà Edera tiếp cận đã thông báo kế hoạch loại bỏ phụ thuộc dễ bị tổn thương hoặc chuyển sang fork đã được vá, một số khác chưa phản hồi, và có nhiều dự án chưa được thông báo có khả năng cũng đang sử dụng nó.

Edera khuyên các nhà phát triển nên nâng cấp lên phiên bản đã được vá hoặc ngay lập tức loại bỏ phụ thuộc tokio-tar dễ bị tấn công. Họ nên chuyển sang fork astral-tokio-tar được duy trì tích cực nếu dự án của họ phụ thuộc vào thư viện tokio-tar dễ bị tổn thương. Fork async-tar của Edera (krata-tokio-tar) sẽ được lưu trữ để giảm sự nhầm lẫn trong hệ sinh thái.