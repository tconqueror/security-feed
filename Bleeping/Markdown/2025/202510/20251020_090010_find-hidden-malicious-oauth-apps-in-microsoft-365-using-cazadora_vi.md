# Tìm các ứng dụng OAuth độc hại ẩn trong Microsoft 365 bằng Cazadora

![Tấn công nhận dạng](https://www.bleepstatic.com/content/posts/2025/10/15/huntress-header-identity-risks.png)

_Tác giả: Matt Kiely, Nhà nghiên cứu An ninh chính tại Huntress Labs_

Tóm tắt: Nếu bạn quản lý dù chỉ một tenant Microsoft 365, đã đến lúc kiểm tra các ứng dụng OAuth của bạn. Theo thống kê, có khả năng cao là một ứng dụng độc hại đang ẩn trong môi trường của bạn.

**Tôi đã viết một script mã nguồn mở có thể giúp bạn làm điều này: <https://github.com/HuskyHacks/cazadora>**

**Cụ thể, hãy kiểm tra trong Enterprise Applications và Application Registrations để tìm:**

* **Ứng dụng được đặt tên theo một tài khoản người dùng**
* **Ứng dụng có tên “Test” hoặc “Test App” hoặc tương tự**
* **Ứng dụng có tên theo tên miền tenant nơi chúng được cài đặt**
* **Ứng dụng dùng các chuỗi tùy ý làm tên, như các tên không phải chữ số chữ cái (ví dụ “........”)**
* **Các reply URL bất thường, cụ thể bao gồm một URL loopback cục bộ với cổng 7823 [“http://localhost:7823/access/”]**

**Nghiêm túc đấy, hãy đi kiểm tra các ứng dụng của bạn! Bài viết vẫn ở đây khi bạn quay lại.**

**Nếu bạn quan tâm đến mấy thứ intel đam mê kỹ thuật, hãy đọc tiếp.**

Hãy tưởng tượng thế này: đó là một sáng Chủ nhật đẹp trời và bạn đang háo hức tận hưởng một ngày nghỉ xứng đáng sau một tuần vất vả. Bạn uể oải bước vào bếp và chuẩn bị thức uống có caffein mình thích. Mặt trời chiếu sáng. Chim hót líu lo. Bạn cúi ra cửa sổ và cảm nhận làn gió mùa hè mát mẻ trên trán. Bạn bình yên trong khoảnh khắc. Bạn hạnh phúc vì được sống.

Rồi bạn nhìn xuống và thấy trên bậu cửa sổ chỉ có một con mối cô độc đứng đó.

Lúc đầu bạn nghĩ, “Chà, chỉ có một con mối thôi, không sao đâu.”

Rồi bạn nghĩ thêm một chút. Máu bạn như đông lại vì nhận ra sự thật khủng khiếp: đây chỉ là con mối duy nhất bạn thấy, nhưng không bao giờ chỉ có một con mối.

Hy vọng được thư giãn của bạn tiêu tan khi bạn lập kế hoạch lột lớp sàn nhà bếp ra.

Đó, đại loại, là vị thế mà tôi và các đồng nghiệp ở Huntress rơi vào khi bắt đầu nhìn vào dữ liệu về ứng dụng Azure và cách chúng bị lợi dụng trong tenant của các đối tác. Vậy hãy cùng chúng tôi đi một chuyến hoang dã khi chúng tôi lột sàn nhà bếp ra và khám phá tổ mối thực sự lớn đến đâu!

## Tấn công ứng dụng OAuth

Kể từ khi phát hành [Unwanted Access capability](https://www.huntress.com/blog/unwanted-access-protecting-against-the-growing-threat-of-session-hijacking-and-credential-theft?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-10-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle2), Huntress SOC đã bận rộn ghi nhận số vụ tấn công nhận dạng bị ngăn chặn. Chúng tôi xây dựng chức năng để nhắm vào các khu vực chính của việc truy cập ban đầu trong không gian nhận dạng, bao gồm trộm thông tin định danh, trộm token, các cuộc tấn công [adversary in the middle (AitM)](https://www.huntress.com/blog/unmasking-the-central-villain-inside-adversary-in-the-middle-attacks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-10-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle2) và đăng nhập bất thường theo vị trí/[VPN](https://www.huntress.com/blog/mommy-does-santa-like-nordvpn?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-10-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle2).

Theo dữ liệu, chức năng này đã làm giảm đáng kể hoạt động của tác nhân đe dọa và hiện chúng tôi đang chặn khoảng từ ba đến sáu nghìn trường hợp truy cập ban đầu mỗi tháng.

Nhưng đúng với nghệ thuật phòng thủ mạng, chúng ta không thể chỉ dựa vào thành công. Tin tặc như zombie trong I Am Legend.

Tại sao? Cả hai đều cháy khi tiếp xúc trực tiếp với ánh nắng mặt trời. Nhưng quan trọng hơn, cả hai sẽ tiến hóa đến mức phòng thủ hiện tại của bạn trở nên vô nghĩa sau một thời gian. Vì vậy chúng tôi tiếp tục tìm kiếm các cách mới để xác định và phá vỡ chuỗi tấn công của họ.

Một lĩnh vực nghiên cứu đang được chú ý đặc biệt là khái niệm Rogue App. Ứng dụng đám mây là phần cốt lõi của trải nghiệm người dùng và cung cấp cho nhà phát triển bộ công cụ mạnh mẽ để xây dựng và mở rộng. Nhưng như chúng tôi đã tìm hiểu gần đây, chính những lợi ích khiến ứng dụng đám mây hấp dẫn với quản trị viên và nhà phát triển cũng khiến chúng hấp dẫn với tội phạm mạng.

Đây có vẻ là nơi tốt tiếp theo để tìm kiếm các cuộc tấn công đã lọt qua hệ thống chống truy cập ban đầu của chúng tôi.

Vì vậy nhóm đã bắt đầu với một số câu hỏi nghiên cứu để trả lời. OAuth applications trong Azure hoạt động như thế nào? Chúng có thể bị lợi dụng ra sao trong tấn công? Điều gì khiến chúng trở nên mạnh mẽ và hữu ích cho tội phạm mạng? Cách tốt nhất để truy tìm những rogue apps này là gì? Và câu hỏi cuối cùng khiến tôi rùng mình: có bao nhiêu ứng dụng như vậy ngoài kia?

![Hình 1: danh sách hiện tại của Application Registrations trên môi trường thử nghiệm của tôi. Hy vọng là môi trường của bạn sẽ không có vài ứng dụng tên “not a backdoor”](https://www.bleepstatic.com/images/news/security/h/huntress-labs/hidden-threats-microsoft-365/app-registrations.jpg)

**Hình 1: danh sách hiện tại của Application Registrations trên môi trường thử nghiệm của tôi. Hy vọng là môi trường của bạn sẽ không có vài ứng dụng tên “not a backdoor”**

Khi tìm kiếm câu trả lời cho những câu hỏi này, chúng tôi nhận được nhiều hơn cả mong đợi.

## Hệ thống đang hoạt động: OAuth Apps hoạt động như thế nào

Giữ chặt, vì đây là khóa học nhanh về ứng dụng Azure và cách chúng hoạt động. Tôi sẽ bắt đầu bằng cách nói rằng hệ thống này phức tạp và kỳ lạ.

Một tài nguyên giúp tôi hiểu là [John Savill’s Technical Training lecture on Azure App Registrations, Enterpriser Apps, and Service Principals](https://www.youtube.com/watch?v=WVNvoiA%5Fktw). Và để biết thêm, John là một chuyên gia được chứng nhận trong quản trị Azure và thumbnail của video này là ông ấy trông lo lắng khi phải giải thích khái niệm.

Vì vậy, đừng lo nếu bạn không hiểu hệ thống đến tận ngóc ngách. Cho mục đích của bài viết này, tôi sẽ giải thích các khái niệm liên quan trực tiếp đến cách ứng dụng có thể bị sử dụng ác ý.

Ứng dụng trên đám mây giống như ứng dụng trên điện thoại hoặc PC của bạn. Chúng là chương trình mô-đun được thiết kế để thực hiện một việc hữu ích. Ứng dụng trong Azure liên kết với Entra ID để tài khoản M365 của bạn có thể, ví dụ, sử dụng một client desktop tổ chức email từ tài khoản đám mây của bạn.

Azure chia ứng dụng thành hai loại: **Enterprise Applications** và **Application Registrations**. Tôi thấy cách đặt tên này cực kỳ gây nhầm lẫn và mất một lúc mới phân biệt được, nhưng khác biệt chính có thể tóm tắt là: “Bạn có tự xây ứng dụng đó, hay bạn đang sử dụng ứng dụng người khác xây?”

Enterprise Applications là ứng dụng được xây dựng, bảo trì, và xuất bản bởi người khác ở tenant khác mà bạn đang sử dụng trong tenant của mình.

Application Registrations là ứng dụng mà bạn xây dựng, bảo trì, và xuất bản trong tenant của bạn cho người khác sử dụng. Nói cách khác, một Application Registration giống như một mẫu cho ứng dụng, còn một Enterprise Application là một instance của ứng dụng được ai đó cài đặt.

Một nhà phát triển sẽ viết code cho ứng dụng và sau đó tạo một Application Registration trong tenant của họ trước khi xuất bản cho sử dụng công khai hoặc nội bộ.

Bây giờ, giả sử một quản trị viên có ý định cài ứng dụng của bạn trong tenant họ. Có thể họ tìm thấy website của bạn và nghĩ ứng dụng của bạn hữu ích. Ứng dụng không thể tự cài đặt mọi nơi chúng muốn. Bạn tưởng tượng được không? Thật hỗn loạn.

Vì vậy phải có hệ thống **authentication** (authN) và **authorization** (authZ) trước khi ai đó có thể cài ứng dụng vào tenant. Thông thường quy trình như sau:

* Người dùng sẽ yêu cầu cài ứng dụng. Trong khi làm điều này, người dùng **xác thực** bằng tên đăng nhập, mật khẩu, và MFA để đảm bảo ứng dụng được cài bởi bên đáng tin.
* Ứng dụng có một tập **quyền (permissions)** cho phép nó làm những gì được thiết kế. Ví dụ, quyền có thể cho phép ứng dụng truy cập Graph API để lấy email của người dùng. Ứng dụng sẽ hiển thị prompt để người dùng **đồng ý các quyền**.

![Hình 2: Quy trình authentication và authorization của ứng dụng. Ứng dụng yêu cầu consent để cài một service principal vào tenant của người dùng.](https://www.bleepstatic.com/images/news/security/h/huntress-labs/hidden-threats-microsoft-365/application-authentication-flow.jpg)

**Hình 2: Quy trình authentication và authorization của ứng dụng. Ứng dụng yêu cầu consent để cài một service principal vào tenant của người dùng.**

**Hình 3: Quy trình authentication và authorization của ứng dụng. Người dùng vui vẻ đồng ý các quyền yêu cầu.**

* Người dùng đồng ý các quyền và **ủy quyền** ứng dụng truy cập tài nguyên dựa trên những quyền đó. Khi **authentication** và **authorization** đã được thiết lập, ứng dụng có thể thực hiện nhiệm vụ của nó.
* Một **service principal** giờ được cài vào tenant của người dùng, hoạt động như một tài khoản cho ứng dụng này. Nó theo dõi các quyền đã được consent và các danh tính đã consent cho ứng dụng. Tài khoản service này hành động đại diện cho ứng dụng khi ứng dụng còn được cài trong tenant.

**Hình 4: quy trình authentication và authorization. Khi cả hai được giải quyết, ứng dụng cài một service principal vào tenant của người dùng.**

Nếu bạn đã bỏ qua phần trước vì nó nhàm chán, tôi không trách bạn. Nhưng các điểm rút ra như sau:

* Ứng dụng có thể được xây dựng nội bộ (Application Registrations) hoặc được cài từ tenant khác (Enterprise Applications).
* Ứng dụng có thể có quyền đại diện (delegated access) thay mặt cho một hoặc nhiều người dùng trong tenant để truy cập tài nguyên.
* Ứng dụng Azure sử dụng hệ thống authentication và authorization tích hợp để hoạt động.
* Bất cứ khi nào một ứng dụng được cài đâu đó, một service principal được cài trong tenant đó và hoạt động như tài khoản làm việc cho ứng dụng.
* Và cuối cùng, cấu hình mặc định của Azure cho phép bất kỳ người dùng nào cài bất kỳ ứng dụng nào và đồng ý các quyền giới hạn trong phạm vi truy cập tài nguyên của họ mà không yêu cầu kiểm duyệt ứng dụng!

Những gì chúng ta có ở đây là một tập primitives tuyệt vời để khai thác.

Tại sao? Bất cứ ai đã dành thời gian quản trị một hệ thống authentication và authorization lớn, phức tạp sẽ nói với bạn rằng kẻ tấn công thích tìm những lỗ hổng không thể vá của hệ thống để khai thác.

Bất kỳ red teamer nào đã chạy một cuộc tấn công Kerberoasting sẽ nói với bạn rằng các primitives khai thác tốt nhất là các tính năng, không phải lỗi, và do đó không thể vá. Ứng dụng trong Azure tuân theo quan điểm này—chúng là một phần của hệ sinh thái, cho dù tốt hay xấu.

Tính tùy biến của chúng cung cấp cho kẻ tấn công nhiều lựa chọn để điều chỉnh ứng dụng phù hợp với kiểu tấn công họ muốn thực hiện. Và chúng phần lớn lẩn trốn vì hệ thống này khá khó hiểu.

Khi bạn dùng ứng dụng trong Azure, dù mục đích tốt hay xấu, bạn vẫn đang hoạt động hoàn toàn trong khung hợp pháp cho phép ứng dụng hoạt động. Đối với các tác nhân đe dọa, đó là một hệ thống vô cùng mạnh để nghịch phá. Hãy xem chúng hữu ích đến mức nào.

## [Abuse Huntress' Identity Security Assessment](https://www.huntress.com/itdr-free-trial?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-10-camp-itdr-global-prospect-all-x-identity%5Fsecurity%5Fassessment)

Biến cảm giác an toàn thành biết chắc bạn an toàn với một Identity Security Assessment.

Bắt đầu thử nghiệm Managed ITDR để khám phá rogue apps, đăng nhập đáng ngờ, quy tắc inbox ẩn, và hoạt động truy cập rủi ro trong tenant Microsoft 365 của bạn. Nhận một Identity Security Assessment tùy chỉnh, gửi thẳng vào hộp thư của bạn.

Tệ nhất? Chúng tôi tìm được điều gì đó. Tốt nhất? Bạn biết mình an toàn.

[Abuse our Assessment](https://www.huntress.com/itdr-free-trial?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-10-camp-itdr-global-prospect-all-x-identity%5Fsecurity%5Fassessment)

## Traitorware: Ứng dụng tốt bị phản bội

Một cái đòn bẩy (crowbar) là công cụ cực kỳ hữu ích. Bạn có thể dùng nó để mở thùng, nạy cửa nếu bị kẹt, và nếu may mắn, thậm chí thoát khỏi một cơ sở nghiên cứu ngầm khổng lồ ở sa mạc New Mexico. Nếu bạn hiểu tham chiếu cuối cùng, bạn qua bài kiểm tra vibe.

Một cái đòn bẩy bản thân nó không phải tốt hay xấu. Nó hữu ích trong nhiều bối cảnh khác nhau. Và những bối cảnh đó quyết định cách chúng ta nhìn nhận cái đòn bẩy như một công cụ. Vì vậy dù bạn đang mở thùng hàng hay đột nhập nhà người khác, cái đòn bẩy vẫn là cái đòn bẩy! Tất nhiên bạn không thể nói tất cả đòn bẩy luôn xấu. Nhưng hầu hết khi bạn thấy ai đó đột nhập nhà, họ có một cái đòn bẩy!

Trong thế giới ứng dụng Azure, loại ứng dụng đầu tiên mà chúng tôi truy tìm giống như cái đòn bẩy. Chúng tôi gọi loại này là **Traitorware**.

Thuật ngữ chỉ các ứng dụng không được thiết kế rõ ràng cho mục đích xấu, nhưng lại cực kỳ hữu dụng cho hacker, tội phạm mạng, và những nhân vật mờ ám. Chúng tôi truy tìm các ứng dụng mà kẻ tấn công thường dùng, ngay cả khi chính ứng dụng đó không xấu.

Tương tự nhất trong an ninh endpoint là giữa Living Off the Land và Bring Your Own tools. Loại tấn công này giống với việc cài Remote Monitoring and Management (RMM) trong cuộc xâm nhập endpoint—tác nhân đe dọa mang một công cụ hợp pháp vào trận đấu mà vô tình hữu ích cho mục đích mờ ám.

**Hình 5: Traitorware, hay Good Apps Gone Rogue. Mỗi ứng dụng đều có kịch bản Jekyll và Hyde.**

Tại thời điểm viết bài này, có năm ứng dụng như vậy mà chúng tôi coi là dấu hiệu khói. Theo thống kê, năm ứng dụng này được kẻ tấn công ưu ái. Với mẫu khoảng 1.5k trường hợp báo cáo và tỷ lệ dương tính giả trung bình 1.8%, dữ liệu cho thấy phát hiện các ứng dụng này sẽ hé lộ hoạt động hack nhiều hơn hoạt động hợp pháp.

Danh sách đầy đủ các ứng dụng Traitorware mà chúng tôi tổng hợp và thông tin chi tiết về cách chúng thường bị lạm dụng có sẵn tại kho mã nguồn mở Rogue Apps của chúng tôi: https://huntresslabs.github.io/rogueapps/.

Nếu bạn đã thấy ứng dụng bị lạm dụng tương tự, chúng tôi rất muốn nghe! Hãy cân nhắc mở một PR và đóng góp vào cơ sở kiến thức để chúng tôi có thể định nghĩa và theo dõi bề mặt tấn công mới nổi thú vị này tốt hơn.

## Stealthware: Ứng dụng ác từ trang trại đến bàn ăn

Mặt khác, hệ sinh thái ứng dụng Azure cũng cung cấp cho hacker công cụ để tạo ứng dụng từ đầu được thiết kế để gây rối.

Tôi đang nói đến EVIL APPS thủ công, sản xuất nhỏ lẻ, làm tại nhà, thủ công — được tạo bởi tay hacker và giao thẳng vào tenant của bạn.

Tên đầy đủ cho các tấn công này là “[OAuth Illicit Consent Grant Attacks](https://learn.microsoft.com/en-us/defender-office-365/detect-and-remediate-illicit-consent-grants)” nhưng gọi vậy giống như gọi một con chó là Canis Lupus. Chỉ có dân nerd mới dùng tên khoa học, nên bạn có thể là một nerd ngầu như tôi và gọi chúng là **Stealthware**.

Khó khăn khi [truy tìm các ứng dụng Stealthware](https://learn.microsoft.com/en-us/security/operations/incident-response-playbook-app-consent) là không có hai ứng dụng nào giống nhau. Bạn không thể tìm chúng bằng cách tìm tên ứng dụng cụ thể. Mỗi ứng dụng được làm riêng và điều chỉnh cho kiểu khai thác mà hacker dự định thực hiện.

Tôi dạy cách tạo một ứng dụng như vậy cho mục đích giáo dục trong [một tập của Tradecraft Tuesday](https://www.youtube.com/live/gsBdZKLOY1w), nếu bạn quan tâm.

**Hình 6: Stealthware, kẻ mạo danh giữa các ứng dụng Azure. Được dựng để gây rối, được dựng để hoà nhập.**

## Cuộc truy tìm đang diễn ra

Với mô hình mối đe dọa đã được định hình, đã đến lúc lặn sâu vào dữ liệu và tìm câu trả lời cho câu hỏi: “Ngoài con mối duy nhất đó, còn bao nhiêu con khác?” Để làm điều này, tôi và Staff Threat Ops Developer Christina Parry bắt đầu hành trình thu thập dữ liệu.

Chúng tôi liệt kê hơn 8000 tenants trên nhiều ngành và lĩnh vực, thu thập tất cả Enterprise Applications và App Registrations của họ, chạy nhiều phân tích trên dữ liệu, và [trình bày phát hiện tại BSidesNYC vào tháng 10/2024](https://www.youtube.com/watch?v=XSzfsz2zoQQ). Tóm tắt như sau:

* Chúng tôi tìm thấy bằng chứng của cả Traitorware và Stealthware trong các tenant khảo sát.
* Khoảng 10% tenant khảo sát có ít nhất một trong các ứng dụng Traitorware được cài.
* Sử dụng kết hợp tỷ lệ hiếm toàn cầu, số người dùng được gán cho ứng dụng, và các quyền được cấp của ứng dụng là cách hiệu quả để truy tìm Stealthware.
* Ứng dụng có tỉ lệ xuất hiện toàn cầu thấp hơn 1% trong các tenant khảo sát và có delegated access cho một người dùng đơn lẻ có nhiều khả năng là Stealthware. Việc phân loại quyền OAuth thành các nhóm dựa trên những gì chúng cho phép kẻ tấn công làm trong xâm nhập và phát hiện các ứng dụng hiếm có quyền mạnh mẽ đã tăng đáng kể tỉ lệ phát hiện.

Sau khi trình bày, chúng tôi bắt tay xây dựng hệ thống để mở rộng và thu thập dữ liệu cho tất cả tenant đối tác Huntress. Sau khi phân tích lại và tinh chỉnh các phân tích, chúng tôi thấy kết luận về ứng dụng Traitorware vẫn ổn định ở khoảng 10%.

Sau khi công bố phát hiện, Huntress SOC cũng vào cuộc. Dựa trên telemetry mới, họ tạo giả thuyết truy săn và xác định hơn 500 trường hợp Stealthware trên tất cả tenant đối tác.

Tôi đã đề cập trước đó rằng bạn không thể truy tìm Stealthware bằng cách tìm tên ứng dụng và kết quả chứng minh điều đó. Đây chỉ là mẫu một số tên ứng dụng độc hại xác thực mà chúng tôi tìm thấy:

**Hình 7: Mẫu tên ứng dụng độc hại có phần kỳ quặc**

Với vài giả thuyết được chứng minh, cuối cùng chúng tôi có thể đưa ra kết luận. OAuth App Attacks không chỉ tồn tại trong tenancy đối tác Huntress, mà còn phổ biến hơn nhiều so với kỳ vọng. Một số ứng dụng này đã tồn tại nhiều năm trước khi chúng tôi phát hiện ra.

Và nếu bạn chỉ rút ra một điều từ bài viết này, hãy nhớ: **theo thống kê, có khả năng cao tenant của bạn cũng bị nhiễm một trong những ứng dụng này**.

## Giới thiệu: Cazadora

Nếu bạn đọc đến đây và đang nghĩ “chà, có lẽ mình nên kiểm tra các ứng dụng,” tuyệt vời! Điều đó có nghĩa tôi đã đủ thuyết phục về mức độ tiềm năng tấn công tồn tại trong hệ sinh thái ứng dụng Azure.

Để tăng tốc quá trình giáo dục cộng đồng và cho quản trị viên Azure cơ hội dọn dẹp tổ mối, tôi đã xây và phát hành một công cụ mã nguồn mở liệt kê các ứng dụng trong tenant của bạn và truy tìm các dấu hiệu đáng nghi.

**Hình 8: Output của Cazadora, xác định một vài ứng dụng có đặc điểm đáng ngờ.**

Giới thiệu: **[Cazadora](https://github.com/HuskyHacks/cazadora)**, một script săn ứng dụng Azure đơn giản. Dù bạn là đối tác Huntress hay không, bất kỳ ai cũng có thể chạy script này để liệt kê và kiểm tra các ứng dụng tenant của mình dựa trên một số thuộc tính tradecraft thường gặp.

Nó sử dụng xác thực người dùng của chính bạn, gọi Graph API, xử lý dữ liệu từ API về Enterprise Applications và App Registrations của tenant, và chạy một số logic săn tìm trên kết quả.

Nó nhanh và thô sơ, nhưng ý tưởng là trao quyền cho quản trị viên Azure khắp nơi có cái nhìn ngay lập tức về các ứng dụng khả nghi trong tenant của họ.

Script không thể tìm 100% ứng dụng xấu ở mọi nơi, đương nhiên. Và ngay cả khi script không tìm được gì, điều đó không có nghĩa tenant của bạn an toàn khỏi các ứng dụng độc hại. Nhưng ít nhất, nó là điểm khởi đầu tốt để quản trị viên Azure kiểm tra và xác định những điều nổi bật.

Vui lòng xem README trong repo để có hướng dẫn! Thử nó nhé. Xem bạn tìm được gì, hoặc…

## Abuse our ITDR Assessment

Theo thống kê, khả năng cao chúng tôi sẽ tìm được điều gì đó. Huntress Identity Security Assessment cung cấp cái nhìn rõ ràng về cảnh quan M365 Identity Threat của bạn — làm nổi bật license types, rogue apps, đăng nhập đáng ngờ, và quy tắc inbox độc hại.

Nếu không tìm thấy mối đe dọa, bạn vẫn thu được thông tin giá trị về các khu vực chính mà chúng tôi giám sát và các mối đe dọa chúng tôi săn.

Tệ nhất? Chúng tôi phát hiện rủi ro. Tốt nhất? Bạn biết mình an toàn. Dù thế nào, bạn rời đi với thông tin và năng lực. [Xem thêm](https://www.huntress.com/itdr-free-trial?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-10-camp-itdr-global-prospect-all-x-identity%5Fsecurity%5Fassessment&utm%5Fcontent=cy25-10-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle2).

## Duy trì Nhận thức Tình huống — Đăng ký Tradecraft Tuesday

Tradecraft Tuesday cung cấp cho chuyên gia an ninh mạng phân tích sâu về các tác nhân đe dọa mới nhất, vector tấn công và chiến lược giảm thiểu.

Mỗi phiên hàng tuần có các hướng dẫn kỹ thuật về các sự cố gần đây, phân tích xu hướng malware, và các indicators of compromise (IOCs) cập nhật.

Người tham dự nhận được:

* Thuyết trình chi tiết về các chiến dịch đe dọa mới nổi và biến thể ransomware
* Phương pháp phòng thủ dựa trên bằng chứng và kỹ thuật khắc phục
* Tương tác trực tiếp với các nhà phân tích Huntress để có góc nhìn hồi đáp sự cố
* Truy cập vào threat intelligence và hướng dẫn phát hiện có thể hành động

Nâng cao thế phòng thủ của bạn với intelligence thời gian thực và giáo dục kỹ thuật thiết kế cho những người chịu trách nhiệm bảo vệ môi trường tổ chức.

### **[Đăng ký Tradecraft Tuesday →](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-10-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle2)**

_Bài viết được tài trợ và viết bởi Huntress Labs (https://www.huntress.com/itdr-free-trial?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-10-camp-itdr-global-prospect-all-x-identity%5Fsecurity%5Fassessment)._