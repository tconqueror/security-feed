# Đã biết. Mới nổi. Không thể ngăn chặn? Các cuộc tấn công mã độc tống tiền vẫn né tránh phòng thủ

![Picus Blue Report 2025](https://www.bleepstatic.com/content/posts/2025/09/14/blue-report-header.png)

Không, đây không phải là điều mới hoặc đặc biệt kỳ lạ, nhưng sau nhiều năm chịu đựng các cuộc tấn công, mã độc tống tiền vẫn nằm trong số những mối đe dọa gây tàn phá nhất đối với các tổ chức toàn cầu ngày nay.

Ngay cả khi các đội an ninh đang đổ nguồn lực lớn vào các nỗ lực phòng ngừa và phát hiện, kẻ tấn công vẫn tìm được cách vượt qua phòng thủ. **Tống tiền kép** đã trở thành cách tiếp cận mặc định, với các nhóm mã hóa hệ thống và đánh cắp dữ liệu nhạy cảm để gây sức ép.

Một số tác nhân **bây giờ bỏ qua bước mã hóa hoàn toàn**, chỉ tập trung vào đánh cắp dữ liệu và tống tiền để tránh bị phát hiện và hợp lý hóa nỗ lực của họ.

Picus Security's [Blue Report 2025](https://hubs.li/Q03HM8Sj0) kéo bức màn để cho thấy phòng thủ an ninh mạng đang trượt dễ dàng như thế nào.

Dựa trên hơn **160 triệu kết quả Breach and Attack Simulation (BAS)**, **Blue Report** năm nay cho thấy hiệu quả phòng ngừa tổng thể giảm từ 69% năm 2024 xuống 62% vào năm 2025. Tuy nhiên phát hiện đáng báo động nhất là **đánh cắp dữ liệu**: khả năng phòng ngừa sụp đổ chỉ còn 3%, giảm từ mức vốn đã không chấp nhận được là **9%** năm ngoái. Điều này để lại các tổ chức bị phơi bày **chính tại giai đoạn** mà các nhóm mã độc tống tiền khai thác nhiều nhất.

Bài học rõ ràng: _giả định không đồng nghĩa với bảo vệ, và những phòng thủ không được xác thực sẽ tiếp tục thất bại khi quan trọng nhất._

Phân tích kết quả, nhanh chóng thấy rằng sẵn sàng đối phó mã độc tống tiền không thể được giả định. Nó phải được chứng minh. Điều đó có nghĩa là liên tục xác thực phòng thủ của tổ chức bạn chống lại cả các họ mã độc tống tiền đã được biết đến lâu lẫn các biến thể mới đang hoạt động ngoài thực tế.

Breach and Attack Simulation cung cấp bằng chứng đó, cho thấy theo thời gian thực liệu các biện pháp bảo vệ có đứng vững hay thất bại.

[![Blue report statistics](https://www.bleepstatic.com/images/news/security/p/picus/blue-report/intro-blog.png)](https://hubs.li/Q03HM8Sj0)

## Tại sao cả mã độc tống tiền đã biết và mới nổi đều quan trọng

Thật không may, đối với mã độc tống tiền, sự quen thuộc thường dẫn đến tự tin sai lầm. Các đội an ninh có thể tin rằng họ được bảo vệ chống lại những chủng lớn tên tuổi, nhưng theo thời gian, nếu để yên, phòng thủ của họ dần suy yếu khi cấu hình trôi dạt và môi trường thay đổi.

Trong khi đó, các kẻ vận hành mã độc tống tiền không ngừng di chuyển. Mã được đóng gói lại, loaders được cập nhật, và các kỹ thuật tránh né được tinh chỉnh để giữ cho các cuộc tấn công không bị phát hiện. Thật không may, những gì hiệu quả với chiến dịch hôm qua thường không còn hiệu quả với nỗ lực đã được cập nhật của hôm nay.

[Blue Report](https://hubs.li/Q03HM8Sj0) năm nay cho thấy điều này một cách rõ ràng.

Trong số 10 chủng mã độc tống tiền dễ vượt phòng thủ nhất, **năm chủng là mới hoặc mới nổi, nhưng chúng vượt qua phòng thủ hiệu quả như những tên tuổi đã tồn tại lâu**.

* **Các họ đã biết vẫn thành công.** [BlackByte (26%)](https://www.picussecurity.com/resource/ttps-used-by-blackbyte-ransomware-targeting-critical-infrastructure) vẫn là mã độc khó ngăn chặn nhất trong năm thứ hai liên tiếp, khai thác các ứng dụng hướng công cộng và đánh cắp dữ liệu trước khi mã hóa. BabLock (34%) tiếp tục gây sức ép lên nạn nhân bằng tống tiền kép, trong khi Maori (41%) tận dụng phương thức phát tán không để lại file và các chiến dịch theo vùng. Sự bền bỉ của chúng cho thấy phòng thủ có thể bị xói mòn dễ dàng trong môi trường thực tế.
* **Các chủng mới nổi tấn công mạnh tương đương.** FAUST (44%), Valak (44%), và Magniber (45%) vượt qua các kiểm soát thông qua sửa đổi registry, payload theo mô-đun, và thực thi theo giai đoạn. Gần một nửa số cuộc tấn công thành công, chứng minh rằng các tên mới nhanh chóng trở nên hiệu quả ngoài thực địa.
* **Các tên đã được khẳng định thích nghi.** BlackKingdom (48%), Black Basta (49%), và Play (50%) né tránh phòng thủ bằng thông tin đăng nhập bị đánh cắp, process hollowing, và thực thi dịch vụ từ xa. Ngay cả sau nhiều năm tài liệu, chúng vẫn khó ngăn chặn.
* **Các kẻ điều hành mã độc tống tiền cấp cao vẫn kiên cường.** AvosLocker chỉ đạt tỷ lệ phòng ngừa 52%, khai thác leo thang quyền hạn và che giấu tinh vi để xâm phạm các lĩnh vực quan trọng mặc dù có các biện pháp phòng thủ được nhắm mục tiêu cụ thể.

Những phát hiện này minh họa một điểm then chốt: **sự khác biệt giữa "đã biết" và "mới nổi" ngày càng trở nên ít ý nghĩa hơn**. _Khi các tổ chức không liên tục kiểm tra phòng thủ của mình, cả các họ đã biết lẫn các chủng mới nổi đều có thể, và cuối cùng sẽ, né được phòng thủ._

![Ransomware threats](https://www.bleepstatic.com/images/news/security/p/picus/blue-report/ransomware-threats.png)

## Những khoảng trống lớn nhất trong phòng thủ

Các nhóm mã độc tống tiền hiếm khi chỉ phụ thuộc vào một chiêu thức duy nhất. Thay vào đó, họ nối nhiều kỹ thuật qua chuỗi tấn công và lợi dụng bộ phòng thủ yếu nhất.

**[Blue Report 2025](https://hubs.li/Q03HM8Sj0)** cho thấy những khoảng trống dai dẳng trong phòng ngừa và phát hiện tiếp tục trao cho kẻ tấn công đúng cơ hội họ tìm kiếm.

* **Phát tán mã độc:** Khả năng phòng ngừa giảm xuống **60%** (từ **71%** năm 2024). Dù đây là một trong các vectơ tấn công lâu đời nhất, loaders và droppers vẫn vượt qua các biện pháp phòng thủ tĩnh.
* **Đường ống phát hiện:** Chỉ **14%** các cuộc tấn công tạo ra cảnh báo, mặc dù **54% được ghi log**. Khoảng cách từ log đến cảnh báo này có thể dễ dàng khiến những người bảo vệ mù trước cả các họ đã biết như BlackByte và các biến thể mới như FAUST và Magniber.
* **[Đánh cắp dữ liệu:](https://www.picussecurity.com/product/data-loss-prevention-dlp-testing)** Hiệu quả trong việc ngăn chặn đánh cắp dữ liệu giảm xuống chỉ còn **3%** vào năm 2025 (từ **9%** năm 2024), là điểm yếu tệ nhất trong mọi vectơ tấn công. Yếu điểm này tiếp tục thúc đẩy sự gia tăng các cuộc tấn công **tống tiền kép**, nơi dữ liệu bị đánh cắp bị rò rỉ để tăng áp lực lên nạn nhân.
* **Bảo vệ endpoint:** Endpoint chặn được **76%** các cuộc tấn công, nhưng di chuyển ngang mạng và leo thang quyền vẫn thành công trong một phần tư các trường hợp. Các họ như Black Basta và Play lợi dụng những điểm yếu này để lan rộng trong mạng bị xâm phạm.

Nhìn chung, mã độc tống tiền thịnh vượng không phải vì kỹ thuật tiên tiến mà vì phòng thủ tiếp tục thất bại ở các điểm then chốt.

**Năm trong số mười họ mã độc tống tiền được nêu trong báo cáo là các chủng đã tồn tại lâu, nhưng chúng vẫn né được phòng thủ hiệu quả như các mối đe dọa mới hoặc [mới nổi](https://www.picussecurity.com/resource/tag/emerging-threat).** Kẻ tấn công không cần đột phá mới, chỉ cần khả năng khai thác những gì đã hỏng.

## [Củng cố phòng thủ mã độc tống tiền trong thời đại tống tiền không cần mã hóa](https://hubs.li/Q03HMp2Q0)

Dựa trên hơn 160M+ mô phỏng tấn công, Picus Blue Report 2025 phơi bày lý do mã độc tống tiền vẫn xuyên thủng phòng thủ — tỷ lệ phòng ngừa giảm xuống 62% và ngăn chặn đánh cắp dữ liệu chỉ còn 3%.

Xem toàn bộ phát hiện và xem cách xác thực liên tục đóng các khoảng trống then chốt.

[Download Now](https://hubs.li/Q03HMp2Q0)

## Cách BAS tăng cường sự sẵn sàng đối phó mã độc tống tiền

Picus [Breach and Attack Simulation (BAS)](https://www.picussecurity.com/breach-and-attack-simulation) giúp thu hẹp khoảng cách giữa những gì các tổ chức _nghĩ_ rằng phòng thủ của họ có thể làm được và cách chúng _thực sự_ hoạt động chống lại mã độc tống tiền.

Không giống như kiểm thử xâm nhập truyền thống, mang tính định kỳ và thủ công, BAS cung cấp các kiểm tra liên tục, tự động cho bạn thấy nơi phòng thủ đứng vững trước các hành vi tấn công thực tế, và nơi chúng không đứng vững, trong môi trường độc đáo và thay đổi của bạn.

**Những lợi ích chính của BAS bao gồm:**

* **Mô phỏng mã độc tống tiền liên tục.** BAS mô phỏng và bắt chước an toàn các TTP của mã độc tống tiền thấy ngoài thực địa, từ xâm nhập ban đầu qua mã hóa và đánh cắp dữ liệu, để chỉ ra chính xác nơi phòng thủ của bạn sụp đổ, trên cả kiểm soát biên và bảo mật endpoint.
* **Xác thực chống lại các họ đã biết và mới nổi.** Picus cập nhật thư viện mối đe dọa BAS hàng ngày với thông tin tình báo về cả mã độc tống tiền đã được thiết lập và các biến thể mới, cho phép các tổ chức thử nghiệm chống lại cùng những họ xuất hiện trong cảnh báo và những họ mới xuất hiện ngoài thực địa.
* **Sửa chữa có thể thực hiện được.** Khi cuộc tấn công thành công trong mô phỏng, BAS cung cấp hướng dẫn khắc phục thực tế, cả theo nhà cung cấp và độc lập nhà cung cấp, để người bảo vệ biết chính xác điều gì cần điều chỉnh.
* **Bằng chứng về sự sẵn sàng.** BAS tạo ra dữ liệu đo được về khả năng chống chịu với mã độc tống tiền, bao gồm tỷ lệ phòng ngừa, phạm vi phát hiện, và trạng thái giảm thiểu, cung cấp cho các đội an ninh dữ liệu cụ thể họ có thể trình bày với lãnh đạo và kiểm toán viên.

## Thu hẹp khoảng cách sẵn sàng

Một trong những niềm tin nguy hiểm nhất trong việc sẵn sàng đối phó mã độc tống tiền là cho rằng phòng thủ của bạn đang hoạt động vì chúng đã hoạt động cho đến thời điểm này, hoặc vì bạn đã triển khai những sản phẩm "đúng".

Blue Report 2025 cho thấy hai giả định này có thể gây hiểu lầm như thế nào: **gần 50%** các nỗ lực mã độc tống tiền đã vượt qua phòng thủ, và chỉ **14%** kích hoạt cảnh báo.

BAS biến các giả định thành bằng chứng bằng cách trả lời những câu hỏi quan trọng nhất:

* Hệ thống DLP của bạn có thực sự ngăn được dữ liệu nhạy cảm rời khỏi mạng không?
* Nếu mã độc tống tiền vượt qua các kiểm soát endpoint, SIEM của bạn có đưa ra cảnh báo kịp thời không?
* Cổng thư điện tử đã được tinh chỉnh đủ để chặn payload phishing dùng bởi BabLock hoặc Play không?
* Các họ mới hơn như FAUST hoặc Magniber có lọt qua mà không bị phát hiện không?

Với BAS, các đội an ninh không phải đoán. Họ biết.

## Kết luận

Cuối cùng, **Blue Report 2025** làm rõ một điều: mã độc tống tiền thịnh vượng không phải vì kẻ tấn công phát minh lại cách chơi, mà vì phòng thủ hiếm khi được kiểm tra trong thực tế. Những điểm yếu an ninh giống nhau lặp lại năm này sang năm khác, với phòng ngừa sụt giảm, phát hiện tụt hậu, và đánh cắp dữ liệu hầu như không bị kiểm soát.

**Breach and Attack Simulation** là mảnh ghép còn thiếu. Bằng cách bắt chước an toàn các cuộc tấn công mã độc tống tiền đầu-cuối, bao gồm xâm nhập ban đầu, truy cập thông tin đăng nhập, di chuyển ngang, và đánh cắp dữ liệu, BAS chỉ ra chính xác nơi phòng thủ của bạn đang và không đang hoạt động và xác nhận liệu các bản vá có đang giữ vững. Nó chuyển sự sẵn sàng từ tin tưởng và giả định sang chứng minh, cung cấp cho người bảo vệ thứ họ có thể đo lường, cải thiện, và trình bày hàng ngày.

Sự sẵn sàng đối phó mã độc tống tiền đã đi quá xa câu hỏi "Chúng ta có được bảo vệ không?". Đó là về việc liên tục chứng minh bằng chứng về độ bền, và BAS là cách duy nhất bền vững để đạt được điều đó.

_**Download the [Blue Report 2025](https://hubs.li/Q03HM8Sj0)** để có bức tranh toàn diện, từ mã độc tống tiền và đánh cắp dữ liệu đến hiệu suất theo ngành, khác biệt theo vùng, khoảng trống chiến thuật và kỹ thuật MITRE ATT&CK, và các lỗ hổng mà kẻ tấn công đang khai thác ngay bây giờ. Xem nơi phòng thủ đang trượt, và tại sao xác thực liên tục là con đường đi tới._ 

_Sponsored and written by [Picus Security](https://hubs.li/Q03HMp2Q0)._