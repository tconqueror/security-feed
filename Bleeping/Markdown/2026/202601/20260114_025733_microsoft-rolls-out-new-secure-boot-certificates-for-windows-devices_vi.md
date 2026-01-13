# Bản cập nhật Windows mới thay thế các chứng chỉ Secure Boot sắp hết hạn

![Windows](https://www.bleepstatic.com/content/hl-images/2025/10/20/Windows-headpic.jpg)

Microsoft đã bắt đầu tự động thay thế các chứng chỉ Secure Boot sắp hết hạn trên các hệ thống Windows 11 24H2 và 25H2 đủ điều kiện.

[Secure Boot](https://www.bleepingcomputer.com/tag/Secure-Boot/) là một tính năng bảo mật ngăn phần mềm độc hại (như rootkit) thực thi trong quá trình khởi động hệ thống bằng cách đảm bảo chỉ các bootloader đáng tin cậy được phép tải trên các máy tính có firmware UEFI. Việc này được thực hiện bằng cách kiểm tra chữ ký số của phần mềm so với một tập hợp các chứng chỉ số đáng tin cậy được lưu trong firmware của thiết bị.

Thông báo hôm nay được đưa ra sau khi Microsoft [đã cảnh báo các quản trị viên CNTT](https://techcommunity.microsoft.com/blog/windows-itpro-blog/secure-boot-playbook-for-certificates-expiring-in-2026/4469235) vào tháng 11 phải cập nhật các chứng chỉ bảo mật được dùng để xác thực firmware UEFI trước khi chúng hết hạn.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

"Các chứng chỉ Secure Boot được sử dụng bởi hầu hết các thiết bị Windows sẽ bắt đầu hết hạn từ tháng Sáu năm 2026. Điều này có thể ảnh hưởng đến khả năng khởi động an toàn của một số thiết bị cá nhân và doanh nghiệp nếu không được cập nhật kịp thời," [Microsoft đã nói](https://x.com/WindowsUpdate/status/2011140448274800881).

"Bắt đầu từ bản cập nhật này, các bản cập nhật chất lượng Windows bao gồm một tập con dữ liệu nhắm mục tiêu thiết bị có độ tin cậy cao xác định các thiết bị đủ điều kiện để tự động nhận các chứng chỉ Secure Boot mới. Thiết bị sẽ nhận các chứng chỉ mới chỉ sau khi cho thấy các tín hiệu cập nhật thành công đủ, đảm bảo triển khai an toàn và theo giai đoạn," [nói thêm](https://support.microsoft.com/en-us/topic/january-13-2026-kb5074109-os-builds-26200-7623-and-26100-7623-3ec427dd-6fc4-4c32-a471-83504dd081cb#:~:text=%5BSecure%20Boot%5D%C2%A0Starting%20with%20this%20update).

Các quản trị viên CNTT muốn duy trì chức năng Secure Boot và đảm bảo bảo mật cho các điểm cuối nên cài đặt các chứng chỉ mới trước khi các chứng chỉ cũ hết hạn vào mùa hè này.

Nếu không làm như vậy có thể dẫn đến mất Windows Boot Manager và các biện pháp bảo vệ Secure Boot, vì các bản cập nhật bảo mật cho các thành phần trước khi khởi động sẽ không còn được cung cấp cho các thiết bị bật Secure Boot.

"Không có các bản cập nhật, các thiết bị Windows được bật Secure Boot có nguy cơ không nhận được các bản cập nhật bảo mật hoặc tin tưởng các boot loader mới, điều này sẽ làm suy yếu cả khả năng phục vụ và bảo mật," [Microsoft giải thích](https://support.microsoft.com/en-us/topic/windows-secure-boot-certificate-expiration-and-ca-updates-7ff40d33-95dc-4c3c-8725-a9b95457578e).

Trong khi Microsoft sẽ tự động cập nhật các thiết bị có độ tin cậy cao qua Windows Update, các tổ chức cũng có thể triển khai các chứng chỉ Secure Boot bằng cách sử dụng khóa registry, Windows Configuration System (WinCS) và các cài đặt Group Policy.

Theo [sổ tay Secure Boot của Microsoft](https://techcommunity.microsoft.com/blog/windows-itpro-blog/secure-boot-playbook-for-certificates-expiring-in-2026/4469235), các quản trị viên nên trước tiên lập kiểm kê đội thiết bị của họ, xác minh trạng thái Secure Boot bằng cách sử dụng lệnh PowerShell hoặc khóa registry, và sau đó áp dụng các bản cập nhật firmware từ nhà sản xuất trước khi cài đặt các bản cập nhật chứng chỉ của Microsoft.