# CISA và FBI cảnh báo về sự gia tăng các cuộc tấn công ransomware Interlock

![Interlock](https://www.bleepstatic.com/content/hl-images/2024/11/03/interlock-header.jpg)

CISA và FBI đã cảnh báo vào thứ ba về việc gia tăng hoạt động ransomware Interlock nhắm mục tiêu vào các doanh nghiệp và các tổ chức cơ sở hạ tầng quan trọng trong các cuộc tấn công tống tiền kép.

[Cảnh báo của hôm nay](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-203a) được viết chung với Bộ Y tế và Dịch vụ Nhân sinh (HHS) và Trung tâm Chia sẻ và Phân tích Thông tin Đa tiểu bang (MS-ISAC), cung cấp cho các nhà bảo vệ mạng các chỉ số xâm phạm (IOCs) được thu thập trong quá trình điều tra các vụ việc gần đây nhất vào tháng 6 năm 2025, cùng với các biện pháp giảm thiểu để bảo vệ mạng của họ khỏi các cuộc tấn công của nhóm ransomware này.

[Interlock](https://www.bleepingcomputer.com/tag/Interlock/) là một hoạt động ransomware tương đối mới xuất hiện vào tháng 9 năm 2024 và kể từ đó đã nhắm mục tiêu vào các nạn nhân trên toàn thế giới qua nhiều lĩnh vực mà đặc biệt là lĩnh vực chăm sóc sức khỏe.

Các tác nhân đe dọa cũng đã từng [liên quan đến các cuộc tấn công ClickFix](https://www.bleepingcomputer.com/news/security/interlock-ransomware-gang-pushes-fake-it-tools-in-clickfix-attacks/), nơi họ giả mạo các công cụ CNTT để có được quyền truy cập mạng ban đầu, cũng như các cuộc tấn công malware trong đó họ [triển khai một trojan truy cập từ xa có tên NodeSnake](https://www.bleepingcomputer.com/news/security/interlock-ransomware-gang-deploys-new-nodesnake-rat-on-universities/) trên các mạng của các trường đại học ở Vương quốc Anh.

Gần đây, nhóm tội phạm mạng đã nhận trách nhiệm về việc [xâm nhập DaVita](https://www.bleepingcomputer.com/news/security/interlock-ransomware-claims-davita-attack-leaks-stolen-data/), một công ty Fortune 500 chuyên về chăm sóc thận, dẫn đến việc đánh cắp và rò rỉ 1,5 terabyte dữ liệu từ hệ thống của họ, cũng như [tấn công Kettering Health](https://www.bleepingcomputer.com/news/security/kettering-health-confirms-interlock-ransomware-behind-cyberattack/), một gã khổng lồ chăm sóc sức khỏe quản lý hơn 120 cơ sở ngoại trú và có hơn 15.000 nhân viên.

![CISA Interlock](https://www.bleepstatic.com/images/news/u/1109292/2025/CISA-Interlock-tweet.png)

Khi điều tra các cuộc tấn công của họ, FBI đã quan sát thấy băng nhóm Interlock sử dụng một số chiến thuật bất thường và gây áp lực lên các nạn nhân của họ trong các cuộc tấn công tống tiền kép.

"FBI đã quan sát thấy các tác nhân có được quyền truy cập ban đầu thông qua tải xuống drive-by từ các trang web hợp lệ bị xâm phạm, đây là một phương pháp không phổ biến trong các nhóm ransomware," bản cảnh báo viết.

"Các tác nhân Interlock sử dụng một mô hình tống tiền kép, trong đó các tác nhân mã hóa hệ thống sau khi xuất khẩu dữ liệu, điều này gia tăng áp lực lên các nạn nhân để trả tiền chuộc nhằm vừa lấy lại dữ liệu của họ vừa ngăn chặn việc nó bị rò rỉ."

Đầu tháng này, nhóm ransomware cũng được quan sát thấy [áp dụng kỹ thuật mới FileFix](https://www.bleepingcomputer.com/news/security/interlock-ransomware-adopts-filefix-method-to-deliver-malware/) để phát tán malware trojan truy cập từ xa (RAT). FileFix là một cuộc tấn công kỹ thuật xã hội mà trong đó các kẻ tấn công vũ khí hóa các yếu tố giao diện người dùng Windows đáng tin cậy, bao gồm Windows File Explorer và HTML Applications (.HTA), để lừa các mục tiêu thực hiện mã độc PowerShell hoặc JavaScript mà không hiển thị bất kỳ cảnh báo bảo mật nào.

Để bảo vệ mạng của họ khỏi các cuộc tấn công ransomware Interlock, các nhóm an ninh được khuyến cáo triển khai lọc Hệ thống Tên miền (DNS), tường lửa truy cập web và đào tạo người dùng nhận diện các nỗ lực kỹ thuật xã hội.

Các nhà bảo vệ cũng được khuyến khích giữ cho hệ thống, phần mềm và firmware được cập nhật và phân đoạn mạng để hạn chế quyền truy cập từ các thiết bị bị xâm phạm.

Ngoài ra, các tổ chức cần thiết lập các chính sách quản lý danh tính, thông tin xác thực và quyền truy cập (ICAM) và yêu cầu xác thực đa yếu tố (MFA) cho tất cả các dịch vụ khi có thể.