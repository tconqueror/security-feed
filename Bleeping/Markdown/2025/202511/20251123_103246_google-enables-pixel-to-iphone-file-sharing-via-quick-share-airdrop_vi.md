# Google cho phép chia sẻ tệp Pixel-to-iPhone qua Quick Share, AirDrop

![Google enables Pixel-to-iPhone file sharing via Quick Share, AirDrop](https://www.bleepstatic.com/content/hl-images/2025/11/21/greensilver.jpg)

Google đã thêm hỗ trợ tương tác giữa Android Quick Share và Apple AirDrop, cho phép người dùng chia sẻ tệp giữa các thiết bị Pixel và iPhone.

Hiện tại, chỉ các thiết bị thuộc dòng Pixel 10-series hỗ trợ khả năng truyền và nhận dữ liệu mới này, nhưng sẽ có thêm nhiều mẫu Android khác theo sau.

Quick Share (trước đây là Nearby Share) là hệ thống chia sẻ tệp không dây tích hợp của Android để gửi đa phương tiện, tài liệu và các tệp khác giữa các thiết bị Android qua Bluetooth hoặc Wi-Fi Direct.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

AirDrop là hệ thống tương đương của Apple, vốn cho đến nay chỉ hoạt động để chia sẻ tệp giữa các iPhone, iPad và Macs.

Cả hai hệ thống đều là độc quyền và theo những phương pháp kỹ thuật khác nhau, mỗi hệ thống sử dụng giao thức phát hiện, luồng xác thực, và định dạng gói tin cùng bộ phân tích riêng.

Việc thiếu một tiêu chuẩn giao tiếp chung giữa các thiết bị của Apple và Google đã hạn chế người dùng chỉ có thể chia sẻ tệp với những người cùng hệ sinh thái.

Google thông báo rằng sự hạn chế này đã được gỡ bỏ, và giờ đây mọi người có thể chia sẻ hoặc nhận tệp từ hoặc đến thiết bị iOS theo cách an toàn.

"Như một phần trong nỗ lực tiếp tục làm cho giao tiếp đa nền tảng trở nên liền mạch hơn cho người dùng, chúng tôi đã làm cho Quick Share có thể tương tác với AirDrop, cho phép chia sẻ tệp hai chiều giữa các thiết bị Android và iOS, bắt đầu với Pixel 10 Family," [đoạn thông báo](https://security.googleblog.com/2025/11/android-quick-share-support-for-airdrop-security.html) viết.

"Tính năng mới này giúp bạn có thể nhanh chóng chia sẻ ảnh, video và tệp với những người bạn chọn liên lạc, mà không phải lo lắng về loại điện thoại họ sử dụng."

Gã khổng lồ công nghệ đảm bảo với người dùng rằng hệ thống chia sẻ tệp mới được xây dựng với bảo mật làm trọng tâm, tuân thủ các biện pháp bảo vệ phát triển nghiêm ngặt của họ, bao gồm mô hình hóa mối đe dọa, các đánh giá bảo mật và quyền riêng tư nội bộ, và kiểm thử xâm nhập nội bộ.

Một cuộc kiểm toán độc lập bởi NetSPI, một công ty an ninh mạng chuyên về kiểm thử xâm nhập, quản lý bề mặt tấn công, và mô phỏng vi phạm, [đã xác nhận](http://www.netspi.com/wp-content/uploads/2025/11/google-feature-review-report.pdf) rằng hệ thống mới là vững chắc và không có rò rỉ dữ liệu.

Google cũng nhấn mạnh rằng ngôn ngữ lập trình Rust đã đóng vai trò then chốt trong triển khai này, để phân tích các gói dữ liệu không dây trong khi loại bỏ "toàn bộ lớp lỗ hổng an toàn bộ nhớ theo thiết kế."

Việc triển khai sử dụng chế độ "Everyone for 10 minutes" của AirDrop để tạo kết nối trực tiếp thiết bị-với-thiết bị mà không liên quan đến máy chủ trung gian hoặc bất kỳ điểm nào có thể ghi nhật ký dữ liệu.

Người dùng được khuyến nghị tự kiểm tra thủ công rằng thiết bị họ thấy trên màn hình thuộc về người họ muốn kết nối, vì vậy cần thận trọng ở bước này để tránh vô tình chia sẻ nội dung nhạy cảm với một thiết bị ngẫu nhiên gần đó.

Google lưu ý rằng chế độ này là bước đầu tiên trong việc thiết lập khả năng tương tác, và với sự hợp tác của Apple, họ mong muốn kích hoạt chế độ "Contacts Only" trong các bản phát hành tương lai.

BleepingComputer đã liên hệ với Apple để yêu cầu bình luận về khả năng này và mức độ sẵn sàng hợp tác hướng tới tính tương tác với Android, nhưng một phản hồi chưa có sẵn ngay lập tức.