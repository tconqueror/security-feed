# Microsoft 365 'Direct Send' bị lạm dụng để gửi email lừa đảo như người dùng nội bộ

![Microsoft 365](https://www.bleepstatic.com/content/hl-images/2023/10/06/Microsoft_365.jpg)

Một chiến dịch lừa đảo đang diễn ra đã lạm dụng một tính năng ít được biết đến trong Microsoft 365 gọi là "Direct Send" để né tránh việc phát hiện bởi bảo mật email và đánh cắp thông tin đăng nhập.

Direct Send là một tính năng của Microsoft 365 cho phép các thiết bị, ứng dụng hoặc dịch vụ đám mây tại chỗ gửi email thông qua máy chủ thông minh của người thuê nhà như thể chúng xuất phát từ miền của tổ chức. Nó được thiết kế để sử dụng bởi các máy in, máy quét và các thiết bị khác cần gửi tin nhắn thay mặt cho công ty.

Tuy nhiên, tính năng này là một [rủi ro bảo mật đã được biết đến](http://www.jumpsec.com/guides/microsoft-direct-send-phishing-abuse-primitive/), vì nó không yêu cầu xác thực, cho phép người dùng từ xa gửi email có vẻ nội bộ từ miền của công ty.

Microsoft khuyến nghị rằng chỉ những khách hàng nâng cao mới nên sử dụng tính năng này, vì độ an toàn của nó phụ thuộc vào việc Microsoft 365 có được cấu hình chính xác hay không và máy chủ thông minh có được bảo vệ đúng cách hay không.

"Chúng tôi khuyến nghị chỉ nên sử dụng Direct Send cho các khách hàng nâng cao sẵn sàng nhận trách nhiệm của các quản trị viên máy chủ email," [Microsoft giải thích](https://learn.microsoft.com/en-us/exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-microsoft-365-or-office-365#direct-send-send-mail-directly-from-your-device-or-application-to-microsoft-365-or-office-365).

"Bạn cần làm quen với việc thiết lập và tuân theo các thực hành tốt nhất để gửi email qua internet. Khi được cấu hình và quản lý đúng cách, Direct Send là một lựa chọn an toàn và khả thi. Nhưng khách hàng sẽ gặp rủi ro misconfiguration có thể làm gián đoạn dòng email hoặc đe dọa an toàn cho giao tiếp của họ."

Công ty đã chia sẻ các cách để tắt tính năng này, được giải thích trong phần sau của bài viết, và cho biết họ đang làm việc để loại bỏ tính năng này.

## Direct Send bị lạm dụng trong một chiến dịch lừa đảo

Chiến dịch lừa đảo này được phát hiện bởi nhóm Phát hiện và Phản hồi Dữ liệu Quản lý Varonis (MDDR), người đã cho BleepingComputer biết rằng nó đang nhắm đến hơn 70 tổ chức trên tất cả các ngành, với 95% nạn nhân có trụ sở tại Hoa Kỳ.

Varonis cho biết chiến dịch bắt đầu vào tháng 5 năm 2025, với hơn 95% các công ty bị nhắm đến có trụ sở tại Hoa Kỳ.

"Nạn nhân thuộc nhiều lĩnh vực kinh doanh khác nhau, nhưng hơn 90% các mục tiêu đã xác định hoạt động trong lĩnh vực Dịch vụ Tài chính, Xây dựng, Kỹ thuật, Sản xuất, Chăm sóc sức khỏe và Bảo hiểm," Joseph Avanzato, Trưởng Nhóm Hoạt động An ninh và Pháp y, đã nói với BleepingComputer.

"Dịch vụ Tài chính là mục tiêu phổ biến nhất, tiếp theo là Sản xuất, Xây dựng/Kỹ thuật và Chăm sóc sức khỏe/Bảo hiểm."

Báo cáo [Varonis giải thích](https://www.varonis.com/blog/direct-send-exploit) rằng các cuộc tấn công được gửi thông qua PowerShell sử dụng máy chủ thông minh của công ty bị nhắm đến (company-com.mail.protection.outlook.com), tạo điều kiện cho một kẻ tấn công gửi tin nhắn có vẻ nội bộ từ các địa chỉ IP bên ngoài.

Một ví dụ về lệnh PowerShell có thể gửi email thông qua tính năng Direct Send là:

```
Send‑MailMessage -SmtpServer company‑com.mail.protection.outlook.com -To joe@company.com -From joe@company.com -Subject "New Missed Fax‑msg" -Body "You have received a call! Click on the link to listen to it. Listen Now" -BodyAsHtml
```

Phương pháp này hoạt động bởi vì việc sử dụng Direct Send với máy chủ thông minh không yêu cầu xác thực và đối xử với người gửi như nội bộ, cho phép các tác nhân đe dọa bỏ qua SPF, DKIM, DMARC và các quy tắc lọc khác.

Các chiến dịch email giả mạo thông báo hộp thư thoại hoặc fax với các tiêu đề email "Người gọi để lại tin nhắn VM." Đính kèm trong các email là các tệp PDF có tiêu đề 'Fax-msg', 'Người gọi để lại tin nhắn VM', 'Chơi\_VM-Now' hoặc 'Nghe'.

![Email lừa đảo từ chiến dịch](https://www.bleepstatic.com/images/news/security/m/microsoft/m/microsoft-365/directsend-phishing/phishing-email.jpg)

**Email lừa đảo từ chiến dịch**  
_Nguồn: Varonis_

Điều bất thường về chiến dịch này là các tệp đính kèm PDF không chứa liên kết đến các trang lừa đảo.

Thay vào đó, các tài liệu hướng dẫn mục tiêu quét mã QR bằng camera smartphone của họ để nghe hộp thư thoại. Các tài liệu PDF cũng được gắn nhãn với logo của công ty để làm cho chúng có vẻ hợp pháp hơn.

![Tài liệu PDF với mã QR](https://www.bleepstatic.com/images/news/security/m/microsoft/m/microsoft-365/directsend-phishing/sample-phishing-email.jpg)

**Tài liệu PDF với mã QR**  
_Nguồn: BleepingComputer_

Quét mã QR và mở liên kết sẽ dẫn bạn đến một trang lừa đảo hiển thị một mẫu đăng nhập Microsoft giả, sẽ được sử dụng để đánh cắp thông tin đăng nhập của nhân viên.

Trong một trường hợp được Varonis ghi nhận, nơi một công ty đã nhận được cảnh báo về hành vi bất thường, các tác nhân đe dọa đã sử dụng PowerShell để gửi email qua máy chủ thông minh từ một địa chỉ IP ở Ukraina là 139.28.36\[.\]230 và các địa chỉ khác trong cùng một phạm vi. 

Những tin nhắn này đã thất bại trong các kiểm tra SPF và DMARC, nhưng chúng đã được xem là lưu lượng nội bộ đáng tin cậy bởi vì chúng được gửi qua máy chủ thông minh nội bộ.

Trong một email khác từ chiến dịch này được BleepingComputer ghi nhận, email có vẻ xuất phát từ một địa chỉ email nội bộ và được gửi qua máy chủ thông minh của tổ chức mặc dù cũng thất bại trong SPF, DKIM và DMARC. Email này có nguồn gốc từ địa chỉ IP 51.89.86\[.\]105.

Varonis đã chia sẻ thêm các chỉ số xâm nhập (IOCs) trong báo cáo của họ, bao gồm các miền được sử dụng trong chiến dịch.

## Giảm thiểu các cuộc tấn công lừa đảo Direct Send

Để giảm thiểu mối đe dọa này, Varonis khuyến nghị bật cài đặt "[Reject Direct Send](https://techcommunity.microsoft.com/blog/exchange/introducing-more-control-over-direct-send-in-exchange-online/4408790?WT.mc%5Fid=M365-MVP-9501)" trong Trung tâm Quản trị Exchange, tính năng mà Microsoft đã giới thiệu vào tháng 4 năm 2025.

Microsoft đã giới thiệu tính năng này vì họ thường đề nghị các công ty bật chế độ mềm SPF để ngăn chặn các lỗi định tuyến tiềm tàng. Tuy nhiên, điều này đã khiến việc chặn email được gửi qua Direct Send trở nên không thể.

"Khi SPF cung cấp sự bảo vệ khỏi việc giả mạo miền của bạn, chúng tôi khuyến nghị khách hàng sử dụng cấu hình SPF Soft Fail do khả năng các kịch bản định tuyến hợp lệ có thể gặp phải lỗi SPF," Microsoft giải thích.

"Như vậy, không có tính năng nào tồn tại để chặn lưu lượng Direct Send cho nhiều khách hàng không cần sử dụng nó. Để điều này, chúng tôi đã phát triển cài đặt Reject Direct Send cho Exchange Online và hôm nay công bố Dự kiến công khai cho tính năng này."

Varonis cũng khuyến nghị triển khai một chính sách DMARC nghiêm ngặt (p=reject), đánh dấu các thông điệp nội bộ không được xác thực để xem xét hoặc cách ly, thực thi SPF hardfail trong Bảo vệ Exchange Online, bật các chính sách Chống Giả mạo, và đào tạo nhân viên để phát hiện các nỗ lực lừa đảo QR.

"Direct Send là một tính năng mạnh mẽ, nhưng trong tay sai lầm, nó trở thành một vector tấn công nguy hiểm", Varonis kết luận.

"Nếu bạn không theo dõi thường xuyên các email nội bộ giả mạo hoặc chưa bật những biện pháp bảo vệ này, bây giờ là thời điểm thích hợp. Đừng giả định rằng nội bộ có nghĩa là an toàn."