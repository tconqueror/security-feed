# The role of the cybersecurity PM in incident-driven development

![ThreatLocker header](https://www.bleepstatic.com/content/posts/2025/07/23/threatlocker-leading-with-urgency.jpg)

_Article written by cybersecurity expert Yuriy Tsibere._

Gone are the days when cybersecurity meant stopping annoying viruses like the Love Bug. Today, it’s about battling a massive, financially motivated cybercrime industry. Attacks are smarter, faster, and more damaging—and that changes everything for product teams.

For product managers (PMs), this means understanding that attackers are constantly exploiting the same weak spots: stolen admin credentials, missing multi-factor authentication (MFA) on VPNs, remote encryption, and clever “living off the land” (LOTL) tricks like using Office to launch PowerShell.

Even something as simple as an unpatched firewall or a rogue USB drive can open the door to a breach.

New vulnerabilities and zero-days are popping up all the time, and product teams have to stay on their toes. A few examples:

* **WannaCry (2017):** Used the EternalBlue flaw in SMBv1 to spread ransomware fast. It forced companies to disable SMBv1 altogether.
* **Some Exchange Server bugs:** Let attackers run malicious scripts, sometimes leading to ransomware.
* **Log4j vulnerability:** A vulnerability in a popular Java logging framework that enables arbitrary code execution. Still showing up in outdated firewalls and VPNs.
* **Follina (MSDT):** Let Office apps launch PowerShell without any user interaction.

Timely patching helps, but it’s not enough. There’s always a gap between discovering a flaw and fixing it. That’s why teams need layered defenses and a mindset that’s ready to respond to incidents as they happen.

## How breach reports drive real-time product shifts

The 100 days to secure your environment [webinar series from ThreatLocker](https://www.youtube.com/playlist?list=PLErDVxBnz0lxGJ7hb9-RWv9bizYCxnJ-g) is a great example of incident-driven development. It helps security leaders focus on what matters most in their first few months.

Real-world breaches often directly lead to new product features or policy changes. Here’s how:

* **Unlocked machines:** a threat actor once accessed a hospital computer that was left open and ran PowerShell. Now, password-protected screen savers are a must.
* **USB data theft:** USB drives are still a go-to for stealing data. Products now offer fine-grained USB controls—blocking unencrypted drives, limiting file types, or capping how many files can be copied.
* **Lateral movement:** Ransomware often spreads using old admin accounts. Tools now detect and remove these after review.
* **LOTL attacks:** Follina showed how legit tools can be misused. [Ringfencing™ helps stop apps](https://www.threatlocker.com/platform/ringfencing) from launching things they shouldn’t.
* **Outbound traffic abuse:** Attacks like SolarWinds used outbound connections. Now, default-deny policies for server traffic are becoming standard.
* **Stolen credentials:** MFA is non-negotiable for cloud accounts, remote access, and domain controllers.
* **Vulnerable VPNs:** Unpatched VPNs are a big risk. Features now include IP-based access controls or even disabling unused VPNs.

## The PM's response: From advisory to actionable feature

For cybersecurity PMs, reacting to threats means more than just writing advisories. It’s about building smarter, safer products. Here’s how:

1. **Get full visibility**  
 Start by understanding what’s running in your environment. Use monitoring agents to track file activity, privilege changes, app launches, and network traffic.
2. **Prioritize risks**  
 With a complete picture, PMs can focus on high-risk tools and behaviors:  
   * Remote access tools like TeamViewer or AnyDesk  
   * Software with too many permissions (e.g., 7-Zip, Nmap)  
   * Risky browser extensions  
   * Software from high-risk regions
3. **Drive adaptive policy creation**  
 Security policies should evolve with the threat landscape:  
   * Test first: Use monitor-only mode and test groups before enforcing new rules.  
   * Be precise: Go beyond on/off switches—use dynamic ACLs, Ringfencing, and app-specific admin rights.  
   * Encourage adoption by minimizing disruption  
         * Offer a store of pre-approved apps  
         * Make it easy to request new software  
         * Explain why restrictions exist—it builds trust  
   * Continuous improvement and monitoring:  
         * Use health reports to spot misconfigurations  
         * Block USB file copies if thresholds are exceeded  
         * Clean up old policies and unused apps regularly
4. **Embrace patch management**  
 Make sure everything—from operating systems to portable applications like PuTTY—is up to date. Use tools to find missing patches and test them with pilot users before rolling out.
5. **Protect backups**  
 Backups must be shielded from compromise. This includes limiting which apps can access them and requiring MFA for backup services. PMs should also test the backups regularly to validate recovery readiness.

Cybersecurity PMs are on the front lines of using real-world protections against real-world threats.

By staying informed, collecting the right data, and building with users in mind, you can reduce risk without making life harder for your team.

**[Book a demo today to learn how ThreatLocker Patch Management can help you with these tasks.](https://www.threatlocker.com/platform/patch-management?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=sponsor&utm%5Fcampaign=yuriy%5F1%5Fq3%5F25&utm%5Fcontent=yuriy%5F1&utm%5Fterm=article)**

_Sponsored and written by [ThreatLocker](https://www.threatlocker.com/pages/application-control-allowlisting?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=sponsor&utm%5Fcampaign=yuriy%5F1%5Fq3%5F25&utm%5Fcontent=yuriy%5F1&utm%5Fterm=article)._

---

# Vai trò của PM an ninh mạng trong phát triển dựa trên sự cố

![ThreatLocker header](https://www.bleepstatic.com/content/posts/2025/07/23/threatlocker-leading-with-urgency.jpg)

_Bài viết của chuyên gia an ninh mạng Yuriy Tsibere._

Những ngày mà an ninh mạng chỉ có nghĩa là ngăn chặn những virus gây khó chịu như Love Bug đã qua rồi. Ngày nay, nó là về việc chiến đấu với một ngành tội phạm mạng lớn mạnh, có động cơ tài chính. Các cuộc tấn công ngày càng thông minh hơn, nhanh hơn, và gây hại hơn—và điều đó thay đổi mọi thứ cho các đội sản phẩm.

Đối với các quản lý sản phẩm (PMs), điều này có nghĩa là hiểu rằng những kẻ tấn công luôn khai thác những điểm yếu giống nhau: thông tin đăng nhập admin bị đánh cắp, thiếu xác thực đa yếu tố (MFA) trên VPN, mã hóa từ xa, và những chiêu trò “sống dựa vào đất” (LOTL) thông minh như việc sử dụng Office để khởi động PowerShell.

Thậm chí một điều đơn giản như một tường lửa chưa được vá hoặc một ổ USB độc hại có thể mở ra cánh cửa cho một cuộc xâm nhập.

Các lỗ hổng mới và zero-day đang xuất hiện liên tục, và các đội sản phẩm phải luôn cảnh giác. Một vài ví dụ:

* **WannaCry (2017):** Đã sử dụng lỗi EternalBlue trong SMBv1 để lây lan ransomware nhanh chóng. Nó buộc các công ty phải vô hiệu hóa hoàn toàn SMBv1.
* **Một số lỗi của Exchange Server:** Cho phép các kẻ tấn công chạy các script độc hại, đôi khi dẫn đến ransomware.
* **Lỗi Log4j:** Một lỗ hổng trong một framework ghi log Java phổ biến cho phép thực thi mã tùy ý. Vẫn xuất hiện trong các tường lửa và VPN đã lỗi thời.
* **Follina (MSDT):** Cho phép các ứng dụng Office khởi động PowerShell mà không cần tương tác của người dùng.

Việc vá lỗi kịp thời giúp ích, nhưng không đủ. Luôn có một khoảng cách giữa việc phát hiện một lỗi và việc sửa chữa nó. Đó là lý do tại sao các nhóm cần phải có các biện pháp bảo vệ nhiều lớp và một tư duy chuẩn bị sẵn sàng để phản ứng với các sự cố khi chúng xảy ra.

## Cách báo cáo vi phạm thúc đẩy sự thay đổi sản phẩm theo thời gian thực

Chương trình webinar 100 ngày để bảo vệ môi trường của bạn [từ ThreatLocker](https://www.youtube.com/playlist?list=PLErDVxBnz0lxGJ7hb9-RWv9bizYCxnJ-g) là một ví dụ tuyệt vời về phát triển dựa trên sự cố. Nó giúp các nhà lãnh đạo an ninh tập trung vào những gì quan trọng nhất trong vài tháng đầu tiên của họ.

Các cuộc vi phạm thực tế thường dẫn trực tiếp đến các tính năng sản phẩm mới hoặc thay đổi chính sách. Dưới đây là cách:

* **Máy tính không khóa:** một kẻ tấn công đã truy cập vào một máy tính bệnh viện bỏ ngỏ và chạy PowerShell. Bây giờ, các chương trình bảo vệ màn hình bằng mật khẩu là điều bắt buộc.
* **Ăn cắp dữ liệu USB:** Ổ USB vẫn là lựa chọn hàng đầu để ăn cắp dữ liệu. Các sản phẩm hiện nay cung cấp kiểm soát USB chính xác—chặn các ổ không được mã hóa, hạn chế loại file, hoặc giới hạn số lượng file có thể được sao chép.
* **Di chuyển ngang:** Ransomware thường lây lan bằng cách sử dụng các tài khoản admin cũ. Các công cụ hiện nay phát hiện và xóa chúng sau khi xem xét.
* **Tấn công LOTL:** Follina đã cho thấy các công cụ hợp pháp có thể bị lạm dụng. [Ringfencing™ giúp ngăn chặn các ứng dụng](https://www.threatlocker.com/platform/ringfencing) khỏi việc khởi động những thứ mà chúng không nên.
* **Sử dụng lưu lượng outbound:** Các cuộc tấn công như SolarWinds đã sử dụng các kết nối outbound. Bây giờ, chính sách từ chối mặc định cho lưu lượng máy chủ đang trở thành tiêu chuẩn.
* **Thông tin đăng nhập bị đánh cắp:** MFA là điều không thể thương lượng cho các tài khoản đám mây, truy cập từ xa, và các bộ điều khiển miền.
* **VPN dễ tổn thương:** Các VPN chưa được vá là một rủi ro lớn. Các tính năng hiện nay bao gồm các kiểm soát truy cập dựa trên IP hoặc thậm chí vô hiệu hóa các VPN không sử dụng.

## Phản ứng của PM: Từ tư vấn đến tính năng có thể hành động

Đối với các PM an ninh mạng, phản ứng với các mối đe dọa có nghĩa là hơn cả việc viết tư vấn. Đó là về việc xây dựng các sản phẩm thông minh hơn, an toàn hơn. Đây là cách:

1. **Có được cái nhìn tổng quan đầy đủ**  
 Bắt đầu bằng cách hiểu những gì đang chạy trong môi trường của bạn. Sử dụng các tác nhân giám sát để theo dõi hoạt động file, thay đổi quyền, khởi động ứng dụng, và lưu lượng mạng.
2. **Ưu tiên rủi ro**  
 Với một bức tranh hoàn chỉnh, PMs có thể tập trung vào các công cụ và hành vi có rủi ro cao:  
   * Các công cụ truy cập từ xa như TeamViewer hoặc AnyDesk  
   * Phần mềm với quá nhiều quyền (ví dụ: 7-Zip, Nmap)  
   * Các mở rộng trình duyệt rủi ro  
   * Phần mềm từ các khu vực có rủi ro cao
3. **Thúc đẩy việc tạo ra chính sách thích ứng**  
 Các chính sách an ninh nên phát triển cùng với cảnh quan mối đe dọa:  
   * Kiểm tra trước: Sử dụng chế độ chỉ giám sát và các nhóm thử nghiệm trước khi thực thi các quy tắc mới.  
   * Chính xác: Đừng chỉ sử dụng công tắc bật/tắt—sử dụng ACL động, Ringfencing, và quyền admin cụ thể cho ứng dụng.  
   * Khuyến khích sự chấp nhận bằng cách giảm thiểu gián đoạn  
         * Cung cấp một cửa hàng các ứng dụng đã được phê duyệt  
         * Làm cho việc yêu cầu phần mềm mới dễ dàng  
         * Giải thích lý do tồn tại của các hạn chế—nó xây dựng lòng tin  
   * Cải tiến và giám sát liên tục:  
         * Sử dụng báo cáo sức khỏe để phát hiện cấu hình sai  
         * Chặn sao chép file USB nếu vượt quá ngưỡng  
         * Thường xuyên làm sạch các chính sách cũ và ứng dụng không sử dụng
4. **Chấp nhận quản lý vá lỗi**  
 Đảm bảo mọi thứ—từ hệ điều hành đến các ứng dụng di động như PuTTY—đều được cập nhật. Sử dụng các công cụ để tìm kiếm các bản vá còn thiếu và thử nghiệm chúng với người dùng thử nghiệm trước khi triển khai.
5. **Bảo vệ sao lưu**  
 Các bản sao lưu phải được bảo vệ khỏi sự xâm phạm. Điều này bao gồm việc hạn chế các ứng dụng có thể truy cập vào chúng và yêu cầu MFA cho các dịch vụ sao lưu. PMs cũng nên kiểm tra các bản sao lưu thường xuyên để xác thực khả năng phục hồi.

Các PM an ninh mạng đang ở trước mặt trận sử dụng các biện pháp bảo vệ thực tế chống lại các mối đe dọa thực tế.

Bằng cách giữ cho mình được thông tin, thu thập dữ liệu chính xác, và xây dựng với người dùng trong tâm trí, bạn có thể giảm thiểu rủi ro mà không làm cuộc sống khó khăn hơn cho đội của mình.

**[Đặt lịch trình demo ngay hôm nay để tìm hiểu cách ThreatLocker Patch Management có thể giúp bạn thực hiện những nhiệm vụ này.](https://www.threatlocker.com/platform/patch-management?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=sponsor&utm%5Fcampaign=yuriy%5F1%5Fq3%5F25&utm%5Fcontent=yuriy%5F1&utm%5Fterm=article)**

_Được tài trợ và viết bởi [ThreatLocker](https://www.threatlocker.com/pages/application-control-allowlisting?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=sponsor&utm%5Fcampaign=yuriy%5F1%5Fq3%5F25&utm%5Fcontent=yuriy%5F1&utm%5Fterm=article)._

---

- **Các điểm yếu dễ bị tổn thương:** Thông tin đăng nhập admin bị đánh cắp, thiếu MFA trên VPN và tường lửa không được vá có thể mở đường cho các cuộc xâm nhập.
- **Sự phát triển của lỗ hổng:** Các lỗ hổng mới thường xuyên xuất hiện, cái mà PMs cần theo dõi và thực hiện các biện pháp khắc phục kịp thời.
- **Tác động của sự cố thực tế:** Các cuộc vi phạm thực tế dẫn đến việc cải thiện các tính năng sản phẩm và chính sách như khóa máy tính và kiểm soát USB.
- **Phát triển chính sách an ninh:** Cần phải có chính sách an ninh thích ứng, có thể thử nghiệm trước khi thực thi và khuyến khích sử dụng thông qua việc giảm thiểu gián đoạn.
- **Quản lý vá lỗi:** Việc cập nhật hệ điều hành và ứng dụng là thiết yếu để giữ cho môi trường an toàn, kèm theo các công cụ phát hiện bản vá còn thiếu.
- **Bảo vệ sao lưu:** Bảo vệ các bản sao lưu bằng cách hạn chế truy cập và yêu cầu MFA đã trở thành ưu tiên quan trọng để đảm bảo an toàn dữ liệu.