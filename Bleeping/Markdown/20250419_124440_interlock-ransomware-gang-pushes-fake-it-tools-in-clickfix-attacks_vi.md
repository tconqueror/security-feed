# Băng nhóm ransomware Interlock đẩy các công cụ CNTT giả trong các cuộc tấn công ClickFix

![Hacker](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

Băng nhóm ransomware Interlock hiện sử dụng các cuộc tấn công ClickFix mà mạo danh các công cụ CNTT để xâm nhập vào mạng lưới doanh nghiệp và triển khai phần mềm mã hóa tệp trên các thiết bị.

ClickFix là một chiến thuật kỹ thuật xã hội nơi các nạn nhân bị lừa thực hiện các lệnh PowerShell nguy hiểm trên hệ thống của họ để được cho là khắc phục một lỗi hoặc xác minh bản thân, dẫn đến việc cài đặt phần mềm độc hại.

Dù đây [không phải lần đầu tiên](https://www.bleepingcomputer.com/news/security/fake-google-chrome-errors-trick-you-into-running-malicious-powershell-scripts/) ClickFix được liên kết với các trường hợp nhiễm ransomware, việc xác nhận về Interlock cho thấy một xu hướng ngày càng gia tăng trong các loại tác nhân đe dọa này sử dụng chiến thuật này.

Interlock là một hoạt động ransomware được khởi xướng vào cuối tháng Chín năm 2024, [nhắm đến các máy chủ FreeBSD](https://www.bleepingcomputer.com/news/security/meet-interlock-the-new-ransomware-targeting-freebsd-servers/) và các hệ thống Windows.

Interlock không được cho là hoạt động theo mô hình ransomware-as-a-service. Tuy nhiên, nó duy trì một cổng rò rỉ dữ liệu trên dark web để tăng áp lực lên các nạn nhân, đòi hỏi thanh toán từ hàng trăm nghìn đến hàng triệu USD.

## Từ ClickFix đến ransomware

Trong quá khứ, Interlock đã sử dụng các bản cập nhật trình duyệt và VPN giả để cài đặt phần mềm độc hại và xâm nhập vào các mạng lưới.

Theo [các nhà nghiên cứu Sekoia](https://blog.sekoia.io/interlock-ransomware-evolving-under-the-radar/), băng nhóm ransomware Interlock đã bắt đầu sử dụng các cuộc tấn công ClickFix vào tháng Giêng năm 2025.

Interlock đã sử dụng ít nhất bốn URL để lưu trữ các thông báo CAPTCHA giả cho biết khách truy cập thực hiện một lệnh trên máy tính của họ để xác minh bản thân và tải xuống một công cụ được quảng cáo.

Các nhà nghiên cứu nói rằng họ phát hiện ra CAPTCHA độc hại trên bốn trang web khác nhau, bắt chước các cổng thông tin của Microsoft hoặc Advanced IP Scanner:

* microsoft-msteams\[.\]com/additional-check.html
* microstteams\[.\]com/additional-check.html
* ecologilives\[.\]com/additional-check.html
* advanceipscaner\[.\]com/additional-check.html

Tuy nhiên, chỉ có trang web giả mạo Advanced IP Scanner, một công cụ quét IP phổ biến thường được sử dụng bởi nhân viên CNTT, dẫn đến việc tải xuống một trình cài đặt độc hại.

![Trang lưu trữ mồi ClickFix của Interlock](https://www.bleepstatic.com/images/news/u/1220909/2025/April/clickfix-page.jpg)

**Trang lưu trữ mồi ClickFix của Interlock**  
_Nguồn: Sekoia_

Nhấn vào nút 'Khắc phục' sao chép lệnh PowerShell độc hại vào clipboard của nạn nhân. Nếu được thực thi trong dấu nhắc lệnh hoặc hộp thoại Chạy của Windows, nó sẽ tải xuống một payload PyInstaller 36MB.

Đồng thời, trang web AdvanceIPScanner hợp pháp mở trong một cửa sổ trình duyệt để giảm nghi ngờ.

Payload độc hại cài đặt một bản sao hợp pháp của phần mềm mà nó giả mạo và đồng thời thực thi một tập lệnh PowerShell nhúng chạy trong một cửa sổ ẩn.

Tập lệnh này đăng ký một khóa Chạy trong Registry Windows để duy trì tính bền vững và sau đó thu thập và rò rỉ thông tin hệ thống bao gồm phiên bản OS, mức quyền của người dùng, các tiến trình đang chạy và các ổ đĩa có sẵn.

Sekoia đã quan sát thấy máy chủ chỉ huy và kiểm soát (C2) phản hồi với nhiều payload khác nhau, bao gồm LummaStealer, BerserkStealer, keyloggers và Interlock RAT.

Cái sau là một trojan đơn giản có thể được cấu hình động, hỗ trợ việc rò rỉ tệp, thực thi lệnh shell và chạy các DLL độc hại.

![Các lệnh Interlock RAT hỗ trợ](https://www.bleepstatic.com/images/news/u/1220909/2025/April/rat-commands.jpg)

**Các lệnh Interlock RAT hỗ trợ**  
_Nguồn: Sekoia_

Sau khi xâm nhập ban đầu và triển khai RAT, các оператор Interlock đã sử dụng thông tin đăng nhập bị đánh cắp để di chuyển theo chiều ngang thông qua RDP, trong khi Sekoia cũng thấy rằng PuTTY, AnyDesk và LogMeIn đã được sử dụng trong một số cuộc tấn công.

Bước cuối cùng trước khi thực thi ransomware là rò rỉ dữ liệu, với các tệp bị đánh cắp được tải lên Azure Blobs do kẻ tấn công kiểm soát.

Biến thể Windows của Interlock được đặt (thông qua một tác vụ được lập lịch) để chạy hàng ngày lúc 08:00 PM, nhưng nhờ vào việc lọc dựa trên phần mở rộng tệp, điều này không gây ra nhiều lớp mã hóa mà phục vụ như một biện pháp dư thừa.

Sekoia cũng báo cáo rằng ghi chú đòi tiền đã phát triển, với các phiên bản mới nhất tập trung nhiều hơn vào khía cạnh pháp lý của việc vi phạm dữ liệu và các hậu quả quy định nếu dữ liệu bị đánh cắp bị công bố công khai.

**Ghi chú đòi tiền mới nhất của Interlock**  
_Nguồn: BleepingComputer_

Các cuộc tấn công ClickFix hiện đã được áp dụng bởi một loạt các tác nhân đe dọa, bao gồm các băng nhóm ransomware khác và tin tặc Triều Tiên.

Tháng trước, Sekoia đã phát hiện ra rằng nhóm tin tặc nổi tiếng Lazarus của Triều Tiên đang sử dụng [các cuộc tấn công ClickFix nhắm đến những người tìm việc](https://www.bleepingcomputer.com/news/security/north-korean-hackers-adopt-clickfix-attacks-to-target-crypto-firms/) trong ngành công nghiệp tiền điện tử.