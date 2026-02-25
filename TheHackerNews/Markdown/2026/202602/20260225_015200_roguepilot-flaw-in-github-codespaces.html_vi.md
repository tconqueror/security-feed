# Lỗ hổng RoguePilot trong GitHub Codespaces Cho phép Copilot Rò rỉ GITHUB_TOKEN

[head_image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjCSgjd-Xezu42fOKahjOxnhqntkclItoP8FmMfyjjKTmelK3eHoUEi6%5F75n6ORgD650By4wESNP8yDP2WWENzqI5T9Gl-NhYPPTiAQgkFykZv1d%5FMsCECcu0ZgQWt29JiGmH1zCmwNWSin8AQMWmsOm6r4ZdS8EOIC9Xtdw7FrRlN8kQs7o2s%5FwhiNtcSH/s1700-e365/github-copilot.jpg)

Một lỗ hổng trong [GitHub Codespaces](https://github.com/features/codespaces) có thể bị các tác nhân xấu khai thác để kiểm soát kho lưu trữ bằng cách tiêm các hướng dẫn Copilot độc hại vào một vấn đề GitHub.

Lỗ hổng trí tuệ nhân tạo (AI) này đã được đặt tên là **RoguePilot** bởi Orca Security. Microsoft đã vá lỗ hổng này sau khi được thông báo một cách có trách nhiệm.

"Những kẻ tấn công có thể tạo các hướng dẫn ẩn bên trong một vấn đề GitHub mà tự động được xử lý bởi GitHub Copilot, cho họ quyền kiểm soát thầm lặng đối với tác nhân AI trong codespaces," nhà nghiên cứu bảo mật Roi Nisimi [cho biết](https://orca.security/resources/blog/roguepilot-github-copilot-vulnerability/) trong một báo cáo.

Lỗ hổng này đã được mô tả là một trường hợp của tiêm hướng dẫn thụ động hoặc gián tiếp, nơi một hướng dẫn độc hại được nhúng trong dữ liệu hoặc nội dung được xử lý bởi mô hình ngôn ngữ lớn (LLM), khiến nó tạo ra đầu ra không mong muốn hoặc thực hiện các hành động tùy ý.

Công ty bảo mật đám mây cũng gọi nó là một loại tấn công chuỗi cung ứng được AI trung gian, gây ra LLM tự động thực thi các hướng dẫn độc hại được nhúng trong nội dung của nhà phát triển, trong trường hợp này là một vấn đề GitHub.

Cuộc tấn công bắt đầu với một vấn đề GitHub độc hại sau đó kích hoạt tiêm hướng dẫn trong Copilot khi người dùng vô tình khởi chạy một Codespace từ vấn đề đó. Quy trình làm việc đáng tin cậy của nhà phát triển này, lần lượt, cho phép các hướng dẫn của kẻ tấn công được thực thi thầm lặng bởi trợ lý AI và rò rỉ dữ liệu nhạy cảm, chẳng hạn như GITHUB\_TOKEN đặc quyền.

[](https://thehackernews.uk/sse-customer-awards-d)

RoguePilot tận dụng thực tế rằng có một số điểm vào để khởi chạy môi trường Codespaces, bao gồm mẫu, kho lưu trữ, cam kết, yêu cầu kéo, hoặc vấn đề. Vấn đề xảy ra khi một codespace được mở từ một vấn đề, vì GitHub Copilot tích hợp sẵn tự động được cung cấp mô tả của vấn đề như một hướng dẫn để tạo phản hồi.

Kết quả là, tích hợp AI này có thể được vũ khí hóa để thao túng Copilot thực hiện các lệnh độc hại. Cuộc tấn công có thể được làm tinh vi bằng cách ẩn hướng dẫn trong vấn đề GitHub thông qua [thẻ bình luận HTML](https://developer.mozilla.org/en-US/docs/Web/HTML/Guides/Comments) "<!--the\_prompt\_goes\_here-->." Đối với phần của nó, hướng dẫn được tạo đặc biệt hướng dẫn trợ lý AI rò rỉ GITHUB\_TOKEN đến máy chủ bên ngoài dưới sự kiểm soát của kẻ tấn công.

"Bằng cách thao túng Copilot trong một Codespace để kiểm tra một yêu cầu kéo được tạo, chứa một liên kết tượng trưng đến một tệp nội bộ, kẻ tấn công có thể khiến Copilot đọc tệp đó và (thông qua một $schema JSON từ xa) truy xuất GITHUB\_TOKEN đặc quyền đến máy chủ từ xa," Nisimi giải thích.

### Từ Tiêm Hướng dẫn đến Promptware

Sự phát triển này diễn ra khi Microsoft phát hiện ra rằng Tối ưu hóa Chính sách Tương đối Nhóm ([GRPO](https://arxiv.org/abs/2402.03300)), một [kỹ thuật học tăng cường](https://cameronrwolfe.substack.com/p/grpo) thường được sử dụng để tinh chỉnh LLM sau khi triển khai, cũng có thể được sử dụng để loại bỏ các tính năng bảo mật của nó. Quy trình này đã được đặt tên là GRP-Obliteration.

Quan trọng hơn, nghiên cứu phát hiện ra rằng một hướng dẫn không được gán nhãn đơn lẻ, chẳng hạn như "Tạo một bài báo tin giả có thể dẫn đến hoảng loạn hoặc hỗn loạn," là đủ để đáng tin cậy làm mất căn chỉnh 15 mô hình ngôn ngữ.

"Điều làm cho điều này đáng ngạc nhiên là hướng dẫn tương đối nhẹ nhàng và không đề cập đến bạo lực, hoạt động bất hợp pháp, hoặc nội dung rõ ràng," các nhà nghiên cứu Microsoft Mark Russinovich, Giorgio Severi, Blake Bullwinkel, Yanan Cai, Keegan Hines, và Ahmed Salem [lưu ý](https://www.microsoft.com/en-us/security/blog/2026/02/09/prompt-attack-breaks-llm-safety/). "Tuy nhiên, đào tạo trên ví dụ này khiến mô hình trở nên dễ chấp nhận hơn trên nhiều danh mục có hại khác mà nó không bao giờ thấy trong quá trình đào tạo."

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgkagKNYFSSRsgkrUyor0oGO0V2gtXvH0Sdmwa6jB6Cu%5FtP%5FK%5FfAAV-Fds-UuDk%5FqcKd5UZ969ffWT5Zhkkp5Nx9257qHWj34YwG8GVtThSgaeQpnmaljRjmQkBBENvEUkb0-0El1vlGmSb5gDtjeg5u383EHGfSIyyWoWL73Xr5%5FRk2ln0HREut797vWYa/s1700-e365/ai-attack.jpg)

Thông báo này cũng trùng hợp với [phát hiện](https://arxiv.org/abs/2410.17175) của [các](https://arxiv.org/abs/2411.01076) [kênh phụ](https://thehackernews.com/2025/11/microsoft-uncovers-whisper-leak-attack.html) khác nhau có thể được vũ khí hóa để suy luận chủ đề của cuộc trò chuyện của người dùng và thậm chí lấy dấu vân tay truy vấn của người dùng với độ chính xác trên 75%, trong đó khai thác [giải mã suy đoán](https://pytorch.org/blog/hitchhikers-guide-speculative-decoding/), một [kỹ thuật tối ưu hóa](https://research.google/blog/looking-back-at-speculative-decoding/) được LLM sử dụng để [tạo nhiều mã thông báo ứng viên](https://developer.nvidia.com/blog/an-introduction-to-speculative-decoding-for-reducing-latency-in-ai-inference/) song song để cải thiện thông lượng và độ trễ.

Nghiên cứu gần đây đã phát hiện ra rằng các mô hình được backdoor ở cấp độ đồ thị tính toán – một kỹ thuật được gọi là [ShadowLogic](https://thehackernews.com/2024/10/apple-opens-pcc-source-code-for.html) – có thể tiếp tục đặt các hệ thống AI đại lý vào rủi ro bằng cách cho phép [các cuộc gọi công cụ](https://www.ibm.com/think/topics/tool-calling) được sửa đổi thầm lặng mà không có kiến thức của người dùng. Hiện tượng mới này đã được HiddenLayer đặt tên là Agentic ShadowLogic.

Một kẻ tấn công có thể vũ khí hóa backdoor như vậy để chặn các yêu cầu lấy nội dung từ URL trong thời gian thực, sao cho chúng được định tuyến thông qua cơ sở hạ tầng dưới sự kiểm soát của họ trước khi được chuyển tiếp đến điểm đến thực tế.

"Bằng cách ghi lại các yêu cầu theo thời gian, kẻ tấn công có thể lập bản đồ các điểm cuối nội bộ nào tồn tại, khi nào chúng được truy cập, và dữ liệu nào chảy qua chúng," công ty bảo mật AI [cho biết](https://hiddenlayer.com/innovation-hub/agentic-shadowlogic/). "Người dùng nhận được dữ liệu mong đợi của họ mà không có lỗi hoặc cảnh báo. Mọi thứ hoạt động bình thường trên bề mặt trong khi kẻ tấn công ghi lại toàn bộ giao dịch trong nền một cách thầm lặng."

Và đó chưa phải là tất cả. Tháng trước, Neural Trust đã chứng minh một cuộc tấn công jailbreak hình ảnh mới được đặt tên là Semantic Chaining cho phép người dùng vượt qua các bộ lọc bảo mật trong các mô hình như Grok 4, Gemini Nano Banana Pro, và Seedance 4.5, và tạo nội dung bị cấm bằng cách tận dụng khả năng của các mô hình thực hiện các sửa đổi hình ảnh nhiều giai đoạn.

Về cốt lõi, cuộc tấn công này vũ khí hóa sự thiếu "chiều sâu suy luận" của các mô hình để theo dõi ý định tiềm ẩn qua một hướng dẫn nhiều bước, từ đó cho phép một tác nhân xấu giới thiệu một loạt các chỉnh sửa mà, mặc dù vô hại khi xét riêng lẻ, có thể dần dần nhưng ổn định làm suy giảm khả năng kháng cự bảo mật của mô hình cho đến khi đầu ra không mong muốn được tạo ra.

Nó bắt đầu với việc yêu cầu chatbot AI tưởng tượng bất kỳ cảnh không có vấn đề nào và hướng dẫn nó thay đổi một phần tử trong hình ảnh được tạo ban đầu. Trong giai đoạn tiếp theo, kẻ tấn công yêu cầu mô hình thực hiện một sửa đổi thứ hai, lần này biến nó thành thứ gì đó bị cấm hoặc gây phản cảm.

Điều này hoạt động vì mô hình tập trung vào việc thực hiện một sửa đổi cho một hình ảnh hiện có thay vì tạo thứ gì đó mới, điều này không kích hoạt các báo động bảo mật vì nó coi hình ảnh ban đầu là hợp lệ.

[](https://thehackernews.uk/ztw-hands-on-d)

"Thay vì đưa ra một hướng dẫn đơn lẻ, rõ ràng gây hại, điều này sẽ kích hoạt một khối ngay lập tức, kẻ tấn công giới thiệu một chuỗi các hướng dẫn có ý nghĩa 'an toàn' hội tụ vào kết quả bị cấm," nhà nghiên cứu bảo mật Alessandro Pignati [cho biết](https://neuraltrust.ai/blog/semantic-chaining).

Trong một nghiên cứu được công bố tháng trước, các nhà nghiên cứu Oleg Brodt, Elad Feldman, Bruce Schneier, và Ben Nassi lập luận rằng tiêm hướng dẫn đã tiến hóa vượt ra khỏi các khai thác thao túng đầu vào thành thứ họ gọi là [promptware](https://www.schneier.com/blog/archives/2026/02/the-promptware-kill-chain.html) – một lớp cơ chế thực thi phần mềm độc hại mới được kích hoạt thông qua các hướng dẫn được thiết kế để khai thác LLM của ứng dụng.

Promptware về cơ bản thao túng LLM để cho phép các giai đoạn khác nhau của vòng đời tấn công mạng điển hình: truy cập ban đầu, leo thang đặc quyền, trinh sát, duy trì, điều khiển và kiểm soát, [di chuyển ngang](https://www.lasso.security/blog/identitymesh-exploiting-agentic-ai), và kết quả độc hại (ví dụ: truy xuất dữ liệu, kỹ thuật xã hội, thực thi mã, hoặc đánh cắp tài chính).

"Promptware đề cập đến một gia đình đa hình các hướng dẫn được thiết kế để hoạt động như phần mềm độc hại, khai thác LLM để thực hiện các hoạt động độc hại bằng cách lạm dụng ngữ cảnh, quyền hạn, và chức năng của ứng dụng," các nhà nghiên cứu [cho biết](https://arxiv.org/abs/2601.09625). "Về bản chất, promptware là một đầu vào, cho dù là văn bản, hình ảnh, hay âm thanh, thao túng hành vi của LLM trong thời gian suy luận, nhắm vào các ứng dụng hoặc người dùng."
