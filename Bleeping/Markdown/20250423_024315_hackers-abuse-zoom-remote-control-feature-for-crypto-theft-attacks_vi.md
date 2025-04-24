# Tin tặc lợi dụng tính năng điều khiển từ xa của Zoom để thực hiện các cuộc tấn công trộm tiền mã hóa

![Zoom](https://www.bleepstatic.com/content/hl-images/2022/09/15/Zoom.jpg)

Một nhóm tin tặc có tên là 'Elusive Comet' nhắm mục tiêu vào người dùng tiền mã hóa trong các cuộc tấn công xã hội nhằm lừa đảo bằng cách lợi dụng tính năng điều khiển từ xa của Zoom để khiến người dùng cấp quyền truy cập vào máy tính của họ.

Tính năng điều khiển từ xa của Zoom cho phép các thành viên tham gia cuộc họp kiểm soát máy tính của một thành viên khác.

Theo công ty an ninh mạng Trail of Bits, đã phát hiện ra chiến dịch lừa đảo xã hội này, các thủ phạm đã sao chép các kỹ thuật mà nhóm tin tặc Lazarus đã sử dụng trong [cuộc tấn công trộm tiền mã hóa lớn 1.5 tỷ đô la của Bybit](https://www.bleepingcomputer.com/news/security/fbi-confirms-lazarus-hackers-were-behind-15b-bybit-crypto-heist/).

"Phương pháp ELUSIVE COMET phản ánh các kỹ thuật đằng sau vụ hack Bybit 1.5 tỷ đô la gần đây vào tháng Hai, trong đó các kẻ tấn công đã thao túng các quy trình hợp pháp thay vì khai thác các lỗ hổng mã," báo cáo của Trail of Bits giải thích.

## Kế hoạch phỏng vấn dựa trên Zoom

Trail of Bits đã tìm hiểu về chiến dịch mới này sau khi các đối tượng đe dọa đã cố gắng thực hiện cuộc tấn công lừa đảo xã hội đối với CEO của họ qua tin nhắn trực tiếp trên X.

Cuộc tấn công bắt đầu bằng việc gửi lời mời tham gia một cuộc phỏng vấn "Bloomberg Crypto" qua Zoom, được gửi đến các mục tiêu có giá trị cao qua các tài khoản giả mạo trên X, hoặc qua email (bloombergconferences\[@\]gmail.com).

Các tài khoản giả mạo này giả mạo các nhà báo tập trung vào tiền mã hóa hoặc các cơ quan Bloomberg và liên hệ với những người mục tiêu qua tin nhắn trực tiếp trên các nền tảng mạng xã hội.

![Tài khoản giả mạo sử dụng trong các cuộc tấn công](https://www.bleepstatic.com/images/news/u/1220909/2025/April/sockpuppets.jpg)

**Tài khoản giả mạo sử dụng trong các cuộc tấn công**  
_Nguồn: Trail of Bits_

Các lời mời được gửi qua các liên kết Calendly để lên lịch một cuộc họp Zoom. Vì cả hai lời mời/liên kết Calendly và Zoom đều là thật, chúng hoạt động như mong đợi và làm giảm nghi ngờ của mục tiêu.

![Trang Calendly được sử dụng trong cuộc tấn công](https://www.bleepstatic.com/images/news/u/1220909/2025/April/calendly.jpg)

**Trang Calendly được sử dụng để lên lịch phỏng vấn**  
_Nguồn: Trail of Bits_

Trong cuộc gọi Zoom, kẻ tấn công khởi động một phiên chia sẻ màn hình và gửi yêu cầu điều khiển từ xa đến mục tiêu.

Mẹo được sử dụng trong giai đoạn này là kẻ tấn công đổi tên hiển thị trên Zoom thành "Zoom", vì vậy thông báo mà nạn nhân thấy đọc "Zoom đang yêu cầu điều khiển từ xa màn hình của bạn", khiến nó trở thành một yêu cầu hợp pháp từ ứng dụng.

**Yêu cầu lừa đảo trên Zoom**  
_Nguồn: Trail of Bits_

Tuy nhiên, việc chấp thuận yêu cầu này đã cho phép kẻ tấn công hoàn toàn kiểm soát đầu vào từ xa hệ thống của nạn nhân, cho phép chúng đánh cắp dữ liệu nhạy cảm, cài đặt malware, truy cập vào các tệp hoặc khởi động các giao dịch tiền mã hóa.

Kẻ tấn công có thể hành động nhanh chóng để thiết lập quyền truy cập liên tục bằng cách cài đặt một backdoor bí mật để khai thác sau này và ngắt kết nối, để lại cho nạn nhân ít cơ hội nhận ra sự xâm phạm.

"Điều làm cho cuộc tấn công này đặc biệt nguy hiểm là sự tương đồng của hộp thoại cấp quyền với các thông báo vô hại khác của Zoom," [nói Trail of Bits](https://blog.trailofbits.com/2025/04/17/mitigating-elusive-comet-zoom-remote-control-attacks/).

"Các người dùng quen với việc nhấp vào "Chấp thuận" trên các thông báo của Zoom có thể cấp quyền kiểm soát hoàn toàn máy tính của họ mà không nhận ra những hệ lụy."

Để phòng chống mối đe dọa này, Trail of Bits đề xuất việc triển khai các chính sách kiểm soát quyền riêng tư (PPPC) trên toàn hệ thống để ngăn chặn quyền truy cập vào khả năng tiếp cận, điều này có thể thực hiện bằng cách sử dụng [bộ công cụ này](https://github.com/trailofbits/it-releases).

Công ty khuyến nghị loại bỏ hoàn toàn Zoom khỏi tất cả các hệ thống cho các môi trường và tổ chức nhạy cảm với an ninh xử lý các tài sản kỹ thuật số có giá trị.

"Đối với các tổ chức xử lý dữ liệu đặc biệt nhạy cảm hoặc các giao dịch tiền mã hóa, việc giảm thiểu rủi ro từ việc loại bỏ hoàn toàn khách hàng Zoom thường vượt quá sự bất tiện nhỏ trong việc sử dụng các lựa chọn dựa trên trình duyệt," báo cáo của Trail of Bits giải thích.