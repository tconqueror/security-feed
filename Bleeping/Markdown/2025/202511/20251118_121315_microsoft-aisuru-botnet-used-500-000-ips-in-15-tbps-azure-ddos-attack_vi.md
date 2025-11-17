# Microsoft: Azure bị tấn công DDoS 15 Tbps bằng 500.000 địa chỉ IP

![DDoS](https://www.bleepstatic.com/content/hl-images/2025/06/12/DDoS-outage-map-globe.jpg)

Microsoft cho biết hôm nay rằng botnet Aisuru đã tấn công mạng Azure của họ bằng một cuộc tấn công DDoS 15.72 terabit trên giây (Tbps), được phát động từ hơn 500.000 địa chỉ IP.

Cuộc tấn công sử dụng các luồng UDP với tốc độ rất cao nhắm vào một địa chỉ IP công cộng cụ thể ở Australia, đạt gần 3.64 tỷ gói tin mỗi giây (bpps).

"Cuộc tấn công xuất phát từ botnet Aisuru. Aisuru là một botnet IoT lớp Turbo Mirai thường xuyên gây ra các cuộc tấn công DDoS phá kỷ lục bằng cách lợi dụng các router và camera gia đình bị xâm nhập, chủ yếu ở các nhà cung cấp dịch vụ internet khu dân cư ở United States và các quốc gia khác," [cho biết](https://techcommunity.microsoft.com/blog/azureinfrastructureblog/defending-the-cloud-azure-neutralized-a-record-breaking-15-tbps-ddos-attack/4470422) Sean Whalen, quản lý cấp cao phụ trách tiếp thị sản phẩm Azure Security.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Những đợt bùng nổ UDP đột ngột này có ít việc giả mạo nguồn và sử dụng các cổng nguồn ngẫu nhiên, điều này giúp đơn giản hóa truy xuất nguồn và tạo điều kiện cho việc thực thi bởi các nhà cung cấp."

Cloudflare [liên kết cùng botnet đó](https://www.bleepingcomputer.com/news/security/cloudflare-mitigates-new-record-breaking-222-tbps-ddos-attack/) với một cuộc tấn công DDoS phá kỷ lục 22.2 terabit trên giây (Tbps) đạt 10.6 tỷ gói tin mỗi giây (Bpps) và đã được giảm nhẹ vào tháng 9 năm 2025. Cuộc tấn công này chỉ kéo dài 40 giây nhưng tương đương với việc phát trực tiếp khoảng một triệu video 4K cùng lúc.

Một tuần trước đó, bộ phận nghiên cứu XLab của công ty an ninh mạng Trung Quốc Qi'anxin đã quy trách nhiệm một cuộc tấn công DDoS 11.5 Tbps khác cho [Aisuru botnet](https://blog.xlab.qianxin.com/super-large-scale-botnet-aisuru-en/), cho biết rằng nó đang kiểm soát khoảng 300.000 bot vào thời điểm đó.

Botnet nhắm vào các lỗ hổng bảo mật trong IP cameras, DVRs/NVRs, chip Realtek, và các router từ T-Mobile, Zyxel, D-Link, và Linksys. Như các nhà nghiên cứu XLab nói, nó bùng nổ về kích thước vào tháng 4 năm 2025 sau khi các điều hành viên xâm nhập server cập nhật firmware của TotoLink và lây nhiễm khoảng 100.000 thiết bị.

Nhà báo an ninh mạng Brian Krebs [báo cáo](https://krebsonsecurity.com/2025/11/cloudflare-scrubs-aisuru-botnet-from-top-domains-list/) đầu tháng này rằng Cloudflare đã xóa nhiều domain liên quan đến botnet Aisuru khỏi bảng xếp hạng công khai "Top Domains" của họ về các website được yêu cầu nhiều nhất (dựa trên khối lượng truy vấn DNS) sau khi chúng bắt đầu vượt qua các trang hợp pháp như Amazon, Microsoft, và Google.

Công ty cho biết các điều hành viên của Aisuru đã cố ý tràn ngập dịch vụ DNS của Cloudflare (1.1.1.1) bằng lưu lượng truy vấn độc hại để nâng cao độ phổ biến của domain của họ trong khi làm suy yếu độ tin cậy của bảng xếp hạng. Cloudflare CEO Matthew Prince cũng xác nhận rằng hành vi của botnet đã làm méo mó nghiêm trọng hệ thống xếp hạng và cho biết Cloudflare nay sẽ gỡ bỏ hoặc hoàn toàn ẩn các domain bị nghi là độc hại để tránh các sự cố tương tự trong tương lai.

Như Cloudflare tiết lộ trong báo cáo 2025 Q1 DDoS Report vào tháng Tư, họ đã [giảm nhẹ một số lượng kỷ lục các cuộc tấn công DDoS](https://www.bleepingcomputer.com/news/security/cloudflare-mitigates-record-number-of-ddos-attacks-in-2025/) năm ngoái, với mức tăng 198% theo quý và tăng 358% theo năm.

Tổng cộng, họ đã chặn 21.3 triệu cuộc tấn công DDoS nhằm vào khách hàng trong suốt năm 2024, cũng như thêm 6.6 triệu cuộc tấn công nhắm vào cơ sở hạ tầng của chính họ trong một chiến dịch nhiều vector kéo dài 18 ngày.