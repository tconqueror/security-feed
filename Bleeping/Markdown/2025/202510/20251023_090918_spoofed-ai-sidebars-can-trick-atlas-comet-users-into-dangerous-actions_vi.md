# Thanh bên AI giả mạo có thể lừa người dùng Atlas, Comet làm theo các hành động nguy hiểm

![Thanh bên AI giả mạo có thể lừa người dùng Atlas, Comet làm theo các hành động nguy hiểm](https://www.bleepstatic.com/content/hl-images/2022/05/12/evil-hacker-ai.jpg)

Các trình duyệt Atlas của OpenAI và Comet của Perplexity dễ bị tấn công giả mạo thanh bên AI tích hợp và có thể khiến người dùng làm theo các hướng dẫn độc hại.

Cuộc tấn công AI Sidebar Spoofing được các nhà nghiên cứu tại công ty bảo mật trình duyệt SquareX phát triển và hoạt động trên các phiên bản mới nhất của cả hai trình duyệt.

Các nhà nghiên cứu đã tạo ba kịch bản tấn công thực tế nơi một tác nhân đe dọa có thể sử dụng AI Sidebar Spoofing để đánh cắp tiền điện tử, truy cập Gmail và Google Drive của mục tiêu, và chiếm quyền điều khiển thiết bị.

Atlas và Comet là các trình duyệt AI dạng tác nhân (agentic) tích hợp các mô hình ngôn ngữ lớn (LLMs) vào một thanh bên để người dùng tương tác khi duyệt web: yêu cầu tóm tắt trang hiện tại, thực thi lệnh, hoặc thực hiện các nhiệm vụ tự động.

Comet được phát hành vào tháng Bảy, trong khi ChatGPT Atlas có sẵn cho macOS đầu tuần này. Kể từ khi ra mắt, Comet đã trở thành mục tiêu của nhiều nghiên cứu \[[1](https://www.bleepingcomputer.com/news/security/commetjacking-attack-tricks-comet-browser-into-stealing-emails/), [2](https://www.bleepingcomputer.com/news/security/perplexitys-comet-ai-browser-tricked-into-buying-fake-items-online/), [3](http://brave.com/blog/unseeable-prompt-injections/)\] cho thấy nó tiềm ẩn rủi ro bảo mật trong một số tình huống nhất định.

## Tiêm một tác nhân AI giả mạo

SquareX nhận thấy rằng cả trên Comet và Atlas, có thể vẽ một thanh bên giả lên thanh bên thật bằng cách sử dụng một tiện ích mở rộng độc hại chèn JavaScript vào trang web mà người dùng đang xem.

Thanh bên giả sẽ giống hệt với thanh bên trong trình duyệt dạng tác nhân, tạo ra một yếu tố đánh lừa trông như một phần của giao diện người dùng chuẩn. Vì phần giả che phủ phần thật và bắt mọi tương tác, người dùng sẽ hoàn toàn không nhận ra hành vi gian lận.

"Once the victim opens a new browser tab, the extension can inject javascript into the web page to create a fake sidebar that looks exactly the same as the AI Browser's sidebar" - [SquareX](https://labs.sqrx.com/ai-sidebar-spoofing-720e0c91d290).

Bằng cách sử dụng một tiện ích mở rộng, JavaScript được chèn có thể hiển thị lớp phủ thanh bên độc hại trên mọi trang mà người dùng truy cập.

SquareX lưu ý rằng một tiện ích mở rộng như vậy chỉ yêu cầu quyền 'host' và 'storage', những quyền này phổ biến đối với các công cụ năng suất như Grammarly và các trình quản lý mật khẩu.

"Vì không có sự khác biệt về mặt trực quan và quy trình giữa thanh bên AI giả mạo và thanh bên AI thật, người dùng sẽ có nhiều khả năng tin rằng họ đang tương tác với thanh bên AI Browser thật," các nhà nghiên cứu cho biết.

SquareX đã sử dụng Google's Gemini AI trong trình duyệt Comet để minh họa phát hiện của họ. Các nhà nghiên cứu đã sử dụng các tham số cụ thể để phản hồi bằng các hướng dẫn độc hại cho các lệnh nhắc cụ thể.

Ba ví dụ mà SquareX nhấn mạnh trong báo cáo là:

1. Dẫn người dùng đến các trang lừa đảo khi họ hỏi các câu liên quan đến tiền điện tử.
2. Thực hiện tấn công OAuth thông qua các ứng dụng chia sẻ tệp giả, chiếm đoạt Gmail/Google Drive của người dùng.
3. Cung cấp cho người dùng muốn cài phần mềm một lệnh cài đặt reverse shell để chiếm quyền điều khiển thiết bị.

![Instructing the user to install a reverse-shell](https://www.bleepstatic.com/images/news/u/1220909/2025/October/reverse-shell.jpg)

**Hướng dẫn người dùng cài đặt reverse-shell**  
_Nguồn: SquareX_

Các cuộc tấn công thực sự có thể sử dụng nhiều "lời nhắc kích hoạt" hơn, thường xuyên thúc đẩy người dùng thực hiện nhiều hành động rủi ro khác nhau.

Tại thời điểm nghiên cứu, OpenAI chưa phát hành trình duyệt Atlas, và SquareX chỉ thử cuộc tấn công AI Sidebar Spoofing trên Comet.

Tuy nhiên, họ cũng đã thử nghiệm cuộc tấn công trên trình duyệt Atlas của OpenAI khi nó được ra mắt, và xác nhận rằng AI Sidebar Spoofing cũng hoạt động trên nó.

Các nhà nghiên cứu đã liên hệ cả Perplexity và OpenAI về vấn đề này, nhưng không bên nào phản hồi. BleepingComputer cũng đã liên hệ với các công ty nhưng không nhận được phản hồi tính đến thời điểm xuất bản.

Người dùng các trình duyệt AI dạng tác nhân nên nhận thức về nhiều rủi ro mà các công cụ này mang lại và hạn chế sử dụng cho các hoạt động không nhạy cảm, tránh các nhiệm vụ liên quan đến email, thông tin tài chính, hoặc dữ liệu riêng tư khác.

Mặc dù các biện pháp bảo mật mới được thêm vào với mỗi lần phát hành để đối phó với các cuộc tấn công mới nổi, những trình duyệt này vẫn chưa đạt tới mức độ trưởng thành cần thiết để giảm bề mặt tấn công xuống mức chấp nhận được cho bất cứ việc gì ngoài duyệt web giải trí.