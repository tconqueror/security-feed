# Microsoft mã nguồn mở mở rộng VS Code Copilot Chat trên GitHub

![Microsoft mã nguồn mở mở rộng VS Code Copilot Chat trên GitHub](https://www.bleepstatic.com/content/hl-images/2025/03/13/VSCode.jpg)

Microsoft đã phát hành mã nguồn của mở rộng GitHub Copilot Chat cho VS Code dưới giấy phép MIT.

Điều này cung cấp cho cộng đồng quyền truy cập vào toàn bộ triển khai của trợ lý lập trình dựa trên trò chuyện, bao gồm việc triển khai "chế độ agent", dữ liệu ngữ cảnh nào được gửi đến các mô hình ngôn ngữ lớn (LLMs), và thiết kế của các prompt hệ thống.

[Kho lưu trữ GitHub lưu trữ mã](https://github.com/microsoft/vscode-copilot-chat) cũng chi tiết về cơ chế thu thập telemetry, giải quyết các câu hỏi lâu dài về tính minh bạch dữ liệu trong các công cụ lập trình hỗ trợ AI.

Bước đi này được coi là [cột mốc đầu tiên](https://code.visualstudio.com/blogs/2025/06/30/openSourceAIEditorFirstMilestone) trong kế hoạch của gã khổng lồ công nghệ để tích hợp các tính năng AI trực tiếp vào trình chỉnh sửa mã nguồn mở phổ biến, một lộ trình được phác thảo lần đầu vào tháng 5 năm 2025.

Visual Studio Code, được ra mắt vào năm 2015, là một trong những trình chỉnh sửa mã phổ biến nhất trên toàn cầu và là một dự án mã nguồn mở chủ lực từ Microsoft. Nó được xây dựng trên khung Electron và hỗ trợ nhiều ngôn ngữ lập trình và mở rộng khác nhau.

GitHub Copilot Chat là một mở rộng trợ lý AI cho VS Code, cho phép các nhà phát triển trò chuyện với một mô hình dựa trên GPT4 bên trong trình chỉnh sửa để nhận trợ giúp trong các tác vụ lập trình.

Trước sự phát triển mạnh mẽ của lập trình hỗ trợ LLM và các xu hướng như "vibe coding", mở rộng này đã đạt được mức độ phổ biến cao với hơn [35 triệu cài đặt](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat) trên Marketplace của VSCode.

![Mở rộng Copilot Chat hoạt động trên IDE của VS Code](https://www.bleepstatic.com/images/news/u/1220909/2025/June/extension.jpg)

**Mở rộng Copilot Chat hoạt động trên IDE của VS Code**  
_Nguồn: GitHub_

Như nhóm VS Code [đã giải thích trước đây](https://code.visualstudio.com/blogs/2025/05/19/openSourceAIEditor), những thay đổi trong bối cảnh công cụ AI như sự phát triển nhanh chóng của hệ sinh thái AI mã nguồn mở và một sân chơi bình đẳng hơn cho tất cả đã giảm thiểu nhu cầu về sự bí mật xung quanh việc thiết kế prompt và giao diện người dùng.

Đồng thời, việc tăng cường nhắm mục tiêu vào các công cụ phát triển bởi các tác nhân độc hại đã làm tăng nhu cầu kêu gọi đóng góp từ cộng đồng để nhanh chóng xác định các vấn đề và phát triển các giải pháp hiệu quả. Thực chất, sự minh bạch giờ đây được coi là ưu việt từ góc độ bảo mật.

Điều quan trọng là cần lưu ý rằng mã cho mở rộng GitHub Copilot ban đầu, một tính năng giúp hoàn thiện mã trực tiếp, vẫn chưa được công khai. Tuy nhiên, Microsoft đã xác nhận kế hoạch chuyển đổi chức năng của nó vào mở rộng Copilot Chat mở này trong những tháng tới, hợp nhất tất cả các tính năng AI chính vào một mô-đun mã nguồn mở duy nhất.

Với việc mở rộng Copilot Chat hiện đã có sẵn công khai trên GitHub, các nhà phát triển được mời khám phá mã, đóng góp và cung cấp phản hồi của họ. Ngoài ra, cũng có một [Câu hỏi thường gặp](https://code.visualstudio.com/docs/copilot/faq) và tài liệu hoàn chỉnh để hướng dẫn các nhà phát triển thông qua kiến trúc và quy trình phát triển.