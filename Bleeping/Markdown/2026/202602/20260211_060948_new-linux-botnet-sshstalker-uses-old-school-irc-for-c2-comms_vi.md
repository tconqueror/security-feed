# Botnet Linux mới SSHStalker sử dụng IRC cổ điển cho liên lạc C2

![Botnet Linux mới SSHStalker sử dụng IRC cổ điển cho liên lạc C2](https://www.bleepstatic.com/content/hl-images/2024/05/14/Linux-botnet.jpg)

Một botnet Linux mới được ghi nhận có tên SSHStalker đang sử dụng giao thức liên lạc IRC (Internet Relay Chat) cho các hoạt động command-and-control (C2).

Giao thức này được phát minh vào năm 1988 và đạt đỉnh phổ biến trong những năm 1990, trở thành giải pháp nhắn tin tức thời dựa trên văn bản chính cho giao tiếp nhóm và riêng tư.

Các cộng đồng kỹ thuật vẫn đánh giá cao nó nhờ tính đơn giản trong triển khai, khả năng tương tác, yêu cầu băng thông thấp và không cần GUI.

[![Wiz](https://www.bleepstatic.com/c/w/S/Secured-Images-970x250.png)](https://www.wiz.io/lp/secure-images-101-a-visual-guide?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FHardened-Images-101-Digital-Poster&sfcid=701Py00000WFCeLIAX&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=Secured-Images-101) 

Botnet SSHStalker dựa vào cơ chế IRC cổ điển như các bot dựa trên C và tính dư phòng đa máy chủ/kênh thay vì các framework C2 hiện đại, ưu tiên khả năng phục hồi, mở rộng quy mô và chi phí thấp hơn là tính ẩn danh và kỹ thuật mới.

Theo các nhà nghiên cứu tại công ty tình báo mối đe dọa Flare, cách tiếp cận này mở rộng sang các đặc điểm khác trong hoạt động của SSHStalker, như sử dụng các bản quét SSH ồn ào, cron jobs một phút và danh sách lớn các CVE 15 năm tuổi.

"Điều chúng tôi thực sự tìm thấy là một bộ công cụ botnet hỗn tạp, kết hợp kiểm soát IRC kiểu cũ, biên dịch nhị phân trên máy chủ, xâm phạm SSH hàng loạt và duy trì hoạt động qua cron. Nói cách khác là hoạt động ưu tiên quy mô hơn sự tàng hình", Flare cho biết.

![Kênh IRC 'infected machines'](https://www.bleepstatic.com/images/news/u/1220909/2026/February/infectedmachines.jpg)

**Kênh IRC 'infected machines'**  
_Nguồn: Flare_

SSHStalker đạt được truy cập ban đầu thông qua quét và brute force SSH tự động, sử dụng file nhị phân Go giả mạo tiện ích khám phá mạng mã nguồn mở phổ biến _nmap_.

Các máy chủ bị xâm phạm sau đó được sử dụng để quét các mục tiêu SSH bổ sung, hoạt động này giống cơ chế lan truyền kiểu sâu cho botnet.

Flare [phát hiện](https://flare.io/learn/resources/blog/old-school-irc-new-victims-inside-the-newly-discovered-sshstalker-linux-botnet) một tệp chứa kết quả từ gần 7.000 lần quét botnet, tất cả từ tháng 1, và tập trung chủ yếu vào các nhà cung cấp dịch vụ lưu trữ đám mây trên nền tảng Oracle Cloud.

Khi SSHStalker lây nhiễm vào một máy chủ, nó tải xuống công cụ GCC để biên dịch payload trên thiết bị nạn nhân nhằm tăng tính di động và né tránh.

Các payload đầu tiên là các bot IRC dựa trên C với máy chủ và kênh C2 được mã hóa cứng, đăng ký nạn nhân mới vào cơ sở hạ tầng IRC của botnet.

Sau đó, phần mềm độc hại tìm nạp các kho lưu trữ có tên GS và _bootbou_, chứa các biến thể bot để điều phối và thực thi tuần tự.

Việc duy trì hoạt động đạt được thông qua cron jobs chạy mỗi 60 giây, kích hoạt cơ chế cập nhật kiểu watchdog kiểm tra xem quy trình bot chính có đang chạy không và khởi động lại nếu bị chấm dứt.

Botnet cũng chứa các khai thác cho 16 CVE nhắm mục tiêu phiên bản kernel Linux từ năm 2009-2010, được sử dụng để leo thang đặc quyền sau khi bước brute force trước đó cấp quyền truy cập cho người dùng có đặc quyền thấp.

**Tổng quan chuỗi tấn công**  
_Nguồn: Flare_

Về kiếm tiền, Flare nhận thấy botnet thực hiện thu thập khóa AWS và quét website. Nó cũng bao gồm bộ công cụ khai thác tiền điện tử như trình khai thác Ethereum hiệu suất cao PhoenixMiner.

Khả năng từ chối dịch vụ phân tán (DDoS) cũng có mặt, mặc dù các nhà nghiên cứu lưu ý họ chưa quan sát thấy bất kỳ cuộc tấn công nào như vậy. Trên thực tế, các bot SSHStalker hiện chỉ kết nối với C2 và sau đó chuyển sang trạng thái nhàn rỗi, cho thấy đang trong giai đoạn thử nghiệm hoặc tích trữ quyền truy cập.

Flare chưa quy kết SSHStalker cho một nhóm mối đe dọa cụ thể nào, mặc dù nhận thấy điểm tương đồng với hệ sinh thái botnet [Outlaw/Maxlas](https://www.bleepingcomputer.com/news/security/rubycarp-hackers-linked-to-10-year-old-cryptomining-botnet/) và các chỉ số liên quan đến Romania.

Công ty tình báo mối đe dọa này đề xuất triển khai giải pháp giám sát cho việc cài đặt và thực thi trình biên dịch trên máy chủ sản xuất, đồng thời cảnh báo cho các kết nối đi kiểu IRC. Các công việc cron có chu kỳ thực thi ngắn từ các đường dẫn bất thường cũng là dấu hiệu cảnh báo lớn.

Các khuyến nghị giảm thiểu bao gồm tắt xác thực mật khẩu SSH, xóa trình biên dịch khỏi hình ảnh sản xuất, thực thi lọc egress và hạn chế thực thi từ '/dev/shm.'