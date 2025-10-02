# Microsoft Defender bug triggers erroneous BIOS update alerts

![Microsoft Defender](https://www.bleepstatic.com/content/hl-images/2023/10/11/Microsoft-Defender_for_Endpoint.jpg)

Microsoft đang làm việc để giải quyết một lỗi khiến Defender for Endpoint gắn nhãn không chính xác firmware BIOS (Basic Input/Output System) của một số thiết bị là đã lỗi thời, dẫn đến người dùng được yêu cầu cập nhật nó.

Trong một [service alert](https://admin.cloud.microsoft/Adminportal/Home?source=applauncher#/windowsreleasehealth/:/issue/DZ1163521) được BleepingComputer nhìn thấy, Redmond cho biết rằng sự cố đã biết này ảnh hưởng đến các thiết bị Dell và được gây ra bởi một lỗi logic của Defender for Endpoint.

"Microsoft have identified that a code bug in the Microsoft Defender for Endpoint logic that fetches vulnerabilities for Dell devices is causing impact," công ty cho biết trước đó hôm nay.

"Your organization is affected by this event, and some users receiving Microsoft Defender for Endpoint alerts for the BIOS version of their Dell devices are impacted."

Trong khi công ty đã phát triển một bản sửa lỗi cho lỗi này và hiện đang chuẩn bị triển khai, họ vẫn chưa tiết lộ các khu vực và số lượng khách hàng bị ảnh hưởng bởi các vấn đề Defender XDR đang diễn ra này.

Hôm nay, các kỹ sư của Microsoft cũng đã [sửa các sự cố màn hình đen gây ảnh hưởng tới macOS devices](http://admin.cloud.microsoft/Adminportal/Home?source=applauncher#/windowsreleasehealth/:/issue/DZ1163645) đã được cập nhật sau ngày 29 tháng 9, do một tình trạng deadlock trong Apple enterprise security framework xảy ra khi nhiều nhà cung cấp bảo mật cùng lắng nghe các sự kiện.

Đầu tháng này, Redmond đã [sửa một dương tính giả khác](https://www.bleepingcomputer.com/news/microsoft/microsoft-anti-spam-bug-blocks-links-in-exchange-online-teams/) đang khiến dịch vụ chống thư rác vô tình chặn người dùng Microsoft Teams và Exchange Online khỏi việc mở các URL.

Microsoft cho biết vào thời điểm đó rằng sự cố do anti-spam engine đánh dấu sai các URL nằm trong các URL khác là có khả năng độc hại, điều này cũng dẫn đến một số email bị cách ly.

Kể từ đầu năm, họ cũng đã xử lý các lỗi machine-learning vốn vô tình đánh dấu email từ Adobe trong Exchange Online là thư rác, một lỗi đã khiến hệ thống chống thư rác [cách ly sai email của một số người dùng Exchange Online](https://www.bleepingcomputer.com/news/microsoft/microsoft-exchange-online-bug-mistakenly-quarantines-user-emails/), và một lỗi thứ ba khiến email từ các tài khoản Gmail bị gắn nhãn là thư rác trong Exchange Online một cách nhầm lẫn.

_Câu chuyện này đang phát triển..._