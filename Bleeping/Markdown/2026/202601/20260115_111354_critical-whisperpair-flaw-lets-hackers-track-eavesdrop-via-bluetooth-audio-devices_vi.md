# Lỗ hổng nghiêm trọng cho phép tin tặc theo dõi, nghe lén qua thiết bị âm thanh Bluetooth

![Tai nghe](https://www.bleepstatic.com/content/hl-images/2026/01/15/headphones.jpg)

Các nhà nghiên cứu bảo mật đã phát hiện một lỗ hổng nghiêm trọng trong giao thức Fast Pair của Google có thể cho phép kẻ tấn công chiếm quyền thiết bị phụ kiện âm thanh Bluetooth, theo dõi người dùng và nghe lén các cuộc trò chuyện của họ.

Lỗ hổng (được theo dõi là [CVE-2025-36911](https://www.cve.org/CVERecord?id=CVE-2025-36911) và được đặt tên là [WhisperPair](https://whisperpair.eu/)) ảnh hưởng tới hàng trăm triệu tai nghe, earbud và loa không dây từ nhiều nhà sản xuất hỗ trợ tính năng Fast Pair của Google. Nó ảnh hưởng người dùng bất kể hệ điều hành smartphone của họ vì lỗ hổng nằm ở chính các phụ kiện, nghĩa là người dùng iPhone với thiết bị Bluetooth dễ tổn thương cũng có nguy cơ như nhau.

Các nhà nghiên cứu thuộc [KU Leuven's Computer Security and Industrial Cryptography group](https://www.esat.kuleuven.be/cosic/) — những người phát hiện ra lỗ hổng — giải thích rằng lỗ hổng bắt nguồn từ việc triển khai không đúng giao thức Fast Pair trong nhiều phụ kiện âm thanh cao cấp.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Mặc dù đặc tả Fast Pair quy định rằng các thiết bị Bluetooth nên bỏ qua các yêu cầu ghép nối khi không ở chế độ ghép nối, nhiều nhà cung cấp đã không thực thi kiểm tra này trong sản phẩm của họ, cho phép các thiết bị trái phép khởi tạo ghép nối mà không có sự đồng ý hoặc biết của người dùng.

"Để bắt đầu quy trình Fast Pair, một Seeker (một điện thoại) gửi một thông điệp đến Provider (một phụ kiện) cho biết rằng nó muốn ghép nối. Đặc tả Fast Pair nêu rằng nếu phụ kiện không ở chế độ ghép nối, nó nên bỏ qua các thông điệp như vậy," [các nhà nghiên cứu cho biết](https://whisperpair.eu/).

"Tuy nhiên, nhiều thiết bị không thực thi kiểm tra này trong thực tế, cho phép các thiết bị trái phép khởi động quá trình ghép nối. Sau khi nhận được phản hồi từ thiết bị dễ tổn thương, một kẻ tấn công có thể hoàn tất quy trình Fast Pair bằng cách thiết lập một ghép nối Bluetooth thông thường."

Kẻ tấn công có thể khai thác lỗ hổng WhisperPair bằng bất kỳ thiết bị có Bluetooth nào (như laptop, Raspberry Pi, hoặc thậm chí một điện thoại) để ép ghép nối với các phụ kiện dễ tổn thương từ Google, Jabra, JBL, Logitech, Marshall, Nothing, OnePlus, Sony, Soundcore và Xiaomi ở khoảng cách lên tới 14 mét chỉ trong vài giây và không cần tương tác của người dùng hay truy cập vật lý.

Sau khi ghép nối, họ giành quyền kiểm soát hoàn toàn thiết bị âm thanh, cho phép họ phát âm thanh với âm lượng lớn hoặc nghe lén cuộc trò chuyện của người dùng qua microphone của thiết bị.

CVE-2025-36911 cũng cho phép kẻ tấn công theo dõi vị trí nạn nhân bằng mạng Google Find Hub nếu phụ kiện chưa bao giờ được ghép nối với thiết bị Android bằng cách thêm thiết bị đó vào tài khoản Google của họ.

"Nạn nhân có thể thấy một thông báo theo dõi không mong muốn sau vài giờ hoặc vài ngày, nhưng thông báo này sẽ hiển thị thiết bị của chính họ," họ thêm vào. "Điều này có thể khiến người dùng bỏ qua cảnh báo như một lỗi, cho phép kẻ tấn công tiếp tục theo dõi nạn nhân trong một khoảng thời gian dài."

Google đã trao cho các nhà nghiên cứu 15.000 đô la, mức tiền thưởng tối đa có thể, và đã làm việc với các nhà sản xuất để phát hành các bản vá bảo mật trong cửa sổ tiết lộ 150 ngày. Tuy nhiên, họ lưu ý rằng các bản cập nhật bảo mật giải quyết lỗ hổng này có thể chưa có sẵn cho tất cả các thiết bị dễ tổn thương.

Biện pháp phòng duy nhất chống lại việc kẻ tấn công chiếm quyền các phụ kiện Bluetooth hỗ trợ Fast Pair là cài đặt các bản cập nhật firmware từ nhà sản xuất thiết bị. Vô hiệu hóa Fast Pair trên điện thoại Android không ngăn được cuộc tấn công, vì tính năng này không thể bị tắt trên chính các phụ kiện.