# Microsoft sửa lỗi Exchange Online đánh dấu email Gmail là thư rác

![Exchange Online](https://www.bleepstatic.com/content/hl-images/2025/05/02/Exchange_Online.jpg)

Microsoft đã khắc phục sự cố với một mô hình machine learning (ML) đã vô tình đánh dấu các email từ tài khoản Gmail là thư rác trong Exchange Online.

Được theo dõi với mã [EX1064599](http://admin.microsoft.com/#/MessageCenter/:/messages/EX1064599) trong trung tâm quản trị Microsoft 365, sự cố bắt đầu ảnh hưởng đến người dùng vào ngày 25 tháng 4 lúc 09:24 UTC, tự động di chuyển các email bị đánh dấu sai là nguy hiểm vào thư mục thư rác.

"Chúng tôi đã xác định rằng mô hình machine learning (ML) của chúng tôi, bảo vệ Exchange Online khỏi các tin nhắn email rủi ro, đang xác định sai các tin nhắn email hợp lệ là thư rác do sự tương đồng của chúng với các tin nhắn email được sử dụng trong các cuộc tấn công thư rác, điều này dẫn đến các tác động," công ty giải thích khi họ thừa nhận lỗi mô hình ML.

Trong một cập nhật cuối cùng cho báo cáo sự cố được thêm vào ngày 1 tháng 5 lúc 16:31 UTC, Microsoft cho biết họ đã khôi phục thành công mô hình ML lỗi thành phiên bản trước đó hoạt động ổn định, giảm thiểu vấn đề dương tính giả. Họ cũng cho biết rằng các quản trị viên và người dùng cũng có thể đã tạo các quy tắc cho phép tùy chỉnh để đảm bảo rằng các tin nhắn Gmail không bị gửi vào thư mục thư rác trong khi dịch vụ đang bị ảnh hưởng.

"Sau một thời gian theo dõi, chúng tôi đã xác nhận thông qua số liệu sức khỏe dịch vụ rằng việc hoàn thành việc khôi phục về mô hình ML trước đây đã thành công trong việc khắc phục tác động," Microsoft cho biết thêm. "Chúng tôi đang tiếp tục điều tra các cơ hội để cải thiện quy trình phát hiện ML của chúng tôi nhằm giảm thiểu các phát hiện dương tính giả và ngăn chặn tác động tương tự trong tương lai."

Trong khi Redmond chưa chia sẻ các khu vực hoặc số lượng khách hàng bị ảnh hưởng, sự cố dịch vụ này đã được gán nhãn như một sự cố, điều này thường liên quan đến ảnh hưởng rõ rệt đến người dùng.

Microsoft đã xử lý các vấn đề tương tự kể từ đầu năm, dẫn đến các email bị đánh dấu sai là thư rác hoặc bị cách ly. Ví dụ, tuần trước, công ty đã giảm thiểu một sự cố machine learning khác mà [vô tình đánh dấu các email của Adobe](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-machine-learning-bug-flagging-adobe-emails-as-spam/) trong Exchange Online là thư rác.

Vào tháng 3, họ đã giải quyết [một trường hợp dương tính giả khác trong Exchange Online](https://www.bleepingcomputer.com/news/microsoft/microsoft-exchange-online-bug-mistakenly-quarantines-user-emails/), khiến các hệ thống chống thư rác cách ly một số email của người dùng không chính xác.

Vào tháng 10 năm 2023, họ cũng đã phải [vô hiệu hóa một quy tắc chống thư rác không tốt](https://www.bleepingcomputer.com/news/microsoft/microsoft-disables-bad-spam-rule-flagging-all-sent-emails-as-junk/) làm ngập hộp thư của quản trị viên Microsoft 365 với các bản sao bcc của các email gửi đi bị đánh dấu sai là thư rác, trong khi vào tháng 8 năm 2024, họ [giảm thiểu một lỗi Exchange Online](https://www.bleepingcomputer.com/news/microsoft/microsoft-exchange-online-mistakenly-tags-emails-as-malware/) đánh dấu các email chứa hình ảnh là độc hại và tự động cách ly chúng.