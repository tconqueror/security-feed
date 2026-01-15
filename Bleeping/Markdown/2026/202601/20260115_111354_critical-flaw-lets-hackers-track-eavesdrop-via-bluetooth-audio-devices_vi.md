# Lỗi nghiêm trọng cho phép hacker theo dõi, nghe lén qua thiết bị âm thanh Bluetooth

![Tai nghe](https://www.bleepstatic.com/content/hl-images/2026/01/15/headphones.jpg)

Các nhà nghiên cứu bảo mật đã phát hiện một lỗ hổng nghiêm trọng trong giao thức Fast Pair của Google có thể cho phép kẻ tấn công chiếm quyền các phụ kiện âm thanh Bluetooth, theo dõi người dùng và nghe lén các cuộc trò chuyện của họ.

Lỗ hổng (được theo dõi dưới tên [CVE-2025-36911](https://www.cve.org/CVERecord?id=CVE-2025-36911) và được đặt tên là [WhisperPair](https://whisperpair.eu/)) ảnh hưởng tới hàng trăm triệu tai nghe không dây, earbuds và loa từ nhiều nhà sản xuất hỗ trợ tính năng Fast Pair của Google. Nó ảnh hưởng tới người dùng bất kể hệ điều hành điện thoại thông minh của họ vì lỗi nằm ở chính các phụ kiện, nghĩa là người dùng iPhone có thiết bị Bluetooth dễ bị tấn công cũng gặp rủi ro tương đương.

Các nhà nghiên cứu thuộc [KU Leuven's Computer Security and Industrial Cryptography group](https://www.esat.kuleuven.be/cosic/) đã phát hiện ra vấn đề và giải thích rằng lỗ hổng bắt nguồn từ việc triển khai không đúng giao thức Fast Pair trong nhiều phụ kiện âm thanh đầu bảng.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Mặc dù đặc tả Fast Pair nêu rằng các thiết bị Bluetooth nên bỏ qua các yêu cầu ghép đôi khi không ở chế độ ghép đôi, nhiều nhà sản xuất đã không thực hiện kiểm tra này trong sản phẩm của họ, cho phép thiết bị trái phép khởi động quá trình ghép đôi mà không có sự đồng ý hay nhận biết của người dùng.

"Để bắt đầu quy trình Fast Pair, một Seeker (một điện thoại) gửi một thông điệp tới Provider (một phụ kiện) cho biết rằng nó muốn ghép đôi. Bản đặc tả Fast Pair quy định rằng nếu phụ kiện không ở chế độ ghép đôi, nó nên bỏ qua các thông điệp như vậy," [các nhà nghiên cứu cho biết](https://whisperpair.eu/).

"Tuy nhiên, nhiều thiết bị không thực thi kiểm tra này trong thực tế, cho phép các thiết bị không được phép bắt đầu quá trình ghép đôi. Sau khi nhận được phản hồi từ thiết bị dễ bị tấn công, kẻ tấn công có thể hoàn tất quy trình Fast Pair bằng cách thiết lập một kết nối ghép đôi Bluetooth thông thường."

Kẻ tấn công có thể khai thác lỗ hổng WhisperPair bằng bất kỳ thiết bị có Bluetooth nào (chẳng hạn như laptop, Raspberry Pi, hoặc thậm chí một điện thoại) để ép ghép đôi với các phụ kiện dễ bị tấn công từ Google, Jabra, JBL, Logitech, Marshall, Nothing, OnePlus, Sony, Soundcore, và Xiaomi ở khoảng cách lên đến 14 mét trong vài giây và không cần tương tác của người dùng hay truy cập vật lý.

Sau khi ghép đôi, họ có toàn quyền kiểm soát thiết bị âm thanh, cho phép phát âm thanh với âm lượng lớn hoặc nghe lén các cuộc trò chuyện của người dùng thông qua micro của thiết bị.

CVE-2025-36911 cũng cho phép kẻ tấn công theo dõi vị trí nạn nhân bằng cách sử dụng mạng Find Hub của Google nếu phụ kiện chưa từng được ghép đôi với một thiết bị Android bằng cách thêm thiết bị đó vào Google account của họ.

"Nạn nhân có thể thấy một thông báo theo dõi không mong muốn sau vài giờ hoặc vài ngày, nhưng thông báo này sẽ hiển thị thiết bị của chính họ," họ bổ sung. "Điều này có thể khiến người dùng cho rằng cảnh báo là một lỗi, cho phép kẻ tấn công tiếp tục theo dõi nạn nhân trong một khoảng thời gian dài."

Google đã trao cho các nhà nghiên cứu 15.000 USD, mức tiền thưởng tối đa có thể, và làm việc với các nhà sản xuất để phát hành bản vá bảo mật trong một cửa sổ tiết lộ kéo dài 150 ngày. Tuy nhiên, họ lưu ý rằng các bản cập nhật bảo mật khắc phục lỗ hổng này có thể chưa có sẵn cho tất cả các thiết bị dễ bị tấn công.

Biện pháp phòng duy nhất chống lại việc kẻ tấn công chiếm đoạt các phụ kiện Bluetooth hỗ trợ Fast Pair dễ bị tấn công là cài đặt các bản cập nhật firmware từ nhà sản xuất thiết bị. Vô hiệu hoá Fast Pair trên điện thoại Android không ngăn được cuộc tấn công, vì tính năng này không thể bị vô hiệu hoá trên chính các phụ kiện.