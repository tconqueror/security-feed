# Qilin phần mềm tống tiền lạm dụng WSL để chạy trình mã hóa Linux trên Windows

![Phần mềm độc hại trên Linux](https://www.bleepstatic.com/content/hl-images/2024/05/31/Linux.jpg)

Chiến dịch phần mềm tống tiền Qilin được phát hiện thực thi trình mã hóa Linux trên Windows bằng cách sử dụng Windows Subsystem for Linux (WSL) để né tránh việc phát hiện bởi các công cụ bảo mật truyền thống.

Phần mềm tống tiền lần đầu xuất hiện với tên "Agenda" vào tháng 8 năm 2022, đổi thương hiệu thành Qilin vào tháng 9 và tiếp tục hoạt động dưới tên đó cho đến nay.

Qilin đã trở thành một trong những chiến dịch phần mềm tống tiền hoạt động tích cực nhất, với nghiên cứu mới từ [Trend Micro](https://www.trendmicro.com/en%5Fus/research/25/j/agenda-ransomware-deploys-linux-variant-on-windows-systems.html) và [Cisco Talos](https://blog.talosintelligence.com/uncovering-qilin-attack-methods-exposed-through-multiple-cases/) cho biết băng nhóm tội phạm mạng đã tấn công hơn 700 nạn nhân ở 62 quốc gia trong năm nay.

Cả hai công ty cho biết nhóm này đã trở thành một trong những mối đe doạ phần mềm tống tiền hoạt động tích cực nhất trên toàn cầu, công bố hơn 40 nạn nhân mới mỗi tháng trong nửa sau của năm 2025. 

Cả hai hãng an ninh mạng báo cáo rằng các chi nhánh Qilin sử dụng kết hợp chương trình hợp pháp và công cụ quản lý từ xa để xâm nhập mạng và đánh cắp thông tin đăng nhập, bao gồm các ứng dụng như AnyDesk, ScreenConnect và Splashtop để truy cập từ xa, và Cyberduck và WinRAR để đánh cắp dữ liệu.

Kẻ đe doạ cũng sử dụng các tiện ích Windows tích hợp phổ biến, chẳng hạn như Microsoft Paint (mspaint.exe) và Notepad (notepad.exe), để kiểm tra tài liệu tìm dữ liệu nhạy cảm trước khi đánh cắp chúng.

## Sử dụng driver dễ bị tổn thương để vô hiệu hoá công cụ bảo mật

Cả Trend Micro và Talos cũng quan sát thấy các chi nhánh Qilin thực hiện các cuộc tấn công Bring Your Own Vulnerable Driver (BYOVD) để vô hiệu hoá phần mềm bảo mật trước khi khởi chạy trình mã hóa.

Kẻ tấn công triển khai các driver đã ký nhưng có lỗ hổng, chẳng hạn như eskle.sys, để chấm dứt các tiến trình antivirus và EDR, và sử dụng DLL sideloading để thả thêm các driver kernel (rwdrv.sys và hlpdrv.sys) cho phép quyền cấp kernel bổ sung.

Talos quan sát thấy kẻ tấn công sử dụng các công cụ như "dark-kill" và "HRSword" để tắt phần mềm bảo mật và xóa dấu vết hoạt động độc hại.

"Talos quan sát thấy dấu vết của các cố gắng vô hiệu hoá EDR bằng nhiều phương pháp," giải thích Cisco Talos.

"Nhìn chung, chúng tôi thường xuyên quan sát thấy các lệnh thực thi trực tiếp 'uninstall.exe' của EDR hoặc cố gắng dừng dịch vụ bằng lệnh sc. Đồng thời, kẻ tấn công cũng được quan sát chạy các công cụ mã nguồn mở như [dark-kill](https://github.com/d1rkmtrr/dark-kill) và HRSword."

## Trình mã hóa Linux được khởi chạy thông qua WSL

Vào tháng 12 năm 2023, [BleepingComputer reported](https://www.bleepingcomputer.com/news/security/linux-version-of-qilin-ransomware-focuses-on-vmware-esxi/) về một trình mã hóa Linux mới của Qilin với trọng tâm mạnh mẽ vào việc mã hóa các máy ảo và máy chủ VMware ESXi.

Các tham số dòng lệnh của trình mã hóa bao gồm các tuỳ chọn để bật chế độ gỡ lỗi, thực hiện chạy thử mà không mã hóa tệp, hoặc tuỳ chỉnh cách các máy ảo và snapshot của chúng được mã hóa.

![Qilin Linux encryptor](https://www.bleepstatic.com/images/news/ransomware/q/qilin/linux-encryptor/qilin-help.jpg)

**Qilin trình mã hóa Linux**  
_Nguồn: BleepingComputer_

Các nhà nghiên cứu từ Trend Micro hiện báo cáo rằng các chi nhánh Qilin đã được thấy sử dụng WinSCP để chuyển trình mã hóa ELF Linux tới các thiết bị bị xâm phạm, sau đó được khởi chạy thông qua phần mềm quản lý từ xa Splashtop (SRManager.exe) trực tiếp trong Windows.

Trong khi Trend Micro ban đầu báo cáo trình mã hóa là đa nền tảng, các trình mã hóa Linux của Qilin là các tệp thực thi ELF \[[VirusTotal](http://www.virustotal.com/gui/file/7a9072dc379ce82fc254b831822eaff37cd243d76ee130386afb385a2437313b)\], nghĩa là chúng không thể chạy nguyên bản trên Windows và cần môi trường chạy như Windows Subsystem for Linux (WSL) để thực thi.

Các câu hỏi bổ sung với Trend Micro tiết lộ rằng các tác nhân đe doạ thực sự đang sử dụng WSL để chạy trình mã hóa.

WSL là một tính năng của Windows cho phép bạn cài đặt và chạy các bản phân phối Linux trực tiếp trong Windows. Khi được cài đặt, bạn có thể mở một shell cho distro mặc định đã cài hoặc sử dụng lệnh `wsl.exe -e` để chạy chương trình Linux trong command prompt của Windows.

Trend Micro told BleepingComputer rằng khi kẻ đe doạ có quyền truy cập vào một thiết bị, chúng bật hoặc cài đặt Windows Subsystem for Linux rồi sử dụng nó để thực thi trình mã hóa, từ đó né tránh phần lớn phần mềm bảo mật Windows truyền thống.

"Trong trường hợp này, kẻ đe doạ đã có thể chạy trình mã hóa Linux trên hệ thống Windows bằng cách lợi dụng Windows Subsystem for Linux (WSL), một tính năng tích hợp cho phép các nhị phân Linux thực thi trực tiếp trên Windows mà không cần máy ảo," Trend Micro told BleepingComputer.

"Sau khi chiếm quyền, kẻ tấn công đã bật hoặc cài đặt WSL bằng các script hoặc công cụ dòng lệnh, rồi triển khai payload ransomware Linux trong môi trường đó. Điều này cho phép họ thực thi trình mã hóa dựa trên Linux trực tiếp trên máy chủ Windows trong khi tránh được nhiều cơ chế phòng thủ tập trung vào phát hiện mã độc Windows truyền thống."

Vì nhiều sản phẩm EDR trên Windows tập trung vào hành vi PE của Windows, chúng bỏ sót hành vi độc hại xảy ra bên trong WSL, cho phép phần mềm độc hại vượt qua việc phát hiện.

Trend Micro cho biết kỹ thuật này cho thấy cách các toán hoạt động phần mềm tống tiền đang thích nghi với môi trường lai Windows và Linux để tối đa hoá phạm vi tấn công và né tránh các biện pháp phòng thủ truyền thống.