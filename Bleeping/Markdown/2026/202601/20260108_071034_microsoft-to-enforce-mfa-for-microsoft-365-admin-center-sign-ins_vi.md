# Microsoft sẽ bắt buộc MFA cho các lần đăng nhập vào Microsoft 365 admin center

![Microsoft](https://www.bleepstatic.com/content/hl-images/2025/08/06/Microsoft.jpg)

Microsoft sẽ bắt đầu thực thi xác thực đa yếu tố (MFA) cho tất cả người dùng truy cập Microsoft 365 admin center bắt đầu từ tháng tới.

Mặc dù yêu cầu MFA cho admin center đã bắt đầu triển khai từ tháng 2 năm 2025, Microsoft sẽ giờ buộc mọi người dùng phải tuân thủ và sẽ chặn những người chưa kích hoạt MFA khỏi đăng nhập vào cổng quản trị Microsoft 365 sau khi thay đổi có hiệu lực vào ngày 9 tháng 2 năm 2026.

Điều này sẽ ảnh hưởng đến các URL portal.office.com/adminportal/home, admin.cloud.microsoft và admin.microsoft.com được sử dụng bởi quản trị viên IT để quản lý tài khoản và dịch vụ Microsoft 365.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Microsoft cho biết việc thực thi MFA cho tất cả các lần đăng nhập vào admin center bổ sung lớp bảo vệ quan trọng vượt ra ngoài bảo mật bằng mật khẩu thông thường, khiến kẻ tấn công khó xâm phạm các tài khoản hơn nhiều.

[Microsoft cho biết](https://admin.microsoft.com/#/MessageCenter/:/messages/MC1215070):

> Việc triển khai MFA trong Microsoft 365 admin center làm giảm đáng kể rủi ro bị xâm phạm tài khoản, ngăn chặn truy cập trái phép và bảo vệ dữ liệu nhạy cảm.
> 
> 
> Bằng cách thêm một lớp bảo vệ bổ sung ngoài xác thực tên người dùng và mật khẩu thông thường, MFA khiến kẻ tấn công khó đánh cắp dữ liệu hơn và ngăn chặn truy cập trái phép do lừa đảo, tấn công nhồi nhét thông tin đăng nhập, brute-force, hoặc tái sử dụng mật khẩu.

Microsoft cũng kêu gọi các quản trị viên hành động ngay để tránh gián đoạn cho hoạt động IT và các chức năng quản trị, vì các tổ chức không bật MFA trước thời hạn vào tháng Hai sẽ gặp gián đoạn truy cập khi quản trị viên bắt đầu gặp lỗi đăng nhập.

Quản trị viên toàn cầu có thể cấu hình MFA bằng [trình hướng dẫn cài đặt của Microsoft](https://aka.ms/MFAWizard) hoặc bằng cách làm theo [tài liệu chính thức](https://learn.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide). Người dùng cá nhân có thể kiểm tra phương thức xác minh của họ và thêm các tùy chọn xác thực thông qua [cổng cài đặt MFA của Microsoft](https://aka.ms/mfasetup).

Microsoft cũng đã thực thi MFA cho các lần đăng nhập vào Azure Portal trên tất cả các tenant kể từ tháng 3 năm 2025, một thay đổi đã được công bố [vào tháng 5 năm 2024](https://www.bleepingcomputer.com/news/microsoft/microsoft-will-start-enforcing-azure-multi-factor-authentication-MFA-in-july-2024/), khi bắt đầu yêu cầu MFA cho tất cả người dùng đăng nhập vào Azure để quản trị tài nguyên. Microsoft cũng [bắt đầu thực thi MFA](https://www.bleepingcomputer.com/news/microsoft/microsoft-to-enforce-mfa-for-azure-resource-management-in-october/) trên Azure CLI, PowerShell, SDKs và APIs vào tháng 10 năm 2025 nhằm bảo vệ tài khoản người dùng trước các cuộc tấn công.

Một [nghiên cứu của Microsoft](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/final/en-us/microsoft-brand/documents/MFA-Microsoft-Research-Paper-update.pdf) từ tháng 11 năm 2023 cho thấy 99,99% các tài khoản được bảo vệ bằng MFA đã chặn thành công các nỗ lực hack, và MFA cũng giảm xác suất bị xâm phạm tài khoản tới 98,56% ngay cả khi thông tin đăng nhập bị lộ.