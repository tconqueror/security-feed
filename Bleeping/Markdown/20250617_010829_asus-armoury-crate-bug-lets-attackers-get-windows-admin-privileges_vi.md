# Lỗi trong ASUS Armoury Crate cho phép kẻ tấn công có quyền quản trị Windows

![ASUS](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

Một lỗ hổng có độ nghiêm trọng cao trong phần mềm ASUS Armoury Crate có thể cho phép kẻ tấn công nâng cao quyền của mình lên mức SYSTEM trên các máy Windows.

Vấn đề bảo mật này được theo dõi với mã [CVE-2025-3464](https://nvd.nist.gov/vuln/detail/CVE-2025-3464) và nhận được điểm số độ nghiêm trọng là 8.8 trên thang điểm 10.

Lỗi này có thể bị khai thác để vượt qua xác thực và ảnh hưởng đến AsIO3.sys của phần mềm quản lý hệ thống Armoury Crate.

Armoury Crate là phần mềm điều khiển hệ thống chính thức cho Windows từ ASUS, cung cấp một giao diện tập trung để điều khiển ánh sáng RGB (Aura Sync), điều chỉnh độ cong quạt, quản lý hồ sơ hiệu suất và các thiết bị ngoại vi ASUS, cũng như tải xuống trình điều khiển và cập nhật firmware.

Để thực hiện tất cả các chức năng này và cung cấp giám sát hệ thống cấp thấp, bộ phần mềm này sử dụng driver kernel để truy cập và điều khiển các tính năng phần cứng.

Nhà nghiên cứu Marcin "Icewall" Noga của Cisco Talos đã báo cáo CVE-2025-3464 cho công ty công nghệ.

Theo một [thông báo của Talos](https://talosintelligence.com/vulnerability%5Freports/TALOS-2025-2150), vấn đề nằm ở việc driver xác minh người gọi dựa trên một SHA-256 hash cứng hóa của AsusCertService.exe và một danh sách cho phép PID, thay vì sử dụng các quyền truy cập cấp hệ điều hành phù hợp.

Khai thác lỗi này liên quan đến việc tạo một hard link từ một ứng dụng thử nghiệm vô hại đến một file thực thi giả. Kẻ tấn công khởi động ứng dụng, tạm dừng nó, và sau đó thay thế hard link để trỏ tới AsusCertService.exe.

Khi driver kiểm tra SHA-256 hash của file, nó đọc binary tin cậy đã được liên kết, cho phép ứng dụng thử nghiệm vượt qua xác thực và truy cập vào driver.

Điều này cấp cho kẻ tấn công quyền truy cập hệ thống cấp thấp, cho phép họ truy cập trực tiếp vào bộ nhớ vật lý, cổng I/O và các thanh ghi cụ thể của mô hình (MSRs), mở đường cho sự xâm nhập toàn bộ hệ điều hành.

Lưu ý rằng kẻ tấn công phải đã có mặt trên hệ thống (nhiễm malware, phishing, tài khoản không quyền bị xâm phạm) để khai thác CVE-2025-3464.

Tuy nhiên, việc phần mềm này được triển khai rộng rãi trên máy tính toàn cầu có thể cho thấy đây là một bề mặt tấn công đủ lớn để việc khai thác trở nên hấp dẫn.

Cisco Talos xác nhận rằng CVE-2025-3464 ảnh hưởng đến phiên bản Armoury Crate 5.9.13.0, nhưng [thông báo của ASUS](https://www.asus.com/content/asus-product-security-advisory/) lưu ý rằng lỗi này ảnh hưởng đến tất cả các phiên bản từ 5.9.9.0 đến 6.1.18.0.

Để giảm thiểu vấn đề bảo mật, được khuyến nghị áp dụng cập nhật mới nhất bằng cách mở ứng dụng Armoury Crate và đi đến "Cài đặt"> "Trung tâm cập nhật"> "Kiểm tra cập nhật"> "Cập nhật."

Cisco đã báo cáo lỗi cho ASUS vào tháng 2 nhưng chưa có sự khai thác nào ở thực tế được quan sát. Tuy nhiên, "ASUS khuyến nghị mạnh mẽ rằng người dùng nên cập nhật cài đặt Armoury Crate của họ lên phiên bản mới nhất."

Các lỗi driver kernel Windows dẫn đến việc nâng cao quyền truy cập cục bộ là [phổ biến trong giới hacker](https://www.bleepingcomputer.com/news/security/windows-kernel-bug-fixed-last-month-exploited-as-zero-day-since-august/), bao gồm [các nhóm ransomware](https://www.bleepingcomputer.com/news/security/ransomware-gangs-exploit-paragon-partition-manager-bug-in-byovd-attacks/), [các hoạt động malware](https://www.bleepingcomputer.com/news/security/new-steelfox-malware-hijacks-windows-pcs-using-vulnerable-driver/), và [các mối đe dọa đối với các cơ quan chính phủ](https://www.bleepingcomputer.com/news/security/windows-kernel-bug-now-exploited-in-attacks-to-gain-system-privileges/).