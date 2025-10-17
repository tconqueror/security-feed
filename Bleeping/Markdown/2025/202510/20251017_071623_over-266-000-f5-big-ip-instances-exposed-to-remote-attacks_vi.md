# Hơn 266.000 thiết bị F5 BIG-IP bị phơi bày cho các cuộc tấn công từ xa

![F5](https://www.bleepstatic.com/content/hl-images/2025/10/15/F5_02.png)

Tổ chức phi lợi nhuận về an ninh mạng Shadowserver Foundation đã phát hiện hơn 266.000 instance F5 BIG-IP bị phơi bày trực tuyến sau vụ vi phạm an ninh mà công ty an ninh mạng F5 công bố trong tuần này.

Công ty tiết lộ vào thứ Tư rằng [nation-state hackers breached its network](https://www.bleepingcomputer.com/news/security/hackers-breach-f5-to-steal-undisclosed-big-ip-flaws-source-code/) và đã đánh cắp mã nguồn cùng thông tin về các lỗi bảo mật BIG-IP chưa được tiết lộ, nhưng không tìm thấy bằng chứng cho thấy những kẻ tấn công đã rò rỉ hoặc khai thác các lỗ hổng chưa được tiết lộ đó trong các cuộc tấn công.

Cùng ngày, F5 cũng [issued patches to address 44 vulnerabilities](https://my.f5.com/manage/s/article/K000156572) (bao gồm những lỗ hổng bị đánh cắp trong cuộc tấn công mạng) và kêu gọi khách hàng cập nhật thiết bị của họ càng sớm càng tốt.

"Updates for BIG-IP, F5OS, BIG-IP Next for Kubernetes, BIG-IQ, and APM clients are available now," công ty cho biết. "Though we have no knowledge of undisclosed critical or remote code execution vulnerabilities, we strongly advise updating your BIG-IP software as soon as possible."

Mặc dù công ty chưa xác nhận điều này công khai, F5 cũng đã liên kết vụ tấn công với China trong các thông báo riêng gửi khách hàng, theo một báo cáo của Bloomberg vào thứ Năm.

F5 cũng đang chia sẻ một hướng dẫn săn tìm mối đe dọa với khách hàng, đề cập đến [the Brickstorm malware](https://www.bleepingcomputer.com/news/security/google-brickstorm-malware-used-to-steal-us-orgs-data-for-over-a-year/), một backdoor viết bằng Go lần đầu được [spotted by Google in April 2024](https://cloud.google.com/blog/topics/threat-intelligence/ivanti-post-exploitation-lateral-movement) trong quá trình điều tra các cuộc tấn công do nhóm đe dọa UNC5291 có liên hệ với China thực hiện. F5 cũng thông báo với khách hàng rằng các tác nhân đe dọa đã hoạt động trong mạng của công ty ít nhất là một năm.

Nhóm giám sát Internet Shadowserver hiện đang theo dõi 266.978 địa chỉ IP có fingerprint F5 BIG-IP, gần một nửa trong số đó (hơn 142.000) ở United States và khoảng 100.000 còn lại ở Europe và Asia.

Tuy nhiên, không có thông tin về bao nhiêu trong số này đã được bảo vệ khỏi các cuộc tấn công có thể khai thác các lỗ hổng BIG-IP được công bố trong tuần này.

![F5 devices exposed online](https://www.bleepstatic.com/images/news/u/1109292/2025/F5%20devices%20exposed%20online.png)

_Thiết bị F5 bị phơi bày trực tuyến (Shadowserver)_

Trong tuần này, CISA cũng [issued an emergency directive](https://www.cisa.gov/news-events/directives/ed-26-01-mitigate-vulnerabilities-f5-devices), yêu cầu các cơ quan liên bang Mỹ bảo đảm F5OS, BIG-IP TMOS, BIG-IQ và BNK/CNF bằng cách cài đặt các bản vá bảo mật mới nhất của F5 trước ngày October 22, trong khi với tất cả phần cứng và phần mềm F5 khác trên mạng của họ, thời hạn được gia hạn đến October 31.

CISA cũng ra lệnh cho họ ngắt kết nối và loại bỏ tất cả các thiết bị F5 có kết nối Internet đã hết hạn hỗ trợ, vì chúng sẽ không còn nhận bản vá nữa và có thể dễ dàng bị chiếm đoạt trong các cuộc tấn công.

"CISA is directing Federal Civilian Executive Branch (FCEB) agencies to inventory F5 BIG-IP products, evaluate if the networked management interfaces are accessible from the public internet, and apply updates from F5," cơ quan an ninh mạng cho biết.

Trong những năm gần đây, cả các nhóm có liên hệ nhà nước và các nhóm tội phạm mạng đã nhắm mục tiêu vào các lỗ hổng BIG-IP để [map internal servers](https://www.bleepingcomputer.com/news/security/cisa-hackers-abuse-f5-big-ip-cookies-to-map-internal-servers/), [hijack devices](https://www.bleepingcomputer.com/news/security/new-big-ip-next-central-manager-bugs-allow-device-takeover/) trên mạng của nạn nhân, [breach corporate networks](https://www.bleepingcomputer.com/news/security/iranian-hackers-are-selling-access-to-corporate-networks/), [steal sensitive files](https://www.bleepingcomputer.com/news/security/hackers-use-f5-big-ip-malware-to-stealthily-steal-data-for-years/), và [deploy data-wiping malware](https://www.bleepingcomputer.com/news/security/fake-f5-big-ip-zero-day-warning-emails-push-data-wipers/).

Các thiết bị F5 BIG-IP bị xâm nhập cũng có thể cho phép tác nhân đe dọa đánh cắp thông tin đăng nhập và API keys, di chuyển ngang trong mạng mục tiêu và thiết lập sự bền vững.

F5 là một công ty công nghệ thuộc Fortune 500 cung cấp an ninh mạng, application delivery networking (ADN), và dịch vụ cho hơn 23.000 khách hàng trên toàn cầu, bao gồm 48 trong số Fortune 50 companies.