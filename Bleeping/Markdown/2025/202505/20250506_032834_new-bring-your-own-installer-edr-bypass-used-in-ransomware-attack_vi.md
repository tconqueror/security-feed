# Kỹ thuật "Bring Your Own Installer" EDR bypass mới được sử dụng trong tấn công ransomware

![Hacker với tay giơ cao](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

Kỹ thuật "Bring Your Own Installer" EDR bypass mới được khai thác trong các cuộc tấn công để vượt qua tính năng bảo vệ chống giả mạo của SentinelOne, cho phép các đối tượng tấn công vô hiệu hóa các tác nhân phát hiện và phản ứng cuối điểm (EDR) để cài đặt ransomware Babuk.

Kỹ thuật này khai thác một lỗ hổng trong quy trình nâng cấp tác nhân cho phép các đối tượng tấn công kết thúc các tác nhân EDR đang chạy, để lại các thiết bị không được bảo vệ.

Cuộc tấn công được phát hiện bởi John Ailes và Tim Mashni của nhóm Phản ứng Sự cố Stroz Friedberg của Aon trong quá trình tham gia với một khách hàng đã bị tấn công ransomware vào đầu năm nay.

Kỹ thuật này không phụ thuộc vào các công cụ hoặc trình điều khiển bên thứ ba như chúng ta thường thấy với các EDR bypass nhưng thay vào đó lạm dụng chính trình cài đặt SentinelOne.

SentinelOne khuyến nghị khách hàng bật cài đặt "Online Authorization", được tắt mặc định, để giảm thiểu cuộc tấn công này.

"Chúng tôi muốn thông báo để đảm bảo rằng các khách hàng của SentinelOne biết để kích hoạt bảo vệ Nâng cấp Địa phương," John Ailes, Giám đốc, Aon's Stroz Friedberg DFIR, đã nói với BleepingComputer.

"Chúng tôi đã điều tra các môi trường với SentinelOne kể từ khi hướng dẫn của họ được gửi đến khách hàng và đã thấy một số khách hàng vẫn chưa kích hoạt. Cuối cùng, việc thông báo để giảm thiểu lỗ hổng này là việc quan trọng nhất."

## Đang bị khai thác trong các cuộc tấn công ransomware

Các nhà nghiên cứu Stroz Friedberg giải thích rằng SentinelOne bảo vệ tác nhân EDR của mình bằng tính năng bảo vệ chống giả mạo yêu cầu hành động thủ công trong bảng điều khiển quản lý của SentinelOne hoặc một mã duy nhất để gỡ bỏ một tác nhân.

Tuy nhiên, giống như nhiều trình cài đặt phần mềm khác, khi cài đặt một phiên bản khác của tác nhân, trình cài đặt SentinelOne sẽ kết thúc bất kỳ quy trình Windows liên quan nào ngay trước khi các tệp hiện tại bị ghi đè bằng phiên bản mới.

Các đối tượng tấn công đã phát hiện ra rằng họ có thể khai thác khoảng thời gian ngắn này bằng cách chạy một trình cài đặt SentinelOne hợp lệ và sau đó kết thúc cưỡng chế quy trình cài đặt ngay sau khi nó tắt dịch vụ của tác nhân đang chạy, để lại các thiết bị không được bảo vệ.

![Chuỗi tấn công EDR bypass Bring Your Own Installer](https://www.bleepstatic.com/images/news/security/b/bring-your-own-installer-edr-bypass/Bring-Your-Own-Installer-EDR-Bypass-attack-flow.png)

**Chuỗi tấn công EDR bypass Bring Your Own Installer**  
_Nguồn: Stroz Friedberg_

Vào đầu năm nay, Stroz Friedberg đã được mời điều tra một cuộc tấn công vào mạng lưới của một khách hàng, với nhật ký chỉ ra rằng các kẻ tấn công đã giành quyền truy cập quản trị vào mạng lưới của khách hàng thông qua một lỗ hổng.

Các kẻ tấn công sau đó đã sử dụng lỗ hổng mới này bằng cách kết thúc quy trình Trình cài đặt Windows của SentinelOne ("`msiexec.exe`") trước khi nó có thể cài đặt và khởi chạy phiên bản mới của tác nhân. Khi các biện pháp bảo vệ bị vô hiệu hóa trên thiết bị, các đối tượng tấn công đã có thể triển khai ransomware.

Trong một cuộc trò chuyện với BleepingComputer, Ailes cho biết các đối tượng tấn công có thể sử dụng các phiên bản mới hoặc cũ của tác nhân để thực hiện cuộc tấn công này, vì vậy ngay cả khi phiên bản mới nhất đang chạy trên các thiết bị, chúng vẫn dễ bị tổn thương.

"Stroz Friedberg cũng đã quan sát thấy rằng máy chủ đã ngừng trực tuyến trong bảng điều khiển quản lý của SentinelOne ngay sau khi trình cài đặt bị kết thúc," cảnh báo [báo cáo của Stroz Friedberg](https://www.aon.com/en/insights/cyber-labs/bring-your-own-installer-bypassing-sentinelone).

"Thử nghiệm thêm cho thấy rằng cuộc tấn công đã thành công ở nhiều phiên bản khác nhau của tác nhân SentinelOne và không phụ thuộc vào các phiên bản cụ thể được quan sát trong sự cố này."

Stroz Friedberg đã thông báo về cuộc tấn công này một cách có trách nhiệm cho SentinelOne, người đã chia sẻ riêng các biện pháp giảm thiểu với khách hàng vào tháng 1 năm 2025.

Biện pháp giảm thiểu là kích hoạt tính năng "Online Authorization" trong cài đặt Chính sách Sentinel, mà khi được kích hoạt, yêu cầu sự chấp thuận từ bảng điều khiển quản lý của SentinelOne trước khi việc nâng cấp, hạ cấp hoặc gỡ bỏ tác nhân xảy ra.

SentinelOne cũng đã chia sẻ lời khuyên của Stroz Friedberg về kỹ thuật mới này với tất cả các nhà cung cấp EDR lớn khác, trong trường hợp họ cũng bị ảnh hưởng.

Palo Alto Networks đã xác nhận với Stroz Friedberg rằng cuộc tấn công này không ảnh hưởng đến phần mềm EDR của họ.