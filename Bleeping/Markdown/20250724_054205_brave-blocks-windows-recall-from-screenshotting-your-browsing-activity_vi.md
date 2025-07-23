# Brave chặn Windows Recall khỏi việc chụp ảnh hoạt động duyệt web của bạn

![Trình duyệt Brave](https://www.bleepstatic.com/content/hl-images/2022/06/22/Brave.jpg)

Brave Software cho biết trình duyệt tập trung vào quyền riêng tư của mình sẽ chặn Windows Recall của Microsoft khỏi việc chụp hình ảnh màn hình của các cửa sổ Brave theo mặc định để bảo vệ quyền riêng tư của người dùng.

Windows Recall là một tính năng có sẵn theo yêu cầu của Windows, chụp ảnh màn hình của các cửa sổ hoạt động mỗi vài giây, phân tích chúng và cho phép người dùng Windows 11 tìm kiếm văn bản trong các bức ảnh bằng ngôn ngữ tự nhiên. Mục tiêu là giúp người dùng dễ dàng tìm thông tin về các hoạt động trước đó trong Windows.

Tuy nhiên, tính năng này đã [gây ra những chỉ trích rộng rãi](https://www.bleepingcomputer.com/news/microsoft/microsofts-new-windows-11-recall-is-a-privacy-nightmare/) vì khả năng có thể tiết lộ dữ liệu nhạy cảm của người dùng Windows, bao gồm mật khẩu, email, hồ sơ sức khỏe và thông tin tài chính.

Microsoft sau đó đã tăng cường bảo mật bằng cách cung cấp các phương pháp cho các nhà cung cấp phần mềm chọn không sử dụng Windows Recall và bảo vệ dữ liệu với Windows Hello Enhanced Sign-in Security (ESS).

Brave hiện đã quyết định chủ động kích hoạt một tính năng kỹ thuật ngăn Recall khỏi việc chụp nội dung của các cửa sổ Brave.

"Với việc Brave tập trung vào các giá trị mặc định tối đa hóa quyền riêng tư và những gì đang bị đe dọa ở đây (toàn bộ lịch sử duyệt web của bạn), chúng tôi đã chủ động vô hiệu hóa Recall cho tất cả các tab Brave," một thông báo mới từ [Brave](https://brave.com/privacy-updates/35-block-recall/) cho biết.

"Chúng tôi nghĩ rằng điều quan trọng là hoạt động duyệt web của bạn trên Brave không vô tình kết thúc trong một cơ sở dữ liệu vĩnh viễn, điều này đặc biệt dễ bị lạm dụng trong những trường hợp nhạy cảm về quyền riêng tư như bạo lực trong quan hệ thân mật."

Một [vấn đề trên GitHub của Brave](https://github.com/brave/brave-browser/issues/46284) giải thích rằng các nhà phát triển đã sử dụng [SetInputScope API](https://learn.microsoft.com/en-us/windows/ai/recall/recall-web-browsers) của Microsoft và thiết lập phạm vi đầu vào là IS_PRIVATE cho tất cả các cửa sổ trình duyệt. Điều này cho Windows biết rằng nội dung không nên được chụp hoặc lập chỉ mục bởi Recall.

"Microsoft cho biết một trình duyệt web có thể sử dụng SetInputScope để thiết lập phạm vi là IS_PRIVATE để đảm bảo rằng Recall không lưu lịch sử duyệt web của người dùng," nội dung vấn đề trên GitHub của Brave cho biết.

"Chúng tôi có thể ép điều đó trở thành sự thật cho tất cả các cửa sổ trong renderer_widget_host_view."

Thay đổi này đã có sẵn trong các bản dựng Brave Nightly và sẽ được phát hành cho các phiên bản ổn định trong những tuần tới. Đối với những ai muốn sử dụng Recall, bạn có thể kích hoạt nó thông qua cài đặt của Brave.

Vào tháng Năm, ứng dụng nhắn tin mã hóa [Signal cũng đã chặn Windows Recall](https://www.bleepingcomputer.com/news/security/signal-now-blocks-microsoft-recall-screenshots-on-windows-11/) bằng cách kích hoạt cờ quản lý DRM trong chương trình, điều này ngăn phần mềm của Microsoft chụp ảnh màn hình của chương trình.

Tuy nhiên, phương pháp này có thể gây ra vấn đề với phần mềm hỗ trợ truy cập, chẳng hạn như trình đọc màn hình, vì vậy Signal cũng cung cấp một cách để tắt cài đặt này.