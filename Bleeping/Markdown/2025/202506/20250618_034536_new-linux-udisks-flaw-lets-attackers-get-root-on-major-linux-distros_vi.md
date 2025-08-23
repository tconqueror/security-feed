# Lỗi udisks mới trên Linux cho phép kẻ tấn công chiếm quyền root trên các bản phân phối Linux chính

![Linux](https://www.bleepstatic.com/content/hl-images/2024/05/31/Linux.jpg)

Kẻ tấn công có thể khai thác hai lỗ hổng leo thang đặc quyền (LPE) mới được phát hiện để có được quyền root trên các hệ thống chạy các bản phân phối Linux chính.

Lỗ hổng đầu tiên (được theo dõi là [CVE-2025-6018](https://security-tracker.debian.org/tracker/CVE-2025-6018)) được phát hiện trong cấu hình của khung Pluggable Authentication Modules (PAM) trên openSUSE Leap 15 và SUSE Linux Enterprise 15, cho phép kẻ tấn công nội bộ thu được quyền hạn của người dùng "allow_active".

Lỗi bảo mật khác ([CVE-2025-6019](https://security-tracker.debian.org/tracker/CVE-2025-6019)) được phát hiện trong libblockdev, cho phép người dùng "allow_active" có được quyền root thông qua daemon udisks (một dịch vụ quản lý lưu trữ chạy theo mặc định trên hầu hết các bản phân phối Linux).

Trong khi việc khai thác thành công hai lỗ hổng như một phần của cuộc tấn công "local-to-root" có thể cho phép kẻ tấn công nhanh chóng chiếm quyền root và hoàn toàn kiểm soát hệ thống SUSE, lỗ hổng libblockdev/udisks cũng cực kỳ nguy hiểm khi tự nó.

"Mặc dù nó về mặt lý thuyết yêu cầu quyền 'allow_active', nhưng udisks được cung cấp theo mặc định trên gần như tất cả các bản phân phối Linux, vì vậy hầu như hệ thống nào cũng dễ bị tổn thương," [nói](https://blog.qualys.com/vulnerabilities-threat-research/2025/06/17/qualys-tru-uncovers-chained-lpe-suse-15-pam-to-full-root-via-libblockdev-udisks) quản lý cấp cao Saeed Abbasi của Qualys TRU.

"Các kỹ thuật để thu được 'allow_active', bao gồm vấn đề PAM được công bố ở đây, càng làm suy yếu rào cản đó. Một kẻ tấn công có thể liên kết những lỗ hổng này để chiếm đoạt root ngay lập tức với nỗ lực tối thiểu."

Đơn vị Nghiên cứu Đe dọa Qualys (TRU), đơn vị đã phát hiện và báo cáo cả hai lỗ hổng, đã phát triển các exploit proof-of-concept và thành công trong việc nhắm vào CVE-2025-6019 để có được quyền root trên các hệ thống Ubuntu, Debian, Fedora, và openSUSE Leap 15.

## Khuyến cáo các quản trị viên cập nhật ngay lập tức

Đội ngũ Cố vấn Bảo mật của Qualys đã chia sẻ thêm thông tin chi tiết kỹ thuật về hai lỗ hổng này [tại đây](https://cdn2.qualys.com/2025/06/17/suse15-pam-udisks-lpe.txt) và liên kết đến các bản vá bảo mật trong bài viết [Openwall này](https://www.openwall.com/lists/oss-security/2025/06/17/5).

"Truy cập root cho phép can thiệp vào agent, lưu lại và di chuyển ngang, vì vậy một máy chủ chưa được vá sẽ làm nguy hiểm toàn bộ đội hình. Cần vá cả PAM và libblockdev/udisks ở mọi nơi để loại bỏ con đường này," Abbasi nói thêm.

"Với sự phổ biến của udisks và sự đơn giản của exploit, các tổ chức phải coi đây là **một rủi ro nghiêm trọng, phổ quát và triển khai các bản vá mà không chậm trễ**."

Trong những năm gần đây, các nhà nghiên cứu của Qualys đã phát hiện ra một số lỗ hổng bảo mật Linux khác cho phép kẻ tấn công chiếm đoạt các hệ thống Linux chưa được vá, thậm chí trong cấu hình mặc định.

Các lỗ hổng bảo mật mà họ phát hiện bao gồm một lỗ hổng trong thành phần pkexec của Polkit ([được gọi là PwnKit](https://www.bleepingcomputer.com/news/security/linux-system-service-bug-gives-root-on-all-major-distros-exploit-released/)), một trong trình tải động ld.so của glibc ([Looney Tunables](https://www.bleepingcomputer.com/news/security/new-looney-tunables-linux-bug-gives-root-on-major-distros/)), một trong lớp filesystem của Kernel ([được gọi là Sequoia](https://www.bleepingcomputer.com/news/security/new-linux-kernel-bug-lets-you-get-root-on-most-modern-distros/)), và một trong chương trình Sudo Unix (còn gọi là [Baron Samedit](https://www.bleepingcomputer.com/news/security/new-linux-sudo-flaw-lets-local-users-gain-root-privileges/)).

Ngay sau khi lỗ hổng Looney Tunables được công bố, các exploit proof-of-concept (PoC) đã được [phát hành trực tuyến](https://www.bleepingcomputer.com/news/security/exploits-released-for-linux-flaw-giving-root-on-major-distros/). Một tháng sau, kẻ tấn công [bắt đầu khai thác nó](https://www.bleepingcomputer.com/news/security/hackers-exploit-looney-tunables-linux-bug-steal-cloud-creds/) để đánh cắp thông tin xác thực của nhà cung cấp dịch vụ đám mây (CSP) bằng cách sử dụng malware Kinsing.

Qualys cũng gần đây [đã phát hiện năm lỗ hổng LPE](https://www.bleepingcomputer.com/news/security/ubuntu-linux-impacted-by-decade-old-needrestart-flaw-that-gives-root/) được giới thiệu hơn 10 năm trước trong tiện ích needrestart được sử dụng theo mặc định trong Ubuntu Linux 21.04 và các phiên bản sau.