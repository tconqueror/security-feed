# Iberia tiết lộ rò rỉ dữ liệu khách hàng sau khi nhà cung cấp bị xâm phạm an ninh

![Iberia](https://www.bleepstatic.com/content/hl-images/2025/11/23/plane-resized.jpg)

Hãng hàng không quốc gia Tây Ban Nha Iberia đã bắt đầu thông báo cho khách hàng về một sự cố an ninh dữ liệu phát sinh từ việc một trong các nhà cung cấp của hãng bị xâm phạm.

Việc công bố này được đưa ra vài ngày sau khi một tội phạm mạng tuyên bố trên các diễn đàn hacker rằng họ đã rò rỉ 77 GB dữ liệu được cho là lấy từ hãng hàng không.

## Dữ liệu khách hàng bị ảnh hưởng

Iberia, hãng hàng không lớn nhất Tây Ban Nha và là một phần của IAG (International Airlines Group), cho biết việc truy cập trái phép vào các hệ thống của một nhà cung cấp đã dẫn đến việc phơi bày một số thông tin khách hàng.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Theo một [email được xem bởi](https://x.com/H4ckmanac/status/1992477567526621446) nền tảng tình báo mối đe dọa Hackmanac, dữ liệu bị xâm phạm có thể bao gồm:

1. Họ và tên khách hàng
2. Địa chỉ email
3. Số nhận dạng thẻ khách hàng thân thiết (Iberia Club)

Hãng cho biết thông tin đăng nhập tài khoản Iberia và mật khẩu của khách hàng không bị xâm phạm, cũng như không có thông tin ngân hàng hay thẻ thanh toán nào bị truy cập.

![](https://www.bleepstatic.com/images/news/u/1164866/2025/Nov/iberia-data-leak/email-notice.jpeg)

**Thông báo sự cố an ninh của Iberia được gửi qua email tới khách hàng** (Hackmanac trên X)

“Ngay khi chúng tôi biết về sự cố, chúng tôi đã kích hoạt các giao thức và thủ tục an ninh của mình và triển khai tất cả các biện pháp kỹ thuật và tổ chức cần thiết để kìm hãm nó, giảm thiểu tác hại và ngăn ngừa tái diễn,” thông báo an ninh được gửi bằng tiếng Tây Ban Nha nêu.

Iberia cho biết họ đã bổ sung các biện pháp bảo vệ cho địa chỉ email liên kết với tài khoản khách hàng, hiện yêu cầu mã xác minh trước khi có thể thực hiện bất kỳ thay đổi nào.

Hãng cũng đang giám sát hệ thống để phát hiện hoạt động đáng ngờ. Các cơ quan chức năng liên quan đã được thông báo, và cuộc điều tra đang tiếp tục phối hợp với nhà cung cấp có liên quan.

“Tính đến ngày gửi thông báo này, chúng tôi chưa có bằng chứng về bất kỳ việc sử dụng gian lận nào đối với dữ liệu này. Trong mọi trường hợp, chúng tôi khuyên bạn hãy chú ý đến bất kỳ thông tin liên lạc đáng ngờ nào bạn có thể nhận được để tránh những vấn đề tiềm ẩn mà chúng có thể gây ra. Chúng tôi khuyến khích bạn báo cáo bất kỳ bất thường hoặc nghi ngờ nào bạn phát hiện tới trung tâm cuộc gọi của chúng tôi qua số điện thoại sau: +34 900111500,” email tiếp tục.

## Việc công bố theo sau các tuyên bố đánh cắp dữ liệu

Thời điểm công bố đáng chú ý vì nó diễn ra sau một tuyên bố khoảng một tuần trước của một tội phạm mạng trực tuyến rằng họ có quyền truy cập vào 77 GB dữ liệu được cho là của Iberia và đang cố gắng bán nó với giá 150.000 đô la.

Trong [bài đăng diễn đàn](https://x.com/H4ckmanac/status/1989305151341969640) (được hiển thị bên dưới), tội phạm mạng tuyên bố kho dữ liệu này đã "được trích xuất trực tiếp từ các máy chủ nội bộ [của hãng hàng không]" và chứa dữ liệu kỹ thuật A320/A321, tệp bảo dưỡng AMP, thông tin về động cơ, và các tài liệu nội bộ khác:

**Kẻ tấn công tuyên bố bán dữ liệu được cho là của Iberia tuần trước** (Hackmanac trên X)

Chưa rõ liệu bản rò rỉ dữ liệu được cho là như vậy có liên quan đến sự cố của Iberia hay không, vì tin rao không đề cập đến thông tin khách hàng mà Iberia cho biết đã bị lộ. Hơn nữa, hãng quy lỗi vi phạm cho một nhà cung cấp bên thứ ba chứ không phải máy chủ của chính hãng.

BleepingComputer chưa xác minh tính xác thực của dữ liệu được quảng cáo trực tuyến. Chúng tôi đã liên hệ với đội ngũ báo chí của Iberia để đặt thêm câu hỏi và sẽ cập nhật bài báo này khi nhận được phản hồi.

Trong khi đó, khách hàng và đối tác của Iberia nên cảnh giác với bất kỳ tin nhắn không được yêu cầu hoặc đáng ngờ nào tự nhận là đến từ hãng, vì những tin nhắn này có thể là các cuộc tấn công lừa đảo (phishing) hoặc tấn công mưu mẹo xã hội (social engineering).