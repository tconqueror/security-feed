# Zeroday Cloud: cuộc thi tấn công mạng trao thưởng $4.5 million

![Zeroday Cloud: cuộc thi tấn công mạng trao thưởng $4.5 million](https://www.bleepstatic.com/content/hl-images/2025/10/06/logo.jpg)

Một cuộc thi tấn công mạng mới mang tên Zeroday Cloud, tập trung vào các công cụ đám mây mã nguồn mở và AI, đã công bố tổng quỹ giải thưởng $4.5 million tiền bounty cho các nhà nghiên cứu nộp exploit cho nhiều mục tiêu khác nhau.

Cuộc thi được khởi xướng bởi bộ phận nghiên cứu của công ty bảo mật đám mây Wiz phối hợp với Google Cloud, AWS và Microsoft, và dự kiến tổ chức vào ngày 10 và 11 tháng 12 tại hội nghị Black Hat Europe ở London, UK.

[Zeroday Cloud](http://www.zeroday.cloud/) có sáu hạng mục riêng biệt để các nhà nghiên cứu tham gia, với các bounty từ $10,000 đến $300,000:

* **AI** – Ollama ($25k), Vllm ($25k), Nvidia Container Toolkit ($40k)
* **Kubernetes và Cloud-Native** – Kubernetes API Server ($80k), Kubelet Server ($40k), Grafana ($10k auth RCE, $40k pre-auth RCE), Prometheus ($40k), Fluent Bit ($10k)
* **Containers và Virtualization** – Docker ($40 user-provided image, $60k arbitrary image), Containerd ($40 user-provided image, $60k arbitrary image), Linux Kernel ($30k container escape on Ubuntu)
* **Web Servers** – nginx ($300k), Apache Tomcat ($100k), Envoy ($50k), Caddy ($50k)
* **Databases** – Redis ($25k auth RCE, $100k pre-auth RCE), PostgreSQL ($20k auth RCE, $100k pre-auth RCE), MariaDB ($20k auth RCE, $100k pre-auth RCE)
* **DevOps & Automation** – Apache Airflow ($40k), Jenkins ($40k), GitLab CE ($40k)

Luật thi quy định rằng các exploit nộp vào phải dẫn tới việc thỏa hiệp hoàn toàn mục tiêu. Wiz giải thích rằng điều này có nghĩa là "a full Container/VM Escape for the Virtualization category, and a 0-click Remote Code Execution (RCE) vulnerability for other targets."

Ban tổ chức cũng cung cấp các [conditions for each target](http://github.com/wiz-sec-public/zeroday-cloud-2025), cũng như hướng dẫn và tài nguyên kỹ thuật (Docker container với mục tiêu ở cấu hình mặc định) để các nhà nghiên cứu bảo mật sử dụng kiểm thử exploit của họ.

Các nhà nghiên cứu đăng ký thông qua nền tảng HackerOne và hoàn tất xác minh danh tính và các mẫu thuế (Tax Forms) trước ngày 20 tháng 11, có thể nộp exploit cho bao nhiêu mục tiêu tùy ý, nhưng mỗi người chỉ được phép một bài dự thi cho mỗi mục tiêu.

Người nộp exploit được chấp nhận sẽ được mời trình diễn exploit trực tiếp trong sự kiện, độc lập hoặc theo đội tối đa năm thành viên.

Những người cư trú ở các quốc gia bị phong tỏa hoặc trừng phạt như Russia, China, Iran, North Korea, Cuba, Sudan, Syria, Libya, Lebanon, và cả các khu vực Crimea và Donetsk, bị hạn chế tham gia cuộc thi Zeroday Cloud.

Toàn bộ luật cho cuộc thi zeroday.cloud có thể được xem [tại đây](https://www.zeroday.cloud/rules).

Tuy nhiên, thông báo về sự kiện này đã không nhận được phản ứng tích cực từ ban tổ chức các cuộc thi Pwn2Own vốn đã rất thành công trong nhiều năm.

Trong một bài đăng công khai, Trend Micro [called out Wiz](https://www.linkedin.com/posts/trend-micro%5Fzeroday-cloud-cloud-security-hacking-competition-activity-7379280371676479488-q3bB?utm%5Fsource=share&utm%5Fmedium=member%5Fdesktop&rcm=ACoAAAq9GN8BFZwqjlHinmMEs4Drc4jOYzu2adM) cáo buộc Wiz đã sao chép luật từ Pwn2Own Ireland. Juan Pablo Castro, Director of Cybersecurity Strategy & Technology tại Trend Micro, nói rằng kết quả của Gemini khi so sánh luật hai sự kiện là "word-for-word" copy.

Wiz đã phản hồi bằng một [defusing statement](https://www.linkedin.com/feed/update/urn:li:activity:7378846266895790080?commentUrn=urn%3Ali%3Acomment%3A%28activity%3A7378846266895790080%2C7379330526891085824%29&replyUrn=urn%3Ali%3Acomment%3A%28activity%3A7378846266895790080%2C7379865041333841920%29&dashCommentUrn=urn%3Ali%3Afsd%5Fcomment%3A%287379330526891085824%2Curn%3Ali%3Aactivity%3A7378846266895790080%29&dashReplyUrn=urn%3Ali%3Afsd%5Fcomment%3A%287379865041333841920%2Curn%3Ali%3Aactivity%3A7378846266895790080%29), thừa nhận rằng sách luật của Pwn2Own "a trusted, mature framework by which we were inspired."