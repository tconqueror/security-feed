# Cuộc tấn công chuỗi cung ứng đánh vào gói npm có 45.000 lượt tải hàng tuần

![NPM](https://www.bleepstatic.com/content/hl-images/2025/05/08/npm.jpg)

Một gói npm có tên 'rand-user-agent' đã bị xâm phạm trong một cuộc tấn công chuỗi cung ứng để chèn mã obfuscated, kích hoạt một trojan truy cập từ xa (RAT) trên hệ thống của người dùng.

Gói '[rand-user-agent](https://www.npmjs.com/package/rand-user-agent)' là một công cụ tạo ra các chuỗi user-agent ngẫu nhiên, hữu ích trong việc cào dữ liệu web, kiểm thử tự động và nghiên cứu bảo mật.

Mặc dù gói này đã bị ngừng phát triển, nhưng nó vẫn khá phổ biến, với trung bình 45.000 lượt tải hàng tuần.

Tuy nhiên, theo các nhà nghiên cứu tại [Aikido](https://www.aikido.dev/blog/catching-a-rat-remote-access-trojian-rand-user-agent-supply-chain-compromise), các tác nhân đe dọa đã lợi dụng trạng thái bán bị bỏ rơi nhưng vẫn phổ biến của nó để chèn mã độc trong các bản phát hành bất hợp pháp tiếp theo mà rất có thể đã được tải xuống bởi một số lượng lớn các dự án thuộc hạ lưu.

Aikido đã phát hiện sự xâm phạm vào ngày 5 tháng 5 năm 2025, khi hệ thống phân tích mã độc của họ đã đánh dấu một phiên bản mới của rand-user-agent, số 1.0.110.

Sau khi xem xét kỹ lưỡng, các nhà nghiên cứu đã phát hiện mã obfuscated ẩn trong tệp 'dist/index.js', chỉ hiển thị khi người dùng cuộn ngang trong chế độ xem nguồn trên trang npm.

![Mã obfuscated ẩn ngoài tầm nhìn](https://www.bleepstatic.com/images/news/u/1220909/2025/May/hidden.jpg)

**Mã obfuscated ẩn ngoài tầm nhìn**  
_Nguồn: Aikido_

Cuộc điều tra cho thấy phiên bản hợp pháp cuối cùng của 'rand-user-agent' là 2.0.82, phát hành cách đây 7 tháng.

Các phiên bản 2.0.83, 2.0.84, và cả 1.0.110, được phát hành sau đó, đều là mã độc và không có bản phát hành tương ứng trên kho lưu trữ GitHub của dự án.

Mã độc nhúng trong các phiên bản mới nhất tạo ra một thư mục ẩn dưới thư mục chính của người dùng (\~/.node\_modules) và mở rộng 'module.paths' để con đường tùy chỉnh này có thể được sử dụng để tải các phụ thuộc, cụ thể là 'axios' và 'socket.io-client.'

Tiếp theo, nó mở một kết nối socket liên tục đến lệnh điều khiển của kẻ tấn công (C2) tại http://85.239.62\[.\]36:3306, và gửi thông tin ID máy bao gồm tên máy, tên người dùng, loại hệ điều hành và một UUID được tạo ra.

Khi RAT hoạt động, nó sẽ nghe lệnh nào trong số dưới đây:

* **cd <path>** \- Thay đổi thư mục làm việc hiện tại
* **ss\_dir** – Đặt lại thư mục làm việc về đường dẫn kịch bản
* **ss\_fcd:<path>** \- Thay đổi mạnh mẽ đến thư mục đã cho
* **ss\_upf:f,d** – Tải lên một tệp đơn f đến đích d
* **ss\_upd:d,dest** – Tải lên tất cả các tệp trong thư mục d đến dest
* **ss\_stop** – Ngắt bất kỳ quá trình tải lên tệp nào đang diễn ra
* **(bất kỳ lệnh nào khác)** – Thực thi nó như một lệnh shell bằng cách sử dụng child\_process.exec()

Tại thời điểm viết bài, các phiên bản độc hại đã được gỡ bỏ khỏi kho lưu trữ của gói trên npm, vì vậy phiên bản mới nhất có sẵn là an toàn, và người dùng nên quay lại với nó.

Tuy nhiên, nếu bạn đã nâng cấp lên các phiên bản 2.0.83, 2.0.84, hoặc 1.0.110, thì điều quan trọng là phải thực hiện quét toàn bộ hệ thống để tìm dấu hiệu xâm phạm. Lưu ý rằng việc hạ cấp về phiên bản hợp pháp không xóa RAT khỏi hệ thống của bạn.

Ngoài ra, hãy cân nhắc sử dụng các phiên bản đã được fork nhưng vẫn được hỗ trợ và theo dõi tốt hơn của công cụ 'rand-user-agent'.

BleepingComputer đã liên hệ với nhà phát triển để tìm hiểu cách gói của họ bị xâm phạm, nhưng không nhận được phản hồi ngay lập tức.