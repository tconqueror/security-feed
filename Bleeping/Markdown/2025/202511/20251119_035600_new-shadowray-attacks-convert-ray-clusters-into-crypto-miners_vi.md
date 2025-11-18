# New ShadowRay attacks convert Ray clusters into crypto miners

![New ShadowRay attacks convert Ray clusters into crypto miners](https://www.bleepstatic.com/content/hl-images/2025/11/05/Credit-card-hacker.jpg)

Một chiến dịch toàn cầu mang tên ShadowRay 2.0 chiếm quyền các Ray Clusters đang lộ ra bằng cách lợi dụng một lỗ hổng thực thi mã cũ để biến chúng thành một botnet đào tiền điện tử có khả năng tự lây lan.

Được phát triển bởi Anyscale, [Ray](http://github.com/ray-project/ray) là khung mã nguồn mở cho phép xây dựng và mở rộng các ứng dụng AI và Python trong một hệ sinh thái điện toán phân tán được tổ chức thành các cụm, hay các nút chính.

Theo các nhà nghiên cứu tại công ty bảo mật lúc chạy Oligo, một tác nhân đe doạ mà họ theo dõi với biệt danh IronErn440 đang sử dụng payload do AI tạo ra để xâm nhập cơ sở hạ tầng Ray dễ bị tấn công mà có thể truy cập qua Internet công cộng.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Họ cho biết hoạt động độc hại không chỉ dừng ở đào tiền điện tử, và trong một số trường hợp còn bao gồm việc đánh cắp dữ liệu và thông tin đăng nhập, cũng như triển khai các cuộc tấn công từ chối dịch vụ phân tán (DDoS).

### Chiến dịch mới, lỗ hổng cũ (chưa được vá)

ShadowRay 2.0 là phần tiếp theo của [chiến dịch ShadowRay khác](https://www.bleepingcomputer.com/news/security/hackers-exploit-ray-framework-flaw-to-breach-servers-hijack-resources/), cũng được Oligo công bố, đã chạy trong khoảng thời gian từ tháng 9/2023 đến tháng 3/2024.

Các nhà nghiên cứu của Oligo phát hiện rằng một lỗ hổng nghiêm trọng cũ được theo dõi dưới mã CVE-2023-48022 đã bị lợi dụng trong cả hai chiến dịch. Vấn đề bảo mật này không được vá vì Ray được thiết kế để chạy trong một môi trường tin cậy được mô tả là "môi trường mạng được kiểm soát nghiêm ngặt."

Tuy nhiên, các nhà nghiên cứu cho biết hiện có hơn 230.000 máy chủ Ray có thể truy cập trên Internet, một mức tăng lớn so với "vài nghìn chúng tôi quan sát trong lần phát hiện ShadowRay ban đầu."

Trong một báo cáo hôm nay, Oligo cho biết họ [quan sát hai làn sóng tấn công](https://www.oligo.security/blog/shadowray-2-0-attackers-turn-ai-against-itself-in-global-campaign-that-hijacks-ai-into-self-propagating-botnet), một là lợi dụng GitLab để phân phối payload và kết thúc vào ngày 5 tháng 11, và một là lợi dụng GitHub, vẫn đang diễn ra từ ngày 17 tháng 11.

![Malicious GitHub repository](https://www.bleepstatic.com/images/news/u/1220909/2025/November/github.jpg)

**Kho lưu trữ GitHub độc hại**  
_Source: Oligo Security_

### Khả năng của payload

Oligo cho biết các payload được sử dụng trong các cuộc tấn công đã được tạo với sự trợ giúp của các mô hình ngôn ngữ lớn. Kết luận này dựa trên phân tích cấu trúc mã, các chú thích có sẵn và mẫu xử lý lỗi.

Ví dụ, sau khi giải mã một trong các payload, các nhà nghiên cứu nhận thấy nó chứa "docstrings và các echo vô nghĩa, điều này cho thấy mạnh mẽ rằng mã được tạo bởi LLM."

**Một phần của payload**  
_Source: Oligo Security_

Các cuộc tấn công lợi dụng CVE-2023-48022 để gửi job tới Jobs API không xác thực của Ray nhằm chạy các payload Bash và Python nhiều giai đoạn, và sử dụng khả năng điều phối của nền tảng để triển khai phần mềm độc hại trên tất cả các nút, cho phép lây lan tự động từ cụm này sang cụm khác.

Mô-đun đào tiền điện tử cũng có vẻ được tạo bằng AI và kiểm tra tài nguyên CPU và GPU sẵn có cũng như loại quyền truy cập. Trong mã payload, các nhà nghiên cứu tìm thấy kẻ tấn công ưa thích một hệ thống có ít nhất tám lõi và quyền root, gọi nó là "a very good boy."

Nó sử dụng XMRig để đào Monero và đảm bảo chỉ sử dụng 60% công suất xử lý để tránh bị phát hiện ngay lập tức.

Oligo phát hiện rằng các miner được thả vào các vị trí tệp lừa đảo và sử dụng tên tiến trình giả như ‘_dns-filter_’ để giữ hoạt động dưới tầm mắt. Tính bền vững đạt được thông qua các cron job và các sửa đổi _systemd_.

Một phát hiện thú vị khác là kẻ tấn công đảm bảo rằng họ là những người duy nhất khai thác cụm Ray bị chiếm dụng cho mục đích đào và chấm dứt bất kỳ script đào nào đối địch. Ngoài ra, họ chặn các pool đào khác thông qua _/etc/hosts_ và _iptables_.

**Cấu hình miner**  
_Source: Oligo Security_

Ngoài đào tiền điện tử, phần mềm độc hại mở nhiều reverse shell Python tới cơ sở hạ tầng của kẻ tấn công để điều khiển tương tác, cho phép truy cập và khả năng trích xuất dữ liệu môi trường workload, thông tin đăng nhập MySQL, các mô hình AI độc quyền và mã nguồn lưu trữ trên cụm.

Nó cũng có thể phát động các cuộc tấn công DDoS sử dụng công cụ Sockstress, khai thác tiêu thụ tài nguyên không đối xứng bằng cách mở số lượng lớn kết nối TCP thông qua raw sockets.

Nhìn vào các cron job do kẻ tấn công tạo, Oligo cho biết một script được thực thi mỗi 15 phút để kiểm tra kho GitHub cho các payload được cập nhật.

**Cài đặt cơ chế bền vững**  
_Source: Oligo Security_

### Phòng vệ trước ShadowRay 2.0

Vì không có bản vá cho CVE-2023-48022, người dùng Ray được khuyến nghị tuân theo [“các thực hành tốt” do nhà cung cấp khuyến nghị](https://docs.ray.io/en/latest/ray-security/index.html) khi triển khai cụm của họ.

Anyscale cũng đã [xuất bản một cập nhật](https://www.anyscale.com/blog/update-on-ray-cve-2023-48022-new-verification-tooling-available) về chủ đề này sau khi chiến dịch ShadowRay đầu tiên được phát hiện, liệt kê một số khuyến nghị, bao gồm việc triển khai Ray trong một môi trường an toàn, đáng tin cậy.

Các cụm nên được bảo vệ khỏi truy cập trái phép bằng các quy tắc tường lửa và chính sách nhóm bảo mật.

Oligo cũng đề xuất thêm xác thực cho cổng Ray Dashboard (8265 theo mặc định) và triển khai giám sát liên tục trên các cụm AI để xác định hoạt động bất thường.