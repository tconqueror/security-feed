# Microsoft gỡ bỏ PowerShell 2.0 khỏi Windows 11, Windows Server

![PowerShell](https://www.bleepstatic.com/content/hl-images/2025/08/13/PowerShell.jpg)

Microsoft sẽ gỡ bỏ PowerShell 2.0 khỏi Windows bắt đầu từ tháng 8, tám năm sau khi [công bố ngừng hỗ trợ](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/) và giữ nó như một tính năng tùy chọn.

Trình xử lý lệnh đã 14 năm tuổi được giới thiệu cùng Windows 7 đã bị gỡ bỏ cho Windows Insiders từ [tháng 7 năm 2025](https://blogs.windows.com/windows-insider/2025/07/03/announcing-windows-11-insider-preview-build-27891-canary-channel/), với việc phát hành Windows 11 Insider Preview Build 27891 cho kênh Canary.

Như đã được nêu chi tiết trong một [tài liệu hỗ trợ](https://support.microsoft.com/en-us/topic/powershell-2-0-removal-from-windows-fe6d1edc-2ed2-4c33-b297-afe82a64200a) được công bố hôm thứ hai, Microsoft sẽ gỡ bỏ vĩnh viễn PowerShell 2.0 khỏi Windows 11 phiên bản 24H2, bắt đầu từ tháng 8, và khỏi Windows Server 2025 vào tháng 9.

"Đối với hầu hết người dùng và tổ chức, sự thay đổi này sẽ không có gì đặc biệt – các phiên bản mới hơn của PowerShell như PowerShell 5.1 và PowerShell 7.x vẫn tiếp tục có sẵn và được hỗ trợ. Tuy nhiên, nếu bạn có các script hoặc phần mềm cũ phụ thuộc rõ ràng vào PowerShell 2.0, bạn sẽ cần có hành động và cập nhật chúng hoặc sử dụng một cách thay thế để tránh bất kỳ gián đoạn nào," [Microsoft nói.](https://support.microsoft.com/en-us/topic/powershell-2-0-removal-from-windows-fe6d1edc-2ed2-4c33-b297-afe82a64200a)

"PowerShell 2.0 sẽ bị gỡ bỏ trong một phiên bản sau đó bắt đầu từ tháng 8 năm 2025 cho Windows 11, phiên bản 24H2 và phát hành vào tháng 9 năm 2025 cho Windows Server 2025. Tất cả các phát hành sau này cho Windows 11 và Windows Server 2025 sẽ không bao gồm PowerShell 2.0."

Di chuyển này là một phần của nỗ lực rộng lớn hơn nhằm gỡ bỏ mã cũ, giảm độ phức tạp của hệ thống và cải thiện bảo mật Windows, theo Microsoft.

## Gỡ bỏ ảnh hưởng đến khách hàng sử dụng script và phần mềm cũ

Các khách hàng của Microsoft sử dụng các ứng dụng cũ, bao gồm các sản phẩm máy chủ Microsoft cũ hơn như Exchange, SharePoint và SQL Server, phụ thuộc vào scripting PowerShell 2.0, sẽ bị ảnh hưởng trực tiếp bởi sự thay đổi này.

Mặc dù các script cũ cố gắng khởi động PowerShell 2.0 sẽ tự động mặc định về PowerShell 5.1, phiên bản tương thích ngược cho hầu hết các lệnh và mô-đun, những người sử dụng các công cụ như vậy được khuyên nên cập nhật hệ thống của họ để tránh gián đoạn.

Công ty cũng cho biết khách hàng nên di chuyển các script và công cụ của họ sang PowerShell 5.1 hoặc PowerShell 7 và thay thế phần mềm lỗi thời không thể hoạt động mà không có hỗ trợ PowerShell 2.0, vì một số trình cài đặt của bên thứ ba cũ có thể không hoạt động trên các phiên bản Windows mới hơn khi cố gắng kích hoạt PowerShell 2.0 trong quá trình cài đặt.

"Bằng cách sử dụng PowerShell 7 mới hơn và được hỗ trợ hoặc PowerShell 5.1, bạn có thể giúp đảm bảo rằng các script chạy an toàn hơn," [Microsoft nói thêm](https://learn.microsoft.com/en-us/windows/release-health/windows-message-center#3628) trong một bài đăng mới trên trung tâm thông điệp.

" Nếu bạn có các script hoặc phần mềm cũ phụ thuộc rõ ràng vào PowerShell 2.0, bạn sẽ cần phải cập nhật chúng hoặc sử dụng một cách thay thế để tránh gián đoạn."