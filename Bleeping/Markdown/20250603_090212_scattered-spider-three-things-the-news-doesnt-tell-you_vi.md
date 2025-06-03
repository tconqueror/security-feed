# Scattered Spider: Ba điều mà tin tức không nói với bạn

![Nhện mạng](https://www.bleepstatic.com/content/posts/2025/06/02/cyber-spider-header.jpg)

Với những cuộc tấn công gần đây vào các nhà bán lẻ ở Vương quốc Anh như Marks & Spencer và Co-op, cái gọi là Scattered Spider đã trở thành tâm điểm trên các phương tiện truyền thông, với sự chú ý tràn vào tin tức chính thống do mức độ gián đoạn nghiêm trọng — hiện tại có vẻ như hàng trăm triệu đô la đã bị mất đi chỉ riêng đối với M&S. 

Sự phủ sóng này cực kỳ giá trị cho cộng đồng an ninh mạng vì nó nâng cao nhận thức về những cuộc chiến mà các nhóm bảo mật đang phải đối mặt mỗi ngày. Nhưng nó cũng đã tạo ra rất nhiều tiếng ồn có thể khiến việc hiểu bức tranh tổng thể trở nên khó khăn. 

Vậy đây là ba điều mà bạn có thể đã bỏ lỡ — một số có thể bạn đã biết, và những điều khác mà bạn có thể không ý thức được nếu bạn chưa theo dõi Scattered Spider ngoài những cuộc tấn công gần đây. 

## 1. Không có cái gọi là Scattered Spider

Là một cộng đồng, đôi khi chúng ta quên rằng việc đặt những cái tên thú vị cho các mẫu hoạt động của kẻ tấn công có thể phóng đại và biến những tội phạm thành siêu ác nhân. Tuy nhiên, những cái tên thú vị là dễ nhớ và có khả năng được công nhận và chấp nhận tốt hơn, điều này hữu ích cho việc chia sẻ thông tin tình báo. 

Nhưng chúng ta cần nhớ rằng Scattered Spider không tự gọi mình là Scattered Spider. CrowdStrike đã làm như vậy. Và có rất nhiều tên khác được đặt cho mẫu hoạt động và kỹ thuật mà chúng ta biết đến với tên Scattered Spider:

* UNC3944 (Mandiant)
* Octo Tempest (Microsoft)
* 0ktapus (Group-IB)
* Muddled Libra (Unit 42)
* Scatter Swine (Okta)

Nhưng điều này không đơn giản như vậy, vì không có ranh giới rõ ràng. Mẫu hoạt động mà các nhà phân tích phân loại là Scattered Spider liên quan đến một số nhóm tội phạm tự đặt tên như, [Lapsus$, Yanluowang, Karakurt](https://www.cisa.gov/sites/default/files/2023-08/CSRB%5FLapsus%24%5F508c.pdf) và [ShinyHunters](https://pushsecurity.com/blog/snowflake-retro/) (đứng sau các cuộc tấn công Snowflake vào năm 2024).

Thông thường, các "thương hiệu" chính do kẻ tấn công tạo ra chồng chéo với các nhóm ransomware/ép buộc, những nhóm này thường có bộ mã hóa ransomware độc đáo của riêng mình (hoặc ít nhất là đã sửa đổi) và nền tảng riêng.

Điều này giải thích cho cái tên thú vị khác mà đã xuất hiện rất nhiều trong các báo cáo gần đây — DragonForce — gây ra sự nhầm lẫn về việc ai thực sự đã thực hiện các cuộc tấn công vào M&S và Co-op. Không giống như Scattered Spider, DragonForce là một nhóm Ransomware-as-a-Service cung cấp công cụ và dịch vụ chuyên biệt cho thuê cho các đối tác như Scattered Spider.

Họ không phải là những người thực hiện cuộc tấn công, nhưng những tội phạm được phân loại dưới "Scattered Spider" thực sự đang sử dụng dịch vụ và phần mềm mã hóa của họ khi họ đã hoàn thành việc xâm nhập ban đầu.

### Điều gì xác định Scattered Spider?

Vậy, nó có phần phức tạp, nhưng điều mà chúng ta thực sự theo dõi là các mẫu hành vi gắn liền với các vùng hoạt động cụ thể. 

Khi bạn nghĩ đến Scattered Spider, bạn có thể nhớ đến các cuộc bắt giữ diễn ra trong suốt năm 2024. Và thế nhưng, các cuộc tấn công vẫn tiếp tục — vì chúng ta không đang nói về một nhóm cá nhân cụ thể chặt chẽ, mà là một cộng đồng hoặc tập thể rộng lớn hơn của các tội phạm, tất cả đều sử dụng kỹ thuật tương tự, với cùng một mục tiêu cuối cùng — kiếm tiền (thường thông qua việc đánh cắp dữ liệu, ransomware và ép buộc). 

Vậy, cái gì xác định cái gọi là Scattered Spider? 

* Chủ yếu là những người nói tiếng Anh bản ngữ sống chủ yếu ở các nước nói tiếng Anh — Vương quốc Anh, Mỹ, Canada, Úc — nhưng cũng có hoạt động được truy dấu đến lục địa Châu Âu, Nga và Ấn Độ.  
![Sự hiện diện của Scattered Spider](https://www.bleepstatic.com/images/news/security/p/push/scattered-spider/unc3944-targeting-map.jpg)  
**Sự hiện diện của Scattered Spider**  
_Nguồn: [Mandiant](https://cloud.google.com/blog/topics/threat-intelligence/unc3944-proactive-hardening-recommendations?linkId=14321163)_
* Sử dụng chủ yếu các chiến thuật, kỹ thuật và quy trình dựa trên danh tính (TTP) chuyên môn hóa trong việc phishing, tấn công thông tin xác thực, lừa đảo help desk/vishing, chuyển SIM, smishing, v.v. — tất cả đều nhằm đạt được sự kiểm soát tài khoản.
* Các kỹ thuật chú trọng đến đám mây, chẳng hạn như nhắm mục tiêu vào các tài khoản nhà cung cấp danh tính đám mây hiện đại như Okta và Microsoft Entra, và lạm dụng các dịch vụ và môi trường đám mây.

Khi chúng ta nghĩ về Scattered Spider, chúng ta nghĩ về kẻ tấn công thông qua đám mây điển hình, người đã trưởng thành trong kỷ nguyên máy tính và dịch vụ Internet hiện đại, nơi việc trở thành một hacker ít liên quan đến việc khai thác mạng hơn là đăng nhập vào các tài khoản trên các ứng dụng và dịch vụ. Đây là những người có thể đã từng thử sức với các trò lừa đảo thẻ tín dụng và các hình thức gian lận Internet khác thay vì lùng sục Internet để tìm các máy chủ hoặc cổng mở bị lộ. 

Vì vậy, họ ưu tiên danh tính, nhưng quan trọng hơn thế, họ linh hoạt và thích nghi. Họ cũng sẵn sàng nhắm đến bất kỳ công ty nào mang lại cơ hội.

## [Tìm hiểu về sự phát triển TTP của Scattered Spider và cách bảo vệ tổ chức của bạn](https://pushsecurity.com/webinar/scatteredspider?utm%5Fcampaign=12883224-FY25Q2%5FScattered-Spider&utm%5Fsource=bleepingcomputer&utm%5Fcontent=sponsored-ad)

Scattered Spider đã thống trị tin tức trong những tuần gần đây sau những vi phạm cao nổi bật ảnh hưởng đến các nhà bán lẻ ở Vương quốc Anh. Nhưng với một lịch sử lâu dài các cuộc tấn công ransomware cao nổi bật, đây chỉ là một ví dụ về cách tiếp cận dựa trên danh tính của họ.

Hãy tham gia Push Security khi họ đi xa hơn những vụ vi phạm và tìm hiểu cách bảo vệ tổ chức của bạn trước kho vũ khí TTP ngày càng phát triển của Scattered Spider. 

[Xem webinar theo yêu cầu](https://pushsecurity.com/webinar/scatteredspider?utm%5Fcampaign=12883224-FY25Q2%5FScattered-Spider&utm%5Fsource=bleepingcomputer&utm%5Fcontent=sponsored-ad)

## 2. Lừa đảo help desk không phải là mới

Câu chuyện chính từ chiến dịch gần đây chống lại các nhà bán lẻ ở Vương quốc Anh là việc sử dụng lừa đảo help desk. Điều này thường liên quan đến việc kẻ tấn công gọi đến help desk của một công ty với một mức độ thông tin nhất định — ít nhất là PII cho phép họ mạo danh nạn nhân của mình, và đôi khi là một mật khẩu, tận dụng khả năng nói tiếng Anh bản ngữ của họ để đánh lừa nhân viên của help desk vào việc cấp cho họ quyền truy cập vào tài khoản người dùng. 

### Cách thức hoạt động

Mục tiêu của một cuộc lừa đảo help desk là buộc nhân viên help desk phải thiết lập lại thông tin đăng nhập và/hoặc MFA được sử dụng để truy cập một tài khoản để kẻ tấn công có thể kiểm soát nó. Họ sẽ sử dụng nhiều câu chuyện và chiến thuật khác nhau để thực hiện điều đó, nhưng thường thì đơn giản như chỉ cần nói “Tôi có một chiếc điện thoại mới, bạn có thể xóa MFA hiện tại của tôi và cho phép tôi đăng ký một cái mới không?”

Từ đó, kẻ tấn công sẽ được gửi một liên kết đặt lại MFA qua email hoặc SMS. Thông thường, điều này sẽ được gửi đến, ví dụ, một số điện thoại trên file — nhưng tại thời điểm này, kẻ tấn công đã thiết lập sự tin tưởng và vượt qua quy trình của help desk ở một mức độ nào đó. Vì vậy, việc hỏi “bạn có thể gửi đến địa chỉ email này không” hoặc “thực tế tôi cũng đã có một số mới, bạn có thể gửi đến…” sẽ khiến nó được gửi trực tiếp đến kẻ tấn công. 

Tại thời điểm này, chỉ đơn giản là sử dụng chức năng đặt lại mật khẩu tự phục vụ của Okta hoặc Entra (mà bạn có thể vượt qua vì giờ bạn đã có yếu tố MFA để xác minh bản thân) và voilà, kẻ tấn công đã chiếm được quyền kiểm soát tài khoản. 

Và phần hay nhất? Hầu hết các trung tâm trợ giúp đều có quy trình giống nhau cho mọi tài khoản — không quan trọng bạn đang mạo danh ai hay tài khoản nào bạn đang cố gắng đặt lại. Vì vậy, những kẻ tấn công thường nhắm mục tiêu vào các tài khoản có khả năng có đặc quyền quản trị viên cao — điều này có nghĩa là một khi họ vào được, việc tiến triển cuộc tấn công trở nên đơn giản và nhiều phần thường phải nâng cấp đặc quyền và di chuyển ngang sẽ bị loại bỏ khỏi con đường tấn công. 

Vì vậy, lừa đảo help desk đã chứng minh là một cách đáng tin cậy để vượt qua MFA và đạt được quyền kiểm soát tài khoản — vị thế từ đó có thể khởi động phần còn lại của một cuộc tấn công, như đánh cắp dữ liệu, triển khai ransomware, v.v. 

### Đây không phải là lần đầu tiên họ thực hiện

Nhưng một điều mà những báo cáo không đề cập là Scattered Spider đã thực hiện điều này thành công từ năm 2022, với các cuộc tấn công vào M&S và Co-op chỉ là phần nổi của tảng băng chìm. Vishing (gọi cho người dùng để làm cho họ từ bỏ mã MFA của mình) đã là một phần trong bộ công cụ của họ từ những ngày đầu, với các cuộc tấn công đầu tiên vào Twilio, LastPass, Riot Games, và Coinbase liên quan đến một số hình thức kỹ thuật xã hội dựa trên giọng nói. 

Đáng chú ý, các cuộc tấn công nổi bật vào Caesars, MGM Resorts, và Transport for London đều liên quan đến việc gọi đến help desk để thiết lập lại thông tin xác thực như là vector truy cập ban đầu. 

* **Caesars** vào tháng 8 năm 2023 nơi những kẻ hacker đã mạo danh một người dùng CNTT và thuyết phục một help desk thuê ngoài thiết lập lại thông tin xác thực, sau đó kẻ tấn công đã đánh cắp cơ sở dữ liệu chương trình khách hàng thân thiết và yêu cầu một khoản thanh toán tiền chuộc 15 triệu đô la.
* **MGM Resorts** vào tháng 9 năm 2023, nơi kẻ hacker sử dụng thông tin từ LinkedIn để mạo danh một nhân viên và thiết lập lại thông tin đăng nhập của nhân viên, dẫn đến việc đánh cắp 6TB dữ liệu. Sau khi MGM từ chối thanh toán, cuộc tấn công cuối cùng đã dẫn đến một sự gián đoạn kéo dài 36 giờ, gây tổn thất 100 triệu đô la và một đơn kiện tập thể được giải quyết với 45 triệu đô la.
* **Transport for London** vào tháng 9 năm 2024 đã dẫn đến 5,000 ngân hàng người dùng bị lộ thông tin, 30,000 nhân viên cần phải đến các buổi hẹn trực tiếp để xác minh danh tính và thiết lập lại mật khẩu, và sự gián đoạn đáng kể cho các dịch vụ trực tuyến kéo dài hàng tháng.

Vì vậy, không chỉ Scattered Spider đã sử dụng những kỹ thuật này trong một khoảng thời gian, mà mức độ nghiêm trọng và tác động của những cuộc tấn công này đã gia tăng.

### Tránh những cạm bẫy help desk

Có rất nhiều lời khuyên để bảo mật help desk đang được lưu hành, nhưng nhiều lời khuyên vẫn dẫn đến một quy trình mà hoặc là có thể bị phishing hoặc khó thực hiện. 

Cuối cùng, các tổ chức cần sẵn sàng để giới thiệu sự khó khăn vào quy trình help desk của họ và hoặc là trì hoãn hoặc từ chối yêu cầu trong các tình huống mà có nguy cơ đáng kể. Vì vậy, ví dụ, có một quy trình để đặt lại MFA nhận thức về rủi ro liên quan đến việc thiết lập lại tài khoản có đặc quyền cao:

* Yêu cầu phê duyệt / leo thang đa bên cho việc đặt lại tài khoản với quyền quản trị
* Yêu cầu xác minh tại chỗ nếu quy trình không thể được thực hiện từ xa
* Đình chỉ việc đặt lại tự phục vụ khi phát hiện hành vi nghi ngờ (điều này sẽ yêu cầu một quy trình nội bộ nào đó và đào tạo nhận thức để nâng cao cảnh giác nếu cuộc tấn công bị nghi ngờ)

Và hãy chú ý đến những cạm bẫy này: 

* Nếu bạn nhận được một cuộc gọi, thực hành tốt là kết thúc cuộc gọi và gọi lại số trên hồ sơ của nhân viên. Nhưng, trong thế giới của việc chuyển SIM, đây không phải là một giải pháp chắc chắn — bạn có thể chỉ đang gọi lại kẻ tấn công.
* Nếu giải pháp của bạn là đưa nhân viên lên camera, thì những deepfake ngày càng tinh vi có thể làm hỏng cách tiếp cận này.

Nhưng, help desk là một mục tiêu vì lý do. Họ "hữu ích" theo bản chất. Điều này thường được phản ánh trong cách họ hoạt động và được đo lường hiệu suất — các sự chậm trễ sẽ không giúp bạn đáp ứng các SLA! Cuối cùng, một quy trình chỉ hoạt động nếu nhân viên sẵn lòng tuân thủ nó — và không thể bị kỹ thuật xã hội thao túng để phá vỡ điều đó.

Help desk đã bị loại khỏi các hoạt động hàng ngày (đặc biệt là khi được thuê ngoài hoặc chuyển ra nước ngoài) cũng có thể dễ bị tấn công khi nhân viên bị mạo danh. 

Nhưng, những cuộc tấn công mà chúng ta đang trải qua hiện tại nên cung cấp cho các bên liên quan về bảo mật rất nhiều lý do cho thấy tại sao việc cải cách help desk rất cần thiết để bảo vệ doanh nghiệp (và những gì có thể xảy ra nếu bạn không thực hiện những thay đổi). 

## 3. Scattered Spider không chỉ thực hiện lừa đảo help desk

Tất cả những điều đó nói lên rằng, có một bức tranh lớn hơn ở đây — lừa đảo help desk không phải là công cụ duy nhất trong bộ công cụ của Scattered Spider. 

Họ đã nhất quán sử dụng một loạt các kỹ thuật, với sự thiên vị đặc biệt cho việc chuyển SIM, smishing, và thậm chí là phishing thông tin xác thực cơ bản (thường nhắm vào các tài khoản Okta). 

Và năm nay, các nhà nghiên cứu an ninh đã quan sát thấy Scattered Spider ngày càng sử dụng bộ công cụ phishing Attacker-in-the-Middle (AiTM) để vượt qua MFA. 

![Các trang phishing của Scattered Spider đang chạy Evilginx](https://www.bleepstatic.com/images/news/security/p/push/scattered-spider/phishing-sites.jpg)

**Các trang phishing của Scattered Spider đang chạy Evilginx**  
_Nguồn: Các nhà nghiên cứu tại [SilentPush](https://www.silentpush.com/blog/scattered-spider-2025/#h-new-scattered-spider-ttps-for-2025)_ 

Điều này thực sự phù hợp với thương hiệu của Scattered Spider. Họ hoàn toàn sử dụng các phương pháp dựa trên danh tính cho các xâm nhập ban đầu của họ, tất cả đều được thiết kế để vượt qua MFA và đạt được quyền kiểm soát tài khoản. 

Các cuộc tấn công của họ thường rất trực diện. Scattered Spider có xu hướng nhắm thẳng vào các tài khoản có quyền truy cập cao, cho phép họ nhanh chóng tiến triển cuộc tấn công của mình.

Ví dụ, trong cuộc tấn công MGM năm 2023, kẻ tấn công đã truy cập trực tiếp một tài khoản có quyền Super Admin trong Okta, mà họ đã kết hợp với một cuộc tấn công [liên bang từ phía vào](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/inbound%5Ffederation/description.md) để mạo danh bất kỳ người dùng nào trong tenant, có được quyền quản trị Azure, và xác thực vào môi trường VMware được lưu trữ trên Azure nơi họ triển khai ransomware. 

Họ cũng đã thể hiện rằng họ đang nhắm mục tiêu cụ thể vào các máy chủ VMware làm mục tiêu cho việc triển khai/mã hóa ransomware, đã được ghi nhận trong các cuộc tấn công MGM và M&S. Bằng cách nhắm vào hypervisor VMware (thường bằng cách thêm danh tính bị xâm phạm của họ vào nhóm Quản trị viên trong VCentre), họ có thể tỉnh táo né tránh các biện pháp kiểm soát cấp độ endpoint được chạy trên các máy ảo, chẳng hạn như EDR. 

Đặc biệt nếu chúng ta xem xét bức tranh lớn hơn với các nhóm lân cận như ShinyHunters, những người đứng sau [các cuộc tấn công Snowflake vào năm 2024](https://pushsecurity.com/blog/snowflake-retro/), và mức độ nghiêm trọng của các cuộc tấn công của họ, chúng ta có thể thấy các mục tiêu tương tự nhưng cách thức đạt được những mục tiêu đó là khác nhau.

Các cuộc tấn công Snowflake đã tận dụng thông tin xác thực bị đánh cắp từ trước đó từ các vụ lây nhiễm infostealer vào năm 2021 để đăng nhập vào các tài khoản mà không có MFA (với các lỗ hổng MFA phổ biến là một vấn đề lớn do bản chất quản lý danh tính Snowflake vào thời điểm đó), dẫn đến hàng trăm triệu hồ sơ bị rò rỉ trên 165 nạn nhân.

Bạn cũng có thể nhìn vào [các nhóm như Lapsus$](https://www.cisa.gov/sites/default/files/2023-08/CSRB%5FLapsus%24%5F508c.pdf), những người đã thể hiện các kỹ thuật tương tự rất đáng chú ý trong quá khứ. 

Vì vậy, tóm lại, Scattered Spider sử dụng một loạt các kỹ thuật dựa trên danh tính để chiếm đoạt các tài khoản ưu tiên cho xâm nhập ban đầu của họ, tất cả đều được thiết kế để vượt qua MFA. Họ không bị ràng buộc vào bất kỳ kỹ thuật cụ thể nào, tuy nhiên, và sẽ sử dụng bất kỳ phương tiện nào cần thiết trong khuôn khổ dựa trên danh tính đó để hoàn thành nhiệm vụ. 

## Kết luận

Bạn có thể coi Scattered Spider như một loại "kẻ tấn công thời kỳ hậu MFA" mà làm mọi thứ có thể để tránh các biện pháp kiểm soát an ninh đã thiết lập.

Bằng cách nhắm vào danh tính và chiếm quyền kiểm soát tài khoản, họ vượt qua càng nhiều bề mặt cuối và mạng càng tốt, cho đến tận cuối chuỗi tấn công — tại điểm mà gần như đã quá muộn để dựa vào các biện pháp kiểm soát đó. 

Vì vậy, đừng quá tập trung vào các lừa đảo help desk — bạn cần xem xét bề mặt tấn công danh tính rộng hơn của bạn và các phương thức xâm nhập khác nhau, từ các ứng dụng và tài khoản có lỗ hổng MFA, các tài khoản địa phương cung cấp cho kẻ tấn công một cổng vào các tài khoản vốn dĩ được truy cập bằng SSO, và các bộ dụng cụ phishing AiTM vượt qua MFA mà hiện tại đã trở thành thông lệ mới cho các cuộc tấn công phishing.

# Muốn biết thêm về Scattered Spider?

**[Xem webinar theo yêu cầu từ các nhà nghiên cứu tại Push Security](https://pushsecurity.com/webinar/scatteredspider?utm%5Fcampaign=12883224-FY25Q2%5FScattered-Spider&utm%5Fsource=bleepingcomputer&utm%5Fcontent=sponsored-ad)** để tìm hiểu thêm về sự phát triển TTP của Scattered Spider và những gì bạn có thể làm để bảo vệ tổ chức của mình. 

[](https://pushsecurity.com/webinar/scatteredspider?utm%5Fcampaign=12883224-FY25Q2%5FScattered-Spider&utm%5Fsource=bleepingcomputer&utm%5Fcontent=sponsored-ad)

## Tìm hiểu cách Push Security ngăn chặn các cuộc tấn công danh tính

Push Security cung cấp khả năng phát hiện và phản ứng đối với các cuộc tấn công danh tính toàn diện trước các kỹ thuật như phishing AiTM, nhồi nhét thông tin xác thực, phun mật khẩu và đánh cắp phiên sử dụng các mã thông báo phiên bị đánh cắp. Bạn cũng có thể sử dụng Push để tìm và sửa chữa các lỗ hổng danh tính trên mọi ứng dụng mà nhân viên của bạn đang sử dụng, chẳng hạn như: đăng nhập ma; khoảng trống SSO; lỗ hổng MFA; mật khẩu yếu, bị xâm phạm và tái sử dụng; tích hợp OAuth rủi ro; và nhiều hơn nữa. 

Nếu bạn muốn biết thêm về cách Push giúp bạn phát hiện và đánh bại các kỹ thuật tấn công danh tính phổ biến, **[hãy đặt một thời gian với một trong các thành viên của chúng tôi để được trình diễn trực tiếp](https://pushsecurity.com/demo/?utm%5Fcampaign=12883224-FY25Q2%5FScattered-Spider&utm%5Fsource=bleepingcomputer&utm%5Fcontent=sponsored-article)**. 

_Được tài trợ và viết bởi [Push Security](https://pushsecurity.com/demo/?utm%5Fcampaign=12883224-FY25Q2%5FScattered-Spider&utm%5Fsource=bleepingcomputer&utm%5Fcontent=sponsored-article)._