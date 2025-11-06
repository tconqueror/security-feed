# Tin tặc Sandworm sử dụng mã độc xóa dữ liệu để phá hoại ngành ngũ cốc của Ukraine

![Tin tặc Sandworm sử dụng mã độc xóa dữ liệu để phá hoại ngành ngũ cốc của Ukraine](https://www.bleepstatic.com/content/hl-images/2025/11/06/hacker.jpg)

Nhóm tin tặc được nhà nước hậu thuẫn Russian Sandworm đã triển khai nhiều họ phần mềm xóa dữ liệu trong các cuộc tấn công nhắm vào hệ thống giáo dục, chính phủ và ngành ngũ cốc của Ukraine, nguồn doanh thu chính của nước này.

Các cuộc tấn công diễn ra vào tháng Sáu và tháng Chín, công ty an ninh mạng ESET cho biết trong một báo cáo hôm nay, và tiếp tục chuỗi các hoạt động phá hoại của Sandworm (a.k.a. APT44) ở Ukraine.

Như tên gọi gợi ý, mục đích của một mã độc xóa dữ liệu là phá hủy thông tin số của mục tiêu bằng cách làm hỏng hoặc xóa tập tin, phân vùng đĩa và master boot records theo cách không cho phép khôi phục. Tác động lên mục tiêu có thể rất tàn phá, tạo ra gián đoạn khó khắc phục.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Không giống ransomware, nơi dữ liệu thường bị đánh cắp rồi mã hóa, mã độc dạng wiper được sử dụng thuần túy trong các chiến dịch phá hoại.

Sau cuộc xâm lược của Russia, Ukraine đã trở thành mục tiêu của nhiều chiến dịch mã độc xóa dữ liệu, phần lớn được quy cho các tác nhân do nhà nước Russia tài trợ, bao gồm [PathWiper](https://www.bleepingcomputer.com/news/security/new-pathwiper-data-wiper-malware-hits-critical-infrastructure-in-ukraine/), [HermeticWiper](https://www.bleepingcomputer.com/news/security/new-data-wiping-malware-used-in-destructive-attacks-on-ukraine/), [CaddyWiper](https://www.bleepingcomputer.com/news/security/new-caddywiper-data-wiping-malware-hits-ukrainian-networks/), [Whispergate](https://www.bleepingcomputer.com/news/security/microsoft-fake-ransomware-targets-ukraine-in-data-wiping-attacks/), và [IsaacWiper](https://www.bleepingcomputer.com/news/security/new-worm-and-data-wiper-malware-seen-hitting-ukrainian-networks/).

### Các cuộc tấn công phá hoại tiếp tục

Báo cáo mới của ESET bao quát hoạt động của các advanced persistent threat (APT) giữa tháng Tư và tháng Chín 2025 và trình bày một số trường hợp wiper được triển khai ở Ukraine, một vài trong số đó nhắm vào sản xuất ngũ cốc của nước này.

Đây là một diễn biến mới, khi các kẻ tấn công đang cho thấy họ bây giờ tập trung vào ngành kinh tế then chốt của Ukraine, bởi xuất khẩu ngũ cốc là nguồn thu chính, đặc biệt trong thời chiến.

“Vào tháng Sáu và tháng Chín, Sandworm đã triển khai nhiều biến thể phần mềm xóa dữ liệu chống lại các thực thể Ukraine hoạt động trong các lĩnh vực chính phủ, năng lượng, logistics và ngũ cốc,” [giải thích ESET](https://www.welivesecurity.com/en/eset-research/eset-apt-activity-report-q2-2025-q3-2025/).

“Mặc dù cả bốn lĩnh vực đều từng là mục tiêu của các cuộc tấn công wiper vào một thời điểm nào đó kể từ 2022, ngành ngũ cốc nổi bật là một mục tiêu không thường xuyên.”

“Xét rằng xuất khẩu ngũ cốc vẫn là một trong những nguồn thu chính của Ukraine, việc nhắm vào như vậy có khả năng phản ánh nỗ lực làm suy yếu nền kinh tế chiến tranh của nước này.”

APT44 cũng đã triển khai các wiper ‘ZeroLot’ và ‘Sting’ vào tháng Tư 2025, nhắm vào một trường đại học ở Ukraine. Sting được thực thi thông qua một tác vụ đã lên lịch trên Windows có tên theo món ăn truyền thống Hungarian goulash.

Lưu ý rằng truy cập ban đầu cho một số sự cố này được đạt được bởi UAC-0099, người sau đó chuyển quyền truy cập cho APT44 để triển khai wiper.

UAC-0099 là một tác nhân đe dọa đã hoạt động từ ít nhất năm 2023 và dường như tập trung các cuộc tấn công vào các tổ chức Ukraine.

Các nhà nghiên cứu lưu ý rằng trong khi [Sandworm](https://www.bleepingcomputer.com/news/security/russian-sandworm-hackers-pose-as-hacktivists-in-water-utility-breaches/) gần đây đã cho thấy sự chú trọng lớn hơn vào các hoạt động gián điệp, các cuộc tấn công mã độc xóa dữ liệu chống lại các thực thể Ukraine vẫn là một hoạt động liên tục của nhóm đe dọa này.

ESET cũng xác định hoạt động liên quan tới Iran mà không thể quy cho một nhóm đe dọa cụ thể, nhưng phù hợp với các tactics, techniques, and procedures (TTPs) liên quan đến các hacker được Iran hậu thuẫn.

Vào tháng Sáu 2025, các cụm hoạt động này đã triển khai các công cụ Go-based dựa trên các wiper mã nguồn mở có sẵn công khai, nhắm vào các lĩnh vực năng lượng và kỹ thuật của Israel.

Phần lớn các hướng dẫn để ngăn chặn ransomware cũng giúp phòng thủ chống lại mã độc xóa dữ liệu. Một bước then chốt là giữ các bản sao lưu dữ liệu quan trọng trên phương tiện offline, ngoài tầm với của tin tặc.

Triển khai các hệ thống phát hiện điểm cuối và ngăn chặn xâm nhập mạnh mẽ và duy trì tất cả phần mềm được cập nhật có thể ngăn chặn một loạt các cuộc tấn công, bao gồm cả các sự cố xóa dữ liệu.