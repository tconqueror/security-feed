# Lỗ hổng Veeam mới khiến máy chủ sao lưu dễ bị tấn công RCE

![Veeam](https://www.bleepstatic.com/content/hl-images/2024/11/08/Veeam.jpg)

Veeam phát hành các bản cập nhật bảo mật để vá nhiều lỗ hổng trong phần mềm Backup & Replication của mình, bao gồm một lỗ hổng thực thi mã từ xa (RCE) nghiêm trọng.

Được theo dõi là CVE-2025-59470, lỗ hổng RCE này ảnh hưởng đến Veeam Backup & Replication 13.0.1.180 và tất cả bản build phiên bản 13 trước đó.

"“Lỗ hổng này cho phép một Backup or Tape Operator thực hiện thực thi mã từ xa (RCE) với quyền postgres bằng cách gửi tham số interval hoặc order độc hại,” Veeam [giải thích](https://www.veeam.com/kb4792) trong một khuyến cáo hôm thứ Ba.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Tuy nhiên, công ty công nghệ thông tin đã điều chỉnh mức đánh giá lên mức nghiêm trọng cao vì lỗ hổng chỉ có thể bị khai thác bởi kẻ tấn công có vai trò Backup or Tape Operator.

Veeam bổ sung rằng "The Backup and Tape Operator roles are considered highly privileged roles and should be protected as such. Following Veeam's recommended Security Guidelines further reduces the opportunity for exploitability."

Veeam phát hành phiên bản 13.0.1.1071 vào ngày 6 tháng 1 để vá CVE-2025-59470 và xử lý hai lỗ hổng khác: mức nghiêm trọng cao (CVE-2025-55125) và mức trung bình (CVE-2025-59468) có thể cho phép Backup or Tape Operator độc hại thực hiện thực thi mã từ xa bằng cách lần lượt tạo tệp cấu hình sao lưu độc hại hoặc gửi tham số mật khẩu độc hại.

Phần mềm sao lưu và phục hồi dữ liệu doanh nghiệp Veeam Backup & Replication (VBR) giúp tạo các bản sao của dữ liệu và ứng dụng quan trọng để có thể khôi phục nhanh chóng sau các cuộc tấn công mạng, lỗi phần cứng hoặc thảm họa.

## Lỗ hổng Veeam bị các nhóm ransomware nhắm tới

VBR đặc biệt phổ biến trong các doanh nghiệp vừa và lớn cũng như các nhà cung cấp dịch vụ được quản lý, nhưng nó cũng thường bị các nhóm ransomware nhắm tới, vì VBR có thể là điểm quay nhanh để di chuyển ngang trong môi trường của nạn nhân.

Các nhóm ransomware trước đây đã [cho BleepingComputer biết](https://www.bleepingcomputer.com/news/security/ransomware-attackers-use-your-cloud-backups-against-you/) rằng họ luôn nhắm vào các máy chủ VBR của nạn nhân vì điều đó đơn giản hóa việc đánh cắp dữ liệu và làm cho việc khôi phục trở nên khó khăn bằng cách xóa các bản sao lưu trước khi triển khai payload ransomware.

Nhóm Cuba ransomware và nhóm có động cơ tài chính FIN7 (nhóm này trước đây từng hợp tác với các nhóm ransomware Conti, REvil, Maze, Egregor, và BlackBasta) cũng từng được liên kết với các cuộc tấn công nhắm vào lỗ hổng VBR trong quá khứ.

Gần đây hơn, các nhân viên phản ứng sự cố Sophos X-Ops đã tiết lộ vào tháng 11 năm 2024 rằng Frag ransomware đã khai thác một lỗ hổng RCE khác của VBR (CVE-2024-40711) [được tiết lộ hai tháng trước đó.](https://www.bleepingcomputer.com/news/security/veeam-warns-of-critical-rce-flaw-in-backup-and-replication-software/) Cùng lỗ hổng bảo mật này cũng đã được sử dụng [trong các cuộc tấn công Akira và Fog ransomware](https://www.bleepingcomputer.com/news/security/akira-and-fog-ransomware-now-exploiting-critical-veeam-rce-flaw/) nhắm vào các máy chủ Veeam backup dễ bị tấn công bắt đầu từ tháng 10 năm 2024.

Sản phẩm của Veeam được sử dụng bởi [hơn 550,000 khách hàng] trên toàn thế giới, bao gồm 74% các công ty thuộc Global 2,000 và 82% các công ty thuộc Fortune 500.