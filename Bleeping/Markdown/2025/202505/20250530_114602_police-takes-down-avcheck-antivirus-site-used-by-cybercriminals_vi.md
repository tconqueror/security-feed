# Cảnh sát xóa sổ trang web AVCheck dùng cho phần mềm antivirus của tội phạm mạng

![Malware](https://www.bleepstatic.com/content/hl-images/2022/05/05/malware-header.jpg)

Một chiến dịch thực thi pháp luật quốc tế đã xóa bỏ AVCheck, một dịch vụ được sử dụng bởi tội phạm mạng để kiểm tra xem phần mềm độc hại của họ có bị phát hiện bởi phần mềm antivirus thương mại hay không trước khi triển khai ở ngoài thực địa.

Tên miền chính thức của dịch vụ tại avcheck.net hiện hiển thị một biển báo tịch thu với biểu trưng của Bộ Tư pháp Hoa Kỳ, FBI, Dịch vụ Bảo mật Hoa Kỳ và cảnh sát Hà Lan (Politie).

Theo thông báo trên trang web của Politie, AVCheck là một trong những dịch vụ chống antivirus (CAV) lớn nhất trên toàn cầu, giúp tội phạm mạng đánh giá tính ẩn danh và khả năng tránh né của phần mềm độc hại của họ.

"Việc đưa dịch vụ AVCheck offline là một bước quan trọng trong việc chống lại tội phạm mạng có tổ chức," [Phát biểu của Matthijs Jaspers thuộc Politie](https://www.politie.nl/nieuws/2025/mei/30/11-sleuteldienst-voor-ontwikkelaars-van-malware-onderuitgehaald.html).

"Với \[hành động này\], chúng tôi gây rối cho tội phạm mạng càng sớm càng tốt trong hoạt động của họ và ngăn chặn nạn nhân."

![Seizure notice](https://www.bleepstatic.com/images/news/u/1220909/2025/May/seized.jpg)

**Thông báo tịch thu trên AVCheck.net**  
_Nguồn: BleepingComputer_

Các điều tra viên cũng đã tìm thấy bằng chứng liên kết các quản trị viên của AVCheck với các dịch vụ mã hóa Cryptor.biz và Crypt.guru. Dịch vụ trước đã bị chính quyền tịch thu, trong khi dịch vụ sau đã ngoại tuyến.

Các dịch vụ mã hóa giúp các tác giả/nhà điều hành phần mềm độc hại mã hóa hoặc làm rối nội dung của các payload của họ để làm cho chúng không thể bị phát hiện bởi antivirus, vì vậy chúng nằm trong cùng một hệ sinh thái.

Tội phạm mạng sử dụng dịch vụ mã hóa để làm rối rắm phần mềm độc hại của họ, kiểm tra nó trên AVCheck hoặc các dịch vụ CAV tương tự để xem nó có thể không bị phát hiện hay không, và chỉ sau đó họ mới triển khai nó chống lại các mục tiêu của mình.

Trước khi xóa sổ AVCheck, cảnh sát đã dựng một trang đăng nhập giả, cảnh báo những người dùng cố gắng đăng nhập về các rủi ro pháp lý liên quan đến việc sử dụng dịch vụ này.

Một thông báo của Bộ Tư pháp Hoa Kỳ nhấn mạnh tầm quan trọng của việc tháo dỡ AVCheck và các dịch vụ mã hóa, điều mà họ nói đã xảy ra vào ngày 27 tháng 5 năm 2025.

"Tội phạm mạng không chỉ tạo ra phần mềm độc hại; họ hoàn thiện nó để gây ra sự tàn phá tối đa," [đại diện FBI Douglas Williams cho biết](https://www.justice.gov/usao-sdtx/pr/websites-selling-hacking-tools-cybercriminals-seized).

"Bằng cách tận dụng các dịch vụ chống antivirus, các diễn viên xấu có thể tinh chỉnh vũ khí của họ chống lại các hệ thống bảo mật khó nhằn nhất trên thế giới để dễ dàng xuyên qua các tường lửa, tránh phân tích pháp y, và gây thiệt hại cho hệ thống của nạn nhân."

Việc phát hiện bản chất bất hợp pháp của AVCheck và tìm ra mối liên hệ với các cuộc tấn công ransomware nhắm vào các thực thể Mỹ đã trở nên khả thi nhờ vào công việc của các đặc vụ ngầm thực hiện các giao dịch mua trên những dịch vụ này, giả làm khách hàng.

"Theo bản khai được nộp để hỗ trợ các vụ tịch thu này, chính quyền đã thực hiện các giao dịch mua ngầm từ các trang web bị tịch thu và phân tích các dịch vụ, xác nhận rằng chúng được thiết kế cho tội phạm mạng," thông báo của Bộ Tư pháp nêu.

"Các tài liệu của tòa án cũng cáo buộc các nhà chức trách đã xem xét các địa chỉ email được liên kết và dữ liệu khác kết nối các dịch vụ với các nhóm ransomware đã nhắm mục tiêu nạn nhân cả trong và ngoài nước, bao gồm khu vực Houston."

Hành động này là một phần của Chiến dịch Endgame, một hành động thực thi pháp luật quốc tế quy mô lớn đã [tịch thu 300 máy chủ và 650 tên miền](https://www.bleepingcomputer.com/news/security/police-takes-down-300-servers-in-ransomware-supply-chain-crackdown/) được sử dụng để tạo điều kiện cho các cuộc tấn công ransomware.

Cùng chiến dịch này đã phá vỡ các hoạt động phần mềm độc hại Danabot và Smokeloader nổi tiếng (trong số tội phạm mạng).