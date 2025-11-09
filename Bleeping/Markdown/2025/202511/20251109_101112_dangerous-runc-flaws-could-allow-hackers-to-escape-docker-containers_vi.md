# Lỗ hổng runC nguy hiểm có thể cho phép hacker thoát khỏi container Docker

![Lỗ hổng runC nguy hiểm có thể cho phép hacker thoát khỏi container Docker](https://www.bleepstatic.com/content/hl-images/2024/08/28/hacker.jpg)

Ba lỗ hổng mới được công bố trong runtime container runC được sử dụng trong Docker và Kubernetes có thể bị lợi dụng để vượt qua các hạn chế cô lập và truy cập vào hệ thống host.

Các vấn đề an ninh, được theo dõi dưới các mã CVE-2025-31133, CVE-2025-52565, và CVE-2025-52881 (all ), đã được báo cáo trong tuần này và được tiết lộ bởi kỹ sư phần mềm SUSE và thành viên hội đồng Open Container Initiative (OCI) [Aleksa Sarai](https://seclists.org/oss-sec/2025/q4/138).

runC là một [universal container runtime](https://www.docker.com/blog/runc/) và là triển khai tham chiếu của OCI để chạy container. Nó chịu trách nhiệm cho các thao tác mức thấp như tạo tiến trình container, thiết lập namespaces, mounts và cgroups mà các công cụ mức cao hơn, như Docker và Kubernetes, có thể gọi.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Kẻ tấn công lợi dụng các lỗ hổng có thể chiếm được quyền ghi trên host chứa container với đặc quyền root:

* [**CVE-2025-31133**](https://github.com/opencontainers/runc/security/advisories/GHSA-9493-h29p-rfm2) — runC sử dụng việc bind-mount /dev/null để “che” các tệp nhạy cảm trên host. Nếu kẻ tấn công thay thế /dev/null bằng một symlink trong quá trình khởi tạo container, runc có thể cuối cùng bind-mount một đích do kẻ tấn công điều khiển vào container với quyền đọc-ghi — cho phép ghi vào /proc và thoát container.
* [**CVE-2025-52565**](https://github.com/opencontainers/runc/security/advisories/GHSA-qw9x-cqr3-wc7r) — Mount bind /dev/console có thể bị chuyển hướng thông qua điều kiện race/symlink sao cho runc mount một đích bất ngờ vào container trước khi các cơ chế bảo vệ được áp dụng. Việc đó một lần nữa có thể làm lộ quyền ghi tới các mục procfs quan trọng và cho phép thoát.
* [**CVE-2025-52881**](https://github.com/opencontainers/runc/security/advisories/GHSA-cgrx-mc8f-2prm) — runC có thể bị lừa thực hiện các thao tác ghi vào /proc mà được chuyển hướng tới các đích do kẻ tấn công kiểm soát. Nó có thể vượt qua các cơ chế relabel của LSM trong một số biến thể và biến các thao tác ghi thông thường của runc thành các ghi tùy ý tới các tệp nguy hiểm như /proc/sysrq-trigger.

CVE-2025-31133 và CVE-2025-52881 ảnh hưởng tới tất cả các phiên bản của runC, trong khi CVE-2025-52565 ảnh hưởng các phiên bản runC 1.0.0-rc3 trở lên. Bản sửa lỗi có sẵn trong các phiên bản runC [1.2.8](https://github.com/opencontainers/runc/releases/tag/v1.2.8), [1.3.3](https://github.com/opencontainers/runc/releases/tag/v1.3.3), [1.4.0-rc.3](https://github.com/opencontainers/runc/releases/tag/v1.4.0-rc.3), và các phiên bản mới hơn.

## Khả năng khai thác và rủi ro

Các nhà nghiên cứu tại công ty an ninh đám mây Sysdig [ghi chú](http://www.sysdig.com/blog/runc-container-escape-vulnerabilities) rằng việc khai thác ba lỗ hổng này "đòi hỏi khả năng khởi tạo container với các cấu hình mount tùy chỉnh," điều mà kẻ tấn công có thể đạt được bằng hình ảnh container hoặc Dockerfile độc hại.

Hiện tại chưa có báo cáo nào về việc bất kỳ lỗ hổng nào trong số này bị khai thác tích cực trên thực tế.

Trong một advisory tuần này, Sysdig chia sẻ rằng các nỗ lực khai thác bất kỳ trong ba vấn đề an ninh này có thể được phát hiện bằng cách giám sát các hành vi symlink đáng ngờ.

Các nhà phát triển RunC cũng chia sẻ các hành động giảm nhẹ, bao gồm kích hoạt user namespaces cho tất cả container mà không ánh xạ người dùng root của host vào namespace của container.

Biện pháp phòng ngừa này nên chặn phần quan trọng nhất của cuộc tấn công nhờ các quyền Unix DAC sẽ ngăn cản người dùng được namespaced truy cập các tệp liên quan.

Sysdig cũng khuyến nghị sử dụng container không có quyền root nếu có thể, để giảm thiểu thiệt hại tiềm năng khi một lỗ hổng bị khai thác.