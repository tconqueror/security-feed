# Các bản cập nhật firmware UEFI mới của Lenovo khắc phục các lỗ hổng bỏ qua Secure Boot

![Lenovo](https://www.bleepstatic.com/content/hl-images/2024/10/29/lenovo-logo.jpg)

Lenovo cảnh báo về những lỗ hổng BIOS nghiêm trọng có thể cho phép kẻ tấn công vượt qua Secure Boot trên các máy tính để bàn all-in-one sử dụng firmware Insyde UEFI tùy chỉnh.

Các thiết bị được xác nhận bị ảnh hưởng bao gồm IdeaCentre AIO 3 24ARR9 và 27ARR9, cũng như Yoga AIO 27IAH10, 32ILL10 và 32IRH8.

UEFI là sự thay thế hiện đại cho BIOS truyền thống trên PC, hoạt động như một giao diện firmware giữa phần cứng của máy tính và hệ điều hành (OS), điều khiển quá trình khởi động và khởi động sớm.

Các lỗ hổng, do Binarly phát hiện, giống như những gì mà các nhà nghiên cứu phát hiện trước đó trong tháng này, ảnh hưởng đến [nhiều mẫu bo mạch Gigabyte](https://www.bleepingcomputer.com/news/security/gigabyte-motherboards-vulnerable-to-uefi-malware-bypassing-secure-boot/), cho phép kẻ tấn công nội bộ thực thi mã tùy ý trong Chế độ Quản lý Hệ thống (SMM).

SMM là chế độ CPU tách biệt với hệ điều hành (OS) và hypervisor, hoạt động với quyền cao hơn ở mức thấp hơn (Ring-2). Lợi dụng các lỗ hổng trong SMM có thể giúp kẻ tấn công cài đặt mã độc "không thể phát hiện", bỏ qua các biện pháp bảo mật cấp OS, chẳng hạn như SecureBoot.

InsydeH2O là một trong những framework UEFI BIOS thương mại được triển khai rộng rãi nhất được sử dụng trong các máy tính xách tay và máy tính để bàn OEM.

Insyde cũng đã [công bố một thông báo](https://www.insyde.com/security-pledge/sa-2025007) giải thích rằng các lỗ hổng phát sinh từ những tùy chỉnh cụ thể của OEM mà Lenovo thực hiện trong các hình ảnh firmware InsydeH2O UEFI, và không áp dụng cho tất cả các hệ thống sử dụng InsydeH2O UEFI.

"Các lỗ hổng mới được phát hiện của Lenovo phát sinh từ những thách thức lặp đi lặp lại liên quan đến sự không nhất quán trong chuỗi cung ứng phần mềm," bình luận của Alex Matrosov từ Binarly với BleepingComputer.

"Tất cả sáu lỗ hổng đều được tìm thấy trong mã cấp Chế độ Quản lý Hệ thống (SMM) - lớp firmware vô hình tải lên trước hệ điều hành của bạn và tồn tại sau mỗi lần tái cài đặt, khiến chúng trở thành bệ phóng hoàn hảo cho các cài đặt âm thầm và bỏ qua Secure Boot."

Sáu lỗ hổng được tóm tắt như sau:

* **[CVE-2025-4421](https://www.binarly.io/advisories/brly-dva-2025-013)**: lỗi trong một trình xử lý SMI (Callback7 qua EfiSmiServices) cho phép một kẻ tấn công ghi vào một địa chỉ SMRAM do kẻ tấn công kiểm soát bằng cách sử dụng một thanh ghi RSI không được xác thực, dẫn đến tăng đặc quyền SMM và thỏa hiệp firmware lâu dài (điểm CVSS: 8.2)
* **[CVE-2025-4422](https://www.binarly.io/advisories/brly-2025-014)**: lỗi trong một trình xử lý SMI (EfiSmiServices, qua gEfiSmmCpuProtocol và EfiPcdProtocol) có thể dẫn đến hỏng bộ nhớ SMM và tăng đặc quyền. (điểm CVSS: 8.2)
* **[CVE-2025-4423](https://www.binarly.io/advisories/brly-dva-2025-015)**: lỗi trong một trình xử lý SMI (SetupAutomationSmm) cho phép ghi nhớ tùy ý trong SMM, dẫn đến tăng đặc quyền SMM và thực thi mã. (điểm CVSS: 8.2)
* **[CVE-2025-4424](https://www.binarly.io/advisories/brly-2025-017)**: kiểm tra đầu vào không đúng trong một trình xử lý SMI (SetupAutomationSmm) cho phép các cuộc gọi không được làm sạch đến SmmSetVariable, dẫn đến thao tác cài đặt firmware. (điểm CVSS: 6)
* **[CVE-2025-4425](https://www.binarly.io/advisories/brly-2025-016)**: tràn bộ đệm ngăn xếp trong một trình xử lý SMI (SetupAutomationSmm) có thể dẫn đến tăng đặc quyền SMM và thực thi mã tùy ý. (điểm CVSS: 8.2)
* **[CVE-2025-4426](https://www.binarly.io/advisories/brly-2025-018)**: lỗi trong một trình xử lý SMI (SetupAutomationSmm) rò rỉ nội dung SMRAM, cho phép tiết lộ thông tin nhạy cảm. (điểm CVSS: 6)

Binarly đã báo cáo các lỗ hổng cho Lenovo vào ngày 8 tháng 4 năm 2025 và nhận được xác nhận từ công ty vào ngày 16 tháng 6. Thông báo phối hợp đã được công bố hôm qua, sau khi hết thời gian 90 ngày công bố.

Lenovo đã [phát hành các bản cập nhật bảo mật firmware](https://support.lenovo.com/us/en/product%5Fsecurity/LEN-201013) cho các mẫu IdeaCenter AIO 3, kêu gọi người dùng nâng cấp lên phiên bản O6BKT1AA.

Các bản cập nhật cho Yoga AIO hiện chưa có sẵn, nhưng nhà cung cấp máy tính dự định phát hành các bản sửa lỗi từ ngày 30 tháng 9 đến 30 tháng 11 năm 2025.