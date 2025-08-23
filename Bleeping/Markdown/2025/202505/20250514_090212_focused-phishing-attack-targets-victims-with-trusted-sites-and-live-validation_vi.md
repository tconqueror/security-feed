# Lừa đảo tập trung: Tấn công nhắm đến nạn nhân thông qua các trang web đáng tin cậy và xác thực trực tiếp

![Phishing Header](https://www.bleepstatic.com/content/posts/2025/05/13/Keep-Aware-Cover-Photo.jpg)

Nhóm nghiên cứu mối đe dọa Keep Aware gần đây đã quan sát một sự cố lừa đảo liên quan đến việc tận dụng cơ sở hạ tầng hợp pháp, xác thực email chính xác và các kỹ thuật giao hàng lẩn tránh.

Cuộc tấn công này minh họa việc lạm dụng các miền đáng tin cậy, thực hành xác thực email lừa đảo phía máy chủ và nhu cầu cấp bách về việc bảo vệ lừa đảo không ngày n нhận trên trình duyệt.

## Điều gì đã xảy ra?

Trong môi trường trực tiếp, [giải pháp bảo mật trình duyệt của Keep Aware](https://keepaware.com/product?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=validated%5Fphishing%5Fmay) đã được cấu hình ở chế độ tắt tiếng để ghi lại tất cả hành vi của người dùng và các chỉ báo mối đe dọa mà không làm gián đoạn phiên.

Điều này cho phép nhóm bảo mật có tầm nhìn đầy đủ vào mọi giai đoạn của nỗ lực lừa đảo khi nó diễn ra, điều này cho phép đánh giá rõ ràng về các vector tấn công, hành động của người dùng và độ tin cậy phát hiện.

## Xác định đánh cắp thông tin xác thực

Trong khi xem xét các phát hiện được quản lý, nhóm nghiên cứu đã quan sát thấy các tín hiệu lừa đảo liên quan đến xác thực kích hoạt ở chế độ im lặng. Điều này cho thấy rằng một nhân viên đã nhập thông tin xác thực trên một trang web nghi ngờ.

Bởi vì trình duyệt đã được cấu hình cho hoạt động chỉ hiển thị, nhóm bảo mật đã có thể quan sát toàn bộ chuỗi chi tiết của nỗ lực đánh cắp thông tin xác thực, thấy được những chiến thuật độc đáo của kẻ tấn công.

Sử dụng cuộc điều tra do tiện ích mở rộng bảo mật trình duyệt của Keep Aware tạo ra, nhóm đã đánh giá nhanh chóng cuộc tấn công lừa đảo chuỗi, xác nhận việc nhập thông tin xác thực và ngay lập tức thực hiện các bước khắc phục, bao gồm đặt lại mật khẩu của người dùng và xem xét bất kỳ hoạt động tài khoản hoặc đăng nhập bất thường nào.

![Screenshot of the chain of redirects in the Keep Aware platform before a threat flagged the suspicious credential input attempt.](https://www.bleepstatic.com/images/news/security/k/keepaware/focused-phishing/group-137.png)

**Hình chụp màn hình của chuỗi chuyển hướng trong nền tảng Keep Aware trước khi một mối đe dọa đánh dấu nỗ lực nhập thông tin xác thực đáng ngờ.**

Bằng cách kích hoạt các biện pháp bảo vệ mặc định của Keep Aware, loại tương tác này hoàn toàn bị chặn. Và trong khi email lừa đảo tự nó không được quan sát trực tiếp, các dữ liệu cho thấy một hiểu biết chính: không có hoạt động trình duyệt nào ngay trước khi truy cập các trang lừa đảo.

Điều này cho thấy người dùng đã nhấp vào một liên kết từ bên ngoài môi trường trình duyệt, nhiều khả năng từ một ứng dụng email, chẳng hạn như Outlook.

Đây là một tình huống phổ biến: ngay cả khi lừa đảo bắt đầu từ hộp thư đến hoặc một nền tảng nhắn tin, cuộc tấn công tự nó gần như luôn diễn ra trong trình duyệt. Hiện nay, trình duyệt là nơi mà niềm tin dễ dàng bị lạm dụng, các kịch bản lẩn trốn được thực hiện sẵn sàng, và thông tin xác thực cuối cùng được thu thập.

Trong trường hợp này, nhân viên đã nhấp vào một liên kết đến một trang web hợp pháp lưu trữ một trang độc hại.

## [Bảo vệ lừa đảo trình duyệt với Keep Aware](https://keepaware.com/request-a-demo?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=validated%5Fphishing%5Fmay)

Keep Aware ngăn chặn các cuộc tấn công lừa đảo trong thời gian thực nơi chúng bắt đầu: bên trong trình duyệt. Bằng cách phân tích hành vi của người dùng, các form gửi dữ liệu và ngữ cảnh trang web, không chỉ URL,

Keep Aware loại bỏ các mối đe dọa trước khi thông tin xác thực rời khỏi trang. Trang bị cho đội ngũ bảo mật của bạn với khả năng hiển thị chính xác, thực thi chính sách và phản ứng với mối đe dọa ngay lập tức từ bên trong các trình duyệt web hiện có trong tổ chức của bạn.

[Yêu cầu một bản demo](https://keepaware.com/request-a-demo?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=validated%5Fphishing%5Fmay)

## Tổng quan về chiến dịch/cuộc tấn công

### 1) Lưu trữ trên một miền hợp pháp

Nhân viên bị nhắm mục tiêu đã truy cập vào một miền hợp pháp, có tuổi đời 9 năm với uy tín sạch sẽ và sự hiện diện mạnh mẽ trên internet để bán lều. Tuy nhiên, miền “đáng tin cậy” này đã bị xâm phạm để lưu trữ một trang form độc hại trên đường dẫn tệp /memo/home.html.

Upon visiting the link, the user was presented with a message claiming a “Confidential Document” had been shared with them, urging them to input their email in order to download the payment PDF.

Đây là những lời kêu gọi xã hội mà chúng tôi thấy thường xuyên—các cụm từ được thiết kế để khiến người dùng nhấp chuột vào liên kết và cung cấp thông tin xác thực nhằm có được quyền truy cập vào một tài liệu kinh doanh giả định.

![Screenshot of a malicious page hosted on a legitimate domain used for email validation](https://www.bleepstatic.com/images/news/security/k/keepaware/focused-phishing/01-screenshot.png)

**Hình chụp màn hình của một trang độc hại được lưu trữ trên một miền hợp pháp được sử dụng cho xác thực email**

#### Lẩn tránh cơ bản: JavaScript chống phân tích

Trang độc hại này bao gồm các biện pháp bảo vệ chống phân tích cơ bản. Nó vô hiệu hóa menu ngữ cảnh nhấp chuột phải và chặn các tổ hợp phím phổ biến mà các nhà phân tích bảo mật hoặc người dùng internet tò mò có thể sử dụng để kiểm tra hoặc lưu trang.

**Đoạn mã JavaScript từ trang độc hại với các biện pháp chống phân tích cơ bản**

Những kỹ thuật đơn giản này được sử dụng rộng rãi để cản trở nỗ lực phân tích từ việc xem mã trang hoặc các hành vi nền.

#### Mã xử lý form

Ngoài các cơ chế chống phân tích, cơ sở hạ tầng lừa đảo này bao gồm logic để xử lý động việc nhập địa chỉ email tùy thuộc vào cách mà nạn nhân đến trang.

#### Tự động điền bằng email của nạn nhân

Nếu liên kết lừa đảo chứa địa chỉ email của nạn nhân trong phần neo của URL (sau ký hiệu “#”), thì mã JavaScript sẽ tự động trích xuất và chèn email đó vào form. Điều này giảm một bước cho nạn nhân, loại bỏ sự cản trở khỏi quá trình và có thể tăng độ tin cậy và tỷ lệ thành công.

**Đoạn mã JavaScript mà sẽ trích xuất địa chỉ email của mục tiêu từ phần neo của URL, nếu có.**

Kỹ thuật tự động điền này đồng nghĩa với việc các email lừa đảo bao gồm các liên kết cụ thể cho mục tiêu, chẳng hạn như: compromised.domain.com/file/path?#victim_email@example.com

Các kỹ thuật tương tự đã được thấy trước đây, như trong một [bài viết gần đây](https://keepaware.com/blog/svg-phishing-email-attachment-a-recent-targeted-campaign?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=validated%5Fphishing%5Fmay), nơi một SVG độc hại được đính kèm trong một email lừa đảo đã sử dụng JavaScript để thêm email của nạn nhân vào một URL độc hại và chuyển hướng trình duyệt.

Các liên kết cụ thể cho mục tiêu mà tự động điền trình duyệt giả mạo phục vụ hai mục đích:

* Để theo dõi người dùng nào nhấp vào các liên kết lừa đảo;
* Để đơn giản hóa quá trình lừa đảo.

#### Logic gửi email

Nếu một địa chỉ email không có mặt trong phần neo của URL, thì form chờ nạn nhân nhập email của mình và gửi đi.

Sau khi gửi form, hai điều xảy ra:

1. **Chuyển hướng đến trang web độc hại:** Trang chuyển hướng tab của người dùng đến một URL khác, một miền phụ độc hại .workers.dev với email trong tham số truy vấn (?ref=<email>).  
**Đoạn mã JavaScript cho thấy gửi email của nạn nhân đến miền phụ .workers.dev**
2. **Email được gửi đến điểm cuối API:** Đồng thời, email và thời gian của người dùng được gửi đến một điểm cuối API.  
**Đoạn mã JavaScript gửi yêu cầu POST với thông tin nạn nhân đến một điểm cuối API**

Cơ chế gửi này báo hiệu một cơ sở hạ tầng lừa đảo tiên tiến hơn, khả năng xác thực nạn nhân trong thời gian thực và điều chỉnh những gì họ thấy tiếp theo.

## 2) “Một bước nữa trước khi bạn tiếp tục”: Sử dụng CAPTCHA

Sau khi gửi một email và trước khi tiến đến trang lừa đảo cuối cùng, người dùng đã được hướng dẫn đến một trang web độc hại khác và bị thách thức bằng một CAPTCHA của Cloudflare.

**Hình chụp màn hình của CAPTCHA trên trang web độc hại**

Chiến thuật này không phải là điều bất thường. CAPTCHA thực (không chỉ các CAPTCHA giả) thường được các tác nhân lừa đảo sử dụng để:

* Ngăn chặn bots và các trình quét tự động phân tích trang lừa đảo cuối cùng
* Tránh bị phát hiện bởi các công cụ quét URL truyền thống
* Tăng độ tin cậy cho quá trình

CAPTCHA có thể giúp các kẻ tấn công tránh các công cụ và giữ cho sự lừa dối tiếp diễn lâu hơn.

# 3) Trang lừa đảo tùy chỉnh, được xác thực bằng email

Sau khi vượt qua CAPTCHA, trang lừa đảo đôi khi chuyển sang một mẫu đăng nhập Microsoft giả mạo. Nhưng không phải lúc nào cũng vậy.

Điều gì kích hoạt tải trọng lừa đảo phụ thuộc vào email mà người dùng nhập.

**Email cá nhân (ví dụ: @gmail.com):** Trang hiển thị một màn hình trống.

**Trang lừa đảo tải lên màn hình trống khi một email cá nhân được cung cấp.**

**Email doanh nghiệp (email hợp lệ, nhưng có thể không có trong danh sách của kẻ tấn công):** Trang hiển thị một trang đăng nhập Microsoft cơ bản, không có tùy chỉnh.

**Trang lừa đảo tải lên một trang đăng nhập Microsoft cơ bản khi một địa chỉ email không phải cá nhân đã được cung cấp.**

**Địa chỉ email đã nhắm mục tiêu (email doanh nghiệp hợp lệ và có trong danh sách của kẻ tấn công):** Trang lừa đảo hiển thị một trang đăng nhập Microsoft giả mạo được tùy chỉnh với logo công ty của nạn nhân, nền được thương hiệu và tham chiếu đến chữ cái giúp đỡ của tổ chức.

**Trang lừa đảo tải lên trang đăng nhập Microsoft tùy chỉnh khi một địa chỉ email có trong danh sách của kẻ tấn công đã được cung cấp.**

Hành vi này gợi ý rằng backend của kẻ tấn công thực hiện xác thực email phía máy chủ. Dựa vào việc liệu email có nằm trong danh sách nhắm mục tiêu hay không hoặc có được coi là email cá nhân, cơ sở hạ tầng lừa đảo chọn lọc một tải trọng gửi đi.

## Lừa đảo được xác thực chính xác, phía máy chủ

Kỹ thuật này, trong đó kẻ tấn công xác thực một địa chỉ email trong thời gian thực để đảm bảo chỉ những mục tiêu đã định hoặc những mục tiêu có giá trị cao hơn nhận được trang lừa đảo cuối cùng, được gọi là “Lừa đảo Xác thực Chính xác”.

Kỹ thuật xác thực email được thực hiện qua mã phía khách hàng hoặc các cuộc gọi API. Trong trường hợp này, việc xác thực email có vẻ xảy ra ở phía máy chủ, không phải bên phía khách hàng qua JavaScript.

Email đã cung cấp được gửi đến một API backend, mà xác định những gì sẽ xảy ra tiếp theo, làm cho logic lừa đảo càng khó phát hiện qua phân tích tĩnh hoặc phía khách hàng đơn thuần.

## Đánh bại lừa đảo chính xác với phát hiện thời gian thực, không mất ngày

Bất chấp độ tinh vi và logic phía máy chủ, mục tiêu cuối cùng vẫn đơn giản: đánh cắp thông tin xác thực. Bất kể cách nào xảy ra việc xác thực email, người dùng mục tiêu cuối cùng sẽ luôn rơi vào một trang độc hại được thiết kế để đánh cắp thông tin xác thực.

Nếu ngăn xếp bảo mật của bạn có thể chặn các trang lừa đảo, dù là không ngày hay không, đã được xác thực chính xác hay không, và trước khi người dùng nhập mật khẩu của họ, kẻ tấn công sẽ rời đi tay không.

Để phòng chống chống lại loại lừa đảo tiên tiến, nhắm mục tiêu này:

* Đảm bảo rằng ngăn xếp bảo mật của bạn có thể phát hiện và chặn các trang lừa đảo ngay cả trên các miền đáng tin cậy
* Đầu tư vào các công cụ nhận biết sự mạo danh của các nền tảng doanh nghiệp hợp pháp mà tổ chức của bạn sử dụng (ví dụ: Microsoft 365, Okta, Google Workspace)
* Đảm bảo rằng nhân viên của bạn có thể bảo vệ ở cấp độ trình duyệt theo thời gian thực, không chỉ lọc email

## Theo kịp với các cuộc tấn công đang phát triển không ngừng

Lừa đảo tiếp tục phát triển—tận dụng cơ sở hạ tầng hợp pháp, xác thực email chính xác và các kỹ thuật giao hàng lẩn tránh. Nhưng trong khi các kỹ thuật dường như ngày càng tinh vi, giải pháp vẫn rõ ràng: bảo vệ trong trình duyệt theo thời gian thực là rất quan trọng.

Ngăn ngừa người dùng tương tác với các trang đăng nhập lừa dối là cách chắc chắn nhất để dừng lừa đảo ngay từ đầu, bất kể bất kỳ logic xác thực tinh vi nào.

**Để tìm hiểu thêm về cách mà Keep Aware có thể giúp ngăn chặn các cuộc tấn công lừa đảo trong trình duyệt, [yêu cầu một buổi demo cá nhân hóa](https://keepaware.com/request-a-demo?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=validated%5Fphishing%5Fmay) với một thành viên trong nhóm.**

_Được tài trợ và viết bởi [Keep Aware](https://keepaware.com/request-a-demo?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=validated%5Fphishing%5Fmay)._