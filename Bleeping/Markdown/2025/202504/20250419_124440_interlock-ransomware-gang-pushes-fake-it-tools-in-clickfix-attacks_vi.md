# Băng nhóm ransomware Interlock đẩy các công cụ CNTT giả trong các cuộc tấn công ClickFix

![Hacker](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

Băng nhóm ransomware Interlock hiện đang sử dụng các cuộc tấn công ClickFix giả mạo các công cụ CNTT để xâm nhập mạng doanh nghiệp và triển khai phần mềm độc hại mã hóa tệp trên các thiết bị.

ClickFix là một chiến thuật kỹ thuật xã hội, nơi nạn nhân bị lừa thực hiện các lệnh PowerShell nguy hiểm trên hệ thống của họ để giả vờ sửa lỗi hoặc xác thực bản thân, dẫn đến việc cài đặt phần mềm độc hại.

Mặc dù đây [không phải là lần đầu tiên](https://www.bleepingcomputer.com/news/security/fake-google-chrome-errors-trick-you-into-running-malicious-powershell-scripts/) ClickFix được liên kết với các nhiễm ransomware, sự xác nhận về Interlock cho thấy một xu hướng ngày càng tăng của những kẻ đe dọa kiểu này sử dụng chiến thuật này.

Interlock là một hoạt động ransomware được khởi động vào cuối tháng 9 năm 2024, [nhắm mục tiêu vào các máy chủ FreeBSD](https://www.bleepingcomputer.com/news/security/meet-interlock-the-new-ransomware-targeting-freebsd-servers/) và các hệ thống Windows.

Không ai tin rằng Interlock hoạt động theo mô hình ransomware-as-a-service. Tuy nhiên, nó duy trì một cổng thông tin rò rỉ dữ liệu trên dark web để tăng cường áp lực lên nạn nhân, yêu cầu thanh toán dao động từ hàng trăm nghìn đến hàng triệu đô la.

## Từ ClickFix đến ransomware

Trong quá khứ, Interlock đã sử dụng các bản cập nhật giả mạo của trình duyệt và ứng dụng VPN để cài đặt phần mềm độc hại và xâm phạm mạng.

Theo các [nhà nghiên cứu Sekoia](https://blog.sekoia.io/interlock-ransomware-evolving-under-the-radar/), băng nhóm ransomware Interlock đã bắt đầu sử dụng các cuộc tấn công ClickFix vào tháng 1 năm 2025.

Interlock đã sử dụng ít nhất bốn URL để lưu trữ các thông báo CAPTCHA giả mạo, yêu cầu người dùng thực hiện một lệnh trên máy tính của họ để xác thực và tải xuống một công cụ được giới thiệu.

Các nhà nghiên cứu cho biết họ đã phát hiện ra các captcha độc hại trên bốn trang web khác nhau, mô phỏng các cổng thông tin của Microsoft hoặc Advanced IP Scanner:

* microsoft-msteams\[.\]com/additional-check.html
* microstteams\[.\]com/additional-check.html
* ecologilives\[.\]com/additional-check.html
* advanceipscaner\[.\]com/additional-check.html

Tuy nhiên, chỉ có trang giả mạo Advanced IP Scanner, một công cụ quét IP phổ biến thường được sử dụng bởi nhân viên CNTT, dẫn đến việc tải xuống một trình cài đặt độc hại.

![Trang hosting mồi ClickFix của Interlock](https://www.bleepstatic.com/images/news/u/1220909/2025/April/clickfix-page.jpg)

**Trang hosting mồi ClickFix của Interlock**  
_Nguồn: Sekoia_

Nhấp vào nút 'Sửa chữa' sao chép lệnh PowerShell độc hại vào clipboard của nạn nhân. Nếu được thực hiện trong Command Prompt hoặc hộp thoại Windows Run, nó sẽ tải xuống một payload PyInstaller có dung lượng 36MB.

Đồng thời, trang web AdvanceIPScanner hợp pháp sẽ mở trong một cửa sổ trình duyệt để giảm nghi ngờ.

Payload độc hại cài đặt một bản sao hợp pháp của phần mềm mà nó giả vờ là và đồng thời thực hiện một script PowerShell nhúng chạy trong một cửa sổ ẩn.

Script này đăng ký một khóa Run trong Windows Registry để duy trì và sau đó thu thập và exfiltrate thông tin hệ thống bao gồm phiên bản OS, cấp độ quyền người dùng, các tiến trình đang chạy và các ổ đĩa có sẵn.

Sekoia đã quan sát thấy Command and Control (C2) phản hồi với các payload khác nhau, bao gồm LummaStealer, BerserkStealer, keyloggers và Interlock RAT.

Cái sau là một trojan đơn giản có thể được cấu hình động, hỗ trợ exfiltration tệp, thực thi lệnh shell và chạy các DLL độc hại.

![Các lệnh mà Interlock RAT hỗ trợ](https://www.bleepstatic.com/images/news/u/1220909/2025/April/rat-commands.jpg)

**Các lệnh mà Interlock RAT hỗ trợ**  
_Nguồn: Sekoia_

Sau khi xâm nhập ban đầu và triển khai RAT, các nhà điều hành Interlock đã sử dụng thông tin đăng nhập bị đánh cắp để di chuyển theo chiều ngang qua RDP, trong khi Sekoia cũng thấy PuTTY, AnyDesk và LogMeIn được sử dụng trong một số cuộc tấn công.

Bước cuối cùng trước khi thực thi ransomware là exfiltration dữ liệu, với các tệp bị đánh cắp được tải lên các Azure Blobs do kẻ tấn công kiểm soát.

Biến thể Windows của Interlock được đặt (qua một tác vụ theo lịch) để chạy hàng ngày vào lúc 08:00 PM, nhưng nhờ vào bộ lọc dựa trên phần mở rộng tệp, điều này không gây ra nhiều lớp mã hóa mà phục vụ như một biện pháp dự phòng.

Sekoia cũng báo cáo rằng ghi chú ransomware cũng đã phát triển, với các phiên bản mới nhất tập trung nhiều hơn vào khía cạnh pháp lý của việc rò rỉ dữ liệu và các hậu quả quy định nếu dữ liệu bị đánh cắp bị công khai.

**Ghi chú ransom mới nhất của Interlock**  
_Nguồn: BleepingComputer_

Các cuộc tấn công ClickFix hiện đã được một loạt kẻ đe dọa áp dụng, bao gồm các băng nhóm ransomware khác và tin tặc Bắc Triều Tiên.

Tháng trước, Sekoia phát hiện ra rằng nhóm tin tặc nổi tiếng Lazarus của Bắc Triều Tiên đã sử dụng [các cuộc tấn công ClickFix nhắm mục tiêu vào những người tìm việc](https://www.bleepingcomputer.com/news/security/north-korean-hackers-adopt-clickfix-attacks-to-target-crypto-firms/) trong ngành công nghiệp tiền điện tử.