# Các tiện ích mở rộng VSCode độc hại trên registry của Microsoft phát tán phần mềm đánh cắp thông tin

![Malicious VSCode extensions on Microsoft's registry drop infostealers](https://www.bleepstatic.com/content/hl-images/2025/03/13/VSCode_bw.jpg)

Hai tiện ích mở rộng độc hại trên Visual Studio Code Marketplace của Microsoft lây nhiễm máy của các nhà phát triển bằng phần mềm độc hại đánh cắp thông tin có thể chụp ảnh màn hình, đánh cắp thông tin đăng nhập, ví tiền mã hóa và chiếm quyền phiên duyệt web.

Thị trường này lưu trữ các tiện ích mở rộng cho môi trường phát triển tích hợp phổ biến VSCode để mở rộng chức năng hoặc thêm các tùy chọn tùy chỉnh.

Hai tiện ích độc hại, có tên Bitcoin Black và Codo AI, cải trang thành một theme màu và một trợ lý AI, tương ứng, và được xuất bản dưới tên nhà phát triển 'BigBlack.' 

Tính đến thời điểm viết bài, Codo AI vẫn còn trên marketplace, mặc dù có ít hơn 30 lượt tải. Bộ đếm của Bitcoin Black chỉ hiển thị một lượt cài đặt.

![CodoAI on VSCode Market](https://www.bleepstatic.com/images/news/u/1220909/2025/December/codoai.jpg)

**Codo AI trên VSCode Market**  
_Source: BleepingComputer.com_

Theo Koi Security, tiện ích độc hại Bitcoin Black có sự kiện kích hoạt "\*" thực thi trên mọi hành động của VSCode. Nó cũng có thể chạy mã PowerShell, điều mà một theme không cần và nên là một dấu hiệu cảnh báo.

Trong các phiên bản cũ hơn, Bitcoin Black sử dụng một script PowerShell để tải về payload được lưu trữ có mật khẩu, điều này tạo ra một cửa sổ PowerShell hiển thị và có thể cảnh báo người dùng.

Trong các phiên bản gần đây hơn, quy trình chuyển sang một batch script (bat.sh) gọi _'curl'_ để tải xuống một file DLL và một file thực thi, và hoạt động diễn ra khi cửa sổ bị ẩn.

![Malicious payload from bat.sh](https://www.bleepstatic.com/images/news/u/1220909/2025/December/payload.jpg)

**Tệp payload độc hại từ bat.sh**  
_Source: Koi Security_

Idan Dardikman của Koi Security cho biết Codo AI có chức năng hỗ trợ mã thông qua ChatGPT hoặc DeepSeek, nhưng cũng bao gồm một phần mã độc.

Cả hai tiện ích đều phân phối một file thực thi hợp pháp của công cụ chụp ảnh màn hình Lightshot và một file DLL độc hại được nạp thông qua kỹ thuật DLL hijacking để triển khai infostealer dưới tên _runtime.exe_.

File DLL độc hại được 29 trong số 72 engine chống virus trên Virus Total gắn cờ là mối đe dọa, nhà nghiên cứu ghi chú trong một [báo cáo](https://www.koi.ai/blog/the-vs-code-malware-that-captures-your-screen) hôm nay.

Phần mềm độc hại tạo một thư mục trong _'%APPDATA%\\Local\\_' và tạo một thư mục có tên _Evelyn_ để lưu trữ dữ liệu bị đánh cắp: chi tiết về tiến trình đang chạy, nội dung clipboard, thông tin đăng nhập WiFi, thông tin hệ thống, ảnh chụp màn hình, danh sách chương trình đã cài đặt và các tiến trình đang chạy.

**Thư mục Evelyn được tạo để lưu trữ dữ liệu đánh cắp**  
_source: BleepingComputer_

Để đánh cắp cookie và chiếm quyền phiên của người dùng, phần mềm độc hại khởi chạy trình duyệt Chrome và Edge ở chế độ headless để có thể lấy cookie đã lưu và chiếm quyền phiên của người dùng.

Phần mềm độc hại cũng đánh cắp các ví tiền mã hóa như Phantom, Metamask, Exodus. Nó tìm kiếm mật khẩu và thông tin đăng nhập.

BleepingComputer đã liên hệ với Microsoft về sự hiện diện của các tiện ích mở rộng trên marketplace, nhưng chưa có bình luận ngay lập tức.

Các tiện ích mở rộng VS Code độc hại đã được đẩy lên các nền tảng cung cấp tiện ích mở rộng cho IDE VS Code, chẳng hạn như OpenVSX và Visual Studio Code, một trong những chiến dịch đáng chú ý nhất là Glassworm.

Các nhà phát triển có thể giảm thiểu rủi ro từ các tiện ích mở rộng VSCode độc hại bằng cách chỉ cài đặt các dự án từ các nhà xuất bản uy tín.