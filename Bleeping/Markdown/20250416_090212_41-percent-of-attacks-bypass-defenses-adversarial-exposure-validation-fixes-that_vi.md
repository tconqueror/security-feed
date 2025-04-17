# 41% Các cuộc tấn công vượt qua được phòng thủ: Adversarial Exposure Validation khắc phục điều đó

![Máy tính với màn hình bị hỏng](https://www.bleepstatic.com/content/posts/2025/04/15/picus-bypass-defenses.jpg)

Công cụ bảo mật của bạn nói rằng mọi thứ đều ổn, nhưng kẻ tấn công vẫn lọt vào.

Bất chấp nhiều năm đầu tư vào firewalls, bảo vệ endpoint, SIEMs và các phòng thủ lớp khác, hầu hết các tổ chức đều phải đối mặt với một sự thật đáng lo ngại: theo [nghiên cứu gần đây](https://hubs.li/Q03gXYTK0) của Picus Security, chỉ **59% các mối đe dọa bị ngăn chặn bởi các biện pháp kiểm soát bảo mật của họ**.

Điều đó có nghĩa là **41% các cuộc tấn công thành công vượt qua được phòng thủ**. Và thiệt hại thực sự thường bắt đầu khi sự nhìn thấy kết thúc.

**40% các môi trường doanh nghiệp có các con đường tấn công dẫn đến việc chiếm quyền quản trị miền**, những lối đi tiềm ẩn mà kẻ tấn công có thể khai thác ngay bây giờ.

Càng tồi tệ hơn, những điểm mù này thường không được phát hiện cho đến khi quá muộn. Các chỉ số truyền thống như không có sự cố hoặc kết quả quét sạch có thể tạo ra cảm giác an toàn sai lầm. Nhưng kẻ tấn công không quan tâm đến những gì mà bảng điều khiển của bạn nói. Họ quan tâm đến những gì họ có thể khai thác.

Vì vậy, câu hỏi không còn là “Tôi có công cụ bảo mật nào không?” mà là: “**Làm thế nào để tôi biết chúng đang hoạt động, ngay bây giờ?**”

## Những gì thiếu trong kiểm tra bảo mật tấn công hiện tại

Các nhóm bảo mật thường dựa vào sự kết hợp giữa các bài kiểm tra thâm nhập hàng năm và các quét lỗ hổng định kỳ. Mặc dù hữu ích và vẫn cần thiết, các phương pháp này có những hạn chế lớn trong bối cảnh mối đe dọa và môi trường CNTT đang thay đổi nhanh chóng hiện nay:

* **Chúng không liên tục.** Các bài kiểm tra điểm thời gian không tính đến sự trôi dạt cấu hình, các lỗ hổng mới hoặc sự thay đổi hàng ngày trong hành vi của kẻ tấn công.
* **Chúng thiếu bối cảnh thế giới thực.** Các quét đánh dấu hàng nghìn CVE mà không cho thấy những gì mà kẻ tấn công thực sự có thể khai thác và không ưu tiên những cái quan trọng nhất đối với môi trường của bạn.
* **Chúng không xác thực các biện pháp kiểm soát.** Chỉ vì một lỗ hổng tồn tại không có nghĩa là EDR hoặc SIEM của bạn sẽ bỏ qua nó, nhưng bạn sẽ không bao giờ biết nếu không thử nghiệm.
* **Chúng thiếu xác minh khắc phục.** Bạn có thể sửa một lỗ hổng, nhưng liệu các hệ thống phát hiện của bạn có nhận ra các khai thác tương tự không? Các cảnh báo có kích hoạt khi chúng nên không?

Điều này tạo ra một khoảng cách nguy hiểm giữa an ninh cảm nhận và khả năng phục hồi thực tế. Cách tiếp cận phản ứng này để lại cho các nhóm không có tầm nhìn. Bạn có thể sửa những gì dễ dàng vá lại nhưng bỏ lỡ những gì có thể khai thác nhất. Bạn có thể giả định rằng các quy tắc phát hiện của bạn hoạt động, cho đến khi chúng không hoạt động.

Để vượt lên trên các đối thủ, các tổ chức cần một cách thông minh và liên tục hơn để xác thực phòng thủ của họ; một cách phản ánh cách mà kẻ tấn công suy nghĩ, hoạt động và phát triển.

## [Gấp đôi khả năng chặn mối đe dọa trong 90 ngày](https://hubs.li/Q03gXZBg0)

Breach and Attack Simulation (BAS) cho phép bạn mô phỏng an toàn các cuộc tấn công thực tế trong môi trường sản xuất của bạn mà không có rủi ro hoặc thời gian chết. 

Khám phá cách mà nền tảng Picus tăng cường phòng ngừa và phát hiện, giúp bạn chặn 2X nhiều mối đe dọa chỉ trong 90 ngày.

[Tải xuống e-book](https://hubs.li/Q03gXZBg0)

## Breach and Attack Simulation (BAS): Liên tục kiểm tra các phòng thủ của bạn

[Breach and Attack Simulation (BAS)](https://www.picussecurity.com/breach-and-attack-simulation) đóng một khoảng cách đáng kể trong xác thực truyền thống. Nó cho phép bạn **mô phỏng các cuộc tấn công mạng thực tế trong môi trường sản xuất của bạn** mà không có rủi ro và không có thời gian chết.

Dưới đây là cách thức hoạt động của nó:

* Các nền tảng BAS khởi động các mô phỏng an toàn của **malware, ransomware, phishing attacks, và hơn thế nữa**, sau đó theo dõi những gì bị chặn, phát hiện, hoặc hoàn toàn bị bỏ qua.
* Những mô phỏng này kiểm tra **firewalls, IPSs, cổng email, EDR, SIEMs, và hơn thế nữa**, để bạn có thể thấy nơi mà các biện pháp kiểm soát thất bại hoặc không kích hoạt.
* Các thư viện mối đe dọa được cập nhật liên tục với các **TTP mới nhất của kẻ tấn công** để có thể đo lường phòng thủ của bạn so với các mối đe dọa hiện tại.

Hãy tưởng tượng BAS như một bài diễn tập phòng cháy chữa cháy suốt ngày đêm cho thiết bị bảo mật của bạn. Khi một khai thác đi qua IPS của bạn hoặc SIEM của bạn không bắt được một beacon đã được nhận diện, bạn sẽ biết điều đó trong vài giờ, không phải vài tháng.

Các nghiên cứu đã tiết lộ rằng các đội sử dụng BAS một cách nhất quán đã được chứng minh là **[gấp đôi khả năng chặn mối đe dọa trong 90 ngày](https://hubs.li/Q03gXZBg0)**.

## Automated Penetration Testing: Khai thác các lỗ hổng, phơi bày các con đường tấn công

Trong khi BAS tập trung vào việc xác minh hiệu quả của các biện pháp kiểm soát, **Automated Penetration Testing** xác định con đường mà một kẻ tấn công thực sự sẽ **di chuyển trong môi trường của bạn**.

Đây là những gì nó mang lại cho kho vũ khí của bạn:

* Nó mô phỏng hoạt động của kẻ tấn công: khai thác lỗ hổng, thu thập thông tin xác thực, di chuyển theo chiều ngang qua các hệ thống, và leo thang đặc quyền.
* Nó xác nhận các bước tấn công thực tế: minh họa không chỉ những gì đang bị tấn công, mà còn cách mà kẻ tấn công sẽ liên kết các bước để truy cập vào các tài sản quan trọng.
* Nó có thể hoạt động liên tục: theo kịp sự phát triển của hạ tầng CNTT của bạn, cho dù có những triển khai mới hoặc sự chậm trễ trong việc vá lỗi.

Ví dụ, một bài kiểm tra thâm nhập tự động có thể tận dụng một máy chủ chưa được vá, đánh cắp thông tin xác thực, và di chuyển theo chiều ngang cho đến khi đến được quyền quản trị miền. Đây không phải là những cuộc tấn công lý thuyết, chúng là những bài diễn tập có thể tái tạo thực tế và tiết lộ **các con đường chính xác mà kẻ tấn công sẽ đi**.

Thực tế, nghiên cứu từ Picus Security phát hiện **[40% các môi trường mà họ thử nghiệm có các con đường khai thác đến quyền quản trị miền](https://hubs.li/Q03gXYTK0)**, một sự xác nhận đáng sợ rằng những lỗ hổng nhỏ có thể dẫn đến những sự thỏa hiệp lớn.

![Nhóm ransomware ít bị ngăn chặn nhất](https://www.bleepstatic.com/images/news/security/p/picus/automated-pentesting/picus-least-prevented-ransomware-group.png)

**Nhóm ransomware ít bị ngăn chặn nhất**

## Adversarial Exposure Validation: Ghép nối BAS và Kiểm thử Thâm nhập Tự động để tăng cường bảo mật

Kết hợp, BAS và kiểm thử thâm nhập tự động cung cấp cho bạn một cái nhìn toàn cảnh 360 độ về tình trạng bảo mật của bạn. Thực hành kết hợp này là những gì Gartner gọi là **[Adversarial Exposure Validation (AEV)](https://www.picussecurity.com/resource/report/gartner-market-guide-for-adversarial-exposure-validation)**, một phương pháp liên tục, thực tế cho việc quản lý rủi ro mạng.

Sử dụng AEV, bạn có thể trả lời hai câu hỏi quan trọng nhất trong bảo mật:

* **Các biện pháp kiểm soát bảo mật của tôi có hoạt động hiệu quả không?** (góc nhìn từ BAS), và
* **Kẻ tấn công có thể đạt được điều gì trong môi trường của tôi?** (góc nhìn từ kiểm thử thâm nhập).

Các chủ đề này sẽ thông báo cho nhau:

* Nếu BAS cho thấy SIEM của bạn đã bỏ lỡ một mô phỏng, hãy sửa các quy tắc, sau đó thực hiện kiểm thử thâm nhập để xem liệu điểm mù đó có dẫn đến quyền truy cập bổ sung không.
* Nếu một bài kiểm tra thâm nhập tự động xác định một vector nâng cao đặc quyền, hãy tái tạo TTP đó với BAS để đảm bảo phát hiện trong tương lai.

Hệ thống khép kín này tương đương với **khắc phục nhanh hơn, phát hiện tốt hơn, và ít suy đoán hơn**.

### 5 Lợi ích chính của Adversarial Exposure Validation cho các đội bảo mật hiện đại

Adversarial Exposure Validation mang đến nhiều hơn sự nhìn thấy, nó thúc đẩy cải tiến có thể đo lường: 

* **Sự tự tin đối với các cuộc tấn công thực tế:** AEV thử nghiệm tính bảo vệ của bạn đối mặt với các mối đe dọa hôm nay—không phải mối đe dọa của năm ngoái. Khi sự thật xảy ra, đội của bạn sẽ đã thấy nó trước đó.
* **Xác thực liên tục các biện pháp kiểm soát bảo mật:** Kiểm tra các EDR, firewalls, và SIEMs hàng ngày, không phải một lần một năm. Phát hiện những sai sót trong phát hiện và cấu hình sớm.
* **Quản lý phơi bày proctive:** Đừng chỉ quét các lỗ hổng. Mô phỏng các cuộc tấn công. AEV giúp ưu tiên các rủi ro dựa trên khả năng khai thác thực tế và ảnh hưởng tiềm tàng đến kinh doanh.
* **Sự sẵn sàng SOC cải thiện:** Mỗi mô phỏng là một cơ hội đào tạo. Các nhà phân tích của bạn cải thiện kỹ năng của họ và xác thực các sách hướng dẫn phản ứng sự cố trong thời gian thực.
* **Tiến bộ bảo mật có thể đo lường:** Theo dõi tỷ lệ phát hiện và ngăn chặn, thời gian phản hồi, và các con đường tấn công đã đóng để thể hiện ROI bảo mật thực sự, cả về nội bộ và cho các kiểm toán viên.

## Một cách tiếp cận tích hợp tới việc xác thực bảo mật

Adversarial Exposure Validation (AEV) thành công không chỉ cần công cụ điểm, mà cần một cách tiếp cận toàn diện, hướng đến mối đe dọa. [Nền tảng Xác thực Bảo mật Picus](https://www.picussecurity.com) cung cấp chính xác điều đó, kết hợp [Breach and Attack Simulation (BAS)](https://www.picussecurity.com/breach-and-attack-simulation) và [Automated Penetration Testing (APT)](https://www.picussecurity.com/use-case/pen-testing-automation) dưới một nền tảng để phá vỡ các rào cản công cụ và hợp nhất kiểm tra bảo mật.

* **Phủ sóng mối đe dọa thế giới thực:** Picus có một [thư viện mối đe dọa](https://www.picussecurity.com/product/picus-threat-library) với hơn 30,000 TTPs, từ ransomware đến cấu hình sai trong đám mây, cho việc kiểm tra hiện tại, liên quan.
* **Giải pháp khắc phục có thể hành động, tích hợp:** Khi một bài kiểm tra tìm thấy một khoảng trống, chẳng hạn như một nỗ lực khai thác bị bỏ lỡ, Picus không chỉ báo cáo. Nền tảng này đề xuất và tự động hóa các giải pháp khắc phục thông qua [Thư viện Giải pháp khắc phục,](https://www.picussecurity.com/product/mitigation-library) tăng tốc giảm thiểu rủi ro.
* **Xác thực liên kết, có liên quan:** Bằng cách kết hợp Xác thực Kiểm soát Bảo mật (SCV) với Xác thực Con đường Tấn công (APV), Picus đóng khoảng cách phát hiện với sự tiến bộ có thể của kẻ tấn công, ưu tiên những gì là quan trọng nhất.

Với Picus, xác thực là một quá trình liên tục của việc thử nghiệm, sửa chữa, và nâng cao, không phải là một checkbox hàng năm.

## Sẵn sàng để xem những gì mà chồng chất bảo mật của bạn còn thiếu?

**Đừng đợi đến khi có sự xâm phạm tiếp theo để phơi bày các điểm mù của bạn.**

Adversarial Exposure Validation giúp bạn xác định và khắc phục 41% các mối đe dọa mà công cụ của bạn có thể bỏ lỡ—trước khi kẻ tấn công khai thác chúng.

**Khám phá tư thế an ninh thực sự của bạn. [Yêu cầu một buổi demo](https://hubs.li/Q03gXYR10).**

_Được tài trợ và viết bởi [Picus Security](https://hubs.li/Q03gXYR10)._