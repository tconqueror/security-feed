# Suy nghĩ lại về bảo mật danh tính trong kỷ nguyên của các tác nhân AI tự chủ

![Người đàn ông với robot](https://www.bleepstatic.com/content/posts/2025/10/29/man-robot-token-security.jpg)

Sự trỗi dậy của các tác nhân AI tự chủ đang thách thức nền tảng của bảo mật doanh nghiệp. Những hệ thống này không chỉ theo quy trình tĩnh hoặc mã nguồn cố định. Chúng đưa ra quyết định độc lập, thực hiện hành động trên nhiều hệ thống, và trong nhiều trường hợp, làm vậy mà không có giám sát của con người.

Đối với CISOs, sự thay đổi này tạo ra một loại danh tính phi-nhân mới (NHIs) khẩn cấp mà các mô hình danh tính, kiểm soát và khung giám sát tập trung vào con người truyền thống không được trang bị để quản trị.

## Các rủi ro kỹ thuật mới nổi của các tác nhân AI

**Shadow Agents:** Khác với nhân viên, các tác nhân AI hiếm khi trải qua quy trình onboarding hoặc offboarding chính thức. Điều này dẫn đến sự bùng nổ tác nhân và các triển khai AI “bóng tối”. Nhiều tác nhân tồn tại lâu sau khi trường hợp sử dụng của chúng đã kết thúc, vẫn giữ thông tin xác thực, token hoạt động, hoặc kết nối tới các hệ thống và ứng dụng quan trọng. Những tác nhân này trở nên hấp dẫn đối với kẻ tấn công và là một điểm mù quản trị ngày càng lớn do quyền hạn quá mức mà chúng nắm giữ.

**Privilege Escalation:** Các tác nhân thường hoạt động với quyền vượt quá mức cần thiết. Điều này cho chúng quyền truy cập rộng hơn mức cần, và trong một số trường hợp, khả năng xâu chuỗi đặc quyền để đạt quyền admin đầy đủ. Kẻ tấn công có thể lợi dụng các khoảng trống này bằng cách chiếm quyền các tác nhân hoặc cung cấp cho chúng hướng dẫn để thực thi các hành động trái phép thông qua API hợp lệ, tạo ra các vi phạm xuất hiện như “đáng tin cậy” trong nhật ký.

**Data Exfiltration:** Các tác nhân AI có thể tổng hợp và truyền tải dữ liệu nhạy cảm ở quy mô lớn. Nếu bị xâm phạm hoặc chỉ đơn giản là định phạm vi kém, một tác nhân AI có token API hoặc tích hợp SaaS có thể rò rỉ dữ liệu nội bộ cho người dùng của nó (khách hàng, nhân viên, hoặc các tác nhân khác) hoặc tới các điểm cuối bên thứ ba mà không kích hoạt cảnh báo. Các thao túng prompt tinh vi hoặc chuỗi tin nhắn giữa các tác nhân có thể được sử dụng để trích xuất các bộ dữ liệu độc quyền và tài sản trí tuệ, và nhiều công cụ bảo mật vẫn chưa báo động đây là bất thường. Điều này không chỉ là một rủi ro bảo mật lớn mà còn có thể là thất bại về tuân thủ cho tổ chức.

Khám phá cách những lỗ hổng này và các rủi ro khác phù hợp với bức tranh rủi ro rộng hơn trong tổng quan của chúng tôi về [10 rủi ro bảo mật hàng đầu của các tác nhân AI tự chủ](https://www.token.security/lp/top-10-security-risks-of-autonomous-ai-agents?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-30).

## [Bảo mật Agentic AI: Suy nghĩ lại về quyền truy cập cho các hệ thống tự chủ](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-30)

Các tác nhân AI không chỉ thực hiện theo hướng dẫn, chúng đang hành động.

Xem cách Token Security đang giúp các doanh nghiệp định nghĩa lại kiểm soát truy cập cho kỷ nguyên của Agentic AI, nơi hành động, ý định và trách nhiệm phải phù hợp với nhau.

[Tải hướng dẫn miễn phí](https://www.token.security/lp/the-ai-security-guide?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-30)

## Tại sao các công cụ bảo mật truyền thống không đủ

Các công cụ bảo mật kế thừa giả định ý định và tương tác của con người. Chúng xác thực người dùng bằng sinh trắc học, giám sát phiên làm việc, và tìm kiếm các sai lệch so với các mẫu mong đợi.

Nhưng Agentic AI hoạt động theo những cách không quen thuộc. Nó sinh ra các tác nhân phụ, gọi các API mới khi cần, và tự lập luận dựa trên các mục tiêu thay đổi. Hành vi của nó không khớp với người dùng con người hoặc hoạt động kịch bản tĩnh, và vì vậy thường khiến các công cụ phát hiện nhầm lẫn.

Tệ hơn, nhiều tác nhân AI hoạt động mà không có quyền sở hữu rõ ràng từ con người. Trong các luồng công việc đa tác nhân, danh tính khởi tạo nhanh chóng bị mất khi hành động lan truyền qua các công cụ.

Kết quả là một mạng lưới hoạt động lan rộng mà không có kiểm soát tập trung hoặc khả năng truy vết. Nhật ký kiểm toán không thể trả lời “ai đã làm điều này?” khi “ai” là một tiến trình tác nhân tự chủ, nhất thời.

## Bảo mật lấy danh tính làm trọng tâm: Chuyển đổi cần thiết

Đối với các lãnh đạo bảo mật, con đường khả thi duy nhất là bảo mật lấy danh tính làm trung tâm cho các tác nhân AI.

Điều đó có nghĩa là mỗi tác nhân phải có một danh tính duy nhất, được quản lý; quyền của nó phải được giới hạn chặt chẽ theo nhiệm vụ; và vòng đời của nó phải được quản lý đúng cách.

Không có danh tính ở trung tâm, mọi kiểm soát khác đều thất bại. Bạn không thể thực thi nguyên tắc ít đặc quyền, phát hiện bất thường, hoặc gán trách nhiệm nếu bạn không biết tác nhân thuộc sở hữu ai và nó được kỳ vọng làm gì.

## Những gì CISOs có thể làm ngay

Để ngăn các tác nhân Agentic AI vượt khỏi tầm kiểm soát, CISOs nên hành động ngay:

1. **Khám phá và lập danh mục các tác nhân**: Bắt đầu bằng việc xác định mọi tác nhân tự chủ hoạt động trong môi trường của bạn—chatbot, bộ nối API, copilots nội bộ, MCP servers, và bất kỳ công cụ AutoGPT-like nào. Lập danh mục nơi chúng chạy, những gì chúng truy cập, và ai đã tạo ra chúng.
2. **Chỉ định chủ sở hữu**: Yêu cầu mỗi tác nhân có một chủ sở hữu là con người chịu trách nhiệm về mục đích, quyền truy cập, và vòng đời của nó. Những tác nhân không có chủ sở hữu nên được đánh dấu và chấm dứt.
3. **Thực thi nguyên tắc ít đặc quyền:** Xem xét quyền của tác nhân định kỳ. Tránh cấp quyền chung hoặc kế thừa. Thiết lập chính sách hết hạn cho token và tự động hóa các bài đánh giá đặc quyền giống như bạn làm cho tài khoản người dùng có đặc quyền.
4. **Truyền bối cảnh danh tính:** Đảm bảo danh tính được truyền qua mọi bước của chuỗi đa tác nhân. Nếu Agent A gọi Agent B, quyền nên bị giới hạn trong bối cảnh người dùng ban đầu. Không có ràng buộc danh tính, mỗi tác nhân trở thành một superuser tiềm năng.
5. **Giám sát và kiểm toán hành vi tác nhân:** Xem tác nhân như các thực thể rủi ro cao trong SIEM. Tìm các bất thường như gọi API bất ngờ, nỗ lực tích hợp mới, hoặc thay đổi trong mẫu truy cập dữ liệu. Sử dụng nhật ký bất biến và thiết lập các rào bảo mật.
6. **Thiết lập công tắc ngắt (Kill Switch):** Các tác nhân hành xử sai phải bị chấm dứt nhanh chóng. Xây dựng quy trình ứng phó khẩn cấp dành riêng cho các tác nhân tự chủ và luân phiên các bí mật có thể đã bị xâm phạm.
7. **Tích hợp các tác nhân vào hệ thống IAM:** Đưa các tác nhân AI vào cấu trúc danh tính của bạn. Gán vai trò cho chúng, cấp chứng chỉ từ vault an toàn, và áp dụng các chính sách hiện có khi thích hợp.

## Chuẩn bị ngay bây giờ hoặc mất kiểm soát sau này

Rủi ro lớn nhất với Agentic AI không phải là một khai thác cụ thể. Đó là ảo tưởng về sự an toàn. Những tác nhân này thường chạy trong các ứng dụng được tin cậy, sử dụng thông tin xác thực quen thuộc, và thực hiện các nhiệm vụ trông có vẻ vô hại bề ngoài.

Nhưng nếu không có tầm nhìn, phạm vi, hoặc chủ sở hữu, chúng có khả năng trở thành điểm vào cho di chuyển ngang, đánh cắp dữ liệu, hoặc thao túng hệ thống.

Khi AI được tích hợp vào nhiều quy trình doanh nghiệp hơn, sự bùng nổ của các tác nhân không được quản trị sẽ gia tăng.

Những nhà lãnh đạo bảo mật hành động ngay bằng cách đặt danh tính, khả năng hiển thị và quản trị truy cập làm lõi của việc áp dụng AI sẽ có vị thế tận dụng lợi ích của Agentic AI mà không đánh mất quyền kiểm soát.

**Để xem cách điều này được thực hiện trong thực tế, [book a demo](https://www.token.security/book-a-demo?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-30) với Token Security.**

_Sponsored and written by [Token Security](https://www.token.security/book-a-demo?utm%5Fsource=3rd-party&utm%5Fmedium=bleepingcomputer&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=october-30)._