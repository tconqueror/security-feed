# Microsoft công bố các mặc định bảo mật mới cho Windows 365 Cloud PCs

![Windows](https://www.bleepstatic.com/content/hl-images/2025/05/28/Windows-headpic.jpg)

Microsoft đã công bố các mặc định bảo mật mới cho Windows 365 bắt đầu từ nửa cuối năm 2025 và ảnh hưởng đến các Cloud PC mới được cung cấp và tái cung cấp.

Công ty cho biết những thay đổi này bao gồm việc vô hiệu hóa bảng clipboard, ổ đĩa, USB và các điều hướng máy in theo mặc định để ngăn người dùng sao chép tập tin giữa các Cloud PC và thiết bị vật lý qua các chức năng clipboard nhằm giảm thiểu rủi ro đánh cắp dữ liệu và ngăn chặn các cuộc tấn công mã độc.

Tuy nhiên, trong khi các điều hướng USB sẽ bị vô hiệu hóa theo mặc định, chúng chỉ nhắm đến truy cập thiết bị cấp thấp, có nghĩa là các chuột USB, bàn phím và webcam sẽ không bị ảnh hưởng vì chúng được quản lý thông qua điều hướng cấp cao. Những mặc định bảo mật mới này cũng sẽ được áp dụng cho các nhóm host mới được tạo cho Azure Virtual Desktop.

Bắt đầu từ tháng trước, Microsoft cũng đã kích hoạt bảo mật dựa trên ảo hóa, Credential Guard và tính toàn vẹn mã được bảo vệ bởi hypervisor (HVCI) theo mặc định trên các Cloud PC Windows 365 chạy hình ảnh Windows 11 gallery nhằm tạo ra các khu vực bộ nhớ an toàn và ngăn chặn việc thực thi mã độc hại ở cấp độ kernel.

"Windows 365 đang nâng cao bảo mật Cloud PC bằng cách vô hiệu hóa bảng clipboard, ổ đĩa, USB và các điều hướng máy in theo mặc định cho tất cả các Cloud PC mới được cung cấp và tái cung cấp," [Microsoft cho biết](https://techcommunity.microsoft.com/blog/windows-itpro-blog/enhanced-security-defaults-for-windows-365-cloud-pcs/4424914).

"Kể từ tháng 5 năm 2025, tất cả các Cloud PC Windows 365 mới được cung cấp và tái cung cấp chạy hình ảnh Windows 11 gallery đều có VBS, Credential Guard và HVCI được kích hoạt theo mặc định."

Microsoft cũng sẽ hiển thị các banner thông báo trong Trung tâm Quản trị Intune để thông báo cho các quản trị viên CNTT về các thay đổi và cho phép họ ghi đè các mặc định mới bằng chính sách cấu hình thiết bị Intune hoặc đối tượng chính sách nhóm nếu người dùng cuối của họ yêu cầu các khả năng điều hướng cụ thể.

![Banner của Trung tâm quản trị Intune về các mặc định điều hướng mới](https://www.bleepstatic.com/images/news/u//1109292/2025/Intune%20admin%20center%20banner%20about%20new%20redirection%20defaults.jpg)

_Banner của Trung tâm quản trị Intune về các mặc định điều hướng mới (Microsoft)_

​"Khi các Cloud PC mới được cung cấp, các mặc định mới cho việc vô hiệu hóa các điều hướng sẽ được áp dụng," công ty giải thích. "Sau đó, Intune sẽ đồng bộ hóa và thực hiện các cài đặt mong muốn của quản trị viên CNTT từ các chính sách hiện có, ghi đè các cấu hình mặc định. Quy trình này giả định rằng Cloud PC mới đang được thêm vào một nhóm hiện có được chỉ định cho chính sách liên quan."

Vào thứ Ba, Microsoft đã công bố rằng họ sẽ bắt đầu [cập nhật các mặc định bảo mật cho tất cả các thuê bao Microsoft 365](https://www.bleepingcomputer.com/news/microsoft/microsoft-365-to-block-file-access-via-legacy-auth-protocols-by-default/) vào tháng 7 để chặn quyền truy cập vào SharePoint, OneDrive và các tệp Office qua các giao thức xác thực cũ.

Bắt đầu từ tháng sau, Microsoft 365 sẽ tự động chặn xác thực trình duyệt cũ đối với OneDrive và SharePoint sử dụng RPS (Relying Party Suite), cùng với giao thức FPRPC (FrontPage Remote Procedure Call) cho việc mở tệp Office.

Kể từ tháng Giêng, công ty cũng đã bắt đầu [vô hiệu hóa tất cả các điều khiển ActiveX](https://www.bleepingcomputer.com/news/microsoft/microsoft-blocks-activex-by-default-in-microsoft-365-office-2024/) trong phiên bản Windows của Microsoft 365 và ứng dụng Office 2024 và cho biết họ sẽ bắt đầu triển khai một tính năng mới của Teams được thiết kế để [chặn chụp màn hình trong các cuộc họp](https://www.bleepingcomputer.com/news/microsoft/microsoft-teams-will-soon-block-screen-capture-during-meetings/) vào tháng 7.

Microsoft cũng [thông báo](https://www.bleepingcomputer.com/news/security/microsoft-outlook-to-block-more-risky-attachments-used-in-attacks/) vào tuần trước rằng họ sẽ thêm các loại tệp .library-ms và .search-ms vào danh sách các tệp đính kèm bị chặn trong Outlook bắt đầu vào tháng 7.