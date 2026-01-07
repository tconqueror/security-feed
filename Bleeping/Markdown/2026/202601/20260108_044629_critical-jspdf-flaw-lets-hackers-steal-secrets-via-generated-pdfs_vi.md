# Lỗ hổng nghiêm trọng của jsPDF cho phép hacker đánh cắp bí mật qua các PDF được tạo

![Lỗ hổng nghiêm trọng của jsPDF cho phép hacker đánh cắp bí mật qua các PDF được tạo](https://www.bleepstatic.com/content/hl-images/2024/12/10/hacker-box.jpg)

Thư viện jsPDF dùng để tạo tài liệu PDF trong các ứng dụng JavaScript có một lỗ hổng nghiêm trọng cho phép kẻ tấn công đánh cắp dữ liệu nhạy cảm từ hệ thống tệp cục bộ bằng cách đưa chúng vào các file được tạo.

Lỗ hổng là một kiểu bảo mật cho phép chèn file cục bộ và vượt đường dẫn (local file inclusion and path traversal) cho phép truyền các đường dẫn không được kiểm duyệt tới cơ chế tải file (loadFile) trong các phiên bản jsPDF trước 4.0. Nó được theo dõi dưới mã [CVE-2025-68428](https://nvd.nist.gov/vuln/detail/CVE-2025-68428) và nhận điểm mức độ nghiêm trọng là 9.2.

Thư viện jsPDF là một package được sử dụng rộng rãi với hơn [3.5 million weekly downloads](https://www.npmjs.com/package/jspdf) trong registry npm.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Trong các bản build Node.js của jsPDF, hàm 'loadFile' được dùng để đọc hệ thống tệp cục bộ. Vấn đề phát sinh khi đầu vào do người dùng điều khiển được truyền làm đường dẫn file, khiến jsPDF kết hợp vào đầu ra PDF được tạo nội dung của file đó.

![Exploitation example](https://www.bleepstatic.com/images/news/u/1100723/jsPDF_CVE-2025-68428_attack.png)

**Ví dụ khai thác**  
_Nguồn: Parallax_

Các phương thức tải file khác cũng bị ảnh hưởng, bao gồm 'addImage', 'html', và 'addFont', vì tất cả đều có thể gọi hàm loadFile.

Theo [bản thông báo bảo mật của jsPDF](http://github.com/parallax/jsPDF/security/advisories/GHSA-f8cm-6447-x5h2), vấn đề chỉ ảnh hưởng đến các bản build Node.js của thư viện, cụ thể là các file _dist/jspdf.node.js_ và _dist/jspdf.node.min.js_.

Trong một báo cáo kỹ thuật chi tiết, công ty bảo mật ứng dụng Endor Labs cho biết rủi ro khai thác là thấp hoặc không tồn tại nếu các đường dẫn file được mã hóa cứng (hardcoded), đến từ cấu hình đáng tin cậy, hoặc nếu sử dụng danh sách cho phép nghiêm ngặt cho các đầu vào.

CVE-2025-68428 đã được sửa trong phiên bản 4.0.0 của jsPDF bằng cách hạn chế truy cập hệ thống tệp theo mặc định và thay vào đó dựa vào chế độ quyền của Node.js.

Tuy nhiên, các nhà nghiên cứu Endor Labs [ghi chú](https://www.endorlabs.com/learn/cve-2025-68428-critical-path-traversal-in-jspdf) rằng chế độ này đang ở trạng thái thử nghiệm trong Node 20, vì vậy khuyến cáo sử dụng các phiên bản 22.13.0, 23.5.0, hoặc 24.0.0 trở lên.

Một lưu ý khác cần cân nhắc là việc bật cờ ‘--permission’, một cách khắc phục được các nhà phát triển gợi ý, ảnh hưởng đến toàn bộ tiến trình Node.js, không chỉ jsPDF.

Endor Labs cũng nhấn mạnh rằng các quyền hệ thống tệp quá rộng được thêm vào cờ cấu hình '--allow-fs-read' sẽ làm vô hiệu hóa bản sửa lỗi.

**Cấu hình quá rộng cho phép**  
_Nguồn: Endor Labs_

Nhóm jsPDF khuyến nghị rằng các phiên bản Node cũ hơn nên kiểm duyệt các đường dẫn do người dùng cung cấp trước khi truyền chúng tới jsPDF.

Với việc jsPDF được triển khai rộng rãi trên nhiều dự án, CVE-2025-68428 là một ứng viên tốt cho việc bị khai thác tích cực.