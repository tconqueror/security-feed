# Agentic BAS AI Chuyển Tiêu Đề Mối Đe Dọa Thành Chiến Lược Phòng Thủ

![Đầu trang Agentic AI](https://www.bleepstatic.com/content/posts/2025/12/03/agentic-ai-header.jpg)

_Bởi Sila Özeren Hacioglu, Kỹ sư Nghiên cứu Bảo mật tại Picus Security._

Đối với các nhà lãnh đạo bảo mật, thông báo đáng sợ nhất không phải lúc nào cũng là một cảnh báo từ SOC; đó là một liên kết đến bài báo gửi bởi một thành viên hội đồng quản trị. Tiêu đề thường mô tả một chiến dịch mới bởi một nhóm đe dọa như FIN8 hoặc một lỗ hổng chuỗi cung ứng lớn vừa bị phơi bày. Câu hỏi đi kèm ngắn nhưng gây tê liệt theo hàm ý: "_Chúng ta có đang bị phơi nhiễm bởi điều này ngay bây giờ không?_".

Trong thế giới trước LLM, trả lời câu hỏi đó đồng nghĩa với một cuộc chạy đua điên cuồng với chiếc đồng hồ không khoan nhượng. Các đội bảo mật phải chờ SLA của nhà cung cấp, thường tám giờ hoặc hơn đối với các mối đe dọa mới nổi, hoặc tự mình phân tích ngược thủ công cuộc tấn công để xây dựng một mô phỏng. Mặc dù cách tiếp cận này cho ra kết quả chính xác, nhưng thời gian thực hiện đã tạo ra một cửa sổ không chắc chắn rất nguy hiểm.

Emulation mối đe dọa dựa trên AI đã loại bỏ phần lớn sự chậm trễ điều tra bằng cách tăng tốc phân tích và mở rộng kiến thức về mối đe dọa. Tuy nhiên, việc mô phỏng bằng AI vẫn tiềm ẩn rủi ro do hạn chế về minh bạch, dễ bị thao túng và hay hallucination.

Tại [BAS Summit](https://events.picussecurity.com/on-demand/the-bas-summit) gần đây, Picus CTO và Đồng sáng lập Volkan Ertürk cảnh báo rằng “_raw generative AI can create exploit risks nearly as serious as the threats themselves._” Picus giải quyết vấn đề này bằng cách sử dụng một phương pháp agentic, **post-LLM approach** mang lại tốc độ ở mức AI mà không tạo ra bề mặt tấn công mới.

Bài đăng này phân tích cách tiếp cận đó trông như thế nào, và tại sao nó cơ bản cải thiện tốc độ và an toàn của việc xác thực mối đe dọa.

## Cạm Bẫy "Prompt-and-Pray"

Phản ứng ngay lập tức với cơn bùng nổ Generative AI là **một nỗ lực tự động hóa red teaming** bằng cách đơn giản yêu cầu Large Language Models (LLMs) **tạo script tấn công**. Về lý thuyết, một kỹ sư có thể nhập một báo cáo tình báo mối đe dọa vào mô hình và yêu cầu nó "soạn một chiến dịch emulation".

Mặc dù cách này chắc chắn nhanh, nhưng nó **thất bại về độ tin cậy và an toàn**. Như Ertürk của Picus đã ghi nhận, tồn tại một số nguy cơ khi áp dụng cách này:

“ ... Can you trust a payload that is built by an AI engine? I don't think so. Right? Maybe it just came up with the real sample that an APT group has been using or a ransomware group has been using. ... then you click that binary, and boom, you may have big problems.”

Vấn đề không chỉ là các binary rủi ro. Như đã đề cập ở trên, **LLMs vẫn dễ bị hallucination**. Nếu không có các rào cản nghiêm ngặt, mô hình có thể tưởng tượng ra những TTP (Tactics, Techniques, and Procedures) mà nhóm đe dọa thực tế không sử dụng, hoặc gợi ý khai thác cho các lỗ hổng không tồn tại. Điều này khiến đội bảo mật phải vật lộn để xác thực hệ thống phòng thủ của họ trước các _mối đe dọa lý thuyết_ trong khi không kịp thời xử lý các mối đe dọa thực sự.

Để giải quyết những vấn đề này, nền tảng Picus áp dụng một mô hình hoàn toàn khác biệt: **the agentic approach**.

## [Biến Tiêu Đề Mối Đe Dọa Thành Phòng Thủ Được Xác Thực Trong Vài Giờ, Không Phải Vài Tuần](https://hubs.li/Q03WnJ5G0)

Ngừng phụ thuộc vào các LLM rủi ro, dễ hallucination. Picus sử dụng một khung đa tác nhân để ánh xạ tình báo mối đe dọa trực tiếp tới các mô phỏng an toàn, đã được xác thực.

Thu hẹp khoảng cách giữa cảnh báo tin tức và sẵn sàng phòng thủ của bạn với nền tảng Agentic BAS đầu tiên trên thế giới.

[Yêu cầu Demo của bạn](https://hubs.li/Q03WnJ5G0)

## Sự Chuyển Dịch Agentic: Điều Phối Thay Vì Sinh Sinh

Cách tiếp cận của Picus, được thể hiện trong _Smart Threat_, chuyển khỏi việc sử dụng AI như một trình tạo mã và thay vào đó dùng AI như một bộ điều phối các thành phần đã biết và an toàn.

Thay vì yêu cầu AI tạo payload, hệ thống chỉ đạo AI ánh xạ mối đe dọa tới [Picus Threat Library](https://www.picussecurity.com/product/picus-threat-library) đáng tin cậy.

"So our approach is ... we need to leverage AI, but we need to use it in a smart way... We need to say that, hey, I have a **threat library**. Map the campaign you built to my TTPs that I know are **high quality**, **low explosive**, and just give me an emulation plan based on what I have and on my TTPs." – Volkan Ertürk, CTO & co-founder of Picus Security.

Tại lõi của mô hình này là một thư viện mối đe dọa được xây dựng và tinh chỉnh qua 12 năm nghiên cứu mối đe dọa thực tế của Picus Labs. Thay vì tạo phần mềm độc hại từ đầu, AI phân tích tình báo bên ngoài và căn chỉnh nó với một đồ thị tri thức đã được xác thực gồm các hành động nguyên tử an toàn. Điều này đảm bảo độ chính xác, tính nhất quán và an toàn.

Để thực hiện điều này một cách đáng tin cậy, Picus sử dụng một **khung đa tác nhân** thay vì một chatbot đơn lẻ duy nhất. Mỗi tác nhân có một chức năng chuyên dụng, ngăn ngừa lỗi và tránh các vấn đề về mở rộng:

* **Planner Agent:** Điều phối quy trình công việc tổng thể
* **Researcher Agent:** Thu thập thông tin tình báo trên web
* **Threat Builder Agent:** Lắp ghép chuỗi tấn công
* **Validation Agent:** Kiểm tra công việc của các tác nhân khác để ngăn chặn hallucination

## Trường Hợp Thực Tế: Ánh Xạ Chiến Dịch Tấn Công FIN8

Để minh họa cách hệ thống hoạt động trong thực tế, dưới đây là quy trình nền tảng Picus theo khi xử lý một yêu cầu liên quan đến nhóm đe dọa “[FIN8](https://www.picussecurity.com/resource/blog/fin8-enhances-its-campaigns-for-advanced-privilege-escalation)”. Ví dụ này cho thấy cách một liên kết tin tức đơn lẻ có thể được chuyển thành một hồ sơ mô phỏng an toàn, chính xác trong vài giờ.

_Một buổi trình diễn cùng quá trình này đã được Picus CTO Volkan Ertürk minh họa trong BAS Summit._

### Bước 1: Thu Thập Tình Báo và Nguồn

Quy trình bắt đầu khi người dùng nhập một URL duy nhất, có thể là một báo cáo mới về một chiến dịch FIN8.

**Researcher Agent** không dừng lại ở nguồn đơn lẻ đó. Nó thu thập các liên kết liên quan, xác thực độ tin cậy của các nguồn đó và tổng hợp dữ liệu để xây dựng một "**báo cáo tình báo hoàn chỉnh**."

### Bước 2: Phân Tích và Phân Rã Hành Vi

Khi tình báo được thu thập, hệ thống thực hiện phân tích hành vi. Nó phân rã câu chuyện chiến dịch thành các thành phần kỹ thuật, xác định các TTP cụ thể mà kẻ tấn công sử dụng.

Mục tiêu ở đây là hiểu _lưu lượng_ của toàn bộ cuộc tấn công, không chỉ các chỉ số tĩnh.

### Bước 3: Ánh Xạ An Toàn thông qua Knowledge Graph

Đây là van an toàn quan trọng.

**Threat Builder Agent** lấy các TTP đã xác định và truy vấn máy chủ Picus MCP (Model Context Protocol). Bởi vì thư viện mối đe dọa nằm trên một đồ thị tri thức, AI có thể ánh xạ hành vi độc hại của kẻ tấn công sang một hành động mô phỏng _an toàn_ tương ứng từ thư viện Picus.

Ví dụ, nếu FIN8 sử dụng một phương pháp cụ thể để trích xuất thông tin đăng nhập, AI sẽ chọn mô-đun Picus vô hại kiểm tra điểm yếu đó mà không thực sự trích xuất bất kỳ thông tin đăng nhập thực nào.

### Bước 4: Xâu Chuỗi và Xác Thực

Cuối cùng, các tác nhân xâu chuỗi những hành động này thành chuỗi tấn công mô phỏng giống với playbook của kẻ thù. **Validation Agent** rà soát việc ánh xạ để đảm bảo không có bước nào được hallucinate hoặc lỗi tiềm ẩn nào được đưa vào.

Kết quả là một hồ sơ mô phỏng sẵn sàng chạy chứa chính xác các MITRE tactics và các hành động Picus cần thiết để kiểm tra mức độ sẵn sàng của tổ chức.

![Hình 1. Ánh xạ Chuỗi Tấn Công với Picus Smart Threat](https://www.bleepstatic.com/images/news/security/p/picus/agentic-ai/attack-chain.jpg)

**Hình 1. Ánh xạ Chuỗi Tấn Công với Picus Smart Threat**

## Tương Lai: Quản Lý Phơi Nhiễm Dưới Dạng Đàm Thoại

Ngoài việc xây dựng mối đe dọa, cách tiếp cận agentic này đang thay đổi giao diện của việc xác thực bảo mật. Picus đang tích hợp những khả năng này vào một giao diện hội thoại có tên "[Numi AI](https://www.picussecurity.com/resource/blog/picus-introduces-numi-ai-your-new-virtual-security-analyst)."

Điều này chuyển trải nghiệm người dùng từ việc điều hướng các bảng điều khiển phức tạp sang các tương tác dựa trên ý định đơn giản, rõ ràng hơn.

Ví dụ, một kỹ sư bảo mật có thể bày tỏ ý định ở mức cao, "**Tôi không muốn bất kỳ mối đe dọa cấu hình nào**", và AI giám sát môi trường, cảnh báo người dùng chỉ khi các thay đổi chính sách liên quan hoặc mối đe dọa mới vi phạm ý định cụ thể đó.

![Hình 2. Smart Threat với Picus Numi AI](https://www.bleepstatic.com/images/news/security/p/picus/agentic-ai/25.png)

**Hình 2. Smart Threat với Picus Numi AI**

Sự chuyển dịch hướng tới "**xác thực bảo mật dựa trên ngữ cảnh**" cho phép các tổ chức _ưu tiên vá lỗ dựa trên những gì thực sự có thể bị khai thác_.

Bằng cách kết hợp tình báo mối đe dọa do AI dẫn dắt với supervised machine learning dự đoán hiệu quả kiểm soát trên các thiết bị không có tác nhân, các đội có thể phân biệt giữa các lỗ hổng mang tính lý thuyết và rủi ro thực sự đối với tổ chức và môi trường cụ thể của họ.

Trong một bối cảnh nơi các tác nhân đe dọa di chuyển nhanh, khả năng biến một tiêu đề thành một chiến lược phòng thủ đã được xác thực trong vài giờ không còn là một sự xa xỉ; **đó là một yêu cầu thiết yếu**.

Cách tiếp cận của Picus gợi ý rằng cách tốt nhất để sử dụng AI không phải là để nó viết phần mềm độc hại, mà là để nó tổ chức việc phòng thủ.

Thu hẹp khoảng cách giữa việc phát hiện mối đe dọa và xác thực phòng thủ của bạn.

**[Yêu cầu một bản demo](https://hubs.li/Q03WnJ5G0)** để xem agentic AI của Picus hoạt động, và tìm hiểu cách triển khai tình báo mối đe dọa nóng trước khi quá muộn.

_Lưu ý: Bài viết này được viết chuyên môn và góp phần bởi [Sila Ozeren Hacioglu](https://www.linkedin.com/in/silaozeren/), Kỹ sư Nghiên cứu Bảo mật tại Picus Security._

_Được tài trợ và viết bởi [Picus Security](https://hubs.li/Q03WnJ5G0)._