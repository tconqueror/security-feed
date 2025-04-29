# Microsoft: Windows Server hotpatching sẽ yêu cầu đăng ký

![Windows Server](https://www.bleepstatic.com/content/hl-images/2024/11/12/Windows-Server.jpg)

Microsoft đã thông báo rằng công ty sẽ sớm giới thiệu các gói đăng ký trả phí cho dịch vụ hotpatching trên Windows Server 2025, một dịch vụ cho phép quản trị viên cài đặt các bản cập nhật bảo mật mà không cần khởi động lại.

Công ty khuyến khích các quản trị viên thử hotpatching miễn phí trước khi nó chính thức có sẵn vào tháng 7, khi họ sẽ phải trả phí cho gói đăng ký để thử nghiệm.

Tuy nhiên, Redmond cũng đã cảnh báo những người đang thử nghiệm hotpatching trên Windows Server 2025 trong giai đoạn xem trước nên hủy đăng ký trước ngày 30 tháng 6 để tránh bị tự động đăng ký vào tháng 7.

"Hotpatching cho Windows Server 2025, đã có sẵn trong giai đoạn xem trước vào năm 2024, sẽ chính thức có sẵn dưới dạng dịch vụ đăng ký vào ngày 1 tháng 7 năm 2025. Với hotpatching, chúng tôi đang chuyển một khả năng trước đây chỉ có trên Azure và nay có sẵn cho các máy Windows Server bên ngoài Azure thông qua Azure Arc," [Microsoft cho biết](https://www.microsoft.com/en-us/windows-server/blog/2025/04/24/tired-of-all-the-restarts-get-hotpatching-for-windows-server/).

"Hotpatching hiện tại có sẵn miễn phí để thử nghiệm, nhưng bắt đầu từ tháng 7 với việc ra mắt gói đăng ký, hotpatching cho Windows Server 2025 sẽ được cung cấp với mức phí $1.50 USD cho mỗi lõi CPU mỗi tháng."

Để sử dụng hotpatching trong các môi trường đa đám mây hoặc tại chỗ, bạn cần có một gói đăng ký dịch vụ Hotpatch và một máy chủ kết nối Azure Arc chạy Windows Server 2025 Standard hoặc Datacenter.

Để kích hoạt hotpatching trên máy chủ của bạn, hãy kết nối nó với Azure Arc theo [các bước này](https://learn.microsoft.com/en-us/azure/azure-arc/servers/onboard-windows-server?toc=%2Fwindows-server%2Fget-started%2Ftoc.json&bc=%2Fwindows-server%2Fbreadcrumbs%2Ftoc.json), sau đó vào Azure Update Manager trong Azure Portal, chọn máy chủ Azure Arc mà bạn đã kích hoạt và kiểm tra tùy chọn hotpatching [như đã mô tả ở đây](http://learn.microsoft.com/en-us/azure/update-manager/manage-hot-patching-arc-machines?tabs=manage-single%2Chotpatch-scale).

Hotpatching đã có sẵn từ tháng 2 năm 2022 cho [Windows Server 2022 Datacenter: Azure Edition](https://www.bleepingcomputer.com/news/microsoft/microsoft-announces-hotpatching-for-windows-server-azure-vms/), khi Microsoft thông báo khả năng sử dụng chung cho các máy ảo cốt lõi Windows Server Azure Edition.

Trên các thiết bị mà hotpatching đã được bật, Windows triển khai các bản cập nhật bảo mật bằng cách vá mã trong bộ nhớ của các tiến trình đang chạy mà không cần khởi động lại chúng sau mỗi lần cài đặt và không cần khởi động lại thiết bị.

Tuy nhiên, các máy chủ vẫn cần khởi động lại sau khi cài đặt các bản cập nhật được cung cấp qua kênh cập nhật Windows thông thường (không phải Hotpatch), mà không được bao gồm trong chương trình Hotpatch. Hai ví dụ về các bản cập nhật không thể được cài đặt mà không khởi động lại là các bản cập nhật không phải Windows (chẳng hạn như các bản sửa lỗi .NET) và các bản cập nhật không bảo mật của Windows.

Microsoft cũng đã bắt đầu thử nghiệm hotpatching trong giai đoạn xem trước công khai cho Windows Server 2025 [vào tháng 9 năm 2024](https://www.bleepingcomputer.com/news/microsoft/windows-server-2025-hotpatching-in-public-preview-installs-security-updates-without-restarts/) và trên Windows 11 24H2 và Windows 365 hai tháng sau đó, [vào tháng 11 năm 2024](https://www.bleepingcomputer.com/news/microsoft/microsoft-now-testing-hotpatch-on-windows-11-24h2-and-windows-365/).

Bắt đầu từ tháng 4 năm 2025, các bản cập nhật hotpatch sẽ [chính thức có sẵn cho khách hàng doanh nghiệp](https://www.bleepingcomputer.com/news/microsoft/microsoft-adds-hotpatching-support-to-windows-11-enterprise/) sử dụng Windows 11 Enterprise 24H2 trên hệ thống x64 (AMD/Intel).