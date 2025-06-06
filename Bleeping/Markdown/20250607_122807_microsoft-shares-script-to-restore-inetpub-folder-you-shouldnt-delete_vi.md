# Microsoft công bố kịch bản để khôi phục thư mục inetpub mà bạn không nên xóa

![Windows](https://www.bleepstatic.com/content/hl-images/2021/05/17/0_Windows-headpic.jpg)

Microsoft đã phát hành một kịch bản PowerShell để giúp khôi phục một thư mục 'inetpub' trống được tạo bởi cập nhật bảo mật Windows tháng 4 năm 2025 nếu bị xóa. Như Microsoft đã cảnh báo trước đó, thư mục này giúp giảm thiểu một lỗ hổng tăng quyền nghiêm trọng của Windows Process Activation.

Vào tháng 4, sau khi cài đặt các bản cập nhật bảo mật mới, người dùng Windows [bất ngờ phát hiện](https://www.bleepingcomputer.com/news/microsoft/windows-11-april-update-unexpectedly-creates-new-inetpub-folder/) rằng một thư mục C:\\Inetpub trống đã được tạo ra. Khi thư mục này liên quan đến Internet Information Server của Microsoft, người dùng thấy khó hiểu khi nó được tạo ra khi máy chủ web không được cài đặt.

Điều này đã khiến một số người xóa thư mục, khiến họ lại bị lỗ hổng đã được vá. Microsoft cho biết rằng những người đã xóa nó [có thể tái tạo lại bằng tay](https://www.bleepingcomputer.com/news/security/microsoft-windows-inetpub-folder-created-by-security-fix-dont-delete/) bằng cách cài đặt Internet Information Services từ bảng điều khiển "Bật hoặc tắt các tính năng của Windows".

Khi IIS được cài đặt, một thư mục inetpub mới sẽ được thêm vào thư mục gốc của ổ C:\\, với các tệp và quyền sở hữu SYSTEM giống như thư mục được tạo ra bởi các bản cập nhật bảo mật của Windows tháng 4. Nếu bạn không sử dụng IIS, bạn có thể gỡ cài đặt nó bằng cách sử dụng cùng một bảng điều khiển Các tính năng của Windows để xóa nó, để lại thư mục C:\\inetpub.

Vào thứ Tư, trong một bản cập nhật mới cho thông báo CVE-2025-21204, công ty cũng đã chia sẻ một [kịch bản khắc phục](https://www.powershellgallery.com/packages/Set-InetpubFolderAcl/1.0) giúp quản trị viên tái tạo lại thư mục này từ shell PowerShell bằng cách sử dụng các lệnh sau:

```
Install-Script -Name Set-InetpubFolderAcl

C:\Program` Files\WindowsPowerShell\Scripts\Set-InetpubFolderAcl.ps1
```

Như Redmond giải thích, kịch bản này sẽ đặt các quyền IIS đúng để ngăn chặn truy cập trái phép và các lỗ hổng tiềm ẩn liên quan đến CVE-2025-21204.

Nó cũng sẽ cập nhật các mục danh sách kiểm soát truy cập (ACL) cho thư mục DeviceHealthAttestation trên các hệ thống Windows Server để đảm bảo nó được bảo mật nếu được tạo bởi các bản cập nhật bảo mật tháng 2 năm 2025.

![Chạy Set-InetpubFolderAcl](https://www.bleepstatic.com/images/news/u/1109292/2025/Using-Set-InetpubFolderAcl.png)

_Thực hiện kịch bản trong Windows PowerShell (BleepingComputer)_

## ​Microsoft: "Đừng xóa nó."

Lỗi bảo mật ([CVE-2025-21204](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-21204)) được giảm thiểu bởi thư mục inetpub này (được tạo tự động bởi các bản cập nhật bảo mật của tháng 4 ngay cả trên các hệ thống mà nền tảng máy chủ web IIS chưa được cài đặt trước đó) do một vấn đề về giải quyết liên kết không chính xác trong Ngăn xếp Cập nhật Windows.

Điều này có thể có nghĩa là Cập nhật Windows có thể theo dõi các liên kết tượng trưng trên các thiết bị chưa được vá theo cách mà có thể để cho các kẻ tấn công tại chỗ lừa hệ điều hành truy cập hoặc chỉnh sửa các tệp hoặc thư mục không mong muốn.

Microsoft cho biết việc khai thác thành công cho phép các kẻ tấn công có quyền hạn thấp tăng quyền và thao tác hoặc thực hiện các thao tác quản lý tệp trong bối cảnh của tài khoản NT AUTHORITY\\SYSTEM.

Mặc dù việc xóa thư mục không gây ra sự cố nào khi sử dụng Windows trong các thử nghiệm của chúng tôi, Microsoft [nói với BleepingComputer](https://www.bleepingcomputer.com/news/security/microsoft-windows-inetpub-folder-created-by-security-fix-dont-delete/) rằng nó được tạo một cách cố ý và không nên bị xóa. Redmond đã đưa ra cảnh báo tương tự trong một thông báo cập nhật cho lỗ hổng bảo mật CVE-2025-21204 để cảnh báo người dùng không được xóa thư mục trống %systemdrive%\\inetpub.

"Thư mục này không nên bị xóa bất kể liệu các Dịch vụ Thông tin Internet (IIS) có hoạt động trên thiết bị mục tiêu hay không. Hành vi này là một phần của những thay đổi nhằm tăng cường bảo vệ và không yêu cầu bất kỳ hành động nào từ các quản trị viên CNTT và người dùng cuối," công ty nhấn mạnh.

Chuyên gia an ninh mạng Kevin Beaumont cũng đã chứng minh rằng người dùng không có quyền quản trị có thể lạm dụng thư mục này [để chặn các bản cập nhật Windows](https://www.bleepingcomputer.com/news/microsoft/windows-inetpub-security-fix-can-be-abused-to-block-future-updates/) không được cài đặt bằng cách tạo một giao lộ giữa C:\\inetpub và bất kỳ tệp Windows nào.