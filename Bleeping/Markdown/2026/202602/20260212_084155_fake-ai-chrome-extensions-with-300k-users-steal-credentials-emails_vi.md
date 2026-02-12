# Tiện ích mở rộng Chrome giả mạo AI với 300K người dùng đánh cắp thông tin đăng nhập, email

![Tiện ích mở rộng Chrome giả mạo AI với 300K người dùng đánh cắp thông tin đăng nhập, email](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Một bộ 30 tiện ích mở rộng Chrome độc hại đã được cài đặt bởi hơn 300.000 người dùng đang ngụy trang thành trợ lý AI để đánh cắp thông tin đăng nhập, nội dung email và thông tin duyệt web.

Một số tiện ích mở rộng vẫn còn hiện diện trong Chrome Web Store và đã được cài đặt bởi hàng chục nghìn người dùng, trong khi những tiện ích khác chỉ hiển thị số lượt cài đặt nhỏ.

Các nhà nghiên cứu tại nền tảng bảo mật trình duyệt LayerX đã phát hiện chiến dịch tiện ích mở rộng độc hại này và đặt tên là AiFrame. Họ phát hiện rằng tất cả các tiện ích mở rộng được phân tích đều là một phần của cùng một nỗ lực độc hại vì chúng giao tiếp với cơ sở hạ tầng dưới một miền duy nhất, _tapnetic\[.\]pro_.

[![Wiz](https://www.bleepstatic.com/c/w/Secured-Images-970x250.png)](https://www.wiz.io/lp/secure-images-101-a-visual-guide?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FHardened-Images-101-Digital-Poster&sfcid=701Py00000WFCeLIAX&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=Secured-Images-101)

Theo họ, tiện ích mở rộng phổ biến nhất trong chiến dịch AiFrame có 80.000 người dùng và được gọi là Gemini AI Sidebar (fppbiomdkfbhgjjdmojlogeceejinadg), nhưng nó không còn trên Chrome Web Store nữa.

Tuy nhiên, BleepingComputer phát hiện rằng các tiện ích mở rộng khác với hàng nghìn người dùng vẫn còn hiện diện trên kho lưu trữ của Google cho các tiện ích mở rộng Chrome. Cần lưu ý rằng tên có thể khác nhau trong một số trường hợp, nhưng định danh là giống nhau.

1. **AI Sidebar** (gghdfkafnhfpaooiolhncejnlgglhkhe) – 70.000 người dùng
2. **AI Assistant** (nlhpidbjmmffhoogcennoiopekbiglbp) – 60.000 người dùng
3. **ChatGPT Translate** (acaeafediijmccnjlokgcdiojiljfpbe) – 30.000 người dùng
4. **AI GPT** (kblengdlefjpjkekanpoidgoghdngdgl) – 20.000 người dùng
5. **ChatGPT** (llojfncgbabajmdglnkbhmiebiinohek) – 20.000 người dùng
6. **AI Sidebar** (djhjckkfgancelbmgcamjimgphaphjdl) – 10.000 người dùng
7. **Google Gemini** (fdlagfnfaheppaigholhoojabfaapnhb) – 10.000 người dùng

LayerX phát hiện rằng tất cả 30 tiện ích mở rộng đều có cùng cấu trúc nội bộ, logic JavaScript, quyền và cơ sở hạ tầng backend.

Các tiện ích bổ sung trình duyệt độc hại này không triển khai chức năng AI cục bộ; thay vào đó, chúng cung cấp tính năng hứa hẹn bằng cách hiển thị iframe toàn màn hình để tải nội dung từ miền từ xa.

Điều này, tự nó đã rủi ro, vì nhà xuất bản có thể thay đổi logic của tiện ích mở rộng bất cứ lúc nào mà không cần đẩy cập nhật - giống như trong trường hợp [Microsoft Office Add-ins](https://www.bleepingcomputer.com/news/security/microsoft-store-outlook-add-in-hijacked-to-steal-4-000-microsoft-accounts/) - do đó tránh được một cuộc đánh giá mới.

Trong nền, các tiện ích mở rộng trích xuất nội dung trang từ các trang web người dùng truy cập, bao gồm cả các trang xác thực nhạy cảm, sử dụng thư viện Readability của Mozilla.

LayerX cho biết một tập hợp con gồm 15 tiện ích mở rộng nhắm mục tiêu cụ thể vào dữ liệu Gmail, sử dụng một kịch bản nội dung chuyên dụng chạy ở 'document\_start' trên 'mail.google.com' và tiêm các phần tử UI.

Kịch bản đọc trực tiếp nội dung email hiển thị từ DOM và liên tục trích xuất văn bản chủ đề email qua '.textContent.' Các nhà nghiên cứu lưu ý rằng ngay cả bản nháp email cũng có thể bị chụp.

"Khi các tính năng liên quan đến Gmail như trả lời hoặc tóm tắt được hỗ trợ bởi AI được gọi, nội dung email được trích xuất được truyền vào logic của tiện ích mở rộng và truyền đến cơ sở hạ tầng backend của bên thứ ba do nhà điều hành tiện ích mở rộng kiểm soát," [LayerX giải thích](https://layerxsecurity.com/blog/aiframe-fake-ai-assistant-extensions-targeting-260000-chrome-users-via-injected-iframes/?utm%5Fsource=BC) trong một báo cáo hôm nay.

"Kết quả là, văn bản tin nhắn email và dữ liệu ngữ cảnh liên quan có thể được gửi ra khỏi thiết bị, ngoài ranh giới bảo mật của Gmail, đến các máy chủ từ xa."

Các tiện ích mở rộng cũng có cơ chế nhận dạng giọng nói và tạo bản ghi được kích hoạt từ xa sử dụng 'Web Speech API,' trả kết quả về cho các nhà điều hành. Tùy thuộc vào quyền được cấp, các tiện ích mở rộng thậm chí có thể rút ra cuộc trò chuyện từ môi trường của nạn nhân.

BleepingComputer đã liên hệ với Google để nhận xét về các phát hiện của LayerX, nhưng chúng tôi chưa nhận được phản hồi vào thời điểm xuất bản.

Được khuyến nghị kiểm tra danh sách các chỉ số xâm phạm của LayerX để có bộ tiện ích mở rộng độc hại đầy đủ. Nếu xâm phạm được xác nhận, người dùng nên đặt lại mật khẩu cho tất cả các tài khoản.