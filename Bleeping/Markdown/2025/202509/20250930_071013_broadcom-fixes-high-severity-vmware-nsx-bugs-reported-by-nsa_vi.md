# Broadcom vá các lỗ hổng VMware NSX mức độ nghiêm trọng cao được NSA báo cáo

![VMware](https://www.bleepstatic.com/content/hl-images/2024/11/18/VMware.jpg)

Broadcom đã phát hành bản cập nhật bảo mật để vá hai lỗ hổng VMware NSX mức độ nghiêm trọng cao do the U.S. National Security Agency (NSA) báo cáo.

VMware NSX là một giải pháp ảo hóa mạng trong VMware Cloud Foundation cho phép quản trị viên triển khai các ứng dụng truyền thống và hiện đại trong các đám mây riêng/hybrid.

Lỗ hổng bảo mật đầu tiên được NSA báo cáo, được theo dõi là [CVE-2025-41251](https://nvd.nist.gov/vuln/detail/CVE-2025-41251), là do một điểm yếu trong cơ chế khôi phục mật khẩu, có thể cho phép các tác nhân chưa xác thực liệt kê được tên người dùng hợp lệ, điều này sau đó có thể được sử dụng trong các cuộc tấn công brute-force.

Lỗ hổng thứ hai ([CVE-2025-41252](https://nvd.nist.gov/vuln/detail/CVE-2025-41252)) là một lỗ hổng liệt kê tên người dùng mà các tác nhân đe dọa chưa xác thực cũng có thể khai thác để liệt kê tên người dùng hợp lệ, có khả năng dẫn đến các nỗ lực truy cập trái phép.

"Broadcom would like to thank the National Security Agency for reporting this issue to us," công ty [cho biết](https://support.broadcom.com/web/ecx/support-content-notification/-/external/content/SecurityAdvisories/0/36150) trong một thông báo bảo mật hôm thứ Hai.

Hôm qua, công ty đã vá một lỗ hổng tiêm header SMTP mức độ nghiêm trọng cao ([CVE-2025-41250](https://nvd.nist.gov/vuln/detail/CVE-2025-41250)) trong VMware vCenter, có thể cho phép kẻ tấn công có đặc quyền không phải quản trị viên và có quyền tạo scheduled tasks thao túng các email thông báo được gửi cho các scheduled tasks.

Trong một thông báo bảo mật thứ hai, Broadcom tiết lộ thêm ba lỗ hổng bảo mật trong VMware Aria Operations và VMware Tools (CVE-2025-41244, CVE-2025-41245, CVE-2025-41246) có thể bị khai thác để leo thang đặc quyền lên root, đánh cắp thông tin đăng nhập của người dùng khác và truy cập các guest VM khác.

Đầu năm nay, [Broadcom cũng đã vá bốn lỗ hổng](https://www.bleepingcomputer.com/news/security/vmware-fixes-four-esxi-zero-day-bugs-exploited-at-pwn2own-berlin/) trong VMware ESXi, Workstation, Fusion, và Tools, những lỗ hổng này đã bị tiết lộ và khai thác như zero-days trong cuộc thi hack Pwn2Own Berlin 2025 vào tháng 5 năm 2025, sau khi [vá ba zero-days VMware đang bị khai thác tích cực](https://www.bleepingcomputer.com/news/security/broadcom-fixes-three-vmware-zero-days-exploited-in-attacks/) (CVE-2025-22224, CVE-2025-22225, và CVE-2025-22226) do Microsoft Threat Intelligence Center báo cáo.

Các hacker được nhà nước bảo trợ và các băng nhóm tội phạm mạng, bao gồm các hoạt động ransomware, thường xuyên nhắm mục tiêu vào các lỗ hổng VMware, vì các doanh nghiệp sử dụng rộng rãi các sản phẩm VMware để chuyển và lưu trữ dữ liệu nhạy cảm của công ty.

Ví dụ, vào tháng Mười Một, [kẻ tấn công bắt đầu khai thác](https://www.bleepingcomputer.com/news/security/critical-rce-bug-in-vmware-vcenter-server-now-exploited-in-attacks/) hai lỗ hổng VMware vCenter Server, một lỗ hổng leo thang đặc quyền lên root (CVE-2024-38813) và một lỗ hổng thực thi mã từ xa nghiêm trọng (CVE-2024-38812), được tiết lộ trong cuộc thi hack Matrix Cup 2024 của Trung Quốc.

Vào tháng Một năm 2024, các hacker nhà nước Trung Quốc bị [liên kết với các cuộc tấn công khai thác một zero-day nghiêm trọng của vCenter Server](https://www.bleepingcomputer.com/news/security/chinese-hackers-exploit-vmware-bug-as-zero-day-for-two-years/) (CVE-2023-34048) kể từ cuối năm 2021, điều này dẫn đến việc [triển khai các backdoor VirtualPita và VirtualPie](https://www.bleepingcomputer.com/news/security/new-malware-backdoors-vmware-esxi-servers-to-hijack-virtual-machines/) trên các hệ thống ESXi bị xâm phạm.