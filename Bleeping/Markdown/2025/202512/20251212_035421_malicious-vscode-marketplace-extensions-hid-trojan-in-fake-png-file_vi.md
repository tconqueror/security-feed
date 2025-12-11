# Tiện ích mở rộng độc hại trên VSCode Marketplace giấu trojan trong tệp PNG giả

![Malicious VSCode Marketplace extensions hid trojan in fake PNG file](https://www.bleepstatic.com/content/hl-images/2025/03/13/VSCode.jpg)

Một chiến dịch lén lút với 19 tiện ích mở rộng trên VSCode Marketplace đã hoạt động từ tháng Hai, nhắm vào các nhà phát triển bằng phần mềm độc hại được giấu bên trong thư mục phụ thuộc.

Hoạt động độc hại này mới được phát hiện gần đây, và các nhà nghiên cứu bảo mật nhận thấy kẻ điều hành đã sử dụng một tệp độc hại giả dạng ảnh .PNG.

VSCode Market là cổng chính thức của Microsoft cho các tiện ích mở rộng dành cho môi trường phát triển tích hợp (IDE) VSCode được sử dụng rộng rãi, cho phép các nhà phát triển mở rộng chức năng hoặc thêm tùy chỉnh giao diện.

Do sự phổ biến và khả năng gây ảnh hưởng cao trong các cuộc tấn công chuỗi cung ứng phần mềm, nền tảng này thường xuyên bị các tác nhân đe dọa nhắm mục tiêu với các chiến dịch ngày càng tinh vi ([liên tục bị nhắm mục tiêu](https://www.bleepingcomputer.com/news/security/malicious-vscode-extensions-on-microsofts-registry-drop-infostealers/)).

ReversingLabs, một công ty chuyên về bảo mật tệp và chuỗi cung ứng phần mềm, phát hiện rằng các tiện ích độc hại được đóng gói sẵn với một thư mục ‘_node\_modules_’ để ngăn VSCode lấy phụ thuộc từ npm registry khi cài đặt chúng.

Bên trong thư mục đóng gói, kẻ tấn công đã thêm một phụ thuộc bị chỉnh sửa, ‘_path-is-absolute_’ hoặc ‘_@actions/io_’, với một lớp bổ sung trong tệp ‘_index.js_’ được thực thi tự động khi khởi động IDE VSCode.

![Malicious code added to the index.js file](https://www.bleepstatic.com/images/news/u/1220909/2025/December/index.jpg)

**Mã độc được thêm vào tệp index.js**  
_Source: ReversingLabs_

Cần lưu ý rằng ‘path-is-absolute’ là một gói npm rất phổ biến với 9 tỷ lượt tải xuống kể từ 2021, và phiên bản bị vũ khí hóa chỉ tồn tại trong 19 tiện ích mở rộng được sử dụng trong chiến dịch.

Mã được giới thiệu bởi lớp mới trong tệp ‘index.js’ giải mã một JavaScript dropper bị che obfuscate bên trong một tệp có tên '_lock_'. Một tệp khác có trong thư mục phụ thuộc là một tệp lưu trữ giả dạng .PNG (_banner.png_) chứa hai tệp nhị phân độc hại: một binary sống-nhờ-đất (LoLBin) có tên '_cmstp.exe_' và một trojan viết bằng Rust.

ReversingLabs vẫn đang phân tích trojan để xác định đầy đủ khả năng của nó.

Theo các nhà nghiên cứu, 19 tiện ích mở rộng VSCode trong chiến dịch sử dụng các biến thể của các tên sau, tất cả được xuất bản với số phiên bản 1.0.0:

* Malkolm Theme
* PandaExpress Theme
* Prada 555 Theme
* Priskinski Theme

ReversingLabs đã báo cáo chúng cho Microsoft, và BleepingComputer xác nhận rằng tất cả đều đã bị gỡ bỏ. Tuy nhiên, người dùng đã cài các tiện ích này nên quét hệ thống để tìm dấu hiệu bị xâm phạm.

Bởi vì các tác nhân đe dọa tìm ra các cách mới để tránh phát hiện trên các kho công cộng được sử dụng cho phát triển phần mềm, khuyến nghị người dùng nên kiểm tra gói trước khi cài đặt, đặc biệt khi nguồn không phải là nhà phát hành uy tín.

Họ nên xem xét kỹ các phụ thuộc, đặc biệt khi chúng được đóng gói trong gói, như trường hợp của tiện ích VS Code, và không được kéo từ nguồn đáng tin cậy, như xảy ra với npm.