"markdown_vn"
# Nhóm ransomware Interlock phát tán công cụ IT giả trong các cuộc tấn công ClickFix

![Hacker](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

Nhóm ransomware Interlock hiện đang sử dụng các cuộc tấn công ClickFix mô phỏng các công cụ IT nhằm xâm nhập các mạng doanh nghiệp và triển khai phần mềm mã hóa tệp trên các thiết bị.

ClickFix là một chiến thuật kỹ thuật xã hội, trong đó nạn nhân bị lừa thực thi các lệnh PowerShell nguy hiểm trên hệ thống của họ để được cho là khắc phục một lỗi hoặc xác thực bản thân, dẫn đến việc cài đặt malware.

Mặc dù đây [không phải là lần đầu tiên](https://www.bleepingcomputer.com/news/security/fake-google-chrome-errors-trick-you-into-running-malicious-powershell-scripts/) ClickFix đã được liên kết với các trường hợp nhiễm ransomware, nhưng xác nhận về Interlock cho thấy một xu hướng gia tăng trong các loại tác nhân đe dọa này sử dụng chiến thuật này.

Interlock là một hoạt động ransomware được khởi động vào cuối tháng 9 năm 2024, [nhắm vào các máy chủ FreeBSD](https://www.bleepingcomputer.com/news/security/meet-interlock-the-new-ransomware-targeting-freebsd-servers/) và các hệ thống Windows.

Interlock không được cho là hoạt động theo mô hình ransomware-as-a-service. Tuy nhiên, nó duy trì một cổng dữ liệu rò rỉ trên dark web để tăng áp lực lên nạn nhân, yêu cầu thanh toán từ hàng trăm nghìn đến hàng triệu đô la.

## Từ ClickFix đến ransomware

Trong quá khứ, Interlock đã sử dụng các cập nhật trình duyệt và VPN giả để cài đặt malware và xâm nhập vào các mạng.

Theo [các nhà nghiên cứu của Sekoia](https://blog.sekoia.io/interlock-ransomware-evolving-under-the-radar/), nhóm ransomware Interlock đã bắt đầu sử dụng các cuộc tấn công ClickFix vào tháng 1 năm 2025.

Interlock đã sử dụng ít nhất bốn URL để lưu trữ các thông báo CAPTCHA giả, yêu cầu người dùng thực hiện một lệnh trên máy tính của họ để xác thực bản thân và tải xuống một công cụ được quảng cáo.

Các nhà nghiên cứu cho biết họ đã phát hiện captcha độc hại trên bốn trang web khác nhau, mô phỏng các cổng Microsoft hoặc Advanced IP Scanner:

* microsoft-msteams\[.\]com/additional-check.html
* microstteams\[.\]com/additional-check.html
* ecologilives\[.\]com/additional-check.html
* advanceipscaner\[.\]com/additional-check.html

Tuy nhiên, chỉ có trang web giả mạo Advanced IP Scanner, một công cụ quét IP phổ biến thường được sử dụng bởi nhân viên IT, dẫn đến việc tải xuống một trình cài đặt độc hại.

![Trang lưu trữ mồi ClickFix của Interlock](https://www.bleepstatic.com/images/news/u/1220909/2025/April/clickfix-page.jpg)

**Trang lưu trữ mồi ClickFix của Interlock**  
_Nguồn: Sekoia_

Nhấp vào nút 'Fix it' sẽ sao chép lệnh PowerShell độc hại vào clipboard của nạn nhân. Nếu lệnh này được thực thi trong một Command Prompt hoặc hộp thoại Run của Windows, nó sẽ tải xuống một payload PyInstaller có kích thước 36MB.

Đồng thời, trang web AdvanceIPScanner hợp pháp sẽ mở trong một cửa sổ trình duyệt để giảm bớt sự nghi ngờ.

Payload độc hại cài đặt một bản sao hợp pháp của phần mềm mà nó giả mạo và đồng thời thực thi một script PowerShell nhúng chạy trong một cửa sổ ẩn.

Script này đăng ký một key Run trong Windows Registry để duy trì hoạt động và sau đó thu thập và xuất khẩu thông tin hệ thống bao gồm phiên bản OS, mức độ quyền người dùng, các tiến trình đang chạy và các ổ đĩa có sẵn.

Sekoia đã quan sát thấy command and control (C2) phản hồi với nhiều payload khác nhau, bao gồm LummaStealer, BerserkStealer, keyloggers và Interlock RAT.

Cái sau là một trojan đơn giản có thể được cấu hình động, hỗ trợ xuất khẩu tệp, thực thi lệnh shell, và chạy các DLL độc hại.

![Các lệnh mà Interlock RAT hỗ trợ](https://www.bleepstatic.com/images/news/u/1220909/2025/April/rat-commands.jpg)

**Các lệnh mà Interlock RAT hỗ trợ**  
_Nguồn: Sekoia_

Sau khi thỏa hiệp ban đầu và triển khai RAT, các nhà điều hành Interlock đã sử dụng thông tin xác thực bị đánh cắp để di chuyển theo chiều ngang qua RDP, trong khi Sekoia cũng đã thấy PuTTY, AnyDesk và LogMeIn được sử dụng trong một số cuộc tấn công.

Bước cuối cùng trước khi thực thi ransomware là xuất khẩu dữ liệu, với các tệp bị đánh cắp được tải lên Azure Blobs do kẻ tấn công kiểm soát.

Biến thể Windows của Interlock được thiết lập (thông qua một tác vụ theo lịch) để chạy hàng ngày vào lúc 08:00 PM, nhưng nhờ vào việc lọc dựa trên phần mở rộng tệp, điều này không gây ra nhiều lớp mã hóa mà chỉ phục vụ như một biện pháp dự phòng.

Sekoia cũng báo cáo rằng thông điệp chuộc đã phát triển, với các phiên bản mới nhất tập trung nhiều hơn vào khía cạnh pháp lý của vụ rò rỉ dữ liệu và các hậu quả quy định nếu dữ liệu bị đánh cắp bị công khai.

**Thông điệp chuộc mới nhất của Interlock**  
_Nguồn: BleepingComputer_

Các cuộc tấn công ClickFix hiện đã được nhiều tác nhân đe dọa khác áp dụng, bao gồm các nhóm ransomware khác và các hacker Bắc Triều Tiên.

Tháng trước, Sekoia phát hiện rằng nhóm hacker Bắc Triều Tiên nổi tiếng Lazarus đang sử dụng [các cuộc tấn công ClickFix nhắm vào những người tìm việc](https://www.bleepingcomputer.com/news/security/north-korean-hackers-adopt-clickfix-attacks-to-target-crypto-firms/) trong ngành công nghiệp tiền điện tử.