# Interlock ransomware gang pushes fake IT tools in ClickFix attacks

![Hacker](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

Nhóm ransomware Interlock hiện đang sử dụng các cuộc tấn công ClickFix, mạo danh các công cụ IT để xâm nhập vào mạng doanh nghiệp và triển khai phần mềm mã hóa file trên các thiết bị.

ClickFix là một chiến thuật kỹ thuật xã hội, nơi nạn nhân bị lừa thực thi các lệnh PowerShell nguy hiểm trên hệ thống của họ để giả vờ sửa lỗi hoặc xác thực bản thân, dẫn đến việc cài đặt malware.

Mặc dù đây [không phải là lần đầu tiên](https://www.bleepingcomputer.com/news/security/fake-google-chrome-errors-trick-you-into-running-malicious-powershell-scripts/) ClickFix được liên kết với các nhiễm ransomware, nhưng việc xác nhận về Interlock cho thấy một xu hướng ngày càng tăng trong các kẻ tấn công này sử dụng chiến thuật này.

Interlock là một hoạt động ransomware được khởi động vào cuối tháng 9 năm 2024, [nhắm mục tiêu vào các máy chủ FreeBSD](https://www.bleepingcomputer.com/news/security/meet-interlock-the-new-ransomware-targeting-freebsd-servers/) và các hệ thống Windows.

Interlock không được tin là hoạt động theo mô hình ransomware-as-a-service. Tuy nhiên, nó duy trì một cổng dữ liệu rò rỉ trên dark web để tăng áp lực lên nạn nhân, yêu cầu thanh toán từ hàng trăm nghìn đô la đến hàng triệu đô la.

## Từ ClickFix đến ransomware

Trong quá khứ, Interlock đã sử dụng các bản cập nhật trình duyệt và khách hàng VPN giả mạo để lắp đặt malware và xâm nhập vào các mạng lưới.

Theo [các nhà nghiên cứu Sekoia](https://blog.sekoia.io/interlock-ransomware-evolving-under-the-radar/), nhóm ransomware Interlock đã bắt đầu sử dụng các cuộc tấn công ClickFix từ tháng 1 năm 2025.

Interlock sử dụng ít nhất bốn URL để lưu trữ các hình thức CAPTCHA giả mạo, yêu cầu người dùng thực thi một lệnh trên máy tính của họ để xác thực và tải xuống một công cụ được quảng cáo.

Các nhà nghiên cứu cho biết họ đã phát hiện CAPTCHA độc hại trên bốn trang web khác nhau, mạo danh các cổng thông tin của Microsoft hoặc Advanced IP Scanner:

* microsoft-msteams\[.\]com/additional-check.html
* microstteams\[.\]com/additional-check.html
* ecologilives\[.\]com/additional-check.html
* advanceipscaner\[.\]com/additional-check.html

Tuy nhiên, chỉ trang web mạo danh Advanced IP Scanner, một công cụ quét IP phổ biến thường được sử dụng bởi nhân viên IT, đã dẫn đến việc tải xuống một trình cài đặt độc hại.

![Page hosting Interlock's ClickFix bait](https://www.bleepstatic.com/images/news/u/1220909/2025/April/clickfix-page.jpg)

**Trang web chứa ClickFix bait của Interlock**  
_Nguồn: Sekoia_

Nhấp vào nút 'Sửa chữa nó' sẽ sao chép lệnh PowerShell độc hại vào clipboard của nạn nhân. Nếu được thực thi trong command prompt hoặc hộp thoại Windows Run, nó sẽ tải xuống một payload PyInstaller 36MB.

Cùng lúc đó, trang web AdvanceIPScanner hợp pháp sẽ mở trong một cửa sổ trình duyệt để giảm thiểu sự nghi ngờ.

Payload độc hại sẽ cài đặt một bản sao hợp pháp của phần mềm mà nó giả mạo và đồng thời thực thi một script PowerShell nhúng chạy trong một cửa sổ ẩn.

Script này sẽ đăng ký một khóa Run trong Windows Registry để duy trì vị trí và sau đó thu thập và xuất thông tin hệ thống bao gồm phiên bản OS, cấp độ quyền người dùng, các tiến trình đang chạy, và các ổ đĩa khả dụng.

Sekoia đã quan sát thấy command and control (C2) phản hồi với các payload khác nhau, bao gồm LummaStealer, BerserkStealer, keyloggers và Interlock RAT.

Cái sau là một trojan đơn giản có thể được cấu hình động, hỗ trợ xuất file, thực thi lệnh shell và chạy các DLL độc hại.

![Commands Interlock RAT supports](https://www.bleepstatic.com/images/news/u/1220909/2025/April/rat-commands.jpg)

**Các lệnh mà Interlock RAT hỗ trợ**  
_Nguồn: Sekoia_

Sau khi thỏa hiệp ban đầu và triển khai RAT, các nhà điều hành Interlock đã sử dụng tài khoản bị đánh cắp để di chuyển theo chiều ngang qua RDP, trong khi Sekoia cũng thấy PuTTY, AnyDesk và LogMeIn được sử dụng trong một số cuộc tấn công.

Bước cuối cùng trước khi thực thi ransomware là xuất dữ liệu, với các file bị đánh cắp được tải lên các Azure Blobs do kẻ tấn công kiểm soát.

Biến thể Windows của Interlock được đặt (thông qua một tác vụ đã lên lịch) để chạy hàng ngày vào lúc 08:00 PM, nhưng nhờ vào việc lọc theo kiểu mở rộng file, điều này không gây ra nhiều lớp mã hóa mà chỉ đóng vai trò như một biện pháp dự phòng.

Sekoia cũng báo cáo rằng bản ghi tiền chuộc đã tiến hóa, với các phiên bản mới nhất tập trung nhiều hơn vào khía cạnh pháp lý của việc vi phạm dữ liệu và các hậu quả quy định nếu dữ liệu bị đánh cắp bị công khai.

**Bản ghi tiền chuộc mới nhất của Interlock**  
_Nguồn: BleepingComputer_

Các cuộc tấn công ClickFix hiện đã được nhiều kẻ tấn công khác áp dụng, bao gồm các băng nhóm ransomware khác và các hacker Bắc Triều Tiên.

Tháng trước, Sekoia phát hiện rằng nhóm hacker Bắc Triều Tiên nổi tiếng Lazarus đã sử dụng [các cuộc tấn công ClickFix nhắm mục tiêu vào các người tìm việc](https://www.bleepingcomputer.com/news/security/north-korean-hackers-adopt-clickfix-attacks-to-target-crypto-firms/) trong ngành công nghiệp tiền điện tử.