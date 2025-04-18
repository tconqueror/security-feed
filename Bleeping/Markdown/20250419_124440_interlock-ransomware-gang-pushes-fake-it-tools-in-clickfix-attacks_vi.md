"markdown_vn"
# Băng nhóm ransomware Interlock đẩy mạnh công cụ IT giả trong các cuộc tấn công ClickFix

![Hackers](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

Băng nhóm ransomware Interlock hiện đang sử dụng các cuộc tấn công ClickFix giả mạo công cụ IT để xâm phạm các mạng lưới công ty và triển khai phần mềm mã hóa file trên thiết bị.

ClickFix là một thủ đoạn kỹ thuật xã hội, nơi các nạn nhân bị lừa thực hiện các lệnh PowerShell nguy hiểm trên hệ thống của họ với mục đích giả vờ sửa lỗi hoặc xác minh bản thân, dẫn đến việc cài đặt malware.

Mặc dù đây [không phải lần đầu tiên](https://www.bleepingcomputer.com/news/security/fake-google-chrome-errors-trick-you-into-running-malicious-powershell-scripts/) ClickFix liên quan đến các vụ nhiễm ransomware, sự xác nhận về Interlock cho thấy một xu hướng ngày càng tăng trong các loại tác nhân đe dọa này sử dụng thủ đoạn này.

Interlock là một hoạt động ransomware được ra mắt vào cuối tháng 9 năm 2024, [nhắm đến các máy chủ FreeBSD](https://www.bleepingcomputer.com/news/security/meet-interlock-the-new-ransomware-targeting-freebsd-servers/) và hệ thống Windows.

Interlock được cho là không hoạt động theo mô hình ransomware-as-a-service. Tuy nhiên, nó duy trì một cổng thông tin rò rỉ dữ liệu trên dark web để gia tăng áp lực lên nạn nhân, yêu cầu thanh toán từ hàng trăm nghìn đô la đến hàng triệu đô la.

## Từ ClickFix đến ransomware

Trước đây, Interlock đã sử dụng các bản cập nhật trình duyệt và client VPN giả để cài đặt malware và xâm nhập các mạng lưới.

Theo [các nhà nghiên cứu Sekoia](https://blog.sekoia.io/interlock-ransomware-evolving-under-the-radar/), băng nhóm ransomware Interlock đã bắt đầu sử dụng các cuộc tấn công ClickFix vào tháng 1 năm 2025.

Interlock đã sử dụng ít nhất bốn URL để chứa các thông báo CAPTCHA giả mạo, yêu cầu du khách thực hiện một lệnh trên máy tính của họ để xác minh và tải xuống một công cụ được quảng bá.

Các nhà nghiên cứu cho biết họ đã phát hiện captcha độc hại trên bốn trang web khác nhau, giả mạo các cổng thông tin Microsoft hoặc Advanced IP Scanner:

* microsoft-msteams\[.\]com/additional-check.html
* microstteams\[.\]com/additional-check.html
* ecologilives\[.\]com/additional-check.html
* advanceipscaner\[.\]com/additional-check.html

Tuy nhiên, chỉ có trang giả mạo Advanced IP Scanner, một công cụ quét IP phổ biến thường được sử dụng bởi nhân viên IT, dẫn đến việc tải xuống một phần mềm lắp đặt độc hại.

![Trang hosting bait ClickFix của Interlock](https://www.bleepstatic.com/images/news/u/1220909/2025/April/clickfix-page.jpg)

**Trang hosting bait ClickFix của Interlock**  
_Nguồn: Sekoia_

Nhấp vào nút 'Fix it' sẽ sao chép lệnh PowerShell độc hại vào clipboard của nạn nhân. Nếu được thực hiện trong một command prompt hoặc hộp thoại Run của Windows, nó sẽ tải xuống một payload PyInstaller 36MB.

Trong cùng lúc đó, trang web AdvanceIPScanner hợp pháp sẽ mở trong một cửa sổ trình duyệt để giảm bớt sự nghi ngờ.

Payload độc hại cài đặt một bản sao hợp pháp của phần mềm mà nó giả vờ là và đồng thời thực thi một script PowerShell nhúng chạy trong một cửa sổ ẩn.

Script này đăng ký một Run key trong Windows Registry để bảo trì và sau đó thu thập và xuất khẩu thông tin hệ thống bao gồm phiên bản OS, mức độ quyền của người dùng, các quy trình đang chạy và các ổ đĩa có sẵn.

Sekoia đã quan sát thấy command and control (C2) phản hồi với nhiều payload khác nhau, bao gồm LummaStealer, BerserkStealer, keyloggers và Interlock RAT.

Cái sau là một trojan đơn giản có thể được cấu hình động, hỗ trợ xuất khẩu file, thực hiện lệnh shell và chạy các DLL độc hại.

![Các lệnh mà Interlock RAT hỗ trợ](https://www.bleepstatic.com/images/news/u/1220909/2025/April/rat-commands.jpg)

**Các lệnh mà Interlock RAT hỗ trợ**  
_Nguồn: Sekoia_

Sau khi xâm nhập ban đầu và triển khai RAT, các operator của Interlock đã sử dụng thông tin đăng nhập bị đánh cắp để di chuyển theo phương pháp ngang qua RDP, trong khi Sekoia cũng thấy PuTTY, AnyDesk và LogMeIn được sử dụng trong một số cuộc tấn công.

Bước cuối cùng trước khi thực hiện ransomware là xuất khẩu dữ liệu, với các file bị đánh cắp được tải lên Azure Blobs do kẻ tấn công kiểm soát.

Biến thể Windows của Interlock được thiết lập (thông qua một công việc đã lên lịch) để chạy hàng ngày lúc 08:00 PM, nhưng nhờ vào bộ lọc dựa trên phần mở rộng file, điều này không gây ra nhiều lớp mã hóa mà chỉ đóng vai trò như một biện pháp dư thừa.

Sekoia cũng báo cáo rằng ghi chú đòi tiền đã phát triển, với các phiên bản mới nhất tập trung nhiều hơn vào khía cạnh pháp lý của vụ rò rỉ dữ liệu và những hậu quả quy định nếu dữ liệu bị đánh cắp trở nên công khai.

**Ghi chú đòi tiền mới nhất của Interlock**  
_Nguồn: BleepingComputer_

Các cuộc tấn công ClickFix hiện đã được áp dụng bởi một loạt các tác nhân đe dọa, bao gồm các băng nhóm ransomware khác và các hacker Bắc Triều Tiên.

Tháng trước, Sekoia phát hiện ra rằng nhóm hacker Bắc Triều Tiên khét tiếng Lazarus đã sử dụng [các cuộc tấn công ClickFix nhắm đến người tìm việc](https://www.bleepingcomputer.com/news/security/north-korean-hackers-adopt-clickfix-attacks-to-target-crypto-firms/) trong ngành công nghiệp cryptocurrency.