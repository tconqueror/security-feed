# Hacker Kimsuky của Triều Tiên bị phơi bày trong vụ rò rỉ dữ liệu bị cáo buộc

![Triều Tiên](https://www.bleepstatic.com/content/hl-images/2023/11/10/North_Korean_hackers_headpic.jpg)

Những hacker được nhà nước Triều Tiên tài trợ, được biết đến với tên gọi Kimsuky, được cho là đã xảy ra một vụ rò rỉ dữ liệu sau khi hai hacker, những người tự mô tả mình là đối lập với các giá trị của Kimsuky, đã ăn cắp dữ liệu của nhóm và rò rỉ công khai trực tuyến.

Hai hacker này, có tên là 'Saber' và 'cyb0rg,' đã viện dẫn lý do đạo đức cho các hành động của họ, cho rằng [Kimsuky](https://www.bleepingcomputer.com/tag/kimsuky/) là "hack vì những lý do sai lầm," khẳng định rằng họ bị thúc đẩy bởi các chương trình chính trị và tuân theo chỉ thị của chế độ thay vì thực hành nghệ thuật hacking một cách độc lập.

"Kimsuky, bạn không phải là một hacker. Bạn bị thúc đẩy bởi lòng tham tài chính, để làm giàu cho những lãnh đạo của bạn, và để thực hiện chương trình chính trị của họ," địa chỉ của những hacker gửi tới Kimsuky [được công bố trong số mới nhất của Phrack](https://data.ddosecrets.com/APT%20Down%20-%20The%20North%20Korea%20Files/phrack-apt-down-the-north-korea-files.pdf), đã được phát hành tại hội nghị DEF CON 33.

"Bạn ăn cắp từ người khác và ưu ái cho riêng mình. Bạn coi mình quan trọng hơn người khác: Bạn là người biến chất về mặt đạo đức."

Các hacker đã công bố một phần backend của Kimsuky, phơi bày cả công cụ của họ và một số dữ liệu bị đánh cắp của họ có thể cung cấp cái nhìn về các chiến dịch chưa biết và các thỏa hiệp chưa được ghi nhận.

Bản dump 8.9GB hiện đang được lưu trữ trên trang web '[Distributed Denial of Secrets'](https://ddosecrets.com/article/apt-down-the-north-korea-files)' chứa, trong số đó có:

* Nhật ký phishing với nhiều tài khoản email dcc.mil.kr (Command chống tình báo Quốc phòng).
* Các miền nhắm mục tiêu khác: spo.go.kr, korea.kr, daum.net, kakao.com, naver.com.
* Tệp nén .7z chứa mã nguồn đầy đủ của nền tảng email thuộc Bộ Ngoại giao Hàn Quốc ("Kebi"), bao gồm các mô-đun webmail, quản trị và lưu trữ.
* Tham chiếu đến các chứng chỉ công dân Hàn Quốc và danh sách đã được chọn lọc của các giáo sư đại học.
* Bộ công cụ "Generator" PHP để xây dựng các trang phishing với các thủ thuật né tránh phát hiện và chuyển hướng.
* Bộ kit phishing hoạt động.
* Các tệp nhị phân chưa xác định (voS9AyMZ.tar.gz, Black.x64.tar.gz) và các tệp thực thi (payload.bin, payload\_test.bin, s.x64.bin) chưa được đánh dấu trong VirusTotal.
* Các tải Cobalt Strike, shell đảo ngược, và mô-đun proxy Onnara được tìm thấy trong bộ nhớ cache kéo và thả của VMware.
* Lịch sử và cấu hình Chrome liên kết với các tài khoản GitHub nghi vấn (wwh1004.github.io, v.v.), các giao dịch VPN (PureVPN, ZoogVPN) qua Google Pay, và việc sử dụng thường xuyên các diễn đàn hacking (freebuf.com, xaker.ru).
* Sử dụng Google Translate cho các thông điệp lỗi tiếng Trung và các chuyến thăm đến các trang web của chính phủ và quân đội Đài Loan.
* Lịch sử Bash với các kết nối SSH đến các hệ thống nội bộ.

Các hacker lưu ý rằng một số thông tin ở trên đã được biết đến hoặc ghi nhận trước đây, ít nhất là một phần.

Tuy nhiên, bản dump mang đến một chiều sâu mới cho dữ liệu và cung cấp sự liên kết giữa các công cụ và hoạt động của Kimsuky, phơi bày và thực sự "đốt cháy" cơ sở hạ tầng và phương pháp của APT.

BleepingComputer đã liên lạc với nhiều nhà nghiên cứu an ninh để xác nhận tính xác thực của các tài liệu bị rò rỉ và giá trị của chúng và sẽ cập nhật câu chuyện nếu chúng tôi nhận được phản hồi.

Mặc dù vụ rò rỉ có thể sẽ không có tác động lâu dài đến hoạt động của Kimsuky, nhưng nó có thể dẫn đến khó khăn trong hoạt động cho Kimsuky và làm gián đoạn các chiến dịch đang diễn ra.

Số mới nhất của [Phrack](https://www.bleepingcomputer.com/news/security/phrack-hacker-zine-publishes-new-edition-after-three-years/) (#72) hiện chỉ có sẵn ở bản sao vật lý giới hạn, nhưng phiên bản trực tuyến sẽ sẵn sàng cho mọi người đọc miễn phí trong những ngày tới [từ đây](https://phrack.org/).