# Microsoft cảnh báo về việc trì hoãn cập nhật Windows do dấu thời gian không chính xác

![Windows](https://www.bleepstatic.com/content/hl-images/2024/12/16/Windows.jpg)

Microsoft đã xác nhận một vấn đề đã biết mới gây ra sự chậm trễ trong việc cung cấp các bản cập nhật bảo mật Windows tháng 6 năm 2025 do dấu thời gian metadata không chính xác.

Theo như Redmond giải thích trong các thông báo gần đây, lỗi này ảnh hưởng đến các hệ thống Windows 10 và Windows 11 trong các môi trường có chính sách hoãn cập nhật chất lượng cho phép quản trị viên trì hoãn cài đặt cập nhật trên các thiết bị được quản lý.

Trong khi sự trì hoãn triển khai cập nhật là kết quả mong đợi khi sử dụng các chính sách như vậy, dấu thời gian sai cho các bản cập nhật bảo mật tháng 6 sẽ trì hoãn chúng vượt quá khoảng thời gian đã được chỉ định bởi quản trị viên, có thể khiến các hệ thống chưa được vá dễ bị tấn công.

"Một số thiết bị trong môi trường mà các quản trị viên CNTT sử dụng chính sách hoãn cập nhật chất lượng (QU) có thể gặp phải sự chậm trễ trong việc nhận được bản cập nhật bảo mật Windows tháng 6 năm 2025," Microsoft [giải thích](https://support.microsoft.com/en-us/topic/june-10-2025-kb5060842-os-build-26100-4349-47ff300b-2a04-440c-9476-2860d04fce8d#ID0EFF). "Mặc dù bản cập nhật được phát hành vào ngày 10 tháng 6 năm 2025, dấu thời gian metadata của nó phản ánh một ngày là 20 tháng 6 năm 2025. Sự khác biệt này có thể khiến các thiết bị có các khoảng thời gian hoãn đã cấu hình nhận được bản cập nhật muộn hơn dự kiến."

Trong khi vẫn đang điều tra vấn đề đã biết này, Microsoft đã cung cấp cho các quản trị viên Windows một số giải pháp tạm thời để tăng tốc độ triển khai cho các bản cập nhật tháng 6 năm 2025 cho đến khi có biện pháp khắc phục.

Để đạt được điều này, Redmond khuyến nghị tạo một chính sách triển khai khẩn cấp để bỏ qua các cài đặt hoãn và đảm bảo rằng các bản cập nhật được cung cấp ngay lập tức trong các tổ chức sử dụng Windows Autopatch. Như một phương án thay thế, các quản trị viên có thể thay đổi cấu hình hoãn hoặc vòng triển khai để giảm thiểu sự chậm trễ cho các thiết bị bị ảnh hưởng.

Như đã nêu chi tiết trong một [thông báo mới từ Trung tâm Thông điệp Microsoft 365](https://admin.microsoft.com/#/MessageCenter/:/messages/AH1104938), điều này có thể được thực hiện qua các bước sau:

1. Đi đến Intune \\ Devices \\ Windows Updates.
2. Nhấp vào Tab Cập nhật chất lượng.
3. Nhấp "Tạo Chính sách Khẩn cấp".
4. Chọn phiên bản 6B, điền các chi tiết liên quan khác và gán các nhóm Entra mong muốn.
5. Xác nhận cập nhật của bạn như bình thường và gán thêm các nhóm vào chính sách để hoàn tất việc triển khai các bản cập nhật mới nhất cho các thiết bị của bạn.

"Vấn đề trì hoãn này chỉ ảnh hưởng đến thời gian có sẵn của các bản cập nhật cho các tổ chức sử dụng chính sách hoãn QU và không ảnh hưởng đến chất lượng hoặc tính khả áp dụng của bản cập nhật," Microsoft cho biết thêm. "Chúng tôi sẽ không thay đổi giá trị metadata từ giá trị hiện tại là 20 tháng 6 năm 2025. Giải pháp tạm thời này là giải pháp cuối cùng chúng tôi sẽ cung cấp cho vấn đề này."

Vào đầu tháng này, Microsoft [đã phát hành một bản cập nhật cấu hình](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-known-issue-that-breaks-windows-11-updates/) (KB5062324) để giải quyết một vấn đề đã biết gây ra sự cố cập nhật sau khi quét cho các bản cập nhật Windows dừng phản hồi trên một số hệ thống Windows 11.

Vào tháng 5, Redmond [đã sửa một lỗi khác](https://www.bleepingcomputer.com/news/microsoft/microsoft-pushes-fix-for-windows-11-update-0x80240069-errors/) chặn các bản cập nhật tính năng Windows 11 24H2 không được cung cấp thông qua Dịch vụ Cập nhật Windows Server (WSUS) sau khi cài đặt các bản cập nhật bảo mật tháng 4 năm 2025.

Một tháng trước đó, công ty đã giải quyết điều mà họ mô tả là một "vấn đề mã tiềm tàng" đã [khiến một số máy tính được nâng cấp lên Windows 11](https://www.bleepingcomputer.com/news/microsoft/microsoft-some-devices-offered-windows-11-upgrades-despite-intune-blocks/) qua đêm mặc dù có chính sách Intune được thiết kế để chặn nâng cấp Windows 11.

Vào tháng 5, công ty cũng đã công bố rằng họ nhắm [đến việc cập nhật tất cả phần mềm trên PC của bạn](https://www.bleepingcomputer.com/news/microsoft/microsoft-wants-windows-to-update-all-software-on-your-pc/) thông qua một nền tảng orchestrating cập nhật mới được xây dựng trên cơ sở hạ tầng Cập nhật Windows hiện tại, một nền tảng nhằm thống nhất hệ thống cập nhật cho tất cả các ứng dụng, trình điều khiển và thành phần hệ thống trên tất cả các hệ thống Windows.