# Criminal IP và Palo Alto Networks Cortex XSOAR tích hợp để mang trí tuệ phơi bày do AI điều khiển vào phản ứng sự cố tự động

![Criminal IP + Palo Alto Cortex](https://www.bleepstatic.com/content/posts/2025/12/16/header-image.jpg)

[Criminal IP](https://www.criminalip.io/ko?mtm%5Fcampaign=PaloAlto%20Integration&mtm%5Fkwd=PaloAlto&mtm%5Fsource=bleepingcomputer%20%2F%20cybernewswire&mtm%5Fmedium=press) (criminalip.io), nền tảng giám sát bề mặt tấn công và tình báo mối đe dọa được hỗ trợ bởi AI do AI SPERA phát triển, hiện đã chính thức tích hợp vào Palo Alto Networks’ Cortex XSOAR.

Sự tích hợp nhúng bối cảnh mối đe dọa bên ngoài theo thời gian thực, trí tuệ phơi bày và quét tự động đa giai đoạn trực tiếp vào engine điều phối của Cortex XSOAR, mang lại cho các nhóm bảo mật độ chính xác sự cố cao hơn và phản ứng nhanh hơn so với các phương pháp chỉ dựa trên log thông thường.

Đối với Palo Alto Networks, được coi là nhà lãnh đạo toàn cầu về an ninh mạng, Cortex XSOAR là trung tâm cho tự động hóa SOC. Với Criminal IP được thêm vào như một tích hợp qua [Cortex Marketplace](https://cortex.marketplace.pan.dev/marketplace/details/CriminalIP/),

Cortex XSOAR giờ có thể cung cấp cho người dùng khả năng đánh giá các IP và domain khả nghi không chỉ thông qua dữ liệu uy tín tĩnh mà còn qua các tín hiệu hành vi, lịch sử phơi bày, tương quan hạ tầng và điểm số mối đe dọa do AI tạo ra, mà không cần hệ thống bổ sung hay tra cứu do nhà phân tích thực hiện.

## Bối cảnh AI để khắc phục giới hạn của phản ứng sự cố chỉ dựa trên log

![Automated playbook example — detecting malicious domains using the three-step scan in the integrated API of Criminal IP and Palo Alto Networks Cortex XSOAR](https://www.bleepstatic.com/images/news/security/c/criminal-ip/palo-alt-cortex/paloalto2.jpg)

**Automated playbook example — detecting malicious domains using the three-step scan in the integrated API of Criminal IP and Palo Alto Networks Cortex XSOAR**

Các đội SOC hiện đại đối mặt với khối lượng cảnh báo quá lớn, trong khi việc mở rộng thông tin truyền thống vẫn phụ thuộc vào các nguồn dữ liệu uy tín tĩnh với bối cảnh hạn chế, thường bỏ sót phơi bày cổng (port exposure), liên kết CVE, tái sử dụng chứng chỉ, thay đổi DNS hoặc hành vi ẩn danh.

Criminal IP lấp đầy khoảng trống này bằng cách liên tục phân tích các tài sản hướng ra Internet toàn cầu và tương quan hành vi IP, hoạt động domain, dữ liệu SSL/TLS, trạng thái port, phơi bày CVE, phát hiện IDS và các chỉ báo che mặt.

Khi một cảnh báo bao gồm IP hoặc domain, Cortex XSOAR có thể tự động kéo thông tin tình báo được làm giàu này vào sự cố đang hoạt động thông qua playbook, cho phép nhà phân tích đánh giá ý định và độ nghiêm trọng mà không cần rời khỏi Cortex SOAR.

## [Dùng thử Criminal IP để phát hiện và phản ứng với các mối đe dọa mới nổi](https://www.criminalip.io/contact-us?mtm%5Fcampaign=PaloAlto%20Integration&mtm%5Fkwd=PaloAlto&mtm%5Fsource=bleepingcomputer%20%2F%20cybernewswire&mtm%5Fmedium=press)

Truy cập Threat Intelligence của Criminal IP cần thiết để chủ động xác định, phân tích và phản ứng với các mối đe dọa mới nổi.

Được hỗ trợ bởi AI và OSINT, nó cung cấp điểm số mối đe dọa, dữ liệu uy tín và phát hiện theo thời gian thực cho nhiều chỉ báo độc hại, từ C2 servers và IOCs đến các dịch vụ che mặt như VPNs, proxies và anonymous VPNs, trên IPs, domains và URLs. Kiến trúc API-first của nó đảm bảo tích hợp liền mạch vào các luồng công việc bảo mật để tăng khả năng hiển thị, tự động hóa và phản ứng.

[Request Your Demo](https://www.criminalip.io/contact-us?mtm%5Fcampaign=PaloAlto%20Integration&mtm%5Fkwd=PaloAlto&mtm%5Fsource=bleepingcomputer%20%2F%20cybernewswire&mtm%5Fmedium=press)

## Quét đa giai đoạn và liên kết phơi bày bên ngoài

Cortex XSOAR playbooks có thể kích hoạt quy trình quét tự động ba giai đoạn của Criminal IP: bắt đầu bằng Quick Lookup, leo thang lên Lite Scan, sau đó thực hiện Full Scan để phân tích toàn diện bề mặt tấn công.

Kết quả Full Scan được chuyển đến dưới dạng báo cáo có cấu trúc trong Cortex XSOAR, với việc polling chung đảm bảo quy trình tiếp tục mà không cần nỗ lực thủ công.

Ngoài việc làm giàu dựa trên cảnh báo, tích hợp còn liên kết telemetry nội bộ với trí tuệ mở Internet, cung cấp hành vi lịch sử, mối quan hệ C2, chỉ báo ẩn danh, hồ sơ lạm dụng và tương quan SSL cho từng chỉ báo.

Cortex XSOAR cũng có thể lên lịch các quét Micro Attack Surface Management để đánh giá các port bị phơi bày, tính hợp lệ của chứng chỉ, dịch vụ dễ tổn thương và phần mềm lỗi thời, cung cấp khả năng ASM nhẹ, liên tục giúp các tổ chức xác định điểm yếu trước khi chúng bị lợi dụng.

## Thúc đẩy chuyển dịch về phía an ninh tự động dựa trên trí tuệ

![Screenshot of the Criminal IP pack on the Cortex Marketplace](https://www.bleepstatic.com/images/news/security/c/criminal-ip/palo-alt-cortex/paloalto3.jpg)

**Screenshot of the Criminal IP pack on the Cortex Marketplace**

Sự tích hợp giữa Palo Alto Networks và Criminal IP phản ánh xu hướng rộng hơn hướng tới vận hành an ninh tự động. Bằng cách kết hợp khả năng tự động hóa và điều phối của Cortex XSOAR với phân tích bên ngoài theo thời gian thực của Criminal IP, các đội SOC có thể tự động hóa các quyết định mà trước đây cần nghiên cứu thủ công trên nhiều nguồn tình báo.

Điều này giảm thời gian phản hồi, cải thiện độ chính xác trong phân loại sự cố và giảm mệt mỏi cho nhà phân tích — những vấn đề đã trở nên trầm trọng hơn khi khối lượng cảnh báo và các mối đe dọa do AI tạo ra tiếp tục tăng.

[Criminal IP](https://www.criminalip.io/ko?mtm%5Fcampaign=PaloAlto%20Integration&mtm%5Fkwd=PaloAlto&mtm%5Fsource=bleepingcomputer%20%2F%20cybernewswire&mtm%5Fmedium=press) hiện đã có mặt trên các marketplace Azure, AWS và Snowflake và duy trì tích hợp với hơn 40 nhà cung cấp bảo mật, bao gồm Cisco, Fortinet và Tenable. Việc mở rộng vào hệ sinh thái Palo Alto Networks đặt nền tảng cho các tích hợp sâu hơn trên các giải pháp XDR và bảo mật đám mây.

AI SPERA CEO Byungtak Kang cho biết việc tích hợp “chứng minh tầm quan trọng ngày càng tăng của threat intelligence do AI điều khiển và exposure analytics trong hoạt động an ninh doanh nghiệp,” đồng thời bổ sung rằng Criminal IP nhằm đóng vai trò trung tâm giúp các tổ chức chuyển dịch sang kiến trúc phòng thủ hoàn toàn tự động.

**Tìm hiểu thêm: <https://cortex.marketplace.pan.dev/marketplace/details/CriminalIP/>**

_Sponsored and written by [Criminal IP](https://www.criminalip.io/ko?mtm%5Fcampaign=PaloAlto%20Integration&mtm%5Fkwd=PaloAlto&mtm%5Fsource=bleepingcomputer%20%2F%20cybernewswire&mtm%5Fmedium=press)._