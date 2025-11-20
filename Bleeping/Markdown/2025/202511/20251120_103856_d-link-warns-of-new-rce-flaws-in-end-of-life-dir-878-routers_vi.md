# D-Link cảnh báo về lỗ hổng RCE mới trên bộ định tuyến DIR-878 đã hết vòng đời

![D-Link cảnh báo về lỗ hổng RCE mới trên bộ định tuyến DIR-878 đã hết vòng đời](https://www.bleepstatic.com/content/hl-images/2024/04/05/map-dlink.jpg)

D-Link cảnh báo về ba lỗ hổng thực thi lệnh có thể khai thác từ xa ảnh hưởng tới tất cả mẫu và phiên bản phần cứng của bộ định tuyến DIR-878 của hãng, thiết bị này đã hết thời gian hỗ trợ nhưng vẫn có bán ở một số thị trường.

Các chi tiết kỹ thuật và mã khai thác proof-of-concept (PoC) minh họa các lỗ hổng đã được công bố bởi một nhà nghiên cứu sử dụng tên [Yangyifan](https://github.com/yifan20020708).

Thường được sử dụng trong gia đình và văn phòng nhỏ, [DIR-878](https://legacy.us.dlink.com/pages/product.aspx?id=99081ddbf70c4c21a387ab599e50d848) được ca ngợi là bộ định tuyến không dây hai băng tần hiệu năng cao khi ra mắt vào năm 2017.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Ngay cả khi thiết bị không còn được hỗ trợ, nó vẫn có thể được mua mới hoặc đã qua sử dụng với mức giá từ $75 đến $122.

Tuy nhiên, vì DIR-878 đã đạt trạng thái end-of-life (EoL) vào năm 2021, D-Link cảnh báo sẽ không phát hành bản cập nhật bảo mật cho mẫu này và khuyến nghị thay thế bằng sản phẩm đang được hỗ trợ.

Tổng cộng, [thông báo bảo mật](http://supportannouncement.us.dlink.com/security/publication.aspx?name=SAP10475) của D-Link liệt kê bốn lỗ hổng, chỉ một trong số đó yêu cầu truy cập vật lý hoặc kiểm soát thiết bị USB để khai thác.

* **CVE-2025-60672** – Thực thi lệnh từ xa không xác thực thông qua các tham số SetDynamicDNSSettings được lưu trong NVRAM và được sử dụng trong các lệnh hệ thống.
* **CVE-2025-60673** – Thực thi lệnh từ xa không xác thực thông qua SetDMZSettings và giá trị IPAddress không được kiểm tra bị chèn vào các lệnh iptables.
* **CVE-2025-60674** – Tràn ngăn xếp trong xử lý lưu trữ USB do trường “Serial Number” quá lớn (tấn công yêu cầu truy cập vật lý hoặc ở cấp thiết bị USB).
* **CVE-2025-60676** – Thực thi lệnh tùy ý thông qua các trường không được kiểm tra trong /tmp/new_qos.rule, được các nhị phân xử lý bằng system().

Mặc dù có thể khai thác từ xa và mã khai thác đã được công khai, U.S. Cybersecurity and Infrastructure Security Agency (CISA) đánh giá rằng các lỗ hổng có mức độ nghiêm trọng trung bình.

Tuy nhiên, một khai thác được công khai thường thu hút sự chú ý của các tác nhân đe dọa, đặc biệt là các điều hành botnet, những người thường đưa chúng vào kho vũ khí để mở rộng mục tiêu tấn công.

Ví dụ, botnet quy mô lớn RondoDox sử dụng hơn [56 lỗ hổng đã biết](https://www.bleepingcomputer.com/news/security/rondodox-botnet-targets-56-n-day-flaws-in-worldwide-attacks/), một số ảnh hưởng tới thiết bị D-Link, và tiếp tục [thêm nhiều hơn](https://www.bleepingcomputer.com/news/security/rondodox-botnet-malware-now-hacks-servers-using-xwiki-flaw/) vào danh sách.

Gần đây, BleepingComputer đưa tin về botnet Aisuru, đã triển khai một cuộc tấn công từ chối dịch vụ phân tán (DDoS) quy mô lớn vào mạng Azure của Microsoft, gửi [15.72 terabits per second](https://www.bleepingcomputer.com/news/microsoft/microsoft-aisuru-botnet-used-500-000-ips-in-15-tbps-azure-ddos-attack/) (Tbps) từ hơn 500,000 IP addresses.