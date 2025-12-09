# SAP khắc phục ba lỗ hổng nghiêm trọng trên nhiều sản phẩm

![SAP](https://www.bleepstatic.com/content/hl-images/2025/05/14/SAP.jpg)

SAP đã phát hành các bản cập nhật bảo mật tháng 12 của mình để xử lý 14 lỗ hổng trên nhiều sản phẩm, bao gồm ba lỗ hổng có mức độ nghiêm trọng cao.

Lỗ hổng nghiêm trọng nhất (CVSS score: 9.9) trong số tất cả là [CVE-2025-42880](https://www.cve.org/CVERecord?id=CVE-2025-42880), một vấn đề chèn mã ảnh hưởng tới SAP Solution Manager ST 720.

"Do thiếu kiểm tra dữ liệu đầu vào, SAP Solution Manager cho phép một kẻ tấn công đã xác thực chèn mã độc khi gọi một remote-enabled function module," là phần mô tả của lỗi.

"Điều này có thể cung cấp cho kẻ tấn công toàn quyền kiểm soát hệ thống, do đó gây ảnh hưởng lớn đến tính bảo mật, tính toàn vẹn và khả năng sẵn sàng của hệ thống."

SAP Solution Manager là nền tảng quản lý vòng đời trung tâm và giám sát của nhà cung cấp, được các doanh nghiệp sử dụng cho giám sát hệ thống, cấu hình kỹ thuật, dịch vụ xử lý sự cố và bàn trợ giúp, trung tâm tài liệu và quản lý kiểm thử.

Lỗ hổng nghiêm trọng tiếp theo mà SAP sửa trong tháng này liên quan đến nhiều lỗ hổng Apache Tomcat ảnh hưởng tới các thành phần SAP Commerce Cloud trong các phiên bản HY_COM 2205, COM_CLOUD 2211, và COM_CLOUD 2211-JDK21.

Các lỗ hổng được theo dõi trong SAP Commerce Cloud dưới một định danh duy nhất, [CVE-2025-55754](https://www.cve.org/CVERecord?id=CVE-2025-55754), được cho điểm CVSS 9.6.

SAP Commerce Cloud là một nền tảng thương mại điện tử cấp doanh nghiệp hỗ trợ các cửa hàng trực tuyến quy mô lớn với danh mục sản phẩm, định giá, chương trình khuyến mãi, thanh toán, quản lý đơn hàng, tài khoản khách hàng và tích hợp ERP/CRM. Nó thường được sử dụng bởi các nhà bán lẻ lớn và thương hiệu toàn cầu.

Lỗ hổng thứ ba ở mức nghiêm trọng (CVSS score: 9.1) được sửa trong tháng này là [CVE-2025-42928](https://www.cve.org/CVERecord?id=CVE-2025-42928), một lỗ hổng deserialization ảnh hưởng tới SAP jConnect, vốn trong một số điều kiện có thể cho phép người dùng có đặc quyền cao thực hiện remote code execution trên mục tiêu thông qua dữ liệu đầu vào được chế tạo đặc biệt.

SAP jConnect là một driver JDBC được các nhà phát triển và quản trị cơ sở dữ liệu dùng để kết nối các ứng dụng Java với cơ sở dữ liệu SAP ASE và SAP SQL Anywhere.

Bản tin [December 2025](https://support.sap.com/en/my-support/knowledge-base/security-notes-news/december-2025.html) của SAP cũng liệt kê các bản sửa cho năm lỗ hổng mức cao và sáu vấn đề mức trung bình, bao gồm memory corruption, thiếu kiểm tra xác thực và phân quyền, cross-site scripting và rò rỉ thông tin.

Các giải pháp của SAP được tích hợp sâu trong môi trường doanh nghiệp và quản lý các khối công việc nhạy cảm, có giá trị cao, khiến chúng trở thành mục tiêu quý giá đối với kẻ tấn công.

Đầu năm nay, các nhà nghiên cứu SecurityBridge đã phát hiện các cuộc tấn công ngoài thực tế lợi dụng một lỗ hổng chèn mã (CVE-2025-42957) ảnh hưởng tới triển khai SAP S/4HANA, Business One và NetWeaver.

SAP chưa đánh dấu bất kỳ trong số 14 lỗ hổng là đang bị khai thác tích cực ngoài thực tế, nhưng quản trị viên nên triển khai các bản sửa mà không chậm trễ.