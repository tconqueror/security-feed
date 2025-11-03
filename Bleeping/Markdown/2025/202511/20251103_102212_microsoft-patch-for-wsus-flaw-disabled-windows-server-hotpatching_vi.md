# Microsoft: Bản vá cho lỗ hổng WSUS đã vô hiệu hóa Hotpatch trên Windows Server

![Windows Server](https://www.bleepstatic.com/content/hl-images/2024/05/16/Windows-Server.jpg)

Một bản cập nhật bảo mật ngoài lịch (out-of-band, OOB) vá lỗ hổng trên Windows Server Update Service (WSUS) đang bị khai thác tích cực đã làm hỏng tính năng Hotpatch trên một số thiết bị Windows Server 2025.

[KB5070881](https://support.microsoft.com/en-us/topic/october-23-2025-kb5070881-os-build-26100-6905-out-of-band-8e7ac742-6785-4677-87e4-b73dd8ac0122), bản cập nhật khẩn cấp gây ra vấn đề này, được phát hành cùng ngày mà một số công ty an ninh mạng xác nhận lỗ hổng thực thi mã từ xa (remote code execution, RCE) [CVE-2025-59287](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59287) [đang bị khai thác ngoài thực tế](https://www.bleepingcomputer.com/news/security/hackers-now-exploiting-critical-windows-server-wsus-flaw-in-attacks/). Trung tâm An ninh Mạng Quốc gia Hà Lan (NCSC-NL) đã xác nhận những phát hiện của các công ty, cảnh báo quản trị viên CNTT về rủi ro gia tăng vì [một PoC exploit đã có sẵn](http://hawktrace.com/blog/CVE-2025-59287).

Vài ngày sau, Cybersecurity and Infrastructure Security Agency (CISA) đã yêu cầu các cơ quan chính phủ Hoa Kỳ bảo mật hệ thống của họ sau khi thêm lỗ hổng này vào danh mục các lỗ hổng bảo mật đã bị lợi dụng trong các cuộc tấn công. Nhóm giám sát Internet Shadowserver hiện đang theo dõi hơn 2.600 instance WSUS với các cổng mặc định (8530/8531) bị mở trên Internet, mặc dù họ không chia sẻ có bao nhiêu đã được vá.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Tuy nhiên, trong một cập nhật cho tài liệu hỗ trợ KB5070881 gốc, Microsoft cho biết một số hệ thống Windows Server 2025 đã đăng ký nhận Hotpatch hiện đã mất trạng thái đăng ký Hotpatch sau khi nhận bản cập nhật OOB xử lý lỗ hổng CVE-2025-59287.

"A very limited number of Hotpatch-enrolled machines received the update before the issue was corrected. The update is now offered only to machines that are not enrolled to receive Hotpatch updates," [Microsoft says](https://support.microsoft.com/en-us/topic/october-23-2025-kb5070881-os-build-26100-6905-out-of-band-8e7ac742-6785-4677-87e4-b73dd8ac0122). "This issue only impacts Windows Server 2025 devices and virtual machines (VMs) enrolled to receive Hotpatch updates."

Microsoft đã ngừng cung cấp bản cập nhật KB5070881 cho các thiết bị Windows Server 2025 đã đăng ký Hotpatch, và cho biết những máy đã cài đặt nó sẽ không còn nhận được các bản cập nhật Hotpatch trong tháng 11 và tháng 12.

Thay vào đó, chúng sẽ được cung cấp các bản cập nhật bảo mật hàng tháng thông thường, điều này sẽ yêu cầu khởi động lại, và sẽ tham gia lại vào đợt triển khai Hotpatch sau khi cài đặt baseline dự kiến cho tháng 1 năm 2026.

## Bản cập nhật bảo mật mới không làm gián đoạn Hotpatch

May mắn thay, quản trị viên chỉ mới tải xuống bản cập nhật lỗi và chưa triển khai có thể cài đặt [KB5070893 security update](https://support.microsoft.com/en-us/topic/october-24-2025-kb5070893-os-build-26100-6905-security-update-for-windows-server-update-services-78f3720c-9511-4deb-b0d7-7bed2016fefd) (phát hành một ngày sau KB5070881 và được thiết kế đặc biệt để vá lỗ hổng CVE-2025-59287 mà không làm gián đoạn Hotpatch) bằng cách vào Settings > Windows Update và chọn Pause updates. Tiếp theo, họ phải bỏ tạm dừng và quét cập nhật để nhận bản cập nhật đúng.

"Hotpatch-enrolled machines that have not installed this update will be offered the October 24, 2025, Security Update for Windows Server Update Services (KB5070893) on top of the planned baseline update for October 2025 ([KB5066835](https://support.microsoft.com/topic/october-14-2025-baseline-58e80013-ba94-46ad-a56c-b6691d2405ad))," Microsoft added.

"Machines installing KB5070893 will remain 'on the Hotpatch train' and will continue to receive Hotpatch updates in November and December. Only those machines that have WSUS enabled will be prompted to restart after installing the Security Update, KB5070893."

Để xử lý lỗ hổng RCE CVE-2025-59287, Microsoft cũng đã tắt hiển thị chi tiết lỗi đồng bộ hóa trong báo cáo lỗi WSUS của mình.

Tuần trước, Microsoft thừa nhận một lỗi đã ngăn người dùng thoát Task Manager trên Windows 11 sau khi cài đặt bản cập nhật tùy chọn tháng 10/2025. Ngoài ra, hãng đã sửa Windows 11 Media Creation Tool (MCT) và khắc phục các lỗi cập nhật 0x800F081F ảnh hưởng đến hệ thống Windows 11 24H2 kể từ tháng Một.