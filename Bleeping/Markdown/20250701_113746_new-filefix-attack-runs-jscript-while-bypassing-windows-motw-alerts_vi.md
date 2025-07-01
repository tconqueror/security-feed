# Cuộc tấn công FileFix mới thực thi JScript trong khi vượt qua cảnh báo MoTW của Windows

![Cuộc tấn công FileFix mới thực thi JScript trong khi vượt qua cảnh báo MoTW của Windows](https://www.bleepstatic.com/content/hl-images/2024/12/15/hacker-card.jpg)

Một cuộc tấn công FileFix mới cho phép thực thi các script độc hại trong khi vượt qua sự bảo vệ Mark of the Web (MoTW) trong Windows bằng cách khai thác cách mà các trình duyệt xử lý các trang web HTML được lưu.

Kỹ thuật này được phát triển bởi nhà nghiên cứu bảo mật mr.d0x. Tuần trước, nhà nghiên cứu đã chỉ ra cách [phương pháp FileFix đầu tiên](https://www.bleepingcomputer.com/news/security/filefix-attack-weaponizes-windows-file-explorer-for-stealthy-powershell-commands/) hoạt động như một sự thay thế cho những cuộc tấn công 'ClickFix' bằng cách đánh lừa người dùng dán một lệnh PowerShell được ngụy trang vào thanh địa chỉ File Explorer.

Cuộc tấn công bao gồm một trang phishing để lừa nạn nhân sao chép một lệnh PowerShell độc hại. Khi họ dán nó vào File Explorer, Windows thực thi PowerShell, làm cho đây là một cuộc tấn công rất tinh vi.

Với [cuộc tấn công FileFix mới](http://mrd0x.com/filefix-part-2/), một kẻ tấn công sẽ sử dụng social engineering để lừa người dùng lưu một trang HTML (sử dụng Ctrl+S) và đổi tên nó thành .HTA, cái mà tự động thực thi JScript nhúng thông qua mshta.exe.

HTML Applications (.HTA) được coi là công nghệ lạc hậu. Loại tệp Windows này có thể được sử dụng để thực thi nội dung HTML và script bằng cách sử dụng mshta.exe hợp pháp trong ngữ cảnh của người dùng hiện tại.

Nhà nghiên cứu đã phát hiện rằng khi các tệp HTML được lưu dưới dạng "Webpage, Complete" (với loại MIME là text/html), chúng không nhận được thẻ MoTW, cho phép thực thi script mà không có cảnh báo cho người dùng.

Khi nạn nhân mở tệp .HTA, script độc hại được nhúng sẽ chạy ngay lập tức mà không có bất kỳ cảnh báo nào.

Phần khó khăn nhất trong cuộc tấn công là bước social engineering, nơi nạn nhân cần phải bị đánh lừa để lưu một trang web và đổi tên nó.

Một cách để vượt qua điều này là thiết kế một miếng mồi hiệu quả hơn, chẳng hạn như trang web độc hại yêu cầu người dùng lưu mã xác thực nhiều yếu tố (MFA) để duy trì quyền truy cập trong tương lai vào một dịch vụ.

Trang sẽ hướng dẫn người dùng nhấn Ctrl+S (Save As), chọn "Webpage, Complete," và lưu tệp với tên 'MfaBackupCodes2025.hta.'

![Ví dụ về trang độc hại](https://www.bleepstatic.com/images/news/u/1220909/2025/June/page.png)

**Ví dụ về trang độc hại**  
_Nguồn: mr.d0x_

Mặc dù điều này yêu cầu nhiều tương tác hơn, nếu trang web độc hại trông giống thật và người dùng không có hiểu biết sâu về các phần mở rộng tệp và cảnh báo bảo mật, họ vẫn có thể bị mắc bẫy.

Một chiến lược phòng thủ hiệu quả chống lại biến thể này của cuộc tấn công FileFix là vô hiệu hóa hoặc xóa nhị phân 'mshta.exe' khỏi môi trường của bạn (được tìm thấy trong C:\\Windows\\System32 và C:\\Windows\\SysWOW64).

Ngoài ra, hãy xem xét bật khả năng hiển thị phần mở rộng tệp trên Windows và chặn các tệp đính kèm HTML trong email.