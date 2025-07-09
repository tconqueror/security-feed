# Lỗi mới của ServiceNow cho phép kẻ tấn công thống kê dữ liệu bị hạn chế

![Data leak](https://www.bleepstatic.com/content/hl-images/2024/08/16/data-leak.jpg)

Một lỗ hổng mới trong ServiceNow, được gọi là Count(er) Strike, cho phép người dùng có quyền hạn thấp trích xuất dữ liệu nhạy cảm từ các bảng mà họ không nên có quyền truy cập.

ServiceNow là một nền tảng đám mây cho phép các tổ chức quản lý các quy trình công việc kỹ thuật số cho hoạt động doanh nghiệp của họ. Nó được áp dụng rộng rãi trong nhiều ngành, bao gồm các tổ chức khu vực công, y tế, các tổ chức tài chính và các doanh nghiệp lớn.

Lỗi này được Varonis Threat Labs phát hiện vào tháng 2 năm 2025 và được gán mã định danh CVE-2025-3648, có thể ảnh hưởng đến các cấu hình có ACL (Access Control Lists) đã cấu hình sai hoặc quá lỏng.

ServiceNow [đã phát hành các khung kiểm soát truy cập bổ sung](https://support.servicenow.com/kb?id=kb%5Farticle%5Fview&sysparm%5Farticle=KB2139567) trong các phiên bản Xanadu và Yokohama, được phát hành vào tháng trước, để giải quyết vấn đề này. Tuy nhiên, tất cả các quản trị viên nên xem xét lại các bảng hiện có để đảm bảo rằng dữ liệu của họ được bảo vệ đúng cách.

## Lỗi Count(er) Strike

ServiceNow sử dụng Access Control Lists (ACL) để hạn chế quyền truy cập vào dữ liệu trong các bảng của mình. Mỗi ACL đánh giá bốn điều kiện khi xác định liệu một người dùng có nên có quyền truy cập vào một tài nguyên cụ thể hay không:

* Các vai trò yêu cầu
* Các thuộc tính bảo mật
* Các điều kiện dữ liệu
* Các điều kiện kịch bản

Để người dùng có được quyền truy cập vào một tài nguyên, tất cả các điều kiện này phải được thỏa mãn.

Tuy nhiên, nếu một tài nguyên được bảo vệ bằng nhiều ACL, trước đây ServiceNow đã sử dụng điều kiện "Cho phép nếu", có nghĩa là nếu một người dùng thỏa mãn chỉ một ACL, họ có thể truy cập, ngay cả khi các ACL khác có thể đã chặn họ.

Trong một số trường hợp, điều này cho phép truy cập hoàn toàn. Tuy nhiên, trong những trường hợp khác, nó cho phép truy cập một phần, chẳng hạn như số lượng bản ghi có thể bị khai thác, như đã giải thích trong phần sau của bài viết.

"Mỗi tài nguyên hoặc bảng trong ServiceNow có thể có nhiều ACL, mỗi cái định nghĩa các điều kiện khác nhau để truy cập," [giải thích báo cáo của Varonis.](https://www.varonis.com/blog/counter-strike-servicenow).

"Tuy nhiên, nếu một người dùng vượt qua chỉ một ACL, họ sẽ có quyền truy cập vào tài nguyên, ngay cả khi các ACL khác có thể không cấp quyền truy cập. Nếu không có ACL nào cho tài nguyên đó, quyền truy cập sẽ mặc định vào thuộc tính truy cập mặc định, được đặt thành từ chối trong hầu hết các trường hợp."

Mô hình lỏng lẻo này đã dẫn Varonis phát hiện ra rằng có thể đạt được quyền truy cập một phần, điều này có thể được sử dụng để thống kê dữ liệu bảo vệ, ngay cả khi người dùng không qua được các ACL nghiêm ngặt hơn.

Varonis phát hiện ra rằng nếu một người dùng không vượt qua điều kiện `data` hoặc điều kiện `script`, ServiceNow vẫn trả về số lượng bản ghi trong UI và HTML nguồn. Trang cũng ghi rõ rằng một số kết quả đã bị xóa do các ràng buộc bảo mật.

![Restricted data still showing record counts and fields](https://www.bleepstatic.com/images/news/security/vulnerabilities/s/servicenow/counterstrike/record-counts.png)

**Dữ liệu bị hạn chế vẫn hiển thị số lượng bản ghi và các trường dữ liệu**  
_Nguồn: Varonis_

Với dữ liệu một phần này, Varonis đã bắt đầu thao tác với các bộ lọc dựa trên URL, chẳng hạn như `STARTSWITH`, `CONTAINS`, `=`, và `!=` để thống kê nội dung của các bản ghi từng ký tự hoặc điều kiện này một lúc.

Ví dụ:

```
https://[my_company].service-now.com/task_list.do?sysparm_query=short_descriptionSTARTSWITHp
```

Lặp lại quy trình này với các giá trị và truy vấn khác nhau cho phép lấy lại dữ liệu từng ký tự hoặc chữ số một.

Để tự động hóa quy trình này, Varonis đã tạo một script thành công trong việc thống kê các bản ghi dữ liệu từ một bảng mà họ chỉ có quyền truy cập hạn chế.

![Enumerating data using a script](https://www.bleepstatic.com/images/news/security/vulnerabilities/s/servicenow/counterstrike/enumerating-dta.png)

**Thống kê dữ liệu bằng một script**  
_Nguồn: Varonis_

Ngay cả khi dữ liệu bản ghi không được hiển thị, số lượng bản ghi rò rỉ đủ thông tin để xác định các trường, bao gồm thông tin xác thực, PII, và dữ liệu cấu hình nội bộ.

Varonis cảnh báo rằng người dùng đăng ký tự động cũng có thể sử dụng cuộc tấn công này. Tính năng tự đăng ký cho phép người dùng tạo tài khoản và truy cập vào phiên bản với các quyền hạn tối thiểu, điều này vẫn có thể được sử dụng để phát động một cuộc tấn công.

"Mặc dù hiếm khi các phiên bản cho phép đăng ký vô danh và truy cập, nhưng cấu hình này đã được tìm thấy trong các hệ thống ServiceNow của một số công ty Fortune 500," cảnh báo Varonis.

## Giảm thiểu cuộc tấn công

Varonis đã nói với BleepingComputer rằng họ đã thử nghiệm cuộc tấn công này trên sản phẩm ITSM của ServiceNow, nhưng cho biết rằng nó cũng nên áp dụng cho tất cả các sản phẩm ServiceNow sử dụng cùng logic ACL.

ServiceNow hiện đã khắc phục cuộc tấn công bằng cách:

* Giới thiệu các ACL 'Deny Unless', yêu cầu người dùng phải vượt qua **tất cả** các ACL để có quyền truy cập vào dữ liệu.
* Thêm Query ACLs, hạn chế các truy vấn thống kê loại này bằng cách sử dụng các toán tử phạm vi.
* Khuyến nghị sử dụng Security Data Filters, điều này ẩn số lượng dòng và ngăn chặn các tín hiệu suy luận.

Tuy nhiên, khách hàng vẫn nên kiểm tra lại các bảng của mình và chỉnh sửa các ACL để đảm bảo chúng không quá lỏng lẻo, và do đó dễ bị tổn thương trước cuộc tấn công này.

Varonis cho biết họ chưa thấy có bằng chứng cho thấy lỗ hổng này đã bị khai thác trong thực tế.