# Ứng dụng Microsoft 365 sắp chặn quyền truy cập tệp qua FPRPC theo mặc định

![Microsoft 365](https://www.bleepstatic.com/content/hl-images/2025/07/25/Microsoft-365.jpg)

Microsoft đã thông báo rằng các ứng dụng Microsoft 365 cho Windows sẽ bắt đầu chặn quyền truy cập vào các tệp qua giao thức xác thực di sản FPRPC không an toàn theo mặc định bắt đầu từ cuối tháng Tám.

Những thay đổi này chỉ áp dụng cho các ứng dụng Microsoft 365 cho Windows và sẽ không ảnh hưởng đến người dùng Microsoft Teams trên Windows, Mac, web, iOS hoặc Android.

"Các ứng dụng Microsoft 365 sẽ chặn các giao thức mở tệp không an toàn như FPRPC theo mặc định bắt đầu từ phiên bản 2508, với các cài đặt Trust Center mới để quản lý các giao thức này," công ty đã [nói](https://admin.microsoft.com/#/MessageCenter/:/messages/MC1130392) trong một thông điệp mới của Trung tâm Quản trị Microsoft 365 vào thứ Tư.

"Các thay đổi này nâng cao bảo mật bằng cách giảm bớt tiếp xúc với các công nghệ lỗi thời như Gọi Thủ tục Từ xa FrontPage (FPRPC), FTP và HTTP."

Bắt đầu từ phiên bản 2508 của các ứng dụng Microsoft 365, quá trình mở tệp sử dụng giao thức FPRPC di sản sẽ bị chặn theo mặc định và sẽ mở bằng một giao thức thay thế an toàn hơn. Các thay đổi sẽ trở nên khả dụng chung vào cuối tháng Tám 2025, với thời gian ước tính cho tất cả các khách hàng vào cuối tháng 9.

Các cài đặt Trust Center mới sẽ cho phép người dùng re-enable FPRPC, trừ khi nó được quản lý bởi chính sách nhóm hoặc dịch vụ chính sách đám mây (CPS). Họ cũng sẽ có thể tắt việc mở tệp FTP và HTTP, điều này vẫn sẽ được phép theo mặc định.

Các quản trị viên có thể quản lý cài đặt giao thức xác thực thông qua dịch vụ chính sách đám mây (CPS), trong phần cài đặt Microsoft 365 Apps. Nếu một giao thức bị vô hiệu hóa qua CPS, người dùng sẽ không thể re-enable nó thông qua Trust Center.

Điều này diễn ra ngay sau một [thông báo vào tháng 6](https://www.bleepingcomputer.com/news/microsoft/microsoft-365-to-block-file-access-via-legacy-auth-protocols-by-default/) mà công ty sẽ bắt đầu cập nhật các mặc định bảo mật cho tất cả các khách hàng Microsoft 365 để chặn quyền truy cập tệp qua các giao thức xác thực di sản, chẳng hạn như RPS (Relying Party Suite) và FPRPC (Gọi Thủ tục Từ xa FrontPage), và bảo vệ người dùng chống lại các cuộc tấn công brute-force và phishing lợi dụng các phương thức xác thực lỗi thời.

Kể từ đầu năm, Microsoft cũng đã bắt đầu [vô hiệu hóa tất cả các điều khiển ActiveX](https://www.bleepingcomputer.com/news/microsoft/microsoft-blocks-activex-by-default-in-microsoft-365-office-2024/) trong các phiên bản Windows của Microsoft 365 và ứng dụng Office 2024, và tiết lộ rằng họ sẽ triển khai một tính năng mới của Teams được thiết kế để [chặn ảnh chụp màn hình trong các cuộc họp](https://www.bleepingcomputer.com/news/microsoft/microsoft-teams-will-soon-block-screen-capture-during-meetings/) vào tháng Bảy.

Gần đây hơn, Microsoft [thông báo](https://www.bleepingcomputer.com/news/security/microsoft-outlook-to-block-more-risky-attachments-used-in-attacks/) rằng họ sẽ bao gồm các loại tệp .library-ms và .search-ms trong danh sách các tệp đính kèm Outlook bị chặn bắt đầu vào tháng Bảy.