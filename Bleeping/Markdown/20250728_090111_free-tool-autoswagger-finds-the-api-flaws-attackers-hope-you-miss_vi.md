# Công Cụ Miễn Phí Autoswagger Tìm Ra Các Lỗ Hổng API Mà Kẻ Tấn Công Hy Vọng Bạn Bỏ Qua

![Autoswagger header](https://www.bleepstatic.com/content/posts/2025/07/23/header-autoswagger.jpg)

## APIs: Vẫn Là Mục Tiêu Dễ Dàng Năm 2025

APIs là xương sống của các ứng dụng hiện đại - và là một trong những phần nhạy cảm nhất của hạ tầng tổ chức. Điều này khiến chúng trở thành mục tiêu hàng đầu cho các kẻ tấn công.

Một trong những ví dụ nổi bật nhất là vụ [vi phạm Optus](https://www.bbc.co.uk/news/world-australia-63056838) vào năm 2022, nơi các kẻ tấn công đã đánh cắp hàng triệu hồ sơ khách hàng thông qua một điểm cuối API không được xác thực - khiến công ty viễn thông này thiệt hại 140 triệu AUD.

Đáng lo ngại, các lỗ hổng như thế này dễ dàng bị khai thác đến mức bạn có thể dạy cho một người không có nền tảng kỹ thuật cách làm trong một ngày. Và ba năm sau, đội ngũ an ninh của [Intruder](https://www.intruder.io?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger) vẫn đang phát hiện ra những vấn đề tương tự trong các API của các tổ chức lớn - bao gồm cả các thành viên của S&P 500.

Đó là lý do tại sao chúng tôi đã xây dựng [Autoswagger](https://github.com/intruder-io/autoswagger/) - một công cụ miễn phí, mã nguồn mở quét các API để phát hiện các lỗ hổng xác thực. Hãy tiếp tục đọc để xem nó hoạt động như thế nào và một số vấn đề bất ngờ mà nó phát hiện ra khi chúng tôi kiểm tra.

## Autoswagger là gì và nó hoạt động như thế nào?

[Autoswagger](https://github.com/intruder-io/autoswagger/) quét các miền để phát hiện tài liệu API bị rò rỉ - như OpenAPI hoặc các sơ đồ Swagger - sau đó phân tích chúng để tạo danh sách các điểm cuối cần kiểm tra. Nó gửi yêu cầu sử dụng các tham số hợp lệ từ tài liệu và đánh dấu bất kỳ điểm cuối nào trả lại dữ liệu mà không có kiểm soát truy cập hợp lý (tức là không có 401 hoặc 403).

Nếu một phản hồi bao gồm dữ liệu nhạy cảm - như thông tin đăng nhập hoặc thông tin cá nhân (PII) - và điểm cuối không được bảo mật đúng cách, nó sẽ được đánh dấu trong đầu ra.

![Autoswagger tool](https://www.bleepstatic.com/images/news/security/i/intruder/autoswagger/autoswagger.jpg)

Autoswagger có thể tải xuống và cài đặt miễn phí qua **[GitHub](https://github.com/intruder-io/autoswagger/)**.

Để kiểm tra nâng cao hơn, [Autoswagger](https://github.com/intruder-io/autoswagger/) có thể được chạy với cờ --brute để cố gắng vượt qua các kiểm tra xác thực. Điều này giúp phát hiện các lỗi trong những điểm cuối từ chối đầu vào chung nhưng chấp nhận các định dạng hoặc giá trị dữ liệu cụ thể.

## [Bảo Mật API Luôn Bật Mà Không Gây Ồn Ào](https://www.intruder.io/use-cases/api-security?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger%5Fcta)

APIs là một trong những cách dễ nhất để vào hệ thống - và các kẻ tấn công biết điều này.

Hàng ngàn đội ngũ tin tưởng vào nền tảng quản lý rò rỉ luôn bật của Intruder để bảo mật ứng dụng và API của họ và khắc phục các vấn đề nghiêm trọng trước khi các kẻ tấn công tìm ra chúng. Tải lên sơ đồ API của bạn và có được sự an tâm trong vài phút.

[Thử Miễn Phí](https://www.intruder.io/use-cases/api-security?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger%5Fcta)

## Xác Thực Bị Lỗi Trong Hành Động: Bốn Lỗ Hổng API Thực Tế được Tìm Thấy Bằng Autoswagger

Chúng tôi đã đưa [Autoswagger](https://github.com/intruder-io/autoswagger/) vào thử nghiệm trên các mục tiêu từ một số chương trình Bug Bounty lớn, quét các API dễ bị tấn công trên quy mô lớn.

Dưới đây là một vài ví dụ thực tế để cho bạn thấy xác thực bị lỗi trông như thế nào trong thực tế.

**Thông Tin Đăng Nhập Microsoft MPN**

Một lỗ hổng mà chúng tôi tìm thấy là ở một điểm cuối đơn giản tên là ‘config’, đã rò rỉ thông tin đăng nhập và khóa API cho các kho dữ liệu của Chương trình Đối tác Microsoft. Trong số dữ liệu bị rò rỉ có một bộ thông tin đăng nhập hợp lệ cho một cơ sở dữ liệu Redis chứa PII của các đối tác, bao gồm các khóa học và chứng nhận mà họ đã tham gia.

Điểm cuối dễ bị tấn công này được chôn sâu sáu lớp (/1/dashboard/mpn/program/api/config/), khiến việc đoán hoặc phát hiện thông qua brute-force gần như không thể - nó chỉ được xác định vì sơ đồ OpenAPI của API này đã bị rò rỉ.

**Hơn 60,000 Hồ Sơ Salesforce**

Một trường hợp khác liên quan đến một API kết nối với một phiên bản Salesforce tại một công ty công nghệ lớn. API này trả lại hồ sơ khách hàng - bao gồm tên, thông tin liên lạc và đơn hàng sản phẩm - mà có thể được trích xuất hàng loạt bằng cách gia tăng tham số url ‘ByDate’ để lấy 1,000 hồ sơ mỗi yêu cầu.

**Truy Cập SQL trên Ứng Dụng Đào Tạo Nội Bộ**

Chúng tôi cũng tìm thấy một API đào tạo nhân viên nội bộ tại một công ty nước giải khát nổi tiếng, chạy trên Azure Functions, cho phép người dùng không xác thực chạy các truy vấn SQL tùy ý trên cơ sở dữ liệu.

Mặc dù dữ liệu bị giới hạn trong các hồ sơ đào tạo nội bộ, nhưng nó bao gồm tên và địa chỉ email của nhân viên - loại chi tiết mà kẻ tấn công có thể sử dụng để tạo ra một chiến dịch lừa đảo thuyết phục.

Các API Azure Functions thường không công khai tài liệu, nhưng một nhà phát triển đã triển khai một phần mở rộng mà đã làm như vậy. Mặc dù có thể điều này là cho một dịch vụ khác tiêu thụ, nhưng không có lý do rõ ràng nào để nó có thể truy cập công khai vì ứng dụng này nhằm mục đích sử dụng nội bộ.

**Liệt Kê Người Dùng Active Directory (AD) (Octopus Deploy)**

Cuối cùng, Autoswagger đã phát hiện ra [CVE-2025-0589](https://cvemon.intruder.io/cves/CVE-2025-0589?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger), cho phép một kẻ tấn công không xác thực [liệt kê thông tin người dùng Active Directory](https://www.intruder.io/research/octopus-deploy-cve-2025-0589?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger) nếu AD được tích hợp với máy chủ Octopus Deploy.

## Tài Liệu Tự Động = Rủi Ro Bề Mặt Tấn Công

Tài liệu API tự động rất tuyệt cho các nhà phát triển - nhưng cũng hữu ích cho các kẻ tấn công. Khi sơ đồ API bị rò rỉ, nó cung cấp cho họ một bản đồ rõ ràng của mọi điểm cuối để nhắm mục tiêu. Nếu không có bản đồ đó, hầu hết sẽ không bận tâm - fuzzing các điểm cuối một cách mù quáng mất nhiều công sức hơn.

Giấu tài liệu không phải là một sự thay thế cho quản lý [lỗ hổng API](https://www.intruder.io/use-cases/api-security?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger) đúng đắn, nhưng việc công khai những tài liệu bạn không cần là một rủi ro không cần thiết. Hầu hết các lỗ hổng mà chúng tôi tìm thấy nằm trong các API không bao giờ có ý định trở thành công khai - nhưng tài liệu của chúng đã bị rò rỉ.

Hãy xem xét môi trường của riêng bạn: nếu các API nội bộ của bạn được tài liệu hóa và bị công khai trên internet, chúng có thể đang trao cho các kẻ tấn công tất cả những gì họ cần.

**Intruder liên tục quét các điểm cuối API để phát hiện một loạt các lỗ hổng, bao gồm tài liệu bị công khai.**

**[Kiểm Tra API Của Bạn Ngay Hôm Nay Bằng Cách Bắt Đầu Thử Nghiệm Miễn Phí 14 Ngày.](https://www.intruder.io/use-cases/api-security?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger)**

### _Về tác giả:_

_Daniel Andrew, Trưởng Dịch Vụ An Ninh, Intruder_

_Daniel Andrew đứng đầu an ninh tấn công tại Intruder, nơi anh dẫn dắt nhóm Bug Bounty Tư Nhân của Intruder. Nền tảng của anh là một chuyên gia kiểm tra thẩm định an ninh được chứng nhận CREST và kỹ sư phần mềm .NET._

_Được tài trợ và viết bởi [Intruder](https://www.intruder.io/use-cases/api-security?utm%5Fsource=bleepingcomputer&utm%5Fmedium=p%5Freferral&utm%5Fcampaign=global%7Cfixed%7C28%5F07%5F2025%5Fautoswagger)._