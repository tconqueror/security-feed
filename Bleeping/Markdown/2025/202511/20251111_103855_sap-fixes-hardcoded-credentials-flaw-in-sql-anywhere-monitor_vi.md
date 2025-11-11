# SAP sửa lỗ hổng thông tin đăng nhập được viết cứng vào mã nguồn trong SQL Anywhere Monitor

![SAP sửa lỗ hổng thông tin đăng nhập được viết cứng vào mã nguồn trong SQL Anywhere Monitor](https://www.bleepstatic.com/content/hl-images/2022/02/09/SAP.jpg)

SAP đã phát hành bản cập nhật bảo mật tháng 11 của mình nhằm khắc phục nhiều lỗ hổng bảo mật, bao gồm một lỗ hổng mức nghiêm trọng tối đa trong phiên bản không-GUI của SQL Anywhere Monitor và một vấn đề chèn mã (code injection) nghiêm trọng trong nền tảng Solution Manager.

Vấn đề bảo mật trong SQL Anywhere Monitor được theo dõi dưới mã CVE-2025-42890 và bao gồm thông tin đăng nhập được viết cứng vào mã nguồn. Do rủi ro tăng cao, lỗ hổng này được chấm điểm mức nghiêm trọng tối đa là 10.0.

“SQL Anywhere Monitor (Non-GUI) đã nhúng thông tin đăng nhập vào mã, làm lộ tài nguyên hoặc chức năng cho người dùng không mong muốn và cung cấp cho kẻ tấn công khả năng thực thi mã tùy ý,” theo [mô tả](https://nvd.nist.gov/vuln/detail/CVE-2025-42890) về lỗ hổng.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Tùy cách sử dụng, kẻ tấn công có được các thông tin đăng nhập này có thể sử dụng chúng để truy cập các chức năng quản trị.

SQL Anywhere Monitor là một công cụ giám sát cơ sở dữ liệu và cảnh báo, là một phần của bộ SQL Anywhere, thường được các tổ chức quản lý các cơ sở dữ liệu phân tán hoặc từ xa sử dụng.

Thành phần monitor không-GUI thường được triển khai trên các thiết bị không có người giám sát, nơi nó chạy mà không có sự giám sát thường xuyên của con người.

Lỗ hổng quan trọng thứ hai, được xác định là CVE-2025-42887, có điểm mức nghiêm trọng 9.9 và ảnh hưởng đến SAP Solution Manager, một nền tảng quản lý vòng đời ứng dụng.

“Do thiếu kiểm tra đầu vào, SAP Solution Manager cho phép một kẻ tấn công đã xác thực chèn mã độc khi gọi một function module được bật remote,” theo [mục nhập](https://nvd.nist.gov/vuln/detail/CVE-2025-42887) trong National Vulnerability Database.

“Điều này có thể cung cấp cho kẻ tấn công quyền kiểm soát đầy đủ hệ thống, do đó dẫn đến tác động lớn đến tính bảo mật, tính toàn vẹn và tính khả dụng của hệ thống.”

SAP Solution Manager là một nền tảng quản lý và giám sát tập trung cho các môi trường SAP, thường được các doanh nghiệp lớn sử dụng, những đơn vị vận hành mạng lưới phức tạp bao gồm ERP, CRM và các giải pháp phân tích.

Trong bối cảnh gói cập nhật bảo mật tháng 11 năm 2025, SAP cũng phát hành bản sửa cho một lỗ hổng mức cao (CVE-2025-42940) và 14 lỗ hổng khác ở mức trung bình.

Ngoài ra, gã khổng lồ phần mềm của Đức cũng phát hành các bản cập nhật cho CVE-2025-42944, một lỗ hổng nghiêm trọng trong NetWeaver đã được xử lý ban đầu vào tháng trước.

Các sản phẩm SAP, được triển khai rộng rãi trong các doanh nghiệp lớn và được giao giữ dữ liệu quan trọng, thường xuyên là mục tiêu của những tác nhân đe dọa tìm cách truy cập giá trị cao.

Đầu năm nay, các nhà nghiên cứu SecurityBridge đã báo cáo việc khai thác tích cực một lỗ hổng chèn mã nghiêm trọng, được theo dõi là CVE-2025-42957, ảnh hưởng đến SAP S/4HANA, Business One và các hệ thống NetWeaver.

Chưa phát hiện việc khai thác tích cực đối với hai lỗ hổng nghiêm trọng mà SAP đã sửa hôm nay, nhưng quản trị viên hệ thống được khuyến cáo áp dụng các bản cập nhật có sẵn càng sớm càng tốt và tuân theo các khuyến nghị giảm thiểu của nhà cung cấp cho CVE-2025-42890 và CVE-2025-42887 (chỉ truy cập được cho những người có tài khoản).