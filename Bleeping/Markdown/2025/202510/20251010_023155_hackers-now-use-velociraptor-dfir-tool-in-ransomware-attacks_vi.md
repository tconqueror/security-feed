# Tin tặc hiện sử dụng công cụ DFIR Velociraptor trong các cuộc tấn công mã độc tống tiền

![Các tin tặc hiện sử dụng công cụ DFIR Velociraptor trong các cuộc tấn công mã độc tống tiền](https://www.bleepstatic.com/content/hl-images/2025/02/12/ransomware-2.jpg)

Các tác nhân đe dọa đã bắt đầu sử dụng công cụ phân tích pháp y số và phản ứng sự cố Velociraptor (DFIR) trong các cuộc tấn công triển khai LockBit và Babuk.

Các nhà nghiên cứu Cisco Talos đánh giá với mức độ tin cậy trung bình rằng kẻ tấn công đứng sau các chiến dịch là một đối thủ có trụ sở tại Trung Quốc được theo dõi dưới tên Storm-2603.

Velociraptor là một [công cụ DFIR mã nguồn mở](http://github.com/Velocidex/velociraptor) do Mike Cohen tạo ra. Dự án đã được Rapid7 mua lại, công ty này cung cấp một phiên bản được cải tiến cho khách hàng của họ.

Công ty an ninh mạng Sophos báo cáo vào ngày 26 tháng 8 rằng tin tặc đã [lợi dụng Velociraptor để truy cập từ xa](https://news.sophos.com/en-us/2025/08/26/velociraptor-incident-response-tool-abused-for-remote-access/). Cụ thể, các tác nhân đe dọa đã sử dụng nó để tải xuống và thực thi Visual Studio Code trên các máy bị xâm phạm, thiết lập một kênh liên lạc an toàn với cơ sở hạ tầng command and control (C2).

Trong một báo cáo phát hành trước đó hôm nay, công ty bảo vệ chống ransomware Halcyon đánh giá rằng Storm-2603 có liên quan đến các tác nhân nhà nước Trung Quốc, là cùng nhóm với ransomware Warlock và CL-CRI-1040, và đã hành động như một chi nhánh (affiliate) của LockBit.

### Truy cập bền bỉ ẩn mình

Cisco Talos cho biết kẻ tấn công đã sử dụng một phiên bản Velociraptor lỗi thời có lỗ hổng leo thang đặc quyền được xác định là CVE-2025-6264, lỗ hổng này có thể cho phép thực thi lệnh tùy ý và chiếm quyền kiểm soát máy chủ.

Trong giai đoạn đầu của cuộc tấn công, tác nhân đe dọa đã tạo các tài khoản quản trị cục bộ được đồng bộ hóa với Entra ID và sử dụng chúng để truy cập console VMware vSphere, cho phép họ kiểm soát bền vững các máy ảo (VMs).

“Sau khi chiếm được quyền truy cập ban đầu, các tác nhân đã cài đặt một phiên bản Velociraptor lỗi thời (version 0.73.4.0) có lỗ hổng leo thang đặc quyền (CVE-2025-6264) có thể dẫn đến thực thi lệnh tùy ý và chiếm quyền điều khiển endpoint,” [giải thích Cisco Talos](https://blog.talosintelligence.com/velociraptor-leveraged-in-ransomware-attacks/).

Các nhà nghiên cứu lưu ý rằng Velociraptor đã giúp kẻ tấn công duy trì tính bền bỉ, khởi chạy nó nhiều lần, ngay cả sau khi host bị cô lập.

Họ cũng quan sát thấy việc thực thi các lệnh theo kiểu Impacket smbexec để chạy chương trình từ xa và việc tạo các scheduled tasks cho các batch script.

Kẻ tấn công đã vô hiệu hóa bảo vệ thời gian thực của Defender bằng cách sửa đổi Active Directory GPOs và tắt giám sát hành vi cùng hoạt động tệp/chương trình.

Các giải pháp endpoint detection and response (EDR) xác định ransomware được triển khai trên hệ thống mục tiêu Windows là LockBit, nhưng phần mở rộng cho các tệp bị mã hóa là “.xlockxlock,” từng thấy trong các cuộc tấn công của Warlock ransomware.

Trên các hệ thống VMware ESXi, các nhà nghiên cứu phát hiện một nhị phân Linux bị nhận diện là Babuk ransomware.

Các nhà nghiên cứu Cisco Talos cũng quan sát thấy việc sử dụng một công cụ mã hoá PowerShell không ghi file (fileless) tạo các khóa AES ngẫu nhiên cho mỗi lần chạy, được cho là công cụ chính cho "mã hóa hàng loạt trên các máy Windows."

Trước khi mã hóa dữ liệu, kẻ tấn công đã sử dụng một script PowerShell khác để trích xuất tệp nhằm mục đích tống tiền kép (double-extortion). Script sử dụng ‘Start-Sleep’ để chèn độ trễ giữa các hành động tải lên nhằm né tránh sandbox và môi trường phân tích.

Các nhà nghiên cứu Cisco Talos cung cấp hai bộ [chỉ số xâm phạm](https://github.com/Cisco-Talos/IOCs/commit/85f343945bee35ffd807a6bd0623ba6c79726902) (IoCs) quan sát được trong các cuộc tấn công, bao gồm các tệp mà tác nhân đe dọa đã tải lên các máy bị xâm phạm và các tệp Velociraptor.