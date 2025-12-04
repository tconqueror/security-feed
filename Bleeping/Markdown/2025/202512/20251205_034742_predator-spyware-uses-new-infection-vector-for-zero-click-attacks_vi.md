# Predator spyware uses new infection vector for zero-click attacks

![Predator spyware uses new infection vector for zero-click attacks](https://www.bleepstatic.com/content/hl-images/2025/12/04/hacked.jpg)

Phần mềm gián điệp Predator của công ty giám sát Intellexa đã sử dụng một cơ chế lây nhiễm không cần tương tác được gọi là “Aladdin”, làm lộ những mục tiêu cụ thể chỉ bằng cách xem một quảng cáo độc hại.

Cơ chế tấn công mạnh mẽ và trước đây chưa được biết đến này được che giấu tinh vi đằng sau các công ty bia trải khắp nhiều quốc gia, nay được phanh phui trong một cuộc điều tra chung mới của [Inside Story](https://insidestory.gr/article/intellexa-leaks-nea-thymata-toy-predator-para-tis-amerikanikes-kyroseis?token=VvhXd6gD6X), [Haaretz](https://www.haaretz.com/israel-news/security-aviation/2025-12-03/ty-article-magazine/.premium/israeli-spyware-firm-intellexa-owned-by-ex-intel-officer-still-active-amid-us-sanctions/0000019a-e3e8-db35-afbf-ebfcb8bb0000), và [WAV Research Collective](https://www.inside-it.ch/intellexa-leaks-beruechtigte-spionagefirma-weiterhin-aktiv-20251203).

Cuộc điều tra dựa trên 'Intellexa Leaks' - một bộ sưu tập tài liệu nội bộ và tài liệu tiếp thị bị rò rỉ của công ty, và được xác thực bởi nghiên cứu kỹ thuật từ các chuyên gia pháp y và bảo mật tại Amnesty International, Google, và Recorded Future.

![Leaked marketing material](https://www.bleepstatic.com/images/news/u/1220909/2025/December/capabilities.jpg)

**Tài liệu tiếp thị rò rỉ của Intellexa**  
_Nguồn: Amnesty International_

### Phân phối phần mềm gián điệp dựa trên quảng cáo

Được triển khai lần đầu vào năm 2024 và được cho là vẫn đang hoạt động và được phát triển tích cực, Aladdin tận dụng hệ thống quảng cáo di động thương mại để phân phối phần mềm độc hại.

Cơ chế này ép các quảng cáo đã bị vũ khí hóa tới những mục tiêu cụ thể được xác định bằng địa chỉ IP công cộng và các nhận dạng khác, chỉ đạo các nền tảng thông qua Nền tảng phía cầu (Demand Side Platform - DSP) để hiển thị chúng trên bất kỳ trang web nào tham gia mạng quảng cáo.

“Quảng cáo độc hại này có thể được hiển thị trên bất kỳ trang web nào có quảng cáo, chẳng hạn như một trang tin tức đáng tin cậy hoặc ứng dụng di động, và sẽ xuất hiện như bất kỳ quảng cáo nào khác mà mục tiêu có khả năng nhìn thấy,” [explains Amnesty International’s Security Lab](https://securitylab.amnesty.org/latest/2025/12/intellexa-leaks-predator-spyware-operations-exposed/).

“Tài liệu nội bộ của công ty giải thích rằng chỉ cần xem quảng cáo là đủ để kích hoạt việc lây nhiễm trên thiết bị của mục tiêu, mà không cần phải nhấp vào quảng cáo.”

![Overview of Aladdin](https://www.bleepstatic.com/images/news/u/1220909/2025/December/aladdin.jpg)

**Tổng quan về Aladdin**  
_Nguồn: Amnesty International_

Mặc dù không có chi tiết về cách thức hoạt động của việc lây nhiễm, Google đề cập rằng các quảng cáo này kích hoạt các chuyển hướng tới các máy chủ phân phối khai thác của Intellexa.

Các quảng cáo được dẫn qua một mạng lưới phức tạp của các công ty quảng cáo trải khắp nhiều quốc gia, bao gồm Ireland, Germany, Switzerland, Greece, Cyprus, the UAE, and Hungary.

Recorded Future đã đào sâu vào mạng quảng cáo này, nối các mối liên hệ giữa những người, công ty và cơ sở hạ tầng chủ chốt, và nêu tên một số công ty đó [trong báo cáo của mình](https://www.recordedfuture.com/research/intellexas-global-corporate-web).

Việc phòng vệ chống lại những quảng cáo độc hại này là phức tạp, nhưng chặn quảng cáo trên trình duyệt sẽ là một khởi đầu tốt.

Một biện pháp phòng thủ tiềm năng khác là đặt trình duyệt ở chế độ ẩn địa chỉ IP công cộng khỏi các trình theo dõi.

Tuy nhiên, các tài liệu rò rỉ cho thấy Intellexa vẫn có thể thu thập thông tin từ các nhà mạng di động trong nước ở quốc gia của khách hàng họ.

**Các quốc gia được xác nhận có hoạt động của Predator**  
_Nguồn: Recorded Future_

## Samsung Exynos và các khai thác zero-day

Một phát hiện then chốt khác trong đợt rò rỉ là xác nhận sự tồn tại của một vector phân phối khác có tên 'Triton', có thể nhắm mục tiêu các thiết bị sử dụng Samsung Exynos bằng các khai thác baseband, ép xảy ra các giảm cấp xuống 2G để mở đường cho việc lây nhiễm.

Các nhà phân tích của Amnesty International không chắc chắn liệu vector này còn được sử dụng hay không và lưu ý rằng còn hai cơ chế phân phối khác, có thể tương tự, với tên mã 'Thor' và 'Oberon', được cho là liên quan đến truyền thông vô tuyến hoặc tấn công truy cập vật lý.

Các nhà nghiên cứu của Google [nêu tên](https://cloud.google.com/blog/topics/threat-intelligence/intellexa-zero-day-exploits-continue) Intellexa là một trong những nhà cung cấp phần mềm gián điệp thương mại tích cực nhất về mặt khai thác zero-day, chịu trách nhiệm cho 15 trong số 70 trường hợp khai thác zero-day mà TAG phát hiện và tài liệu hóa kể từ năm 2021.

Google cho biết Intellexa phát triển các khai thác của riêng mình và cũng mua chuỗi khai thác từ các thực thể bên ngoài để bao phủ toàn bộ phổ mục tiêu cần thiết.

Mặc dù có các biện pháp trừng phạt và các cuộc điều tra đang diễn ra chống lại Intellexa ở Greece, nhà điều hành phần mềm gián điệp vẫn hoạt động tích cực như chưa từng có, theo Amnesty International.

Khi Predator tiến hóa trở nên tinh vi hơn và khó truy vết hơn, người dùng được khuyến nghị cân nhắc bật bảo vệ bổ sung trên thiết bị di động của họ, như Advanced Protection trên Android và Lockdown Mode trên iOS.