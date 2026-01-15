# Gootloader hiện sử dụng các kho lưu trữ ZIP gồm 1.000 phần để phân phối bí mật

![Gootloader hiện sử dụng các kho lưu trữ ZIP gồm 1.000 phần để phân phối bí mật](https://www.bleepstatic.com/content/hl-images/2022/08/21/compressed-folder-light-rays.jpg)

Phần mềm độc hại Gootloader, thường được sử dụng để truy cập ban đầu, hiện đang sử dụng một kho lưu trữ ZIP bị hỏng được thiết kế để né tránh phát hiện bằng cách nối tới 1.000 kho lưu trữ.

Khi làm vậy, phần mềm độc hại, vốn là một tệp JScript được lưu trữ, khiến nhiều công cụ bị treo khi cố gắng phân tích nó.

Theo các nhà nghiên cứu, tệp độc hại này có thể được giải nén thành công bằng tiện ích mặc định trên Windows, nhưng các công cụ dựa vào 7-Zip và WinRAR thì thất bại.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101)

Để đạt được điều này, tác nhân đe dọa đứng sau phần mềm độc hại đã nối từ 500 đến 1.000 kho lưu trữ ZIP, đồng thời sử dụng các mẹo khác để khiến việc phân tích bằng công cụ trở nên khó hơn.

Bộ tải Gootloader đã hoạt động từ năm 2020 và được sử dụng bởi nhiều hoạt động tội phạm mạng khác nhau, bao gồm cả việc triển khai ransomware.

Sau bảy tháng gián đoạn, chiến dịch đã trở lại vào tháng Mười Một năm ngoái, theo báo cáo của các nhà nghiên cứu bảo mật tại Huntress Labs và the DFIR Report.

Mặc dù các kho lưu trữ ZIP bị hỏng đã xuất hiện vào thời điểm đó, nhưng chúng chỉ có các chỉnh sửa tối thiểu, và có sự không khớp tên tệp khi cố gắng trích xuất dữ liệu.

Để tăng cường chống phân tích ở giai đoạn này, các nhà điều hành Gootloader hiện đã triển khai các cơ chế làm mơ hồ phức tạp hơn nhiều, theo các nhà nghiên cứu của Expel đang phân tích các mẫu gần đây hơn.

Cụ thể, các cơ chế sau đây hiện được sử dụng để né tránh phát hiện và phân tích:

* Nối tới một nghìn kho lưu trữ ZIP, tận dụng thực tế rằng các bộ phân tích đọc từ cuối tệp.
* Sử dụng một End of Central Directory (EOCD) bị cắt ngắn, thiếu hai byte bắt buộc, làm hỏng việc phân tích cú pháp bởi hầu hết công cụ.
* Ngẫu nhiên hóa các trường số đĩa, khiến công cụ mong đợi các kho lưu trữ đa đĩa không tồn tại.
* Thêm sự không khớp metadata giữa Local File Headers và các mục trong Central Directory.
* Tạo các mẫu ZIP và JScript duy nhất cho mỗi lần tải xuống để né tránh phát hiện tĩnh.
* Giao ZIP dưới dạng một blob được mã hóa XOR, blob này được giải mã và liên tục được ghép thêm phía client cho đến khi đạt kích thước mong muốn, né tránh phát hiện dựa trên mạng.

![Sự không khớp giữa Local File Header và Central Directories](https://www.bleepstatic.com/images/news/u/1220909/2026/January/mismatch.jpg)

**Sự không khớp giữa Local File Header và Central Directories**  
_Nguồn: Expel_

Khi được thực thi trên máy chủ, JScript của phần mềm độc hại khởi động qua Windows Script Host (WScript) từ một thư mục tạm thời và thiết lập khả năng tồn tại bằng cách thêm các tệp lối tắt (.LNK) vào thư mục Startup trỏ tới một tệp JScript thứ hai.

Payload này được thực thi khi khởi chạy lần đầu và với mỗi lần khởi động hệ thống, kích hoạt CScript với NTFS shortnames, tiếp theo là PowerShell khởi sinh một tiến trình PowerShell.

Trong khi tác giả của Gootloader đã thêm nhiều kỹ thuật làm hỏng để né tránh phát hiện mà không làm hỏng chức năng, các nhà nghiên cứu của Expel đã sử dụng các bất thường cấu trúc để giúp người phòng thủ phát hiện mối đe dọa. Nhóm cũng chia sẻ một quy tắc YARA có thể "nhận diện một cách nhất quán các kho lưu trữ ZIP hiện tại."

Việc phát hiện dựa trên việc phát hiện một kết hợp cụ thể của các đặc điểm header ZIP, hàng trăm Local File Headers lặp lại, và các bản ghi EOCD.

Các nhà nghiên cứu khuyến nghị rằng người phòng thủ thay đổi ứng dụng mặc định để mở các tệp JScript sang Notepad thay vì Windows Script Host, nhằm ngăn chặn việc thực thi chúng.

Để giảm bề mặt tấn công, Expel khuyên chặn _wscript.exe_ và _cscript.exe_ không cho thực thi nội dung được tải xuống nếu không cần các tệp JScript.