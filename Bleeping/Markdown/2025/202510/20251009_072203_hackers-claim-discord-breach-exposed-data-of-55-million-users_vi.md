# Tin tặc tuyên bố vụ rò rỉ Discord làm lộ dữ liệu của 5,5 triệu người dùng

![Discord](https://www.bleepstatic.com/content/hl-images/2021/03/05/discord-header-l.jpg)

Discord cho biết họ sẽ không trả tiền cho những kẻ đe dọa tuyên bố đã đánh cắp dữ liệu của 5,5 triệu người dùng duy nhất từ instance hệ thống hỗ trợ Zendesk của công ty, bao gồm ảnh giấy tờ tùy thân của chính phủ và thông tin thanh toán một phần cho một số người.

Công ty cũng phản bác các tuyên bố rằng 2,1 triệu ảnh giấy tờ tùy thân của chính phủ đã bị tiết lộ trong vụ rò rỉ, khẳng định rằng khoảng 70.000 người dùng có ảnh giấy tờ tùy thân bị phơi bày.

Trong khi những kẻ tấn công khẳng định vụ rò rỉ xảy ra thông qua instance Zendesk của Discord, công ty chưa xác nhận điều này và chỉ mô tả rằng sự việc liên quan đến một dịch vụ bên thứ ba được sử dụng cho hỗ trợ khách hàng.

"Đầu tiên, như đã nêu trong bài đăng trên blog của chúng tôi, đây không phải là một vụ rò rỉ của Discord, mà là của một dịch vụ bên thứ ba mà chúng tôi sử dụng để hỗ trợ nỗ lực dịch vụ khách hàng của mình," Discord nói với BleepingComputer trong một tuyên bố.

"Thứ hai, các con số đang được chia sẻ là không chính xác và là một phần của nỗ lực tống tiền nhằm lấy tiền từ Discord. Trong số các tài khoản bị ảnh hưởng trên toàn cầu, chúng tôi đã xác định khoảng 70.000 người dùng có thể đã có ảnh giấy tờ tùy thân của chính phủ bị phơi bày, mà nhà cung cấp dịch vụ của chúng tôi đã sử dụng để xem xét các kháng nghị liên quan độ tuổi."

"Thứ ba, chúng tôi sẽ không thưởng cho những người chịu trách nhiệm về hành vi bất hợp pháp của họ."

Trong cuộc trao đổi với những kẻ tấn công, BleepingComputer được thông báo rằng Discord không minh bạch về mức độ nghiêm trọng của vụ rò rỉ, khẳng định rằng họ đã đánh cắp 1,6 TB dữ liệu từ instance Zendesk của công ty.

Theo kẻ đe dọa, họ đã truy cập vào instance Zendesk của Discord trong 58 giờ bắt đầu từ ngày 20 tháng 9 năm 2025. Tuy nhiên, những kẻ tấn công cho biết vụ rò rỉ không phát sinh từ một lỗ hổng hay vi phạm Zendesk mà là do một tài khoản bị xâm phạm thuộc về một nhân viên hỗ trợ được thuê thông qua một nhà cung cấp BPO (business process outsourcing) mà Discord sử dụng.

Vì nhiều công ty đã thuê ngoài bộ phận hỗ trợ và help desk CNTT cho các BPO, những nhà cung cấp này đã trở thành mục tiêu phổ biến để kẻ tấn công truy cập vào các môi trường khách hàng hạ nguồn.

Các tin tặc cho biết instance Zendesk nội bộ của Discord đã cho phép họ truy cập vào một ứng dụng hỗ trợ, được biết đến với tên Zenbar, cho phép họ thực hiện các tác vụ liên quan đến hỗ trợ, chẳng hạn như vô hiệu hóa xác thực đa yếu tố và tra cứu số điện thoại cũng như địa chỉ email của người dùng.

Sử dụng quyền truy cập vào nền tảng hỗ trợ của Discord, những kẻ tấn công tuyên bố đã đánh cắp 1,6 terabyte dữ liệu, bao gồm khoảng 1,5 TB tệp đính kèm của ticket và hơn 100 GB bản ghi hội thoại ticket.

Những kẻ tấn công nói rằng điều này bao gồm khoảng 8,4 triệu ticket ảnh hưởng đến 5,5 triệu người dùng duy nhất, và rằng khoảng 580.000 người dùng chứa một số loại thông tin thanh toán.

Các tác nhân đe dọa tự thừa nhận với BleepingComputer rằng họ không chắc có bao nhiêu giấy tờ tùy thân của chính phủ bị đánh cắp, nhưng họ tin rằng nhiều hơn 70.000, vì họ cho biết có khoảng 521.000 ticket xác minh độ tuổi.

Các tác nhân đe dọa cũng chia sẻ một mẫu dữ liệu người dùng bị đánh cắp, có thể bao gồm nhiều loại thông tin khác nhau, bao gồm địa chỉ email, tên người dùng và ID Discord, số điện thoại, thông tin thanh toán một phần, ngày sinh, thông tin liên quan tới xác thực đa yếu tố, mức độ hoạt động đáng ngờ và các thông tin nội bộ khác.

Thông tin thanh toán của một số người dùng được cho là có thể truy xuất thông qua các tích hợp Zendesk với hệ thống nội bộ của Discord. Các tích hợp này được cho là đã cho phép những kẻ tấn công thực hiện hàng triệu truy vấn API tới cơ sở dữ liệu nội bộ của Discord thông qua nền tảng Zendesk và truy xuất thêm thông tin.

BleepingComputer không thể độc lập xác minh các tuyên bố của tin tặc hoặc tính xác thực của các mẫu dữ liệu được cung cấp.

Nhóm tin tặc cho biết họ đã yêu cầu 5 triệu đô la tiền chuộc, sau đó giảm xuống còn 3,5 triệu đô la, và đã tiến hành các cuộc đàm phán riêng với Discord trong khoảng thời gian từ 25 tháng 9 đến 2 tháng 10.

Sau khi Discord ngừng liên lạc và phát hành tuyên bố công khai về sự cố, các kẻ tấn công nói rằng họ "cực kỳ tức giận" và có kế hoạch công khai rò rỉ dữ liệu nếu yêu cầu tống tiền không được đáp ứng.

BleepingComputer đã liên hệ với Discord với các câu hỏi bổ sung về những tuyên bố này, bao gồm lý do tại sao họ giữ ảnh giấy tờ tùy thân sau khi hoàn tất xác minh độ tuổi, nhưng không nhận được câu trả lời ngoài tuyên bố nêu trên.