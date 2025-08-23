# FBI: Nhóm tấn công mã độc Play đã xâm phạm 900 nạn nhân, bao gồm các tổ chức quan trọng

![FBI](https://www.bleepstatic.com/content/hl-images/2022/12/16/FBI__headpic.jpg)

Trong một cập nhật cho lời cảnh báo chung với CISA và Trung tâm An ninh mạng Úc, FBI cho biết nhóm mã độc Play đã xâm phạm khoảng 900 tổ chức tính đến tháng 5 năm 2025, gấp ba lần số nạn nhân [đã báo cáo vào tháng 10 năm 2023](https://www.bleepingcomputer.com/news/security/fbi-play-ransomware-breached-300-victims-including-critical-orgs/).

"Kể từ tháng 6 năm 2022, nhóm mã độc Play (còn được biết đến là Playcrypt) đã ảnh hưởng đến nhiều loại hình kinh doanh và cơ sở hạ tầng quan trọng ở Bắc Mỹ, Nam Mỹ và Châu Âu. Mã độc Play là một trong những nhóm ransomware hoạt động tích cực nhất vào năm 2024," FBI [cảnh báo](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-352a).

"Tính đến tháng 5 năm 2025, FBI đã nhận biết khoảng 900 thực thể bị ảnh hưởng mà nhóm tội phạm mã độc đã khai thác."

Cập nhật hôm nay cũng cho biết rằng nhóm ransomware sẽ sử dụng mã độc biên dịch lại trong mọi cuộc tấn công, khiến cho việc phát hiện và chặn bởi các giải pháp bảo mật trở nên khó khăn hơn và một số nạn nhân cũng bị liên lạc qua điện thoại và bị đe dọa phải trả tiền chuộc để tránh việc dữ liệu bị đánh cắp từ mạng của họ bị rò rỉ trực tuyến.

Nó cũng lưu ý rằng nhóm này sử dụng mã độc biên dịch lại trong mọi cuộc tấn công, làm cho việc phát hiện và chặn bởi các giải pháp bảo mật trở nên khó khăn hơn. Thêm vào đó, một số nạn nhân đã bị liên lạc qua điện thoại và bị đe dọa phải trả tiền chuộc để ngăn chặn dữ liệu bị đánh cắp của họ bị rò rỉ trực tuyến.

Kể từ đầu năm, các nhà môi giới truy cập ban đầu có liên kết với các nhà điều hành ransomware Play cũng đã khai thác một số lỗ hổng (CVE-2024-57726, CVE-2024-57727, và CVE-2024-57728) trong công cụ giám sát và quản lý từ xa trong các cuộc tấn công thực thi mã từ xa nhằm vào các tổ chức ở Hoa Kỳ.

Trong một sự cố như vậy, các tác nhân mối đe dọa không xác định đã [nhắm mục tiêu các khách hàng SimpleHelp RMM có lỗ hổng](https://www.bleepingcomputer.com/news/security/hackers-exploit-simplehelp-rmm-flaws-to-deploy-sliver-malware/) để tạo tài khoản quản trị, cài đặt backdoor vào các hệ thống bị xâm phạm bằng các beacon Sliver, có khả năng chuẩn bị cho các cuộc tấn công ransomware trong tương lai.

## Hoạt động ransomware-as-a-service (RaaS) của Play

[Nhóm ransomware Play](https://www.bleepingcomputer.com/tag/play/) đã xuất hiện gần ba năm trước, với những nạn nhân đầu tiên tìm kiếm sự trợ giúp trên [diễn đàn BleepingComputer](https://www.bleepingcomputer.com/forums/t/773651/play-ransomware-play-support-topic/) vào tháng 6 năm 2022\. Trước khi triển khai ransomware trên mạng của nạn nhân, các chi nhánh của Play sẽ đánh cắp các tài liệu nhạy cảm từ các hệ thống bị xâm phạm và sử dụng chúng để gây áp lực yêu cầu nạn nhân trả tiền chuộc dưới đe dọa công bố dữ liệu bị đánh cắp trên trang web rò rỉ của nhóm này trên dark web.

Tuy nhiên, khác với các hoạt động ransomware khác, mã độc Play sử dụng email làm kênh đàm phán và sẽ không cung cấp cho nạn nhân liên kết trang đàm phán Tor.

Nhóm ransomware này cũng sử dụng một công cụ VSS Copying Tool tùy chỉnh giúp [đánh cắp các tệp từ các bản sao khối lượng bóng](https://www.bleepingcomputer.com/news/security/play-ransomware-gang-uses-custom-shadow-volume-copy-data-theft-tool/), ngay cả khi được sử dụng bởi các ứng dụng khác.

Các nạn nhân nổi bật trước đây của ransomware Play bao gồm công ty điện toán đám mây [Rackspace](https://www.bleepingcomputer.com/news/security/rackspace-confirms-play-ransomware-was-behind-recent-cyberattack/), [Thành phố Oakland](https://www.bleepingcomputer.com/news/security/play-ransomware-claims-disruptive-attack-on-city-of-oakland/) ở California, [Quận Dallas](https://www.bleepingcomputer.com/news/security/dallas-county-data-of-200-000-exposed-in-2023-ransomware-attack/), tập đoàn bán lẻ ô tô [Arnold Clark](https://www.bleepingcomputer.com/news/security/arnold-clark-customer-data-stolen-in-attack-claimed-by-play-ransomware/), [thành phố Antwerp của Bỉ](https://www.bleepingcomputer.com/news/security/play-ransomware-claims-attack-on-belgium-city-of-antwerp/), và gần đây nhất là [chuỗi cửa hàng bánh ngọt Krispy Kreme](https://www.bleepingcomputer.com/news/security/krispy-kreme-breach-data-theft-claimed-by-play-ransomware-gang/) và nhà cung cấp linh kiện bán dẫn Mỹ [Microchip Technology](https://www.bleepingcomputer.com/news/security/microchip-technology-confirms-data-was-stolen-in-cyberattack/).

Trong hướng dẫn được ban hành bởi FBI, CISA và Trung tâm An ninh mạng Úc, các đội ngũ bảo mật được khuyến nghị ưu tiên duy trì hệ thống, phần mềm và firmware của họ luôn được cập nhật để giảm thiểu khả năng khai thác các lỗ hổng chưa được vá trong các cuộc tấn công ransomware của Play.

Các người bảo vệ cũng được khuyên nên triển khai xác thực đa yếu tố (MFA) trên tất cả các dịch vụ, tập trung vào VPN, webmail và các tài khoản có quyền truy cập vào các hệ thống quan trọng trong mạng lưới của tổ chức họ.

Ngoài ra, họ cũng nên duy trì các bản sao lưu dữ liệu ngoại tuyến và phát triển cũng như kiểm tra quy trình phục hồi như một phần trong thực tiễn an ninh tiêu chuẩn của tổ chức mình.