# Mở rộng Zero Trust cho tác nhân AI: “Không bao giờ tin tưởng, luôn xác minh” trở nên tự động

![AI Zero Trust](https://www.bleepstatic.com/content/posts/2025/11/12/token-security-ai-zero-trust.jpg)

_Viết bởi Ido Shlomo, CTO và Đồng sáng lập, Token Security_

Khi các tổ chức nhanh chóng áp dụng trợ lý AI và các tác nhân tự chủ để đơn giản hóa luồng công việc và tăng hiệu quả, họ có thể vô tình mở rộng bề mặt tấn công. Các tác nhân AI, cho dù được nhúng vào vận hành CNTT, quy trình dịch vụ khách hàng, hay công cụ nội bộ dựa trên LLM, đang hành động thay chúng ta, đưa ra quyết định, truy cập dữ liệu nhạy cảm và thực thi các hành động tự động ở tốc độ máy.

Thách thức? Hầu hết các khung bảo mật không được xây dựng với những tác nhân mới này trong tâm trí. Chúng ta đã dành nhiều năm tinh chỉnh Zero Trust cho người dùng và ứng dụng, nhưng bây giờ cần đặt ra một câu hỏi khó: Điều gì xảy ra khi người dùng là một phần mềm tự định hướng?

Câu trả lời bắt đầu bằng một cam kết mới đối với Zero Trust để áp dụng không chỉ cho con người và các dịch vụ truyền thống, mà cho mọi tác nhân AI hoạt động bên trong hệ thống của chúng ta.

## Sự trỗi dậy của các tác nhân tự chủ

Trong nhiều thập kỷ, danh tính là mối quan tâm thiên về con người. Rồi xuất hiện tài khoản dịch vụ, container và API (các danh tính máy) đòi hỏi quản trị riêng. Giờ đây chúng ta đối mặt với bước tiến tiếp theo: các danh tính mang tính tác nhân.

Các tác nhân AI hành xử linh hoạt như con người, nhưng ở quy mô và tốc độ của máy móc. Khác với mã tĩnh, chúng học, thích nghi và đưa ra quyết định tự chủ. Điều đó có nghĩa hành vi của chúng khó dự đoán hơn, và yêu cầu truy cập của chúng thay đổi một cách động.

Tuy nhiên nhiều tác nhân này hiện nay hoạt động với thông tin đăng nhập được mã hóa cứng, đặc quyền quá mức và không có trách nhiệm thực sự. Về bản chất, chúng ta đã trao cho thực tập sinh một huy hiệu admin và bảo họ làm việc nhanh.

Nếu CISOs muốn [triển khai AI một cách an toàn và bảo mật](https://www.token.security/blog/the-top-10-identity-centric-security-risks-of-autonomous-ai-agents?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=november-12), những tác nhân này phải trở thành danh tính hạng nhất, được quản trị nghiêm ngặt hơn bất kỳ nhân viên hay ứng dụng nào.

## [Bảo mật Agentic AI: Một hướng dẫn miễn phí từ Token Security](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-30)

Các tác nhân AI không chỉ làm theo lệnh, họ đang chủ động hành động.

Xem cách Token Security đang giúp doanh nghiệp định nghĩa lại kiểm soát truy cập cho kỷ nguyên Agentic AI, nơi hành động, ý định và trách nhiệm phải tương thích.

[Tải xuống tại đây](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-30)

## “Không bao giờ tin tưởng, luôn xác minh” cho AI

Zero Trust bắt đầu với một nguyên tắc đơn giản: không bao giờ tin tưởng, luôn luôn xác minh. Nó giả định rằng người dùng, máy móc và tác nhân sẽ bị xâm phạm, và yêu cầu mọi yêu cầu truy cập, bất kể nguồn gốc, phải được xác thực, ủy quyền và giám sát.

Triết lý này áp dụng hoàn hảo cho các tác nhân tự chủ. Đây là cách nó trông như thế trong thực tế:

* Danh tính là ưu tiên số một: Mỗi tác nhân AI phải có một danh tính duy nhất, có thể kiểm toán. Không dùng chung thông tin đăng nhập. Không token dịch vụ ẩn danh. Mỗi hành động phải có thể quy trách nhiệm.
* Nguyên tắc ít đặc quyền: Các tác nhân chỉ nên có quyền truy cập tối thiểu cần thiết cho chức năng của chúng. Nếu một tác nhân được thiết kế để đọc dữ liệu bán hàng, nó không nên có khả năng ghi vào hồ sơ thanh toán hoặc truy cập hệ thống nhân sự.
* Thực thi động, theo ngữ cảnh: Khi các tác nhân phát triển và nhiệm vụ thay đổi, quyền của chúng phải được đánh giá liên tục. Chính sách tĩnh sẽ không hiệu quả. Ngữ cảnh thời gian thực, chẳng hạn đang truy cập gì, bởi ai và trong điều kiện nào, nên là cơ sở cho quyết định.
* Giám sát và xác thực liên tục: Tự chủ không có nghĩa là không được giám sát. Các tác nhân phải được giám sát như người dùng có đặc quyền. Những hành vi bất thường như truy cập hệ thống mới, chuyển lượng lớn dữ liệu hoặc leo thang đặc quyền nên kích hoạt cảnh báo hoặc can thiệp.

## Rủi ro của việc trao quyền quá mức

AI đang được áp dụng nhanh để thúc đẩy đổi mới, cải thiện hiệu suất và tạo lợi thế cạnh tranh. Nó không có ý định gây hại, nhưng điều đó không có nghĩa là không thể gây hại.

Hãy tưởng tượng một tác nhân helpdesk có quyền rộng trên các hệ thống nội bộ. Nó được thiết kế để tự động xử lý vé, nhưng một prompt injection hoặc cấu hình sai khiến nó đặt lại mật khẩu người dùng, xóa hồ sơ hoặc gửi dữ liệu nhạy cảm ra bên ngoài qua email.

Đây không phải là lý thuyết, điều đó đang xảy ra. Các tác nhân AI có thể "ảo tưởng" ra hành vi mới, hiểu sai hướng dẫn, hoặc hoạt động ngoài phạm vi mong đợi. Tệ hơn nữa, kẻ tấn công biết điều này và đang chủ động dò xét các giao diện AI để tìm cách xâm nhập chúng.

Đây là điều chúng tôi gọi là Excessive Agency: khi các tác nhân AI được trao quyền nhiều hơn mức cần thiết, và không có rào chắn nào để ngăn chúng sử dụng quyền đó.

## Xây dựng rào chắn mà không gây tắc nghẽn

Những chuyên gia bảo mật giờ đang đi trên một đường mỏng. Một mặt, họ muốn thúc đẩy đổi mới. Mặt khác, họ cần thực thi kỷ luật. Cân bằng đó đặc biệt mong manh với AI.

Giải pháp nằm ở thiết kế các rào chắn có thể mở rộng. Điều đó có nghĩa là:

* Scoped tokens và thông tin đăng nhập thời hạn ngắn: Thay vì bí mật dài hạn, phát hành token truy cập có thời hạn với phạm vi xác định hẹp. Nếu bị lộ, chúng sẽ hết hạn nhanh và gây hại tối thiểu.
* Mô hình tin cậy nhiều tầng: Không phải hành động nào cũng giống nhau. Các tác vụ thường nhật, rủi ro thấp có thể được tự động hóa tự do. Các thao tác rủi ro cao, như xóa dữ liệu hoặc chuyển tiền, nên yêu cầu phê duyệt có con người tham gia hoặc kích hoạt đa yếu tố.
* Áp dụng ranh giới truy cập: Đừng cho phép các tác nhân gọi mọi thứ ở mọi nơi. [Thực thi chính sách truy cập nghiêm ngặt và ranh giới ở mức dịch vụ](https://www.token.security/blog/securing-agentic-ai-defining-permissions-for-unpredictable-ai-agents?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=november-12) để chúng hoạt động trong phạm vi được phép.
* Sở hữu rõ ràng: Mỗi tác nhân nên có một chủ sở hữu con người nội bộ, người chịu trách nhiệm về mục đích, hành vi và quyền hạn của nó.

Với những kiểm soát này, bảo mật trở thành yếu tố hỗ trợ AI, chứ không phải rào cản.

## Lời kêu gọi gửi tới CISOs: Dẫn dắt bằng danh tính

Chúng ta đang bước vào kỷ nguyên nơi “đăng nhập” không còn chỉ thuộc về con người. Các tác nhân đang viết mã, phân tích rủi ro, truy vấn dữ liệu và trò chuyện với khách hàng. Nếu chúng ta coi họ là phần bị lãng quên trong chiến lược danh tính, chúng ta đang xây dựng hệ thống trên niềm tin mù quáng và đó chính xác là điều Zero Trust ra đời để ngăn chặn.

CISOs phải dẫn dắt. Bắt đầu bằng việc mở rộng khung Zero Trust để bao gồm rõ ràng các tác nhân tự chủ. Từ đó, cần đầu tư vào kiến trúc bảo mật AI ưu tiên danh tính, công cụ giám sát và quản trị truy cập có khả năng xử lý các tác nhân không phải con người. Nếu bạn đang mở rộng hạ tầng AI, Token Security có thể giúp đảm bảo an ninh trong suốt quá trình.

**[Đặt lịch demo kỹ thuật với nhóm của chúng tôi](https://www.token.security/book-a-demo?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=november-12) để xem cách chúng tôi bảo mật agentic AI mà không hy sinh tốc độ.**

Bảo mật không phải là ngăn chặn AI. Nó là cho phép AI hoạt động một cách an toàn, có thể dự đoán và có trách nhiệm.

_Tài trợ và viết bởi [Token Security](https://www.token.security/book-a-demo?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=november-12)._