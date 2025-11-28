# GreyNoise ra mắt công cụ quét miễn phí để kiểm tra xem bạn có phải một phần của botnet không

![GreyNoise ra mắt công cụ quét miễn phí để kiểm tra xem bạn có phải một phần của botnet không](https://www.bleepstatic.com/content/hl-images/2024/04/02/scanner.jpg)

GreyNoise Labs đã ra mắt một công cụ miễn phí có tên là GreyNoise IP Check cho phép người dùng kiểm tra xem địa chỉ IP của họ có bị quan sát thấy trong các hoạt động quét độc hại, như botnet và mạng proxy dân cư hay không.

Công ty giám sát mối đe dọa theo dõi hoạt động trên toàn bộ Internet thông qua một mạng cảm biến toàn cầu cho biết vấn đề này đã tăng lên đáng kể trong năm qua, với nhiều người dùng vô tình hỗ trợ hoạt động độc hại trực tuyến.

"Trong năm vừa qua, các mạng proxy dân cư đã bùng nổ và biến các kết nối internet gia đình thành các điểm thoát cho lưu lượng của người khác," [giải thích bởi GreyNoise](https://www.greynoise.io/blog/your-ip-address-might-be-someone-elses-problem).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Đôi khi mọi người biết rõ họ cài phần mềm như vậy để đổi lấy vài đô la. Thường hơn, phần mềm độc hại lẻn vào thiết bị, thường qua các ứng dụng độc hại hoặc tiện ích mở rộng trình duyệt, và lặng lẽ biến chúng thành các nút trong cơ sở hạ tầng của người khác."

Mặc dù có những cách để xác định nếu ai đó đã trở thành một phần của hoạt động botnet độc hại, như kiểm tra nhật ký thiết bị, cấu hình, lưu lượng mạng và mẫu hoạt động, một công cụ chỉ kiểm tra địa chỉ IP là phương pháp ít xâm phạm nhất.

Những người truy cập [trang web của bộ quét](https://check.labs.greynoise.io/) sẽ nhận được một trong ba kết quả sau:

1. **Sạch**: Không phát hiện hoạt động quét độc hại.
2. **Độc hại/Đáng ngờ**: IP đã thể hiện hành vi quét. Người dùng nên điều tra các thiết bị trong mạng của họ.
3. **Dịch vụ doanh nghiệp thông thường**: IP thuộc về VPN, mạng công ty, hoặc nhà cung cấp đám mây, và hoạt động quét là bình thường đối với những môi trường đó.

![Clean scan result](https://www.bleepstatic.com/images/news/u/1220909/2025/November/scanresult.jpg)

**Kết quả quét: Sạch**  
_Nguồn: BleepingComputer_

Khi bất kỳ hoạt động nào được liên kết với địa chỉ IP được cung cấp, nền tảng cũng sẽ bao gồm một dòng thời gian lịch sử 90 ngày, điều này có thể giúp xác định điểm khả nghi có thể là thời điểm nhiễm.

Ví dụ, khi việc cài đặt một client chia sẻ băng thông hoặc một ứng dụng mờ ám xảy ra trước hoạt động quét độc hại, có thể tạo ra sự tương quan mạnh mẽ để cho phép thực hiện các hành động khắc phục.

**Dữ liệu hoạt động lịch sử**  
_Nguồn: GreyNoise_

Đối với người dùng kỹ thuật hơn, GreyNoise cũng cung cấp một JSON API không yêu cầu xác thực và không giới hạn tốc độ, có thể truy cập qua curl, và có thể tích hợp vào các script hoặc hệ thống kiểm tra.

Nếu kết quả quét của bạn cho thấy 'Độc hại/Đáng ngờ', nên bắt đầu điều tra bằng cách chạy quét malware trên tất cả thiết bị trong cùng mạng, đặc biệt tập trung vào các thiết bị như router và smart TV.

Người dùng được khuyên cập nhật thiết bị lên firmware mới nhất, thay đổi thông tin đăng nhập admin, và tắt các tính năng truy cập từ xa nếu không cần thiết.