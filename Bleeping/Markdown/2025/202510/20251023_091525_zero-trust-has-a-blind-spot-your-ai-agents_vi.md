# Zero Trust có một điểm mù — Các tác nhân AI của bạn

![tác nhân AI](https://www.bleepstatic.com/content/posts/2025/10/23/robots-ai-token-security.jpg)

_Bởi Ido Shlomo, Giám đốc Công nghệ và Đồng sáng lập, Token Security_

Agentic AI đã đến. Từ các GPT tùy chỉnh đến các trợ lý đồng hành tự trị, các tác nhân AI hiện thay mặt người dùng và tổ chức hành động, hoặc thậm chí đóng vai trò như một đồng đội khác, đưa ra quyết định, truy cập hệ thống và gọi các tác nhân khác mà không có sự can thiệp trực tiếp của con người.

Nhưng cùng với mức độ tự chủ mới này xuất hiện một câu hỏi an ninh cấp bách: Nếu AI đang làm công việc, làm sao chúng ta biết khi nào có thể tin tưởng nó?

Trong các hệ thống truyền thống, kiến trúc Zero Trust giả định không có sự tin tưởng ngầm, nơi mọi người dùng, endpoint, workload và dịch vụ phải liên tục chứng minh họ là ai và họ được phép làm gì.

Tuy nhiên, trong thế giới agentic AI, các nguyên tắc này nhanh chóng bị phá vỡ. Các tác nhân AI thường hoạt động dưới thông tin đăng nhập được kế thừa, không có chủ sở hữu đã đăng ký hoặc quản trị danh tính.

Hệ quả là một quần thể ngày càng tăng của các tác nhân có vẻ được tin cậy nhưng thực tế thì không, [một trong nhiều rủi ro của các tác nhân AI tự chủ trong hạ tầng của bạn](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-23).

Để đóng khoảng trống này, các tổ chức phải áp dụng NIST AI Risk Management Framework ([AI RMF](https://www.nist.gov/itl/ai-risk-management-framework)) thông qua lăng kính Zero Trust với danh tính ở cốt lõi. Danh tính phải là gốc rễ của sự tin cậy cho AI, và nếu không có nó, mọi thứ khác (kiểm soát truy cập, khả năng kiểm toán, trách nhiệm giải trình) sẽ sụp đổ.

## Rủi ro danh tính trong kỷ nguyên tác nhân

NIST’s AI RMF cung cấp hướng dẫn ở mức cao để quản lý rủi ro AI qua bốn chức năng: Map, Measure, Manage, và Govern. Nhưng khi diễn giải những chức năng này qua lăng kính quản trị danh tính, sẽ lộ ra nơi các rủi ro riêng cho AI đang ẩn náu.

Hãy xem chức năng “Map”. Hiện có bao nhiêu tác nhân AI đang hoạt động trong tổ chức của bạn? Ai đã tạo chúng và ai là chủ sở hữu? Chúng có quyền truy cập vào hệ thống và dịch vụ doanh nghiệp nào? Hầu hết các đội bảo mật ngày nay không thể trả lời những câu hỏi này.

Các tác nhân AI đang được khởi tạo trên các máy phát triển nội bộ, tài khoản production, hoặc sandbox đám mây với rất ít giám sát.

Các tác nhân bóng đêm thường kế thừa các thông tin đăng nhập quá nhiều quyền hoặc xác thực bằng bí mật tồn tại lâu dài. Nhiều tác nhân tồn tại mà không có chủ sở hữu, không có chính sách xoay vòng, không có việc điều chỉnh quyền theo mức cần thiết, và không có giám sát.

Những “tác nhân mồ côi” này vi phạm Zero Trust theo mặc định. Chúng hoạt động mà không có một danh tính đáng tin cậy, nghĩa là hệ thống đang tin tưởng các thực thể mà nó không thể xác minh.

## [Securing Agentic AI: Rethinking Permissions for Autonomous Systems](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-23)

Các tác nhân AI giờ đây đang hành động — không chỉ thực hiện theo chỉ dẫn.

Tìm hiểu cách Token Security giúp các doanh nghiệp định nghĩa lại kiểm soát truy cập cho thời đại Agentic AI, nơi hành động, ý định và trách nhiệm phải phù hợp.

[Download the Free Guide](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-23)

## Tại sao danh tính phải được đặt lên trước

Để khắc phục điều này, các đội bảo mật phải bắt đầu với nguyên lý đầu tiên của Zero Trust: quyền và thông tin đăng nhập đúng cần được áp dụng trước khi cấp sự tin tưởng. Điều này không chỉ áp dụng cho người dùng, mà còn cho các tác nhân AI.

Mỗi tác nhân AI nên có:

* Một danh tính duy nhất, được quản lý
* Một chủ sở hữu rõ ràng hoặc đội chịu trách nhiệm
* Một sơ đồ quyền dựa trên ý định, gắn với quyền truy cập mà nó thực sự cần
* Một vòng đời: được tạo, xem xét, xoay vòng và nghỉ hưu như bất kỳ danh tính nào khác

Điều này biến agentic AI từ một rủi ro không được quản trị thành một thực thể được quản trị. [Danh tính trở thành người gác cổng cho mọi thứ mà tác nhân AI chạm tới](https://www.token.security/blog/securing-agentic-ai-why-everything-starts-with-identity?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-23), cho dù đó là đọc dữ liệu nhạy cảm, phát lệnh hệ thống, hay gọi một tác nhân khác.

## Áp dụng Khung NIST: Zero Trust hướng tới danh tính

Dưới đây là cách mỗi chức năng của NIST AI RMF có thể được triển khai thông qua một cách tiếp cận Zero Trust lấy danh tính làm trung tâm:

**Map:** Khám phá và lập danh mục tất cả các tác nhân AI, bao gồm GPTs tùy chỉnh, copilots, và MCP servers. Đánh dấu các tác nhân thiếu hoặc có quyền sở hữu không rõ ràng. Lập bản đồ những gì mỗi tác nhân có thể truy cập và liên kết đó với mục đích dự định của nó. Giám sát hành vi tác nhân liên tục, không chỉ cho đầu ra mô hình mà còn cho hành vi danh tính. Liệu tác nhân có đang truy cập các hệ thống mà nó chưa từng sử dụng trước đây không? Thông tin đăng nhập của nó đã hết hạn nhưng vẫn hoạt động? Việc sử dụng danh tính bất thường là dấu hiệu cảnh báo sớm về xâm phạm hoặc lệch hướng.

**Manage:** Điều chỉnh quyền cho phù hợp với mọi danh tính AI. Sử dụng truy cập dựa trên ý định để đảm bảo nguyên tắc ít đặc quyền được thực thi một cách động. Thu hồi các thông tin đăng nhập cũ, xoay vòng bí mật, và loại bỏ các tác nhân không còn phục vụ mục đích.

**Govern:** Áp dụng quản trị danh tính cho các tác nhân AI với cùng mức nghiêm ngặt như đối với con người. Giao chủ sở hữu, thực thi chính sách vòng đời, và kiểm toán việc sử dụng danh tính trên hệ sinh thái đa tác nhân của bạn. Nếu một tác nhân thực hiện một hành động nhạy cảm, bạn nên có khả năng trả lời ngay: Ai đã ủy quyền điều này, và tại sao?

## Từ điểm mù đến sự tin tưởng đã được chứng minh

Các rủi ro là có thật. Các tác nhân AI mồ côi có thể đóng vai trò là cửa hậu cho kẻ tấn công. Các tác nhân có quyền quá mức có thể trộm xuất dữ liệu nhạy cảm trong vài giây. Và khi xảy ra vi phạm, dấu vết kiểm toán thường không tồn tại. Không có danh tính rõ ràng, các đội bảo mật gặp khó khăn trong việc xác định vấn đề: “Chúng tôi không biết ai đã làm điều đó.”

Danh tính không thể chỉ là một lớp khác trong bảo mật AI. Nó cần phải là nền tảng. Nó phù hợp với Zero Trust bằng cách đảm bảo mọi hành động của tác nhân AI được gắn với một thực thể đã biết và được quản trị. Và nó cho phép áp dụng AI an toàn ở quy mô bởi vì sự tin tưởng vào AI phải được kiếm được, không phải giả định.

Các tác nhân AI có thể tự chủ, nhưng sự tin tưởng vào chúng phải được xây dựng trên trách nhiệm giải trình. Danh tính là cách chúng ta đạt được điều đó và thiết lập sự tin tưởng đó. Bằng cách nhúng các kiểm soát danh tính vào mọi giai đoạn triển khai AI (khám phá, cấp quyền, giám sát và quản trị), các tổ chức có thể loại bỏ điểm mù và thực thi Zero Trust ở nơi quan trọng nhất.

Đã đến lúc chúng ta bắt đầu áp dụng nó cho các tác nhân AI để đảm bảo một tư thế an ninh và tuân thủ mạnh hơn.

**Nếu bạn đã sẵn sàng để lập bản đồ agentic AI của mình và kiểm soát các tác nhân, [book a demo of Token Security](https://www.token.security/book-a-demo?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-23) để xem nền tảng của chúng tôi thực hiện điều đó như thế nào.**

_Bài viết được tài trợ và viết bởi [Token Security](https://www.token.security/book-a-demo?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-23)._