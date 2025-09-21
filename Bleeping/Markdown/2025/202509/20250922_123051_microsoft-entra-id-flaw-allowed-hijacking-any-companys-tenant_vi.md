# Microsoft Entra ID lỗ hổng cho phép chiếm đoạt tenant của bất kỳ công ty nào

![Microsoft Entra ID issues gave access to any tenant in the world](https://www.bleepstatic.com/content/hl-images/2025/09/21/MIcrosoft_Entra_ID.jpg)

Một sự kết hợp nghiêm trọng của các thành phần kế thừa có thể đã cho phép truy cập hoàn toàn vào tenant Microsoft Entra ID của mọi công ty trên thế giới.

Sự pha trộn nguy hiểm bao gồm các token không được tài liệu gọi là “actor tokens” và một lỗ hổng trong Azure AD Graph API (CVE-2025-55241) cho phép các token này hoạt động với môi trường Entra ID của bất kỳ tổ chức nào.

Một tác nhân đe dọa khai thác vấn đề này sẽ có quyền truy cập vào rất nhiều dữ liệu nhạy cảm mà không để lại bất kỳ dấu vết nào trong nhật ký trên môi trường bị tấn công, ngoại trừ các hành động của chính họ.

Entra ID là dịch vụ quản lý danh tính và truy cập (IAM) dựa trên đám mây của Microsoft, trước đây được biết đến với tên Azure Active Directory (Azure AD), cung cấp cho các tổ chức đăng nhập một lần, xác thực đa yếu tố và các kiểm soát bảo mật trên các ứng dụng và tài nguyên.

Một instance Entra ID dành riêng đại diện cho một tổ chức và quản lý truy cập an toàn tới tất cả các ứng dụng được sử dụng, cả on-premise và trên đám mây.

Điều này có thể bao gồm các dịch vụ Microsoft 365, các sản phẩm SaaS tùy chỉnh và bên thứ ba như Salesforce, Dropbox, hoặc các ứng dụng đám mây từ Google, Amazon, hoặc SAP.

Nhà nghiên cứu an ninh Dirk-jan Mollema, người sáng lập của Outsider Security, đã phát hiện ra một lỗi xác thực token cho phép anh ta có quyền Global Admin trong mọi tenant Entra ID.

Mức độ truy cập này cho phép thỏa hiệp toàn bộ tenant và mở cửa tới bất kỳ dịch vụ nào được xác thực thông qua Entra ID.

### Mạo danh bất kỳ người dùng nào trong tenant

Trong một bài đăng blog kỹ thuật, Mollema giải thích rằng actor tokens được cấp bởi một dịch vụ kế thừa gọi là Access Control Service, “được sử dụng để xác thực với các ứng dụng SharePoint và cũng dường như được Microsoft sử dụng nội bộ.”

Nhà nghiên cứu phát hiện chúng khi điều tra các thiết lập Exchange hybrid. Anh nhận thấy Exchange sẽ yêu cầu chúng khi giao tiếp với các dịch vụ khác thay mặt cho một người dùng.

“Actor token cho phép nó 'hành động' như một người dùng khác trong tenant khi nói chuyện với Exchange Online, SharePoint và như đã thấy là Azure AD Graph” - Dirk-jan Mollema

Actor tokens không được ký, có nghĩa là chúng có thể được sử dụng để mạo danh bất kỳ người dùng nào trong tenant, và có hiệu lực 24 giờ mà không thể bị thu hồi trong khoảng thời gian này.

Mollema nói rằng “toàn bộ thiết kế Actor token này là điều không bao giờ nên tồn tại,” vì chúng thiếu các kiểm soát bảo mật cần thiết:

* không có nhật ký khi Actor tokens được cấp
* vì các dịch vụ này có thể tạo các token mạo danh không được ký mà không cần nói chuyện với Entra ID, cũng không có nhật ký nào khi chúng được tạo hoặc sử dụng
* chúng không thể bị thu hồi trong thời hạn 24 giờ
* chúng hoàn toàn bỏ qua bất kỳ hạn chế nào được cấu hình trong Conditional Access
* chúng ta phải dựa vào nhật ký từ nhà cung cấp tài nguyên để biết các token này đã được sử dụng trong tenant

Nhà nghiên cứu cho biết Microsoft dựa vào actor tokens nội bộ cho giao tiếp dịch vụ tới dịch vụ và công ty có kế hoạch loại bỏ chúng.

Microsoft gọi chúng là “high-privileged access (HPA)” cho phép một ứng dụng hoặc dịch vụ, "mạo danh người dùng khác mà không cung cấp bất kỳ bằng chứng nào về ngữ cảnh người dùng."

Trong khi thử nghiệm nhiều cách sử dụng actor token, Mollema đã thay đổi tenant ID sang một tenant khác với tenant tạo token, và gửi nó tới Azure AD Graph API đã bị deprecate (graph.windows.net), mong đợi một thông báo “access denied”.

Thay vào đó, lỗi mà nhà nghiên cứu thấy chỉ ra rằng token hợp lệ, nhưng truy cập bị từ chối vì định danh của người dùng không được tìm thấy trong tenant.

![Azure AD Graph error indicates that token is valid but user does not exist](https://www.bleepstatic.com/images/news/u/1100723/Azure-AD-Graph-API-error_Mollema.png)

**Azure AD Graph error indicates that token is valid but user does not exist**  
_source: Dirk-jan Mollema_

Mollema thử lại, lần này với một user ID hợp lệ từ tenant bị nhắm mục tiêu, và thấy Azure AD Graph API trả về dữ liệu được yêu cầu.

“Tôi đã thử điều này trên vài tenant thử nghiệm khác mà tôi có quyền truy cập, để chắc chắn tôi không bị sai, nhưng tôi thực sự có thể truy cập dữ liệu trong các tenant khác, miễn là tôi biết tenant ID của họ (đây là thông tin công khai) và _netId_ của một người dùng trong tenant đó.”

Sử dụng cùng một actor token, nhà nghiên cứu có thể mạo danh Global Administrator trong tenant mục tiêu và thực hiện tất cả các hành động liên quan tới vai trò này (ví dụ: quản lý và tạo người dùng với các vai trò khác nhau, sửa đổi cấu hình, đặt lại mật khẩu, thêm admin).

Mollema nhấn mạnh rằng không có hành động nào cần thiết để có được quyền Global Admin tạo ra bất kỳ nhật ký nào trong tenant nạn nhân.

Từ góc nhìn kẻ tấn công, việc khai thác các vấn đề sẽ khả thi trong vài bước, bắt đầu bằng việc tạo actor token từ một tenant do họ kiểm soát:

* Tìm tenant ID cho môi trường mục tiêu có thể thực hiện bằng các API công khai dựa trên tên miền
* Tìm một _netId_ hợp lệ của một người dùng thường trong tenant mục tiêu
* Tạo một token mạo danh với actor token từ tenant của kẻ tấn công bằng cách sử dụng tenant ID và _netId_ của người dùng trong tenant nạn nhân
* Liệt kê tất cả Global Admin trong tenant và _netId_ của họ
* Tạo token mạo danh cho Global Admin
* Thực hiện bất kỳ hành động đọc/ghi nào thông qua Azure AD Graph API

Mollema lưu ý rằng chỉ hoạt động ở bước cuối cùng sẽ được ghi lại trong tenant nạn nhân.

Cần lưu ý rằng Microsoft đã bắt đầu quá trình deprecation cho dịch vụ Azure AD Graph API từ tháng Chín năm ngoái.

Vào cuối tháng Sáu, công ty cảnh báo rằng các ứng dụng được cấu hình cho extended access nhưng vẫn sử dụng Azure AD Graph sẽ không còn có thể sử dụng các API này kể từ đầu tháng Chín 2025.

Mollema đã báo cáo các vấn đề cho Microsoft vào ngày 14 tháng Bảy và công ty xác nhận rằng vấn đề đã được giải quyết chín ngày sau đó.

Vào ngày 4 tháng Chín, Microsoft cũng đã vá CVE-2025-55241, mô tả đây là một lỗ hổng leo thang đặc quyền nghiêm trọng trong Azure Entra.