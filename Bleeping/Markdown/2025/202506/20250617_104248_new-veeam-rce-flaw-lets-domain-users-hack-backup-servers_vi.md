# Lỗ hổng RCE mới của Veeam cho phép người dùng miền tấn công máy chủ sao lưu

![Veeam](https://www.bleepstatic.com/content/hl-images/2024/11/08/Veeam.jpg)

Veeam đã phát hành các bản cập nhật bảo mật hôm nay để sửa chữa một số lỗ hổng trong Veeam Backup & Replication (VBR), bao gồm một lỗ hổng nghiêm trọng về thực thi mã từ xa (RCE).

Được theo dõi dưới mã CVE-2025-23121, lỗ hổng bảo mật này đã được các nhà nghiên cứu bảo mật tại watchTowr và CodeWhite báo cáo và chỉ ảnh hưởng đến các cài đặt đã tham gia miền.

Như Veeam đã [giải thích](https://www.veeam.com/kb4743) trong một thông báo bảo mật vào thứ Ba, lỗ hổng này có thể bị khai thác bởi những người dùng miền đã xác thực thông qua các cuộc tấn công có độ phức tạp thấp để có được quyền thực thi mã từ xa trên Máy chủ Sao lưu. Lỗi này ảnh hưởng đến Veeam Backup & Replication phiên bản 12 trở lên và đã được sửa trong phiên bản 12.3.2.3617, đã được phát hành vào sáng nay.

Mặc dù CVE-2025-23121 chỉ ảnh hưởng đến các cài đặt VBR đã tham gia miền, bất kỳ người dùng miền nào cũng có thể khai thác nó, khiến nó trở nên dễ bị lợi dụng trong các cấu hình đó.

Đáng tiếc, nhiều công ty đã tham gia máy chủ sao lưu của họ vào một miền Windows, phớt lờ [các phương pháp tốt nhất của Veeam](https://bp.veeam.com/security/Design-and-implementation/Hardening/Workgroup%5For%5FDomain.html#best-practice), khuyên các quản trị viên nên sử dụng một Forest Active Directory riêng biệt và bảo vệ các tài khoản quản trị bằng xác thực hai yếu tố.

Vào tháng Ba, Veeam đã [vá một lỗ hổng RCE khác](https://www.bleepingcomputer.com/news/security/veeam-rce-bug-lets-domain-users-hack-backup-servers-patch-now/) (CVE-2025-23120) trong phần mềm Backup & Replication của Veeam ảnh hưởng đến các cài đặt đã tham gia miền.

Các băng nhóm ransomware cũng đã [nói với BleepingComputer](https://www.bleepingcomputer.com/news/security/ransomware-attackers-use-your-cloud-backups-against-you/) nhiều năm trước rằng họ luôn nhắm đến các máy chủ VBR vì chúng đơn giản hóa việc lấy cắp dữ liệu của các nạn nhân và chặn các nỗ lực phục hồi bằng cách xóa các bản sao lưu trước khi triển khai các tải trọng ransomware trên mạng của các nạn nhân.

Như các nhân viên ứng phó sự cố Sophos X-Ops đã tiết lộ vào tháng 11, một lỗ hổng RCE khác trong VBR (CVE-2024-40711) [được công bố vào tháng 9](https://www.bleepingcomputer.com/news/security/veeam-warns-of-critical-rce-flaw-in-backup-and-replication-software/) hiện đang bị khai thác [để triển khai ransomware Frag](https://www.bleepingcomputer.com/news/security/critical-veeam-rce-bug-now-used-in-frag-ransomware-attacks/).

Lỗ hổng tương tự cũng đã được sử dụng để giành quyền thực thi mã từ xa trên các máy chủ sao lưu Veeam dễ bị tổn thương [trong các cuộc tấn công ransomware Akira và Fog](https://www.bleepingcomputer.com/news/security/akira-and-fog-ransomware-now-exploiting-critical-veeam-rce-flaw/) bắt đầu từ tháng 10.

Trong quá khứ, băng nhóm [Cuba ransomware](https://www.bleepingcomputer.com/news/security/cuba-ransomware-uses-veeam-exploit-against-critical-us-organizations/) và [FIN7,](https://www.bleepingcomputer.com/news/security/hackers-target-vulnerable-veeam-backup-servers-exposed-online/) một nhóm đe dọa có động cơ tài chính nổi tiếng hợp tác với các băng nhóm ransomware Conti, REvil, Maze, Egregor và BlackBasta, cũng đã được quan sát thấy khai thác các lỗ hổng VBR.

Sản phẩm của Veeam được sử dụng bởi [hơn 550,000 khách hàng](https://www.veeam.com/company/press-release/veeam-the-worlds-1-leader-in-data-resilience-launches-new-enterprise-capabilities-in-veeam-data-platform-v12-3-including-microsoft-entra-id-protection.html) trên toàn thế giới, bao gồm 82% các công ty trong danh sách Fortune 500 và 74% các công ty trong danh sách Global 2,000.