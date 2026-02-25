# Định Mức Ưu Tiên Danh Tính Không Phải Là Vấn Đề Của Danh Sách Công Việc - Đó Là Vấn Đề Toán Học Về Rủi Ro

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgMTMMgXEuUSPrdURyFMOZE-RcFyvZCBxQS7hyphenhyphenRvjSZ2FVcKyDWdsHgAmWv5qQg72UCTBEwWtlNs8FDhNnhh8u%5F-tmcAa9hLAljsN8sezEmXwujJ5Gc12LLbC8tA%5FOkxnpQPNjPUxQj0516b7Nbz%5FahD8yX9K2RWbSSK7bu%5FdtBLVhA0EjxGsSp6Dic9jI/s1700-e365/main.gif)

Hầu hết các chương trình danh tính vẫn ưu tiên công việc theo cách họ ưu tiên các phiếu yêu cầu IT: theo khối lượng, mức độ ồn ào, hoặc "cái gì đã không vượt qua kiểm tra kiểm soát". Cách tiếp cận này sẽ phá vỡ ngay khi môi trường của bạn ngừng chủ yếu là con người và chủ yếu là đã được onboard.

Trong các doanh nghiệp hiện đại, rủi ro danh tính được tạo ra bởi sự kết hợp của nhiều yếu tố: tư thế kiểm soát, vệ sinh, bối cảnh kinh doanh, và ý định. Bất kỳ yếu tố nào trong số này có thể có thể kiểm soát được một mình. Nguy hiểm thực sự là sự kết hợp độc hại, khi nhiều điểm yếu cùng nhau và kẻ tấn công có được một chuỗi sạch từ điểm vào đến tác động.

Một khuôn khổ ưu tiên hữu ích coi rủi ro danh tính là phơi bày ngữ cảnh, không phải là sự hoàn chỉnh về cấu hình.

## **1\. Tư Thế Kiểm Soát: Tuân Thủ và Bảo Mật Là Tín Hiệu Rủi Ro, Không Phải Là Hộp Kiểm**

Tư thế kiểm soát trả lời một câu hỏi đơn giản: Nếu có điều gì đó sai, chúng ta có ngăn chặn được không, phát hiện được không, và chứng minh được không?

Trong các chương trình IAM cổ điển, kiểm soát được đánh giá là "đã cấu hình / chưa cấu hình". Nhưng ưu tiên cần nhiều sắc thái hơn: một kiểm soát bị thiếu là một bộ khuếch đại rủi ro mà mức độ nghiêm trọng phụ thuộc vào danh tính nào nó bảo vệ, danh tính đó có thể làm gì và các kiểm soát khác có thể đã có ở hạ nguồn.

Các danh mục kiểm soát chính trực tiếp định hình phơi bày:

* **Kiểm soát Xác thực & Phiên**
* MFA, thực thi SSO, hết hạn phiên/phiên, kiểm soát làm mới, giới hạn tốc độ đăng nhập, khóa tài khoản.
* **Quản lý Danh tính & Bí mật**
* Không có thông tin xác thực rõ ràng/nhúng cứng, băm mạnh, sử dụng IdP an toàn, xoay vòng bí mật đúng cách.
* **Kiểm soát Phân quyền & Truy cập**
* Thực thi kiểm soát truy cập, đăng nhập và thử nghiệm phân quyền được kiểm toán, chuyển hướng/callback an toàn cho luồng SSO.
* **Kiểm soát Giao thức & Mật mã**
* Giao thức tiêu chuẩn ngành, tránh các giao thức cũ, và tư thế hướng tới tương lai (ví dụ: an toàn lượng tử).

