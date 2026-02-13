# Các tiện ích Chrome giả mạo AI với 300.000 người dùng đánh cắp thông tin xác thực, email

![Fake AI Chrome extensions with 300K users steal credentials, emails](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Một tập hợp 30 tiện ích Chrome độc hại đã được cài đặt bởi hơn 300.000 người dùng đang đóng giả AI để đánh cắp thông tin xác thực, nội dung email và dữ liệu duyệt web.

Một số tiện ích vẫn còn tồn tại trong Chrome Web Store và đã được cài đặt bởi hàng chục nghìn người dùng, trong khi những tiện ích khác có số lượng cài đặt thấp hơn.

Các nhà nghiên cứu tại nền tảng bảo mật trình duyệt LayerX đã phát hiện chiến dịch tiện ích độc hại này và đặt tên là AiFrame. Họ phát hiện tất cả các tiện ích được phân tích đều thuộc cùng một hoạt động độc hại vì chúng giao tiếp với cơ sở hạ tầng dưới một tên miền duy nhất, _tapnetic[.]pro_.

[![Wiz](https://www.bleepstatic.com/c/w/GitLab-970x250.png)](https://www.wiz.io/lp/gitlab-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FGitLab-Security-Best-Practices-Cheat-Sheet&sfcid=701Vh00000Wn1rmIAB&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=GitLab-Best-Practices) 

Theo họ, tiện ích phổ biến nhất trong chiến dịch AiFrame có 80.000 người dùng và được gọi là Gemini AI Sidebar (fppbiomdkfbhgjjdmojlogeceejinadg), nhưng nó không còn trên Chrome Web Store.

Tuy nhiên, BleepingComputer phát hiện các tiện ích khác có hàng nghìn người dùng vẫn tồn tại trên kho lưu trữ tiện ích Chrome của Google. Cần lưu ý rằng tên gọi có thể khác nhau trong một số trường hợp, nhưng định danh vẫn giống nhau.

1. **AI Sidebar** (gghdfkafnhfpaooiolhncejnlgglhkhe) – 70.000 người dùng
2. **AI Assistant** (nlhpidbjmmffhoogcennoiopekbiglbp) – 60.000 người dùng
3. **ChatGPT Translate** (acaeafediijmccnjlokgcdiojiljfpbe) – 30.000 người dùng
4. **AI GPT** (kblengdlefjpjkekanpoidgoghdngdgl) – 20.000 người dùng
5. **ChatGPT** (llojfncgbabajmdglnkbhmiebiinohek) – 20.000 người dùng
6. **AI Sidebar** (djhjckkfgancelbmgcamjimgphaphjdl) – 10.000 người dùng
7. **Google Gemini** (fdlagfnfaheppaigholhoojabfaapnhb) – 10.000 người dùng

LayerX phát hiện tất cả 30 tiện ích chia sẻ cùng cấu trúc nội bộ, logic JavaScript, quyền truy cập và cơ sở hạ tầng backend.

Các tiện ích trình duyệt độc hại này không triển khai chức năng AI cục bộ; thay vào đó, chúng cung cấp tính năng được hứa hẹn bằng cách hiển thị iframe toàn màn hình để tải nội dung từ một tên miền từ xa.

Điều này tự thân đã rủi ro, vì nhà phát hành có thể thay đổi logic của tiện ích bất kỳ lúc nào mà không cần cập nhật - giống như trường hợp của [Microsoft Office Add-ins](https://www.bleepingcomputer.com/news/security/microsoft-store-outlook-add-in-hijacked-to-steal-4-000-microsoft-accounts/) \- qua đó tránh được việc đánh giá lại.

Ở chế độ nền, các tiện ích này trích xuất nội dung trang từ các trang web người dùng truy cập, bao gồm cả các trang xác thực nhạy cảm, bằng thư viện Readability của Mozilla.

LayerX cho biết một tập hợp con gồm 15 tiện ích nhắm mục tiêu cụ thể vào dữ liệu Gmail, sử dụng tập lệnh nội dung chuyên dụng chạy ở 'document_start' trên 'mail.google.com' và tiêm các phần tử giao diện người dùng.

Tập lệnh đọc nội dung email hiển thị trực tiếp từ DOM và liên tục trích xuất văn bản chủ đề email qua '.textContent'. Các nhà nghiên cứu lưu ý rằng ngay cả bản nháp email cũng có thể bị thu thập.

"Khi các tính năng liên quan đến Gmail như trả lời hoặc tóm tắt được hỗ trợ bởi AI được kích hoạt, nội dung email được trích xuất sẽ được chuyển vào logic của tiện ích và truyền đến cơ sở hạ tầng backend bên thứ ba do nhà vận hành tiện ích kiểm soát," [LayerX giải thích](https://layerxsecurity.com/blog/aiframe-fake-ai-assistant-extensions-targeting-260000-chrome-users-via-injected-iframes/?utm%5Fsource=BC) trong một báo cáo hôm nay.

"Do đó, văn bản tin nhắn email và dữ liệu ngữ cảnh liên quan có thể được gửi ra khỏi thiết bị, vượt ra ngoài ranh giới bảo mật của Gmail, đến các máy chủ từ xa."

Các tiện ích này cũng có cơ chế nhận dạng giọng nói và tạo bản ghi được kích hoạt từ xa bằng 'Web Speech API', trả về kết quả cho các nhà vận hành. Tùy thuộc vào các quyền đã cấp, các tiện ích thậm chí có thể lấy cắp các cuộc trò chuyện từ môi trường của nạn nhân.

BleepingComputer đã liên hệ với Google để nhận bình luận về phát hiện của LayerX, nhưng chưa nhận được phản hồi vào thời điểm công bố.

Nên kiểm tra danh sách chỉ số xâm phạm (IoC) của LayerX để xem toàn bộ tập hợp các tiện ích độc hại. Nếu xác nhận bị xâm phạm, người dùng nên đặt lại mật khẩu cho tất cả tài khoản.