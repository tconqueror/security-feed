# ShinyHunters đứng sau các cuộc tấn công đánh cắp dữ liệu Salesforce tại Qantas, Allianz Life và LVMH

![Tin tặc mặt cười](https://www.bleepstatic.com/content/hl-images/2024/06/15/emoji-hacker.jpg)

Một làn sóng vi phạm dữ liệu ảnh hưởng đến các công ty như Qantas, Allianz Life, LVMH và Adidas đã được liên kết với nhóm tống tiền ShinyHunters, nhóm này đã sử dụng các cuộc tấn công vishing để đánh cắp dữ liệu từ các instance Salesforce CRM.

Vào tháng 6, Nhóm Tình báo Đe dọa của Google (GTIG) đã cảnh báo rằng các tác nhân đe dọa được theo dõi như UNC6040 đang [nhắm mục tiêu đến các khách hàng Salesforce trong các cuộc tấn công xã hội](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/).

Trong các cuộc tấn công này, các tác nhân đe dọa đã giả mạo nhân viên hỗ trợ CNTT trong các cuộc gọi điện thoại đến những nhân viên mục tiêu, cố gắng thuyết phục họ truy cập vào trang thiết lập ứng dụng kết nối của Salesforce. Trên trang này, họ được yêu cầu nhập một "mã kết nối", mã này liên kết một phiên bản độc hại của ứng dụng OAuth Data Loader của Salesforce vào môi trường Salesforce của mục tiêu.

Trong một số trường hợp, thành phần Data Loader đã được đổi tên thành "My Ticket Portal," để làm cho nó có vẻ thuyết phục hơn trong các cuộc tấn công.

![Nhắc nhập mã kết nối](https://www.bleepstatic.com/images/news/u/1220909/2025/June/prompt.jpg)

**Nhắc nhập mã kết nối**  
_Nguồn: Google_

GTIG cho biết rằng những cuộc tấn công này thường được tiến hành thông qua vishing (voice phishing), nhưng thông tin xác thực và mã MFA cũng đã bị đánh cắp thông qua các trang phishing giả mạo trang đăng nhập Okta.

Vào thời điểm báo cáo này, nhiều công ty đã báo cáo các vi phạm dữ liệu liên quan đến dịch vụ khách hàng bên thứ ba hoặc hệ thống CRM dựa trên đám mây.

Các công ty con của LVMH [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), và [Tiffany & Co.](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/) mỗi công bố việc truy cập trái phép vào một cơ sở dữ liệu thông tin khách hàng, với [Tiffany Korea thông báo cho khách hàng](http://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/) rằng kẻ tấn công đã xâm nhập vào một "nền tảng nhà cung cấp dùng để quản lý dữ liệu khách hàng."

[Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), và [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/) cũng đã báo cáo các vi phạm liên quan đến các hệ thống bên thứ ba, với Allianz xác nhận đó là một nền tảng quản lý quan hệ khách hàng bên thứ ba.

"Vào ngày 16 tháng 7 năm 2025, một tác nhân đe dọa độc hại đã truy cập vào một hệ thống CRM dựa trên đám mây của bên thứ ba được sử dụng bởi Công ty Bảo hiểm Allianz Life của Bắc Mỹ (Allianz Life)," một phát ngôn viên của Allianz Life nói với BleepingComputer.

Trong khi BleepingComputer đã biết rằng vi phạm dữ liệu của Qantas cũng liên quan đến một nền tảng quản lý quan hệ khách hàng bên thứ ba, công ty sẽ không xác nhận rằng đó là Salesforce. Tuy nhiên, các báo cáo trước đó từ truyền thông địa phương cho rằng dữ liệu đã bị đánh cắp từ instance Salesforce của Qantas.

Hơn nữa, các tài liệu tòa án cho biết rằng các tác nhân đe dọa đã nhắm mục tiêu vào các bảng cơ sở dữ liệu "[Accounts](https://help.salesforce.com/s/articleView?id=commerce.om%5Faccount%5Ffields.htm&type=5)" và "[Contacts](https://help.salesforce.com/s/articleView?id=commerce.om%5Fcontact%5Ffields.htm&language=en%5FUS&type=5)", cả hai đều là các đối tượng Salesforce.

Mặc dù không công ty nào trong số này đã công khai chỉ tên Salesforce, nhưng BleepingComputer đã xác nhận rằng tất cả đều bị nhắm mục tiêu trong cùng một chiến dịch được Google chi tiết.

Các cuộc tấn công chưa dẫn đến việc tống tiền công khai hay rò rỉ dữ liệu, với việc BleepingComputer biết rằng các tác nhân đe dọa đang cố gắng tống tiền riêng tư các công ty qua email, nơi họ tự xưng là ShinyHunters.

Người ta tin rằng khi các nỗ lực tống tiền này thất bại, các tác nhân đe dọa sẽ công bố thông tin bị đánh cắp trong một làn sóng rò rỉ dài, tương tự như các cuộc tấn công [Snowflake](https://www.bleepingcomputer.com/news/security/snowflake-account-hacks-linked-to-santander-ticketmaster-breaches/) trước đây của ShinyHunter.

## ShinyHunters là ai

Những vụ vi phạm này cũng đã gây ra sự nhầm lẫn trong cộng đồng an ninh mạng và truyền thông, bao gồm cả BleepingComputer, khi các cuộc tấn công được gán cho Scattered Spider (được Mandiant theo dõi là UNC3944), vì những tác nhân đe dọa đó cũng đã nhắm mục tiêu vào [ngành hàng không](https://www.bleepingcomputer.com/news/security/scattered-spider-hackers-shift-focus-to-aviation-transportation-firms/), [bán lẻ](https://www.bleepingcomputer.com/news/security/google-scattered-spider-switches-targets-to-us-retail-chains/), và [bảo hiểm](https://www.bleepingcomputer.com/news/security/google-warns-scattered-spider-hackers-now-target-us-insurance-companies/) xung quanh cùng một thời điểm và thể hiện các chiến thuật tương tự.

Tuy nhiên, các tác nhân đe dọa liên kết với Scattered Spider có xu hướng thực hiện các cuộc tấn công vào mạng lưới đầy đủ, culminating with data theft and, sometimes, ransomware. ShinyHunters, được theo dõi như UNC6040, ngược lại, có xu hướng tập trung nhiều hơn vào các cuộc tấn công tống tiền đánh cắp dữ liệu nhắm vào một nền tảng đám mây hoặc ứng dụng web cụ thể.

BleepingComputer và một số nhà nghiên cứu an ninh tin rằng cả UNC6040 và UNC3944 đều bao gồm các thành viên chồng chéo giao tiếp trong cùng một cộng đồng trực tuyến. Nhóm đe dọa này cũng được cho là chồng chéo với "The Com," một mạng lưới các tội phạm mạng nói tiếng Anh có kinh nghiệm.

"Từ thông tin tình báo của Recorded Future, các TTP chồng chéo giữa các cuộc tấn công của Scattered Spider và ShinyHunters chỉ ra có khả năng có sự giao thoa giữa hai nhóm," Allan Liska, một nhà phân tích tình báo của Recorded Future, nói với BleepingComputer.

Các nhà nghiên cứu khác đã cho BleepingComputer biết rằng ShinyHunters và Scattered Spider dường như hoạt động đồng bộ, nhắm mục tiêu vào cùng các ngành công nghiệp trong cùng một thời điểm, khiến việc gán các cuộc tấn công trở nên khó khăn hơn.

Một số người cũng tin rằng cả hai nhóm có liên hệ với các tác nhân đe dọa từ nhóm tấn công [Lapsus$](https://www.bleepingcomputer.com/news/security/lapsus-teen-hackers-convicted-of-high-profile-cyberattacks/) đã ngừng hoạt động, với các báo cáo cho thấy một trong số các [tin tặc Scattered Spider gần đây bị bắt](https://www.bleepingcomputer.com/news/security/four-arrested-in-uk-over-mands-co-op-harrods-cyberattacks/) cũng đã [tham gia Lapsus$](http://krebsonsecurity.com/2025/07/uk-charges-four-in-scattered-spider-ransom-group/).

Một lý thuyết khác là ShinyHunters hoạt động như một dịch vụ tống tiền-as-a-service, nơi họ tống tiền các công ty thay mặt cho các tác nhân đe dọa khác thông qua một khoản chia sẻ doanh thu, tương tự như cách thức hoạt động của các băng nhóm ransomware-as-a-service.

Lý thuyết này được ủng hộ bởi các cuộc trò chuyện trước đây mà BleepingComputer đã có với ShinyHunters, nơi họ nói rằng họ không phải là người đứng sau một vụ vi phạm, mà chỉ hành động như người bán dữ liệu bị đánh cắp.

Những vụ vi phạm này bao gồm [PowerSchool](https://www.bleepingcomputer.com/news/security/powerschool-hacker-now-extorting-individual-school-districts/), [Oracle Cloud](https://www.bleepingcomputer.com/news/security/oracle-customers-confirm-data-stolen-in-alleged-cloud-breach-is-valid/), các cuộc tấn công [Snowflake](https://www.bleepingcomputer.com/tag/snowflake/), [AT&T](https://www.bleepingcomputer.com/news/security/old-atandt-data-leak-repackaged-to-link-ssns-dobs-to-49m-phone-numbers/), [NitroPDF](https://www.bleepingcomputer.com/news/security/hacker-leaks-full-database-of-77-million-nitro-pdf-user-records/), [Wattpad](https://www.bleepingcomputer.com/news/security/wattpad-data-breach-exposes-account-info-for-millions-of-users/), [MathWay](https://www.bleepingcomputer.com/news/security/mathway-investigates-data-breach-after-25m-records-sold-on-dark-web/), và [nhiều hơn nữa](https://www.bleepingcomputer.com/news/security/hacker-leaks-386-million-user-records-from-18-companies-for-free/).

![ShinyHunters đang cố gắng bán dữ liệu vi phạm AT&T](https://www.bleepstatic.com/images/news/security/d/data-breaches/a/att/shiny-forum-post.png)

**ShinyHunters đang cố gắng bán dữ liệu vi phạm AT&T**  
_Nguồn: BleepingComputer_

Để làm cho tình hình trở nên khó khăn thêm, đã có [nhiều cuộc bắt giữ](https://www.bleepingcomputer.com/news/security/shinyhunters-member-pleads-guilty-to-6-million-in-data-theft-damages/) những người liên quan đến tên gọi "ShinyHunters," bao gồm những người đã bị bắt vì các cuộc tấn công [Snowflake](https://www.bleepingcomputer.com/news/security/us-indicts-snowflake-hackers-who-extorted-25-million-from-3-victims/), vi phạm tại PowerSchool, và [hoạt động của diễn đàn tấn công Breached v2](https://www.bleepingcomputer.com/news/security/breachforums-hacking-forum-operators-reportedly-arrested-in-france/).

Tuy nhiên, ngay cả sau những vụ bắt giữ này, các cuộc tấn công mới vẫn xảy ra với các công ty nhận được email tống tiền nói rằng, "Chúng tôi là ShinyHunters," tự gọi mình là một "tập thể."

## Bảo vệ các instance Salesforce khỏi các cuộc tấn công

Trong một tuyên bố gửi tới BleepingComputer, Salesforce nhấn mạnh rằng nền tảng này không bị tấn công mà thực tế là tài khoản của khách hàng đang bị xâm phạm thông qua kỹ thuật xã hội.

"Salesforce không bị xâm phạm, và các vấn đề được mô tả không phải do bất kỳ lỗ hổng nào trong nền tảng của chúng tôi. Trong khi Salesforce xây dựng bảo mật cấp doanh nghiệp vào mọi thứ chúng tôi làm, khách hàng cũng đóng một vai trò quan trọng trong việc giữ cho dữ liệu của họ an toàn — đặc biệt là giữa sự gia tăng của các cuộc tấn công phishing và kỹ thuật xã hội tinh vi," Salesforce nói với BleepingComputer.

"Chúng tôi tiếp tục khuyến khích tất cả khách hàng tuân thủ các phương pháp tốt nhất về bảo mật, bao gồm việc kích hoạt xác thực đa yếu tố (MFA), thực hiện nguyên tắc quyền hạn tối thiểu, và quản lý cẩn thận các ứng dụng kết nối. Để biết thêm thông tin, vui lòng truy cập: <https://www.salesforce.com/blog/protect-against-social-engineering/>."

Salesforce đang kêu gọi khách hàng tăng cường tư thế bảo mật của họ bằng cách:

* Thiết lập các dải IP đáng tin cậy cho việc đăng nhập
* Thực hiện nguyên tắc quyền hạn tối thiểu cho quyền truy cập ứng dụng
* Bật xác thực đa yếu tố (MFA)
* Giới hạn việc sử dụng ứng dụng kết nối và quản lý chính sách truy cập
* Sử dụng Salesforce Shield cho phát hiện mối đe dọa nâng cao, theo dõi sự kiện và chính sách giao dịch
* Thêm một liên hệ Bảo mật được chỉ định để trao đổi sự cố

Các chi tiết thêm về các biện pháp giảm thiểu này có thể được tìm thấy trong hướng dẫn của Salesforce được liên kết ở trên.