[](https://eu1.hubs.ly/H0qBxh30)

**Lăng kính ưu tiên** - các kiểm soát bị thiếu không quan trọng như nhau ở mọi nơi. Thiếu MFA trên danh tính tác động thấp không giống như thiếu MFA trên danh tính đặc quyền liên quan đến hệ thống kinh doanh quan trọng. Tư thế kiểm soát phải được đánh giá trong ngữ cảnh.

[ ](https://eu1.hubs.ly/H0r-TLL0) 

**[Các Lỗ Hổng Bảo Mật Danh Tính Hàng Đầu Cần Tìm và Đóng](https://eu1.hubs.ly/H0r-TLL0)**

Một danh sách kiểm tra thực tế để giúp bạn đánh giá tài sản ứng dụng của mình và cải thiện tư thế bảo mật danh tính của tổ chức bằng cách:

* Xác định khoảng trống nào phổ biến nhất
* Giải thích ngắn gọn tại sao chúng quan trọng để giải quyết
* Đề xuất các hành động cụ thể để thực hiện với các công cụ/quy trình hiện có
* Cân nhắc bổ sung cần lưu ý

**[Tải xuống danh sách kiểm tra](https://eu1.hubs.ly/H0r-TLL0)**

## **2\. Vệ Sinh Danh Tính: Những Điểm Yếu Cấu Trúc Mà Kẻ Tấn Công (và Đại Lý AI Tự Động của bạn) Yêu Thích**

Vệ sinh không phải là về sự gọn gàng; nó là về quyền sở hữu, vòng đời, và ý định. Vệ sinh trả lời: Ai sở hữu danh tính này? Tại sao nó tồn tại? Nó còn cần thiết không?

Các điều kiện vệ sinh phổ biến nhất tạo ra phơi bày hệ thống:

* **Danh tính cục bộ** - Bỏ qua các chính sách tập trung (SSO/MFA/truy cập có điều kiện), lệch khỏi tiêu chuẩn, khó kiểm toán hơn.
* **[Danh tính mồ côi](https://eu1.hubs.ly/H0qBxd60)** - Không có chủ sở hữu chịu trách nhiệm = không ai nhận thấy lạm dụng, không ai dọn dẹp, không ai xác nhận.
* **Danh tính ngủ đông** - "Không sử dụng" không có nghĩa là an toàn, ngủ đông thường có nghĩa là không được giám sát và tồn tại.
* **Danh tính phi con người (NHIs) không có quyền sở hữu hoặc mục đích rõ ràng** - Danh tính dịch vụ, token API, danh tính đại lý phát triển với tự động hóa và luồng công việc đại lý.
* **Danh tính dịch vụ và token cũ** - Đặc quyền tích lũy, xoay vòng dừng lại, và "tạm thời" trở thành vĩnh viễn.

**Lăng kính ưu tiên** - Các vấn đề vệ sinh là nguyên liệu thô của các vụ vi phạm. Kẻ tấn công thích danh tính bị bỏ quên vì chúng ít được bảo vệ, ít được giám sát, và có nhiều khả năng giữ lại đặc quyền dư thừa.

## **3\. Bối Cảnh Kinh Doanh: Rủi Ro Tỷ Lệ Thuận với Tác Động, không Chỉ Là Khả Năng Khai Thác**

Các nhóm bảo mật thường ưu tiên dựa trên mức độ nghiêm trọng kỹ thuật một mình. Điều đó là chưa đầy đủ. Bối cảnh kinh doanh hỏi: Nếu bị xâm phạm, cái gì sẽ bị hỏng?

Bối cảnh kinh doanh bao gồm:

* **Tính quan trọng của kinh doanh** của ứng dụng hoặc luồng công việc (doanh thu, vận hành, niềm tin của khách hàng)
* **Độ nhạy dữ liệu** (PII, PHI, dữ liệu tài chính, dữ liệu được quy định)
* **Bán kính nổ** qua các đường dẫn tin cậy (hệ thống hạ nguồn nào trở nên có thể truy cập được)
* **Phụ thuộc vận hành** (cái gì gây ra sự cố, giao hàng trễ, lương thất bại, v.v.)

**Lăng kính ưu tiên** - Rủi ro danh tính không chỉ là "kẻ tấn công có thể vào được không," mà là "điều gì xảy ra nếu họ làm vậy." Phơi bày mức độ nghiêm trọng cao trong hệ thống tác động thấp không nên vượt qua phơi bày mức độ vừa phải trong hệ thống then chốt sứ mệnh.

## **4\. Ý Định Người Dùng: Chiều Kích Thiếu Trong Hầu Hết Các Chương Trình Danh Tính**

Các quyết định danh tính thường được đưa ra mà không trả lời: Danh tính này đang cố gắng làm gì ngay bây giờ, và điều đó có phù hợp với mục đích của nó không?

Ý định trở nên quan trọng với:

* **Luồng công việc đại lý** tự động gọi công cụ và thực hiện hành động
* **Mẫu M2M** trông hợp lệ nhưng có thể bất thường trong trình tự hoặc đích đến
* **Hành vi rủi ro nội bộ** nơi thông tin xác thực hợp lệ nhưng cách sử dụng thì không

Các tín hiệu giúp suy luận ý định bao gồm:

* Mẫu tương tác (công cụ/điểm cuối nào được gọi, theo thứ tự nào)
* Bất thường dựa trên thời gian và tần suất truy cập
* Sử dụng đặc quyền vs. đặc quyền được giao (điều gì thực sự được thực hiện)
* Hành vi di chuyển ngang qua ứng dụng (chuyển động ngang bất thường)

**Lăng kính ưu tiên** - Một danh tính được kiểm soát yếu với _ý định hoạt động, bất thường_ nên nhảy lên đầu hàng đợi, vì nó không chỉ dễ bị tổn thương, nó có thể đang được sử dụng _ngay bây giờ_.

[](https://eu1.hubs.ly/H0rjCJ20)

### **Sự Kết Hợp Độc Hại: Nơi Rủi Ro Trở Nên Phi Tuyến Tính**

Sai lầm ưu tiên lớn nhất là coi các vấn đề là cộng dồn. Các sự cố danh tính thực tế là nhân: kẻ tấn công chuỗi các điểm yếu. Rủi ro tăng theo cấp số nhân khi các khoảng trống kiểm soát, vệ sinh kém, tác động cao, và ý định đáng ngờ cùng nhau.

Ví dụ về các kết hợp độc hại nên được coi là "bỏ tất cả":

#### **Kết Hợp Độc Hại Cấp Độ Nhập (Mục Tiêu Dễ)**

* Danh tính mồ côi + thiếu MFA
* Danh tính mồ côi + thiếu MFA + thiếu giới hạn tốc độ đăng nhập
* Danh tính cục bộ + thiếu ghi nhật ký kiểm toán cho đăng nhập/phân quyền
* Danh tính mồ côi + đặc quyền quá mức (ngay cả khi hôm nay "không có gì trông sai")

#### **Rủi Ro Khai Thác Tích Cực (Nhạy Cảm Về Thời Gian)**

* Danh tính mồ côi + thiếu MFA + hoạt động gần đây
* Danh tính ngủ đông + hoạt động gần đây (tại sao nó thức dậy?)
* Danh tính cục bộ + chỉ báo thông tin xác thực bị lộ (hoặc mẫu nhúng cứng đã biết)

#### **Phơi Bày Hệ Thống Mức Độ Nghiêm Trọng Cao**

* Danh tính mồ côi + thiếu MFA + thiếu giới hạn tốc độ
* Danh tính cục bộ + thiếu ghi nhật ký kiểm toán + thiếu giới hạn tốc độ (đường dẫn xâm phạm thầm lặng)
* NHI ngủ đông + thông tin xác thực nhúng cứng + không ghi nhật ký kiểm toán (truy cập máy tồn tại, vô hình)
* Thêm tính quan trọng của kinh doanh và truy cập dữ liệu nhạy cảm, và bạn có rủi ro cấp hội đồng quản trị.

#### **Cảnh Báo Vi Phạm**

* Danh tính mồ côi + danh tính ngủ đông + thiếu MFA + thiếu giới hạn tốc độ + hoạt động gần đây (ra khỏi giai đoạn ngủ đông)
* Danh tính cục bộ + danh tính ngủ đông + thiếu giới hạn tốc độ + hoạt động gần đây
* NHI ngủ đông + thông tin xác thực nhúng cứng + sử dụng danh tính đồng thời

Đây là trọng tâm của việc ưu tiên danh tính: sự kết hợp độc hại định nghĩa rủi ro, không phải bất kỳ phát hiện đơn lẻ nào trong cô lập.

### **Một Mô Hình Ưu Tiên Thực Tế Bạn Có Thể Sử Dụng**

Khi bạn quyết định sửa cái gì trước, hãy đặt bốn câu hỏi:

1. **Tư thế kiểm soát:** kiểm soát phòng ngừa/phát hiện/xác nhận nào bị thiếu?
2. **Vệ sinh danh tính:** chúng ta có quyền sở hữu, rõ ràng vòng đời, và sự tồn tại có mục đích không?
3. **Bối cảnh kinh doanh:** tác động là gì nếu bị xâm phạm?
4. **Ý định người dùng:** hoạt động có phù hợp với mục đích không, hay nó báo hiệu lạm dụng?

Sau đó ưu tiên công việc mang lại giảm rủi ro nhiều nhất, không phải đóng nhiều hộp kiểm nhất:

* Sửa một kết hợp độc hại có thể loại bỏ rủi ro tương đương với sửa hàng chục phát hiện ngữ cảnh thấp.
* Mục tiêu là bề mặt phơi bày thu hẹp, không phải bảng điều khiển đẹp hơn.

## **Điểm Mấu Chốt**

Rủi ro danh tính không phải là danh sách, nó là một đồ thị các đường dẫn tin cậy cộng với ngữ cảnh. Tư thế kiểm soát, vệ sinh, bối cảnh kinh doanh, và ý định mỗi cái đều quan trọng một mình, nhưng nguy hiểm đến từ sự cùng nhau của chúng. Nếu bạn xây dựng ưu tiên xung quanh các kết hợp độc hại, bạn ngừng theo đuổi khối lượng và bắt đầu giảm khả năng vi phạm thực tế và phơi bày kiểm toán.

### **[Orchid Giải Quyết Như Thế Nào](https://eu1.hubs.ly/H0qBxh00)**

[Orchid](https://eu1.hubs.ly/H0qBxh00) khám phá thụ động toàn bộ tài sản ứng dụng được quản lý hoặc không được quản lý và danh tính qua telemetry, xây dựng đồ thị danh tính, và chuyển đổi tín hiệu tư thế + vệ sinh + bối cảnh kinh doanh + hoạt động thành điểm rủi ro ngữ cảnh. Nó xếp hạng các kết hợp độc hại quan trọng nhất, qua mức độ nghiêm trọng động sản xuất kế hoạch khắc phục có trình tự, và sau đó thúc đẩy onboard không cần code vào quản trị (danh tính được quản lý/chính sách IGA) với giám sát liên tục, vì vậy các nhóm giảm phơi bày thực tế nhanh, không chỉ đóng nhiều phát hiện nhất.