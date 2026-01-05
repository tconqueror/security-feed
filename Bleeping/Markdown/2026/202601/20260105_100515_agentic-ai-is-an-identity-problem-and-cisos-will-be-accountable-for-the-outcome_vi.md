# Agentic AI là một vấn đề về danh tính và CISOs sẽ chịu trách nhiệm cho kết quả

![Tiêu đề 'CISOs on the line'](https://www.bleepstatic.com/content/posts/2026/01/05/token-security-cisos-on-the-line.jpg)

_Tác giả Itamar Apelblat, Giám đốc điều hành & Đồng sáng lập, Token Security_

Nếu bạn là một CISO ngày nay, Agentic AI có lẽ mang lại cảm giác quen thuộc một cách khó chịu. Công nghệ là mới, nhưng mô thức thì không. Lãnh đạo doanh nghiệp đang thúc đẩy mạnh việc triển khai các agent AI khắp tổ chức, trong khi các đội an ninh được kỳ vọng làm cho việc đó an toàn mà không làm chậm tiến độ.

Sự căng thẳng đó đã tồn tại trước đây với cloud, SaaS và DevOps. Mỗi lần như vậy, danh tính luôn đứng ở trung tâm của cả rủi ro lẫn giải pháp.

Agentic AI cũng không khác. Vấn đề chủ yếu không phải là quản trị AI. Đó là vấn đề danh tính, và cuối cùng CISOs sẽ chịu trách nhiệm cho kết quả.

Trong nhiều năm, các chương trình an ninh được thiết kế xung quanh danh tính con người. Nhân viên và nhà thầu được tập trung hóa, vai trò được định nghĩa, quyền truy cập được xem xét, và việc offboarding có thể dự đoán được. Danh tính máy móc đã làm gián đoạn mô hình đó bằng cách nhân bản nhanh chóng và lan tỏa khắp các cloud, pipeline và nền tảng SaaS. Quản trị đi sau, nhưng những giả định cốt lõi vẫn còn. Các agent AI phá vỡ hoàn toàn những giả định đó.

Các agent AI đại diện cho một lớp danh tính mới. Chúng hành xử có ý định như con người, nhưng hoạt động với quy mô và tính bền bỉ của máy móc. Chúng mặc định phân tán, dễ tạo ra, và có khả năng hành động trên nhiều hệ thống mà không cần sự can thiệp trực tiếp của con người.

Từ góc độ danh tính, đây là sự kết hợp phức tạp nhất có thể. Các agent này xác thực, ủy quyền, và thực hiện hành động, nhưng chúng không vừa vặn với các mô hình danh tính hiện có.

## [Bảo mật Agentic AI: Hướng dẫn miễn phí từ Token Security](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=jan-5)

Các agent AI không chỉ tuân theo chỉ thị, chúng đang hành động.

Xem cách Token Security đang giúp các doanh nghiệp định nghĩa lại kiểm soát truy cập cho thời đại Agentic AI, nơi hành động, ý định và trách nhiệm phải được đồng bộ.

[Tải về tại đây](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=jan-5)

Điều này quan trọng vì danh tính vẫn là nguyên nhân gốc rễ phổ biến nhất của các sự cố. Credential bị lạm dụng. Quyền ưu tiên tích tụ. Quyền sở hữu trở nên không rõ ràng. Agentic AI khuếch đại tất cả các rủi ro này cùng một lúc.

Nhiều agent được cấp quyền truy cập rộng chỉ để hoạt động nhanh. Ít được xem xét. Còn ít hơn nữa bị ngừng sử dụng.

Một số tiếp tục hoạt động lâu sau khi các dự án hoặc những người tạo ra chúng đã rời đi. Đối với kẻ tấn công, những danh tính luôn bật, có quyền quá nhiều này là mục tiêu lý tưởng, chỉ cần nhìn vào [mới nhất từ OWASP mà xác định rủi ro đó](https://www.token.security/blog/owasp-top-10-and-the-identity-first-security-imperative-for-autonomous-ai-agents?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=jan-5).

Các công cụ IAM và PAM truyền thống không được thiết kế cho thực tế này. Chúng giả định người dùng là con người hoặc, ở mức độ tốt nhất, là các workload có thể dự đoán. Các agent AI không sống trong một thư mục duy nhất, không tuân theo vai trò tĩnh, và không giới hạn trong một biên giới nền tảng đơn lẻ.

Cố gắng bảo mật chúng bằng các kiểm soát cũ, tập trung vào con người tạo ra các điểm mù và sự tự tin giả tạo. Tin tưởng vào nhà cung cấp nền tảng AI để giải quyết vấn đề này cũng rủi ro không kém. Cũng như các nhà cung cấp cloud không giải quyết xong bảo mật cloud, các nền tảng agent sẽ không giải quyết rủi ro danh tính doanh nghiệp.

Con đường phía trước không phải là hạn chế sáng tạo, mà là áp dụng một kỷ luật mà CISOs đã hiểu: quản lý vòng đời. Bảo mật danh tính lực lượng lao động chỉ trở nên có thể mở rộng khi tổ chức coi danh tính như một vòng đời, từ onboarding đến offboarding. Các agent AI đòi hỏi cùng tư duy đó, được điều chỉnh cho tốc độ và quy mô.

Mỗi agent cần có quyền sở hữu rõ ràng liên kết với identity provider. Mục đích của nó phải rõ ràng và có thể đo lường. Quyền truy cập của nó nên phù hợp với những gì nó thực sự làm, không phải những gì tiện lợi khi tạo ra. Hoạt động phải được quan sát liên tục để phát hiện sự trôi dạt đặc quyền sớm. Và khi agent trở nên không hoạt động, dự án kết thúc, hoặc chủ sở hữu rời đi, quyền truy cập phải bị thu hồi tự động. Nếu không có các kiểm soát này, việc áp dụng AI cuối cùng sẽ sụp đổ dưới chính rủi ro của nó.

Một thay đổi quan trọng mà CISOs phải thấm nhuần là bảo mật danh tính agent về cơ bản là một vấn đề tương quan dữ liệu. Bạn không thể hiểu rủi ro của một agent chỉ bằng cách nhìn vào chính agent đó.

Rủi ro thực sự được xác định bởi những gì agent có thể tiếp cận. Điều đó bao gồm các cloud roles mà nó đảm nhận, các ứng dụng SaaS mà nó truy cập, dữ liệu mà nó có thể đọc hoặc sửa đổi, và các danh tính hạ nguồn mà nó sử dụng.

Bảo mật Agentic AI đòi hỏi tương quan các tín hiệu danh tính trên các nền tảng agent, identity providers, hạ tầng, ứng dụng và lớp dữ liệu.

Việc tương quan này cho phép CISOs trả lời các câu hỏi quan trọng trong các cuộc kiểm toán, báo cáo hội đồng, và phản ứng sự cố. Ai đã có quyền truy cập? Tại sao họ có quyền đó? Liệu quyền đó có phù hợp? Và liệu nó còn nên tồn tại không? Nếu không có ngữ cảnh đó, các agent AI vẫn mù mờ và không thể quản trị. [Đây là một danh sách kiểm tra an ninh cho CISOs](https://www.token.security/lp/ciso-guide-to-agentic-ai-and-non-human-identity-security?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=jan-5) giúp lên kế hoạch cho các câu hỏi như vậy.

Nhiều tổ chức hiện đang ở giai đoạn phản ứng, phát hiện agent sprawl sau khi nó đã vào sản xuất. Giai đoạn đó sẽ qua nhanh. Giai đoạn tiếp theo là phòng ngừa.

Kỷ luật về danh tính phải di chuyển sớm hơn trong vòng đời, ngay tại thời điểm agent được tạo. Những người xây dựng cần các hàng rào bảo vệ buộc phải làm rõ ý định và phạm vi, thay vì mặc định cấp nhiều quyền chỉ để nó hoạt động. Nếu kỷ luật này vắng mặt, CISOs sẽ thừa hưởng rủi ro và cuối cùng là hậu quả.

Agentic AI đang trở thành một phần vĩnh viễn trong cách doanh nghiệp vận hành. Câu hỏi không phải là liệu nó có mở rộng được không, mà là liệu nó có mở rộng an toàn không. CISOs sẽ quyết định câu trả lời. Nếu danh tính agent vẫn không được quản lý, AI sẽ gây ra các vi phạm, thất bại về tuân thủ và phản ứng cấp cao làm chậm đổi mới.

Nếu danh tính agent được quản trị thông qua quản lý vòng đời và khả năng hiển thị, AI trở nên bền vững, linh hoạt và an toàn.

Những tổ chức thành công sẽ không phải là những tổ chức nói có hoặc không với Agentic AI. Họ sẽ là những tổ chức nói có một cách tự tin, bởi vì họ nhận ra sớm rằng bảo mật Agentic AI là một ưu tiên về danh tính.

Nếu bạn đã sẵn sàng xử lý bảo mật Agentic AI một cách tự tin, Token có thể giúp.

**[Đặt lịch demo tại đây](https://www.token.security/book-a-demo?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=jan-5) để chúng tôi có thể cho bạn thấy điều gì tạo nên nền tảng của chúng tôi khác biệt trong việc giữ an toàn cho tổ chức của bạn.**

_Được tài trợ và viết bởi [Token Security](https://www.token.security/book-a-demo?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=jan-5)._