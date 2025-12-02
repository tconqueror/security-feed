# North Korea dụ dỗ kỹ sư cho thuê danh tính trong kế hoạch nhân viên IT giả

![Famous Chollima lừa các dev cho thuê danh tính trong kế hoạch nhân viên IT giả](https://www.bleepstatic.com/content/hl-images/2023/08/31/Lazarus-1.jpg)

Trong một chiến dịch tình báo chưa từng có, các nhà nghiên cứu bảo mật đã phơi bày cách mà North Korean IT recruiters nhắm mục tiêu và dụ dỗ các lập trình viên cho thuê danh tính của họ để huy động quỹ bất hợp pháp.

Famous Chollima (còn được biết đến với tên WageMole), một phần của nhóm do nhà nước Bắc Triều Tiên bảo trợ Lazarus, nổi tiếng với các chiến dịch social-engineering nhằm thâm nhập các công ty phương Tây để do thám và tạo doanh thu cho chế độ.

Họ đã lừa được các nhà tuyển dụng và có được các vị trí tại các công ty Fortune 500 bằng cách lợi dụng danh tính bị đánh cắp và rất nhiều AI, bao gồm cả video deep fake, và tránh xuất hiện trước camera trong các buổi phỏng vấn.

Một phương pháp khác là tuyển các kỹ sư hợp pháp và thuyết phục họ đóng vai bề ngoài trong hoạt động của các đặc vụ DPRK để có được công việc từ xa tại công ty mục tiêu.

Người đóng thế sẽ là bộ mặt của các đặc vụ trong tương tác với công ty trong suốt các buổi phỏng vấn và sẽ nhận một phần trăm lương, trong khoảng từ 20% đến 35% trong suốt thời hạn hợp đồng.

Để nhận được số tiền lớn hơn, kỹ sư bị lôi kéo sẽ phải cho phép các đặc vụ DPRK sử dụng máy tính của họ.

Việc này nhằm che giấu vị trí của người Bắc Triều Tiên và dấu vết của họ, vì họ sẽ sử dụng máy tính và kỹ sư như một proxy cho các hoạt động ác ý.

[Mauro Eldritch](https://www.linkedin.com/in/mauroeldritch/), một hacker và chuyên gia threat intelligence tại BCA LTD, cho biết rằng kỹ sư bị thỏa hiệp phải chịu toàn bộ rủi ro vì họ đã cho thuê danh tính và sẽ là người duy nhất chịu trách nhiệm cho bất kỳ thiệt hại nào gây ra.

### Gửi thư rác vào các kho GitHub

Eldritch quen thuộc với các thủ thuật tuyển dụng của Famous Chollima khi dẫn dắt Quetzal Team, Web3 Threats Research Team tại công ty dịch vụ tài chính số Bitso.

Ông đã ghi lại nhiều cuộc tiếp xúc với các đặc vụ DPRK tìm kiếm các kỹ sư hoặc nhà phát triển nhẹ dạ sẵn sàng kiếm tiền nhanh \[[1](https://quetzal.bitso.com/p/interview-with-the-chollima), [2](https://quetzal.bitso.com/p/interview-with-the-chollima-ii), [3,](https://quetzal.bitso.com/p/interview-with-the-chollima-iii) [4](https://quetzal.bitso.com/p/interview-with-the-chollima-iv), [5](https://quetzal.bitso.com/p/interview-with-the-chollima-v)\].

Gần đây, ông phát hiện nhiều tài khoản trên GitHub đang spam các repository với thông báo tuyển dụng cho những người sẽ tham dự các buổi phỏng vấn kỹ thuật (.NET, Java, C#, Python, JavaScript, Ruby, Golang, Blockchain) dưới một danh tính giả được cung cấp.

![Repositories with recruitment messages](https://www.bleepstatic.com/images/news/u/1100723/C%20-%20pull%20requests_DPRK-offer.png)

**Repositories with Famous Chollima recruitment messages**  
_nguồn: Mauro Eldritch and Heiner García_

Ứng viên sẽ không cần phải thành thạo các lĩnh vực kỹ thuật, vì nhà tuyển dụng sẽ hỗ trợ “để trả lời phỏng vấn viên một cách hiệu quả.”

Để làm cho đề nghị hấp dẫn hơn, đặc vụ DPRK đặt kỳ vọng tài chính vào “khoảng $3000 mỗi tháng.”

![Famous Chollima recruitment message](https://www.bleepstatic.com/images/news/u/1100723/B%20-%20DPRK-offer.png)

**Famous Chollima recruitment message**  
_nguồn: Mauro Eldritch and Heiner García_

Eldritch nhận lời thử thách và phát triển một kế hoạch cùng với Heiner García từ sáng kiến threat intelligence NorthScan để vạch trần việc thâm nhập nhân lực IT của Bắc Triều Tiên.

Hai nhà nghiên cứu sử dụng sandbox và nền tảng phân tích phần mềm độc hại ANY.RUN để thiết lập một honeypot mô phỏng laptop farm có thể ghi lại hoạt động theo thời gian thực để phân tích sau về chiến thuật và công cụ được sử dụng trong chiến dịch.

García đảm nhận vai trò kỹ sư mới, trả lời lời mời tuyển dụng. Ông mạo danh một cá nhân đã được liên hệ trước đó, một nhà phát triển tên Andy Jones, có trụ sở tại Hoa Kỳ.

Hai nhà nghiên cứu tạo một hồ sơ GitHub mới mô phỏng Jones tới từng repository công khai và các chi tiết liên quan.

Sau nhiều lần tương tác với đặc vụ DPRK để lấy thông tin về hoạt động, nhà tuyển dụng Bắc Triều Tiên yêu cầu truy cập từ xa 24/7 vào laptop của Eldritch qua AnyDesk cho “công việc từ xa.”

Từ từ, đặc vụ tiết lộ rằng hắn cần ID, họ tên đầy đủ, tình trạng visa và địa chỉ để nộp đơn phỏng vấn với tên Andy Jones.

Khi đóng vai trò frontman trong các buổi phỏng vấn, persona của Eldritch sẽ nhận 20% lương, hoặc “10% chỉ cho việc sử dụng thông tin và laptop của tôi trong khi hắn tự thực hiện các buổi phỏng vấn.”

Đặc vụ DPRK cũng yêu cầu số an sinh xã hội, cho các kiểm tra lý lịch, và giải thích rằng tất cả tài khoản cần được xác minh trên các nền tảng tuân thủ KYC.

### Truy cập từ xa qua Astrill VPN

Sau khi thiết lập môi trường ANY.RUN được sandbox hóa, đặt tại Đức, và dẫn đường kết nối qua một residential proxy để xuất hiện như ở Mỹ, các nhà nghiên cứu sẵn sàng cho “nhà tuyển dụng” kết nối từ xa vào “laptop” của họ.

Các nhà nghiên cứu kiểm soát hoàn toàn môi trường và có thể ngăn chặn kẻ đe dọa duyệt web trong khi giữ kết nối từ xa hoạt động, và làm treo máy theo ý muốn, để từ chối hoạt động ác ý chống lại bên thứ ba.

Sau khi kết nối từ xa vào máy của các nhà nghiên cứu, kẻ đe dọa bắt đầu kiểm tra phần cứng trên hệ thống, đặt Google Chrome làm trình duyệt mặc định, và xác minh vị trí của trạm.

Các nhà nghiên cứu nhận thấy rằng kết nối từ xa đi qua Astrill VPN, một dịch vụ phổ biến trong số các nhân viên IT giả của Bắc Triều Tiên.

[](http://x.com/craiu/status/1899045753286209988) 

**North Koreans IT worker prefer Astrill VPN**  
_nguồn: Costin Raiu_

### Công cụ và mánh khoé nghề

Hai nhà nghiên cứu cố gắng trì hoãn hoạt động của người Bắc Triều Tiên càng nhiều càng tốt, đẩy sự kiên nhẫn của hắn tới giới hạn bằng cách làm treo máy và xóa mọi tiến trình, hoặc trì hoãn trả lời tin nhắn.

Họ thậm chí đổ lỗi cho mọi “sự cố” kỹ thuật là do cấu hình mạng hoặc việc đặc vụ sử dụng kết nối VPN.

Trong một trường hợp, các nhà nghiên cứu gài đặc vụ DPRK vào một vòng đăng nhập và CAPTCHA mà hắn mất gần một giờ để thoát ra.

Tuy nhiên, tất cả những hành động này dẫn tới việc thu thập được nhiều thông tin hơn về hoạt động, các cá nhân liên quan, đối tác tiềm năng từ các quốc gia khác nhau, và các công cụ cùng mánh khoé đã được sử dụng.

Các nhà nghiên cứu quan sát thấy nhiều extension hỗ trợ AI như AIApply, Simplify Copilot, Final Round AI, và Saved Prompts giúp kẻ đe dọa tự động điền đơn xin việc và tạo resume, lưu các prompt cho ChatGPT LLM, và nhận trả lời theo thời gian thực trong các buổi phỏng vấn.

Bên cạnh đó, kẻ đe dọa cũng tiết lộ các extension xác thực OTP, việc sử dụng Google Remote Desktop, và các thủ thuật trinh sát hệ thống thường quy.

Trong một thời điểm, nhà tuyển dụng giả đăng nhập vào tài khoản Google và kích hoạt tuỳ chọn đồng bộ hóa, điều này tải về trong trình duyệt tất cả các tuỳ chọn liên quan tới profile, và cho phép truy cập vào hộp thư đến email của hắn.

**GMail inbox used by the North Korean fake IT recruiter**  
_nguồn: Mauro Eldritch and Heiner García_

García và Eldritch có thể thấy nhiều đăng ký các nền tảng tìm việc, extension trình duyệt đã cài, các workspace Slack và các cuộc trò chuyện từng phần.

“Hắn thường xuyên nói chuyện với một cá nhân tên Zeeshan Jamshed người trong cuộc trò chuyện ban đầu cho biết rằng người đó sẽ vắng mặt vì Eid, lễ hội của người Hồi giáo,” các nhà nghiên cứu cho biết trong báo cáo chia sẻ với BleepingComputer.

Theo báo cáo, đội Famous Chollima tham gia vào chiến dịch này gồm sáu thành viên, sử dụng các tên Mateo, Julián, Aaron,  
Jesús, Sebastián, và Alfredo.

Tuy nhiên, cần lưu ý rằng có nhiều đội Bắc Triều Tiên tham gia vào các hoạt động Famous Chollima, một số đội có tới mười thành viên, và họ cạnh tranh với nhau, lôi kéo các nạn nhân tiềm năng, như Eldritch và García cũng chỉ ra trong báo cáo.

Thông tin thu thập được từ tương tác với kẻ đe dọa Bắc Triều Tiên có thể giúp những người phòng thủ ở cả doanh nghiệp nhỏ và lớn như một cảnh báo sớm về một nỗ lực xâm nhập tiềm năng.

Dữ liệu có thể giúp họ dự đoán hành vi của nhóm, gián đoạn quy trình làm việc, và cải thiện khả năng phát hiện vượt ra ngoài việc so khớp các IoC phần mềm độc hại tiêu chuẩn.