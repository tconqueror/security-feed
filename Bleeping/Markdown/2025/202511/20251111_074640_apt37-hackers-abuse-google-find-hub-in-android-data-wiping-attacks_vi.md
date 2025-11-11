# Tin tặc APT37 lạm dụng Google Find Hub trong các cuộc tấn công xóa dữ liệu Android

![APT37 hackers abuse Google Find Hub in Android data-wiping attacks](https://www.bleepstatic.com/content/hl-images/2023/11/10/North_Korean_hackers_headpic.jpg)

Tin tặc Bắc Triều Tiên đang lợi dụng công cụ Google Find Hub để theo dõi vị trí GPS của mục tiêu và từ xa thiết lập lại thiết bị Android về cài đặt gốc.

Các cuộc tấn công chủ yếu nhắm vào người dân Hàn Quốc, và bắt đầu bằng cách tiếp cận các nạn nhân tiềm năng qua ứng dụng nhắn tin KakaoTalk - ứng dụng nhắn tin tức thời phổ biến nhất ở nước này.

Công ty giải pháp an ninh mạng Hàn Quốc Genians liên kết hoạt động độc hại này với cụm hoạt động KONNI, mà "có mục tiêu và cơ sở hạ tầng chồng chéo với Kimsuky và APT37."

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

KONNI thường đề cập đến một công cụ truy cập từ xa đã được liên kết với các cuộc tấn công từ tin tặc Bắc Triều Tiên trong các nhóm APT37 (ScarCruft) và Kimsuky (Emerald Sleet) nhắm vào nhiều lĩnh vực (ví dụ: giáo dục, chính phủ và tiền điện tử).

Theo Genians, chiến dịch KONNI lây nhiễm máy tính bằng các trojan truy cập từ xa cho phép rút trộm dữ liệu nhạy cảm.

Việc xóa thiết bị Android được thực hiện nhằm cô lập nạn nhân, xóa dấu vết tấn công, trì hoãn khôi phục và làm im lặng cảnh báo bảo mật. Cụ thể, việc đặt lại ngắt kết nối nạn nhân khỏi các phiên KakaoTalk trên PC, mà kẻ tấn công chiếm quyền sau khi xóa để phát tán tới danh bạ của mục tiêu.

### Chuỗi lây nhiễm

Chiến dịch KONNI được Genians phân tích nhắm mục tiêu thông qua các tin nhắn spear-phishing giả mạo Cơ quan Thuế Quốc gia Hàn Quốc, cảnh sát và các cơ quan khác.

Khi nạn nhân thực thi tệp đính kèm MSI được ký số (hoặc một .ZIP chứa nó), tệp này gọi một _install.bat_ nhúng và một script _error.vbs_ được dùng làm mồi nhử để đánh lừa người dùng với một "lỗi gói ngôn ngữ" giả.

Tệp BAT kích hoạt một script AutoIT (IoKITr.au3) thiết lập tính bền vững trên thiết bị thông qua một tác vụ đã lên lịch. Script lấy các module bổ sung từ một điểm command and control (C2), và cung cấp cho tác nhân đe dọa quyền truy cập từ xa, khả năng ghi lại phím và khả năng đưa thêm payload vào hệ thống.

Genians báo cáo rằng các payload thứ cấp được script tải về bao gồm RemcosRAT, QuasarRAT và RftRAT.

Những công cụ này được dùng để thu thập thông tin đăng nhập tài khoản Google và Naver của nạn nhân, cho phép chúng đăng nhập vào Gmail và Naver mail của mục tiêu, thay đổi cài đặt bảo mật và xóa nhật ký cho thấy sự xâm phạm.

### Sử dụng Find Hub để thiết lập lại thiết bị

Từ tài khoản Google bị xâm phạm, kẻ tấn công mở Google Find Hub để truy xuất các thiết bị Android đã đăng ký và truy vấn vị trí GPS của chúng.

Find Hub là công cụ mặc định "Find my Device" của Android, cho phép người dùng định vị từ xa, khóa, hoặc thậm chí xóa dữ liệu thiết bị Android trong trường hợp mất mát hoặc trộm cắp.

Phân tích pháp lý của Genians trên một số hệ thống máy tính nạn nhân cho thấy kẻ tấn công đã xóa thiết bị mục tiêu thông qua lệnh đặt lại từ xa của Find Hub.

"Cuộc điều tra phát hiện vào sáng ngày 5 tháng 9 một tác nhân đe dọa đã xâm phạm và lạm dụng tài khoản KakaoTalk của một cố vấn có trụ sở tại Hàn Quốc chuyên hỗ trợ tâm lý cho thanh thiếu niên đào tẩu Bắc Triều Tiên, và gửi một tệp độc hại ngụy trang thành 'chương trình giảm căng thẳng' cho một học sinh đào tẩu thật sự," [các nhà nghiên cứu của Genians cho biết](https://www.genians.co.kr/en/blog/threat%5Fintelligence/android).

Các nhà nghiên cứu cho biết tin tặc đã sử dụng tính năng theo dõi GPS để chọn thời điểm khi mục tiêu đang ở ngoài trời và ít có khả năng phản ứng khẩn cấp với tình huống.

![Tổng quan về các cuộc tấn công KONNI](https://www.bleepstatic.com/images/news/u/1220909/2025/November/attack-overview.jpg)

**Tổng quan về các cuộc tấn công KONNI**  
_Nguồn: Genians Security_

Trong cuộc tấn công, tác nhân đe dọa đã chạy các lệnh đặt lại từ xa trên tất cả các thiết bị Android đã đăng ký. Điều này dẫn tới việc xóa hoàn toàn dữ liệu quan trọng. Kẻ tấn công đã thực hiện lệnh xóa ba lần, điều này ngăn chặn việc phục hồi và sử dụng thiết bị trong một khoảng thời gian dài hơn.

Khi các cảnh báo trên di động bị vô hiệu hóa, kẻ tấn công đã sử dụng phiên KakaoTalk trên PC của nạn nhân đã đăng nhập trên máy tính đã bị xâm phạm để phân phối các tệp độc hại tới danh bạ của nạn nhân.

Vào ngày 15 tháng 9, Genians đã phát hiện một cuộc tấn công khác trên một nạn nhân riêng biệt sử dụng cùng phương pháp.

Để chặn các cuộc tấn công này, khuyến nghị bảo vệ tài khoản Google bằng cách bật xác thực đa yếu tố và đảm bảo truy cập nhanh tới tài khoản khôi phục.

Khi nhận tệp trên các ứng dụng nhắn tin, luôn cố gắng xác minh danh tính người gửi bằng cách gọi trực tiếp cho họ trước khi tải xuống/mở tệp.

Báo cáo của Genians bao gồm phân tích kỹ thuật về phần mềm độc hại được sử dụng cũng như danh sách các chỉ số xâm phạm (IoCs) liên quan đến hoạt động được điều tra.