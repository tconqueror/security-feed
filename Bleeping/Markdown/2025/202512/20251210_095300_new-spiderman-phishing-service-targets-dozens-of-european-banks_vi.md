# Dịch vụ lừa đảo Spiderman mới nhắm vào hàng chục ngân hàng châu Âu

![Dịch vụ lừa đảo Spiderman mới nhắm vào hàng chục ngân hàng châu Âu](https://www.bleepstatic.com/content/hl-images/2025/12/10/spiderman.jpg)

Một bộ kit phishing mới có tên Spiderman đang nhắm tới khách hàng của nhiều ngân hàng châu Âu và dịch vụ tiền điện tử bằng cách sử dụng các bản sao trang web chính xác đến từng pixel của các trang hợp pháp.

Nền tảng này cho phép tội phạm mạng triển khai các chiến dịch phishing có thể thu thập thông tin đăng nhập, mã xác thực hai yếu tố (2FA) và dữ liệu thẻ tín dụng.

The Spiderman phishing kit, analyzed by researchers at Varonis, targets financial institutions in five countries, including major brands such as Deutsche Bank, ING, Comdirect, Blau, O2, CaixaBank, Volksbank, and Commerzbank.

Các nhà nghiên cứu quan sát thấy rằng nó có thể tạo các trang phishing cho cổng trực tuyến của các công ty fintech, chẳng hạn như dịch vụ Thụy Điển Klarna và PayPal. Nó cũng có thể đánh cắp cụm từ khôi phục (seed phrases) cho các ví tiền điện tử Ledger, Metamask và Exodus.

![Một số nền tảng bị nhắm tới](https://www.bleepstatic.com/images/news/u/1220909/2025/December/04.jpg)

**Một số nền tảng bị nhắm tới**  
_Nguồn: Varonis_

“Bởi vì Spiderman có cấu trúc mô-đun, các ngân hàng, cổng và phương thức xác thực mới có thể được thêm vào. Khi các nước châu Âu triển khai các luồng e-banking cập nhật, bộ kit này có khả năng phát triển song song,” Varonis nói trong [báo cáo](https://www.varonis.com/blog/spiderman-phishing-kit).

Các nhà nghiên cứu phát hiện rằng Spiderman được nhiều tội phạm mạng ưa chuộng, với một trong các nhóm của nó trên Signal có tới 750 thành viên.

Từ bảng điều khiển, các kẻ vận hành có thể xem phiên của nạn nhân theo thời gian thực, thu thập thông tin đăng nhập, xuất dữ liệu chỉ với một cú nhấp, chặn PhotoTAN/mã xác thực một lần (OTP) theo thời gian thực và thu thập chi tiết thẻ tín dụng.

![Tương tác thời gian thực với nạn nhân thông qua bảng điều khiển](https://www.bleepstatic.com/images/news/u/1220909/2025/December/01.jpg)

**Tương tác thời gian thực thông qua bảng điều khiển**  
_Nguồn: Varonis_

PhotoTAN là một hệ thống OTP được nhiều ngân hàng ở châu Âu sử dụng, trong đó một hình ghép nhiều màu được hiển thị trong bước đăng nhập hoặc phê duyệt giao dịch, và người dùng phải quét bằng ứng dụng của ngân hàng để tiếp tục.

Ứng dụng giải mã hình ghép và hiển thị một mã OTP đặc thù cho giao dịch mà người dùng phải nhập lại vào trang ngân hàng.

Mặc dù chặn PhotoTAN [không phải là một tính năng mới](https://www.bleepingcomputer.com/news/security/new-v3b-phishing-kit-targets-customers-of-54-european-banks/) trong các bộ kit phishing, nó được coi là một “tính năng cần có” cho các nền tảng nhắm tới các tổ chức châu Âu.

Các kẻ vận hành Spiderman có thể cấu hình phạm vi mục tiêu từ bảng điều khiển, giới hạn vào các quốc gia cụ thể, thêm danh sách cho phép ISP, bộ lọc theo loại thiết bị (người dùng di động hoặc máy tính để bàn), và thiết lập chuyển hướng cho khách truy cập không đủ điều kiện cho các cuộc tấn công phishing.

Các nhà nghiên cứu của Varonis cảnh báo rằng dữ liệu bị thu thập bởi Spiderman có thể dẫn tới chiếm đoạt tài khoản ngân hàng, SIM swapping, gian lận thẻ tín dụng và đánh cắp danh tính.

Tất cả các bộ kit phishing đều phụ thuộc vào việc nạn nhân nhấp vào một liên kết dẫn họ tới trang đăng nhập giả, vì vậy biện pháp bảo vệ tốt nhất là luôn xác nhận bạn đang ở trên tên miền chính thức trước khi nhập thông tin đăng nhập, và kiểm tra kỹ các cửa sổ browser-in-the-browser có thể hiển thị URL chính xác.

Nhận được một tin nhắn SMS hoặc lời nhắc PhotoTAN trên thiết bị của bạn mà không liên quan đến hành động bạn thực hiện là dấu hiệu của một nỗ lực chiếm đoạt và nên được báo ngay cho ngân hàng.