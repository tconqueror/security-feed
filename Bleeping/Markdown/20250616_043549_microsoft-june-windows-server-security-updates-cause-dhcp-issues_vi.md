# Microsoft: Cập nhật bảo mật Windows Server tháng 6 gây ra vấn đề DHCP

![Windows Server](https://www.bleepstatic.com/content/hl-images/2024/05/16/Windows-Server.jpg)

Microsoft đã thừa nhận một vấn đề mới do các bản cập nhật bảo mật tháng 6 năm 2025 gây ra, làm cho dịch vụ DHCP bị treo trên một số hệ thống Windows Server.

Trên các hệ thống Windows Server, dịch vụ Dynamic Host Configuration Protocol (DHCP) Server tự động cấp phát địa chỉ IP và các cấu hình mạng khác, giảm thiểu quản lý mạng và đảm bảo cấu hình địa chỉ IP đáng tin cậy trong các mạng Windows.

Trong các môi trường bị ảnh hưởng, vấn đề DHCP mới đã được Microsoft xác nhận vào cuối tuần qua ngăn cản việc gia hạn địa chỉ IP unicast được áp dụng chính xác qua các thiết bị mạng.

"Dịch vụ DHCP Server có thể ngừng phản hồi một cách không đều đặn sau khi cài đặt bản cập nhật bảo mật này. Vấn đề này ảnh hưởng đến việc gia hạn IP cho các khách hàng," công ty cho biết trong các bản cập nhật được thêm vào các thông báo bảo mật được phát hành trong tháng này vào thứ Ba của các bản vá.

Danh sách các phiên bản Windows bị ảnh hưởng và các bản cập nhật gây ra vấn đề này bao gồm:

* Windows Server 2016 ([KB5061010](https://support.microsoft.com/en-us/topic/june-10-2025-kb5061010-os-build-14393-8148-6766ca26-dc1e-4592-b959-d0c92d6deb6f))
* Windows Server 2019 ([KB5060531](https://support.microsoft.com/en-gb/topic/june-10-2025-kb5060531-os-build-17763-7434-32fce7e7-305d-4d32-913f-3fdc0709a763))
* Windows Server 2022 ([KB5060526](https://support.microsoft.com/en-us/topic/june-10-2025-kb5060526-os-build-20348-3807-4e9453c4-6602-48ea-b349-689cd66dfdb9))
* Windows Server 2025 ([KB5060842](https://support.microsoft.com/en-us/topic/june-10-2025-kb5060842-os-build-26100-4349-47ff300b-2a04-440c-9476-2860d04fce8d))

"Chúng tôi đang làm việc để phát hành một giải pháp trong những ngày tới và sẽ cung cấp thêm thông tin khi nó có sẵn," Microsoft cho biết thêm.

Trong tháng này, vào thứ Ba của các bản vá, Redmond đã giải quyết một vấn đề Windows Server khác mà đã [kích hoạt các lỗi ứng dụng hoặc dịch vụ](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-unreachable-windows-server-domain-controllers/) sau khi gây ra một số bộ điều khiển miền Windows Server 2025 trở nên không thể truy cập được sau khi khởi động lại.

Các bản cập nhật tích lũy tháng 6 năm 2025 cũng đã [sửa các vấn đề xác thực](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-windows-server-auth-issues-caused-by-april-updates/) trên các bộ điều khiển miền Windows Server được kích hoạt sau khi triển khai các bản cập nhật bảo mật tháng 4 năm 2025.

Vào tháng 5, Microsoft cũng đã [phát hành các bản cập nhật ngoài lịch](https://www.bleepingcomputer.com/news/microsoft/windows-server-emergency-update-fixes-hyper-v-vm-freezes-restart-issues/) để giải quyết một lỗi gây ra một số máy ảo Hyper-V với Windows 10, Windows 11 và Windows Server khởi động lại hoặc bị treo một cách không mong muốn.

Một tháng trước đó, công ty đã [phát hành một bộ cập nhật khẩn cấp khác](https://www.bleepingcomputer.com/news/microsoft/new-windows-server-emergency-updates-fix-container-launch-issue/) mà đã giải quyết một vấn đề đã biết ngăn cản các container Windows khởi động trên các hệ thống Windows Server 2019, Windows Server 2022 và Windows Server 2025.

Các vấn đề khởi động này chỉ ảnh hưởng đến các container dưới chế độ cách ly Hyper-V, cho phép nhiều container hoạt động đồng thời trên một máy chủ Windows duy nhất bên trong các máy ảo riêng biệt.