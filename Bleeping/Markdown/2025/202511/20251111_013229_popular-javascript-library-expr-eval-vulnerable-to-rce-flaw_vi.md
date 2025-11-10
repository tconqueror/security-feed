# Thư viện JavaScript phổ biến expr-eval dễ bị lỗ hổng RCE

![Thư viện JavaScript phổ biến expr-eval dễ bị lỗ hổng RCE](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_headpic.jpg)

Một lỗ hổng nghiêm trọng trong thư viện JavaScript _expr-eval_ phổ biến, có hơn 800.000 lượt tải xuống mỗi tuần trên NPM, có thể bị lợi dụng để thực thi mã từ xa thông qua dữ liệu đầu vào được tạo độc hại.

Vấn đề bảo mật được phát hiện bởi nhà nghiên cứu bảo mật Jangwoo Choe và được theo dõi dưới mã [CVE-2025-12735](https://nvd.nist.gov/vuln/detail/CVE-2025-12735). Theo U.S. Cybersecurity and Infrastructure Security Agency (CISA), mức độ nghiêm trọng được đánh giá là critical, với điểm 9.8.

Được phát triển ban đầu bởi Matthew Crumley, [expr-eval](https://www.npmjs.com/package/expr-eval) là một bộ phân tích và đánh giá biểu thức JavaScript nhỏ, được dùng trong các dự án cần phân tích an toàn và tính toán các biểu thức toán học do người dùng cung cấp tại thời gian chạy.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP)

Ví dụ bao gồm các máy tính trực tuyến, bộ công cụ giáo dục, công cụ mô phỏng, công cụ tài chính, và gần đây hơn là các hệ thống AI và xử lý ngôn ngữ tự nhiên (NLP) phân tích các biểu thức toán học từ phần mô tả văn bản.

Trong một khuyến cáo vào cuối tuần, CERT Coordination Center (CERT-CC) thuộc Software Engineering Institute (SEI) của Carnegie Mellon cho biết lỗ hổng là do thư viện không kiểm tra đối tượng biến/bối cảnh được truyền vào hàm _Parser.evaluate()_, cho phép kẻ tấn công cung cấp các đối tượng function độc hại mà trình phân tích sẽ gọi trong quá trình đánh giá.

"Một lỗ hổng cho phép đối phương kiểm soát hoàn toàn hành vi của phần mềm hoặc tiết lộ toàn bộ thông tin trên hệ thống bị ảnh hưởng" - [CERT-CC](https://kb.cert.org/vuls/id/263614)

CVE-2025-12735 ảnh hưởng cả phiên bản gốc expr-eval, với phiên bản ổn định được phát hành cách đây 6 năm, và fork đang được duy trì tích cực hiện nay, _expr-eval-fork_, có hơn 80.000 lượt tải xuống hàng tuần trên kho NPM cho Node.js.

Dựa trên dữ liệu từ npmjs.com, thư viện được sử dụng trong hơn 250 dự án. Một bản sửa bảo mật cho CVE-2025-12735 có trong [expr-eval-fork version 3.0.0](https://www.npmjs.com/package/expr-eval-fork), với khuyến nghị rằng các dự án bị ảnh hưởng nên chuyển sang phiên bản này càng sớm càng tốt.

Bản vá thực thi một allowlist các hàm an toàn để đánh giá, một hệ thống đăng ký cho các hàm tùy chỉnh, và tăng cường độ bao phủ kiểm thử cho các ràng buộc này.

Đối với người dùng expr-eval, hiện có một [pull request](https://github.com/silentmatt/expr-eval/pull/288) thực hiện bản sửa; tuy nhiên, do các người duy trì dự án không phản hồi, không rõ khi nào nó sẽ được gộp vào một phát hành mới.

Các nhà phát triển phần mềm bị ảnh hưởng được khuyến cáo di chuyển ngay lập tức sang expr-eval-fork v3.0.0 và công bố lại thư viện của họ để người dùng nhận được bản sửa.