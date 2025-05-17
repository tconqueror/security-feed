# Công cụ 'Defendnot' mới lừa Windows vô hiệu hóa Microsoft Defender

![Microsoft Defender](https://www.bleepstatic.com/content/hl-images/2022/02/10/0_Microsoft-Defender.jpg)

Một công cụ mới mang tên 'Defendnot' có thể vô hiệu hóa Microsoft Defender trên các thiết bị Windows bằng cách đăng ký một sản phẩm antivirus giả, ngay cả khi không có AV thật nào được cài đặt.

Mẹo này sử dụng một API Trung tâm an ninh Windows (WSC) không được tài liệu, mà phần mềm antivirus sử dụng để thông báo cho Windows rằng nó đã được cài đặt và đang quản lý bảo vệ thời gian thực cho thiết bị.

Khi một chương trình antivirus được đăng ký, Windows tự động vô hiệu hóa Microsoft Defender để tránh xung đột từ việc chạy nhiều ứng dụng bảo mật trên cùng một thiết bị.

[Công cụ Defendnot](https://github.com/es3n1n/defendnot), được tạo ra bởi nhà nghiên cứu [es3n1n](https://x.com/es3n1n), lạm dụng API này bằng cách đăng ký một sản phẩm antivirus giả đáp ứng tất cả các kiểm tra xác thực của Windows.

Công cụ này dựa trên một dự án trước đó được gọi là [no-defender](https://github.com/es3n1n/no-defender), mà đã sử dụng mã từ một sản phẩm antivirus của bên thứ ba để giả mạo đăng ký với WSC. Công cụ trước đó đã bị gỡ xuống khỏi GitHub sau khi nhà cung cấp đã gửi yêu cầu DMCA.

"Rồi, sau vài tuần phát hành, dự án đã phát triển một cách khá lớn và đạt khoảng 1,5k sao, sau đó các nhà phát triển của sản phẩm antivirus tôi đang sử dụng đã gửi yêu cầu DMCA và tôi thực sự không muốn làm gì với điều đó nên đã xóa mọi thứ và thôi," nhà phát triển giải thích trong một [bài đăng trên blog](https://blog.es3n1n.eu/posts/how-i-ruined-my-vacation/).

Defendnot tránh các vấn đề về bản quyền bằng cách xây dựng chức năng từ đầu thông qua một DLL antivirus giả.

Thông thường, API WSC được bảo vệ thông qua Protected Process Light (PPL), chữ ký số hợp lệ, và các tính năng khác.

Để vượt qua các yêu cầu này, Defendnot tiêm DLL của nó vào một quy trình hệ thống, Taskmgr.exe, đã được ký và đã được Microsoft tin cậy. Từ trong quy trình đó, nó có thể đăng ký antivirus giả với một tên hiển thị giả mạo.

Một khi đã được đăng ký, Microsoft Defender ngay lập tức tự mình tắt, để lại không có bảo vệ hoạt động nào trên thiết bị.

![Defendnot đã đăng ký trên một thiết bị](https://www.bleepstatic.com/images/news/security/d/defendnot/defendnot-bleepingcomputer.jpg)

**Defendnot đã đăng ký trên một thiết bị**  
_Nguồn: BleepingComputer_

Công cụ này cũng bao gồm một trình tải (loader) mà truyền dữ liệu cấu hình thông qua một tệp ctx.bin và cho phép bạn đặt tên antivirus bạn muốn sử dụng, tắt đăng ký và bật ghi chú chi tiết.

Để duy trì hoạt động, Defendnot tạo một autorun thông qua Trình lập lịch tác vụ Windows để nó khởi động khi bạn đăng nhập vào Windows.

Mặc dù Defendnot được coi là một dự án nghiên cứu, công cụ này chứng tỏ cách các tính năng hệ thống đáng tin cậy có thể bị thao tác để tắt các tính năng bảo mật.

Hiện tại, Microsoft Defender đang phát hiện và cách ly Defendnot như một 'Win32/Sabsik.FL.!ml; detection.