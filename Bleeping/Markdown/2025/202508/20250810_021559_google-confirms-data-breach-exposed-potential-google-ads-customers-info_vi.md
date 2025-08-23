# Google xác nhận việc rò rỉ dữ liệu làm lộ thông tin khách hàng tiềm năng của Google Ads

![Google Ads](https://www.bleepstatic.com/content/hl-images/2025/01/15/Google-Ads.jpg)

Google đã xác nhận rằng một [vụ rò rỉ dữ liệu được tiết lộ gần đây](https://www.bleepingcomputer.com/news/security/google-suffers-data-breach-in-ongoing-salesforce-data-theft-attacks/) của một trong các phiên bản Salesforce CRM của họ đã liên quan đến thông tin của các khách hàng tiềm năng của Google Ads.

"Chúng tôi viết thư này để thông báo cho bạn về một sự kiện đã ảnh hưởng đến một bộ dữ liệu hạn chế trong một trong các phiên bản Salesforce doanh nghiệp của Google được sử dụng để liên lạc với các khách hàng tiềm năng của Ads," nội dung thông báo rò rỉ dữ liệu được chia sẻ với BleepingComputer cho biết.

"Các hồ sơ của chúng tôi cho thấy thông tin liên lạc doanh nghiệp cơ bản và các ghi chú liên quan đã bị ảnh hưởng bởi sự kiện này."

Google cho biết thông tin bị lộ bao gồm tên doanh nghiệp, số điện thoại và "các ghi chú liên quan" cho một đại diện bán hàng của Google để liên hệ lại với họ.

Công ty cho biết thông tin thanh toán không bị lộ và không có tác động nào đến dữ liệu của Ads trong Google Ads Account, Merchant Center, Google Analytics và các sản phẩm Ads khác.

Vụ rò rỉ được thực hiện bởi các tác nhân đe dọa được gọi là ShinyHunters, những người đứng sau một làn sóng tấn công trộm cắp dữ liệu đang diễn ra nhắm vào khách hàng Salesforce.

Trong khi Google không cho biết có bao nhiêu cá nhân bị ảnh hưởng, ShinyHunters cho biết thông tin bị đánh cắp chứa khoảng 2,55 triệu hồ sơ dữ liệu. Không rõ liệu có các bản sao trong các hồ sơ này hay không.

ShinyHunters còn cho biết với BleepingComputer rằng họ cũng đang làm việc với các tác nhân đe dọa liên quan đến "Scattered Spider, những người chịu trách nhiệm chính trong việc truy cập ban đầu vào hệ thống mục tiêu.

"Như chúng tôi đã nói đi nói lại, ShinyHunters và Scattered Spider là một," ShinyHunters đã nói với BleepingComputer.

"Họ cung cấp cho chúng tôi quyền truy cập ban đầu và chúng tôi thực hiện việc dump dữ liệu và xuất xứ các phiên bản Salesforce CRM. Giống như chúng tôi đã làm với Snowflake."

Các tác nhân đe dọa hiện đang tự gọi mình là "Sp1d3rHunters," để minh họa nhóm chồng chéo những người tham gia vào các cuộc tấn công này.

Như một phần của các cuộc tấn công này, các tác nhân đe dọa thực hiện các cuộc tấn công kỹ thuật xã hội chống lại nhân viên để có được quyền truy cập vào thông tin xác thực hoặc đánh lừa họ liên kết một phiên bản độc hại của ứng dụng Data Loader OAuth của Salesforce vào môi trường Salesforce của mục tiêu.

Các tác nhân sau đó tải toàn bộ cơ sở dữ liệu Salesforce xuống và tống tiền các công ty qua email, đe dọa sẽ công khai dữ liệu bị đánh cắp nếu không thanh toán tiền chuộc.

Các cuộc tấn công Salesforce này đã [được báo cáo lần đầu bởi Nhóm Tình báo Đe dọa của Google (GTIG)](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) vào tháng Sáu, với công ty gặp phải số phận tương tự một tháng sau đó.

Databreaches.net đã báo cáo rằng các tác nhân đe dọa đã [gửi một yêu cầu tống tiền tới Google](http://databreaches.net/2025/08/08/shinyhunters-sent-google-an-extortion-demand-shiny-comments-on-current-activities/). Sau khi công bố câu chuyện, ShinyHunters đã nói với BleepingComputer rằng họ đã yêu cầu 20 Bitcoins, hoặc khoảng 2,3 triệu đô la, từ Google để không tiết lộ dữ liệu.

"Tôi không quan tâm đến việc tống tiền Google, tôi chỉ gửi cho họ một email giả mạo vì lý do vui vẻ," tác nhân đe dọa nói.

ShinyHunters cho biết kể từ đó họ đã chuyển sang một công cụ tùy chỉnh mới giúp dễ dàng và nhanh chóng hơn trong việc đánh cắp dữ liệu từ các phiên bản Salesforce đã bị xâm phạm.

Trong một bản cập nhật, [Google gần đây đã thừa nhận](https://cloud.google.com/blog/topics/threat-intelligence/voice-phishing-data-extortion#:~:text=UNC6040%20%28Evolving%20TTPs%29) công cụ mới, cho biết rằng họ đã thấy các đoạn mã Python được sử dụng trong các cuộc tấn công thay vì Data Loader của Salesforce.

_Cập nhật 8/9/25: Đã thêm thông tin thêm về yêu cầu tống tiền._