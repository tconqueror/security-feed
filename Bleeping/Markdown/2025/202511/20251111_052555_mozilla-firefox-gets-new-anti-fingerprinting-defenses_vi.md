# Mozilla Firefox được trang bị các biện pháp chống định danh vân tay kỹ thuật số mới

![Mozilla Firefox được trang bị các biện pháp chống định danh vân tay kỹ thuật số mới](https://www.bleepstatic.com/content/hl-images/2024/03/22/Firefox-headpic.jpg)

Mozilla đã thông báo một bản nâng cấp quyền riêng tư lớn trong Firefox 145 giúp giảm thêm số lượng người dùng dễ bị định danh vân tay kỹ thuật số.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Các định danh tinh vi, như múi giờ, chi tiết phần cứng và trình duyệt, có thể được sử dụng để tạo một chữ ký số duy nhất để nhận dạng người dùng trên internet.

Loại dữ liệu này có thể là phiên bản trình duyệt của bạn, hệ điều hành, độ phân giải màn hình và độ sâu màu, ngôn ngữ hệ thống, phông chữ đã cài đặt, múi giờ, hành vi kết xuất của GPU, số lõi CPU, khả năng cảm ứng và bộ nhớ thiết bị.

Hệ thống chống fingerprinting hiện có của Firefox, là một phần của cơ chế 'Enhanced Tracking Protection', chặn nhiều script theo dõi và fingerprinting đã biết, hầu hết trong số đó vốn dĩ phổ biến và không liên quan đến việc cải thiện trải nghiệm người dùng.

“Kể từ 2021, Firefox đã dần tiến triển các biện pháp bảo vệ chống fingerprinting, bao phủ những kỹ thuật fingerprinting phổ biến nhất,” [giải thích Mozilla](https://blog.mozilla.org/en/firefox/fingerprinting-protections/).

“Chúng bao gồm những thứ như cách card đồ họa của bạn vẽ hình ảnh, phông chữ mà máy tính bạn có, và thậm chí những khác biệt nhỏ về cách nó thực hiện các phép toán.”

Những chặn chống fingerprinting này, mà Mozilla gọi là ‘Phase 1 Protections’, đã giảm khả năng theo dõi xuống khoảng 35%, so với mức cơ bản 65% khi không có biện pháp bảo vệ nào.

Bây giờ, các biện pháp ‘Phase 2’ đang được triển khai, chặn các yêu cầu nhằm phát hiện phông chữ đã cài đặt, chi tiết phần cứng, số lõi bộ xử lý, hỗ trợ đa chạm, và kích thước dock/thanh tác vụ.

Cụ thể, các biện pháp bảo vệ mới bao gồm những điều sau:

* Nhiễu ngẫu nhiên được thêm vào hình nền chỉ khi một trang web đọc lại chúng, không phải khi chúng chỉ được hiển thị.
* Chỉ sử dụng phông chữ tiêu chuẩn của hệ điều hành; phông chữ cục bộ bị chặn, ngoại trừ phông chữ quan trọng cho các ngôn ngữ như Japanese, Thai, Arabic, Chinese, Korean, và Hebrew.
* Hỗ trợ cảm ứng được báo cáo là 0, 1, hoặc 5.
* Độ phân giải màn hình khả dụng là chiều cao màn hình trừ 48 pixel.
* Số lõi bộ xử lý luôn được báo cáo là 2.

Nhờ các biện pháp bổ sung này, chỉ 20% người dùng vẫn có thể bị định danh duy nhất và bị theo dõi liên tục.

![Phần trăm khả năng theo dõi người dùng trong mỗi trường hợp](https://www.bleepstatic.com/images/news/u/1220909/2025/November/perc.png)

**Phần trăm khả năng theo dõi người dùng trong mỗi trường hợp**  
_Nguồn: Mozilla_

Mozilla giải thích rằng họ không thể chặn mọi thứ một cách quá mạnh để giảm khả năng theo dõi hơn nữa, vì điều đó cuối cùng sẽ dẫn đến các vấn đề về khả năng sử dụng làm hỏng các tính năng hợp pháp của trang web.

Nhiều công cụ năng suất phụ thuộc vào dữ liệu thời gian thực và vị trí thực tế để cung cấp chức năng mong muốn, vì vậy một cổng trao đổi cần được duy trì, ngay cả khi kích thước của nó đang thu nhỏ lại.

Những người gặp vấn đề về khả năng sử dụng với các lớp bảo vệ mới được cung cấp tùy chọn để [vô hiệu hóa chúng trên các trang cụ thể](https://support.mozilla.org/en-US/kb/firefox-protection-against-fingerprinting#w%5Fhow-do-i-disable-this-protection-for-a-website).

Firefox 145 sẽ chính thức được phát hành vào ngày mai, nhưng người dùng đã có thể tải xuống trình cài đặt cho hệ điều hành của họ từ [Mozilla’s FTP server](https://ftp.mozilla.org/pub/firefox/releases/145.0/).

Lưu ý rằng đây là bản phát hành đầu tiên không cung cấp phiên bản 32-bit cho Linux, mà Mozilla đã ngừng hỗ trợ do nhu cầu người dùng giảm khiến việc phát triển và kiểm thử không còn đáng giá.