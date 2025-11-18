# Windows 11 nhận các công cụ mới Cloud Rebuild và Point-in-Time Restore

![Windows 11](https://www.bleepstatic.com/content/hl-images/2024/07/18/Windows--11.jpg)

Microsoft thông báo hai tính năng khôi phục Windows 11 mới hôm nay tại hội nghị nhà phát triển Ignite, gọi là Cloud Rebuild và Point-in-Time Restore (PITR), nhằm giảm thời gian ngưng hoạt động và giúp khôi phục dễ dàng hơn khi gặp sự cố hệ thống hoặc bản cập nhật lỗi.

Các tính năng khôi phục mới này là một phần của [Windows Resiliency Initiative](https://blogs.windows.com/windowsexperience/2025/06/26/the-windows-resiliency-initiative-building-resilience-for-a-future-ready-enterprise/) của Microsoft và được thiết kế để giúp các tổ chức nhanh chóng khôi phục thiết bị khi một thiết bị không thể khởi động hoặc hoạt động đúng.

Tính năng đầu tiên, Point-in-Time Restore (PITR), cho phép người dùng và quản trị viên CNTT quay lại hệ thống Windows 11 về một bản snapshot trước đó, lành mạnh, trong vòng vài phút.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Tương tự như System Restore, PITR khôi phục lại hệ điều hành, các thiết lập và tệp hệ thống về trạng thái đã lưu trước đó. Tuy nhiên, Point-in-Time Restore phát triển trên tính năng System Restore bằng cách chụp toàn bộ snapshot của hệ thống tại các thời điểm khác nhau, vì vậy nó cũng có thể khôi phục tệp cục bộ và ứng dụng.

Microsoft cho biết tính năng này sẽ vào giai đoạn xem trước trong tuần này trên một bản dựng Windows 11 Insider sắp tới.

Microsoft cũng giới thiệu Cloud Rebuild, một công cụ có thể kích hoạt từ xa việc cài đặt lại hoàn toàn Windows 11 từ cloud cho các thiết bị gặp sự cố kéo dài hoặc trở nên không hoạt động.

"Through the Intune portal, admins will be able to select the desired Windows release and language, triggering the PC to download installation media and rebuild itself," [explains Microsoft](https://blogs.windows.com/windowsexperience/2025/11/18/preparing-for-whats-next-windows-security-and-resiliency-innovations-help-organizations-mitigate-risks-recover-faster-and-prepare-for-the-era-of-ai/).

"Quá trình tận dụng Autopilot để cung cấp không cần can thiệp, đảm bảo đăng ký MDM và tuân thủ chính sách sau khi rebuild. Việc khôi phục dữ liệu và thiết lập người dùng được đơn giản hóa thông qua OneDrive và Windows Backup for Organizations. Cách tiếp cận này sẽ giảm thời gian ngừng hoạt động từ hàng giờ — hoặc hàng ngày — xuống còn một phần nhỏ của thời gian đó."

Microsoft cho biết cả hai tính năng này sẽ được tích hợp trực tiếp trong Microsoft Intune trong nửa đầu năm 2026, cho phép quản trị viên Windows kích hoạt các hành động khôi phục từ xa, phối hợp khắc phục trên toàn doanh nghiệp và điều khiển chức năng Windows Recovery Environment (WinRE) trực tiếp từ Intune.

Đầu tháng này, Microsoft bắt đầu thử nghiệm phiên bản cập nhật của Quick Machine Recovery (QMR), một công cụ được thiết kế để giúp quản trị viên giải quyết lỗi khởi động Windows mà không cần truy cập vật lý vào thiết bị.

![Quick Machine Recovery in the Advanced Startup menu](https://www.bleepstatic.com/images/news/Microsoft/windows-11/q/quick-machine-recovery/quick-machine-recovery.jpg)

**Cài đặt Quick Machine Recovery trên Windows 11**  
_Nguồn: Microsoft_

Khi Windows 11 gặp lỗi khởi động do thay đổi cấu hình, ổ đĩa có vấn đề hoặc bản cập nhật, nó sẽ tự động khởi chạy Windows Recovery Environment, tải QMR và gửi thông tin crash tới Microsoft.

Dựa trên phân tích dữ liệu này, Microsoft có thể áp dụng các bản sửa từ xa như gỡ bỏ driver hoặc bản cập nhật gây vấn đề và thay đổi các thiết lập cấu hình.

Microsoft cho biết bản phát hành mới nhất cải thiện quy trình sửa chữa khởi động của QMR bằng cách thực hiện một lần quét để phát hiện và giải quyết vấn đề, thay vì lặp đi lặp lại việc tìm kiếm giải pháp trong một vòng lặp.