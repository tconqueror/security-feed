# Lỗ hổng Ni8mare mức nghiêm trọng tối đa cho phép hacker chiếm quyền điều khiển các máy chủ n8n

![Lỗ hổng Ni8mare mức nghiêm trọng tối đa cho phép hacker chiếm quyền điều khiển các máy chủ n8n](https://www.bleepstatic.com/content/hl-images/2024/03/05/hand.jpg)

Một lỗ hổng có mức nghiêm trọng tối đa mang tên "Ni8mare" cho phép kẻ tấn công từ xa, không cần xác thực, chiếm quyền kiểm soát các triển khai cục bộ của nền tảng tự động hóa luồng công việc n8n.

Vấn đề bảo mật được xác định là CVE-2026-21858 và có điểm nghiêm trọng 10/10. Theo các nhà nghiên cứu tại công ty bảo mật dữ liệu Cyera, có hơn 100.000 máy chủ n8n dễ bị tấn công.

n8n là một công cụ tự động hóa luồng công việc mã nguồn mở cho phép người dùng kết nối các ứng dụng, API và dịch vụ thành các luồng công việc phức tạp thông qua trình chỉnh sửa trực quan. Nó chủ yếu được dùng để tự động hóa các tác vụ và hỗ trợ tích hợp với dịch vụ AI và các dịch vụ mô hình ngôn ngữ lớn (LLM).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Nó có hơn 50.000 lượt tải xuống hàng tuần [trên npm](https://www.npmjs.com/package/n8n?activeTab=versions) và hơn 100 triệu lượt kéo trên Docker Hub. Đây là một công cụ phổ biến trong lĩnh vực AI, nơi nó được sử dụng để điều phối các cuộc gọi tới LLM, xây dựng các tác nhân AI và các [RAG pipelines](https://blog.n8n.io/rag-pipeline/), và [tự động hóa thu thập](https://n8n.io/integrations/solve-data/) và truy xuất dữ liệu.

### Chi tiết Ni8mare

Lỗ hổng Ni8mare cho phép kẻ tấn công truy cập các tập tin trên máy chủ cơ sở bằng cách thực thi một số workflow dựa trên biểu mẫu.

"Một workflow dễ bị tấn công có thể cấp quyền truy cập cho một kẻ tấn công từ xa không xác thực. Điều này có thể dẫn đến việc lộ thông tin nhạy cảm được lưu trữ trên hệ thống và có thể cho phép xâm phạm thêm tùy theo cấu hình triển khai và cách sử dụng workflow," các nhà phát triển n8n [cho biết](https://github.com/n8n-io/n8n/security/advisories/GHSA-v4pr-fm98-w9pg).

Các nhà nghiên cứu của Cyera phát hiện lỗ hổng Ni8mare (CVE-2026-21858) và đã báo cáo cho n8n vào ngày 9 tháng 11 năm 2025. Họ cho biết vấn đề bảo mật là do nhầm lẫn về content-type trong cách n8n phân tích dữ liệu.

n8n sử dụng hai hàm để xử lý dữ liệu đến dựa trên header 'content-type' được cấu hình trong một webhook, thành phần kích hoạt sự kiện trong workflow bằng cách lắng nghe các thông điệp cụ thể.

Khi yêu cầu webhook được đánh dấu là multipart/form-data, n8n xử lý nó như một tải lên tập tin và sử dụng một parser tải lên đặc biệt lưu các tập tin vào các vị trí tạm thời được tạo ngẫu nhiên.

"Điều này có nghĩa người dùng không thể kiểm soát nơi các tập tin kết thúc, điều này bảo vệ chống lại các cuộc tấn công path traversal."

Tuy nhiên, với tất cả các content-type khác, n8n sử dụng parser tiêu chuẩn của nó.

Cyera [phát hiện](http://www.cyera.com/research-labs/ni8mare-unauthenticated-remote-code-execution-in-n8n-cve-2026-21858) rằng bằng cách thiết lập một content type khác, chẳng hạn application/json, kẻ tấn công có thể vượt qua parser dành cho tải lên.

Trong tình huống này, n8n vẫn xử lý các trường liên quan đến tập tin nhưng làm như vậy mà không xác minh rằng yêu cầu thực sự chứa một tải lên tập tin hợp lệ. Điều này cho phép kẻ tấn công hoàn toàn kiểm soát metadata của tập tin, bao gồm đường dẫn tập tin.

![The flawed parser logic](https://www.bleepstatic.com/images/news/u/1220909/2026/January/diagram(2).jpg)

**Logic parser bị lỗi**  
_Source: Cyera_

"Vì hàm này được gọi mà không xác minh content type là multipart/form-data, chúng tôi kiểm soát toàn bộ đối tượng req.body.files. Điều đó có nghĩa chúng tôi kiểm soát tham số filepath – vì vậy thay vì sao chép một tập tin được tải lên, chúng tôi có thể sao chép bất kỳ tập tin cục bộ nào từ hệ thống," Cyera giải thích.

Điều này cho phép đọc các tập tin tùy ý từ một instance n8n, có thể làm lộ các bí mật bằng cách thêm các tập tin nội bộ vào cơ sở tri thức của workflow.

Cyera nói rằng điều này có thể bị lợi dụng để lộ các bí mật được lưu trên instance, chèn các tập tin nhạy cảm vào workflow, giả mạo cookie phiên để vượt qua xác thực, hoặc thậm chí thực thi các lệnh tùy ý.

**Kích hoạt Ni8mare (CVE-2026-21858) để truy cập cơ sở dữ liệu**  
_Source: Cyera_

Cyera nhấn mạnh rằng n8n thường lưu trữ API key, OAuth token, thông tin đăng nhập cơ sở dữ liệu, quyền truy cập lưu trữ đám mây, bí mật CI/CD và dữ liệu kinh doanh, khiến nó trở thành một trung tâm tự động hóa quan trọng.

Các nhà phát triển n8n cho biết hiện không có cách khắc phục chính thức cho Ni8mare, nhưng một biện pháp giảm thiểu là hạn chế hoặc vô hiệu hóa các webhook và endpoint biểu mẫu có thể truy cập công khai.

Hành động được khuyến nghị là cập nhật lên n8n phiên bản 1.121.0 hoặc các phiên bản mới hơn.