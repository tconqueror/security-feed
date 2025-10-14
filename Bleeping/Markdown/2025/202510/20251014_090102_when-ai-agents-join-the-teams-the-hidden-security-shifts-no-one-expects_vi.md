# Khi Các Tác Nhân AI Tham Gia Vào Các Nhóm: Những Thay Đổi Bảo Mật Ẩn Mà Không Ai Ngờ Tới

![Rủi ro của trí tuệ nhân tạo](https://www.bleepstatic.com/content/hl-images/2022/05/12/evil-hacker-ai.jpg)

_Viết bởi Ido Shlomo, Đồng sáng lập và CTO, Token Security_

Các trợ lý AI không còn chỉ tóm tắt ghi chú cuộc họp, viết email và trả lời câu hỏi nữa. Chúng đang thực hiện hành động, chẳng hạn mở ticket, phân tích log, quản lý tài khoản và thậm chí tự động khắc phục sự cố.

Chào mừng bạn đến thời đại của AI tác nhân, thứ không chỉ nói cho bạn biết việc tiếp theo cần làm — nó tự làm thay bạn. Những tác nhân này mạnh mẽ vô cùng, nhưng chúng cũng đang tạo ra một loại rủi ro bảo mật hoàn toàn mới mà không nhiều người lường trước được: [new kind of security risk](https://www.token.security/blog/the-top-10-identity-centric-security-risks-of-autonomous-ai-agents?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-14).

## Sự Trỗi Dậy Lặng Lẽ của Các Tác Nhân Tự Chủ

Ban đầu, việc áp dụng AI trong các công ty có vẻ vô hại. Những công cụ như ChatGPT và Copilot hỗ trợ mọi người viết và lập trình cơ bản, nhưng không tự hành động độc lập. Điều đó đang thay đổi nhanh chóng.

Không có đánh giá bảo mật hay sự phê duyệt, các nhóm đang triển khai các hệ thống AI tự chủ có thể diễn giải mục tiêu, lập kế hoạch các bước, gọi API và kích hoạt các tác nhân khác. Một trợ lý marketing AI giờ có thể phân tích dữ liệu hiệu suất chiến dịch và chủ động tối ưu mục tiêu và ngân sách. Một tác nhân DevOps có thể quét sự cố và bắt đầu khắc phục mà không chờ con người.

Hệ quả? Một lớp tác nhân ngày càng tăng có khả năng đưa ra quyết định và thực hiện hành động nhanh hơn khả năng giám sát của con người.

## Nó Không Chỉ Là “Một Con Bot Khác”

Trong khi các tổ chức đã bắt đầu quản lý Non-Human Identities (NHIs), chẳng hạn như service accounts và API keys, AI tác nhân không khớp hoàn toàn với khuôn mẫu đó.

Khác với một workflow, vốn theo một chuỗi hành động có thể dự đoán, một tác nhân AI suy luận về việc tiếp theo nên làm. Nó có khả năng xâu chuỗi nhiều bước, truy cập các hệ thống khác nhau và điều chỉnh kế hoạch trong quá trình thực hiện. Chính sự linh hoạt đó khiến các tác nhân vừa mạnh mẽ vừa nguy hiểm. Bởi vì tác nhân có thể hoạt động xuyên biên giới, hành động đơn giản là cấp cho chúng quyền truy cập vào một cơ sở dữ liệu, một CRM và Slack có thể biến chúng thành một trong những người dùng quyền lực nhất trong công ty.

Hệ sinh thái đa tác nhân đang giới thiệu những mức độ phức tạp mới. Một khi một tác nhân bắt đầu gọi hoặc thậm chí tạo các tác nhân khác, khả năng truy vết một hành động trở lại con người khởi xướng nó bắt đầu trở nên mơ hồ.

## [Bảo mật AI tác nhân: Nghĩ lại quyền hạn cho các hệ thống tự chủ](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-14)

Các tác nhân AI giờ đang hành động — không chỉ làm theo lệnh.

Tìm hiểu cách Token Security đang giúp các doanh nghiệp định nghĩa lại kiểm soát truy cập cho thời đại Agentic AI, nơi hành động, ý định và trách nhiệm phải phù hợp với nhau.

[Download the Brief](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-14)

## Shadow AI Đã Ở Đây

Ngay cả những công ty thận trọng cũng phát hiện shadow AI len lỏi vào môi trường của họ. Một product manager đăng ký một công cụ nghiên cứu AI mới. Một nhóm kết nối một bot cuộc họp với các ổ đĩa nội bộ. Một kỹ sư khởi chạy một trợ lý AI cục bộ có thể truy vấn log khách hàng.

Mỗi cái về bản chất là một service và vì vậy, mỗi cái đều cần quản trị. Nhưng hầu hết các công cụ này vào doanh nghiệp mà không có đánh giá chính thức, quét bảo mật hoặc hồ sơ danh tính.

Các công cụ quan sát truyền thống không nhìn thấy chúng rõ ràng. Các công cụ CASB có thể cảnh báo một domain SaaS mới, nhưng chúng sẽ không bắt được vài trăm tác nhân AI đang chạy lặng lẽ trên cloud functions hoặc VM.

Không phải ác ý; chỉ là nhanh. Và tốc độ luôn là kẻ thù của sự giám sát.

## Quy Tắc Mới Cho Một Loại Danh Tính Mới

Vậy, làm thế nào để bạn bảo mật một thứ mà bạn có thể không nhìn thấy và nó hoạt động ở tốc độ máy móc? Nhóm bảo mật cần điều chỉnh chiến lược danh tính theo các cách mới:

1. Track ownership and lifecycles. Mỗi tác nhân cần một chủ sở hữu được đặt tên. Khi con người rời đi, tác nhân cũng phải như vậy.
2. Apply intent and context. Mỗi hành động của tác nhân nên mang dữ liệu “thay mặt cho”: ai đã kích hoạt nó, nhiệm vụ nó đang thực hiện và dữ liệu nào nó được phép chạm tới. Mất chuỗi đó, bạn mất trách nhiệm giải trình.
3. Default to read-only permissions. Tác nhân nên bắt đầu chỉ với quyền xem. Quyền ghi phải được phê duyệt rõ ràng và có giới hạn thời gian.

## Vấn Đề Vòng Đời

Hầu hết các công ty không có quy trình rõ ràng để khai tử các tác nhân AI khi chúng không còn cần thiết. Một prototype của developer bắt đầu như một thí nghiệm vào tháng Ba vẫn đang chạy vào tháng Mười, sử dụng credentials được tạo bởi người đã không còn làm việc trong công ty. Một tác nhân khác âm thầm phát triển qua các thay đổi prompt và tool cho đến khi giờ nó có quyền truy cập dữ liệu khách hàng. Trong khi các tác nhân này không có hành vi ác ý, chúng vô hình, tồn tại dai dẳng và có sức mạnh lớn.

Đó là lý do nhiều doanh nghiệp đang tạo danh mục các tác nhân AI liệt kê mọi tác nhân đang hoạt động, mục đích, chủ sở hữu, quyền hạn và vòng đời của chúng. Đó là nền tảng cần thiết để làm cho các tác nhân AI và danh tính của chúng có thể quản lý được.

## Hàng Rào Chứ Không Phải Sự Sợ Hãi

Mục tiêu không phải là ngăn chặn tác nhân hoạt động khi tổ chức của bạn tìm kiếm các lợi thế hiệu quả và cạnh tranh từ AI. Mục tiêu là đảm bảo chúng có giám sát và quản trị hiệu quả.

Cũng như các tổ chức không cấp ngay quyền admin cho một nhân viên mới, họ cần giao cho các tác nhân AI trách nhiệm cụ thể, xem xét công việc của chúng và kiểm tra các quyết định của chúng.

Chìa khóa là quản trị để cho phép các nhóm xây dựng hệ thống tự động giới hạn phạm vi, ghi log hành vi và tắt các tiến trình bất thường trước khi chúng gây hại. Bởi vì những tác nhân này không chỉ tóm tắt báo cáo hoặc phân loại ticket. Chúng đang đóng sự cố, phê duyệt giao dịch và tương tác trực tiếp với khách hàng.

Khi điều đó xảy ra, “shadow AI” sẽ không còn là điều hiếu kỳ, mà sẽ là một cuộc khủng hoảng.

## Kết Luận

Agentic AI không phải là vấn đề của tương lai. Nó đã ở trong ngăn xếp của bạn. Nếu bạn vẫn quản lý danh tính chỉ như con người hoặc không phải con người, đã đến lúc phải dành chỗ cho một hạng mục thứ ba: các tác nhân tự chủ. Chúng cần danh tính, quyền hạn và trách nhiệm giải trình.

Chúng cũng cần kiểm soát và governance, và càng sớm chúng ta đối xử với các tác nhân như đồng nghiệp có siêu năng lực, thay vì các script có credentials, doanh nghiệp sẽ càng an toàn hơn.

**Xem Token Security’s [AI Security Guide](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-14) để biết thêm các best practices từ hơn 14+ lãnh đạo ngành cybersec.**

_Tài trợ và viết bởi Token Security._