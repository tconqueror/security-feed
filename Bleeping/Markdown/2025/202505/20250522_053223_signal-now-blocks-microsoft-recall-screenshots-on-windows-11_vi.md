# Signal hiện ngăn chặn Microsoft Recall chụp ảnh màn hình trên Windows 11

![Signal](https://www.bleepstatic.com/content/hl-images/2024/08/09/Signal-red.jpg)

​Signal đã cập nhật ứng dụng Windows của mình để bảo vệ quyền riêng tư của người dùng bằng cách ngăn chặn tính năng Recall được hỗ trợ bởi AI của Microsoft chụp ảnh màn hình cuộc trò chuyện của họ.

Tính năng bảo mật quyền riêng tư mới này, được gọi là "bảo mật màn hình", hiện đã được kích hoạt mặc định trên tất cả các thiết bị Windows 11, nơi Recall liên tục chụp ảnh màn hình của tất cả các cửa sổ hoạt động mỗi vài giây và phân tích chúng để xây dựng một cơ sở dữ liệu có thể tìm kiếm bằng ngôn ngữ tự nhiên.

Khi được kích hoạt, bảo mật màn hình sẽ đặt cờ Quản lý Quyền Kỹ thuật số (DRM) trên các cửa sổ ứng dụng của Signal, chặn nội dung của chúng khỏi việc bị Recall hoặc các ứng dụng và tính năng khác của Windows ghi lại.

Microsoft đã giới thiệu Recall [vào tháng 5 năm 2024](https://www.bleepingcomputer.com/news/microsoft/windows-11-recall-ai-feature-will-record-everything-you-do-on-your-pc/) khi các chuyên gia bảo mật mô tả nó là một [cơn ác mộng về quyền riêng tư](https://www.bleepingcomputer.com/news/microsoft/microsofts-new-windows-11-recall-is-a-privacy-nightmare/) và là một rủi ro bảo mật đáng kể vì kẻ tấn công có thể dễ dàng biến nó thành công cụ để đánh cắp dữ liệu người dùng.

Để giải quyết những lo ngại này, Microsoft đã biến Recall thành một tính năng có thể gỡ bỏ [đăng ký](https://www.bleepingcomputer.com/news/microsoft/microsoft-makes-windows-recall-opt-in-secures-data-with-windows-hello/) mà yêu cầu người dùng đăng nhập [bằng Windows Hello](https://www.bleepingcomputer.com/news/microsoft/microsoft-makes-windows-recall-opt-in-secures-data-with-windows-hello/) và đã nâng cấp nó để [lọc thông tin nhạy cảm](https://www.bleepingcomputer.com/news/microsoft/microsoft-windows-recall-now-can-be-removed-is-more-secure/) (như thông tin đăng nhập và số thẻ tín dụng) và loại trừ một số ứng dụng, trang web hoặc phiên duyệt riêng tư khỏi việc bị ghi lại.

David Weston, Phó Chủ tịch của Microsoft về Bảo mật Doanh nghiệp và Hệ điều hành, cũng cho biết vào tháng 9 rằng Microsoft đã thêm giới hạn tỷ lệ và bảo vệ chống tấn công [malware](https://www.bleepingcomputer.com/news/microsoft/microsoft-windows-recall-now-can-be-removed-is-more-secure/) vào Recall, cũng như khả năng điều chỉnh cài đặt lưu trữ, xóa snapshot, và hoàn toàn tắt việc lưu snapshot.

"Mặc dù Microsoft đã thực hiện một số điều chỉnh trong suốt mười hai tháng qua để đáp ứng phản hồi quan trọng, nhưng phiên bản được cải tiến của Recall vẫn đặt bất kỳ nội dung nào được hiển thị trong các ứng dụng bảo vệ quyền riêng tư như Signal vào rủi ro," nhà phát triển Signal Joshua Lund [cho biết trong một bài đăng blog hôm thứ Tư](https://signal.org/blog/signal-doesnt-recall/).

"Kết quả là, chúng tôi đang kích hoạt một lớp bảo vệ bổ sung mặc định trên Windows 11 nhằm giúp duy trì sự bảo mật của Signal Desktop trên nền tảng đó mặc dù nó gây ra một số thiệt hại về khả năng sử dụng. Microsoft đơn giản đã không cho chúng tôi lựa chọn nào khác."

Bảo mật màn hình của Signal có thể gây ra các vấn đề với các trình đọc màn hình, vì vậy những người muốn tắt tính năng này có thể làm như vậy từ Cài đặt Signal > Quyền riêng tư > Bảo mật màn hình.

Signal cũng sẽ hiển thị một cảnh báo trước khi tắt bảo mật màn hình, cảnh báo rằng Windows có thể chụp ảnh màn hình các cuộc trò chuyện trên Signal của họ khi tính năng này bị vô hiệu hóa.

![Cảnh báo về bảo mật màn hình Signal](https://www.bleepstatic.com/images/news/u/1109292/2025/Disable_Signal_screen_security.jpg)

_Cảnh báo bảo mật màn hình Signal (Signal)_

"Các ứng dụng như Signal hầu như không có quyền kiểm soát đối với nội dung mà Recall có thể ghi lại, và việc triển khai 'DRM' hoạt động vì lợi ích của bạn (không phải chống lại bạn) là lựa chọn tốt nhất mà chúng tôi có," Lund bổ sung.

​"Chúng tôi hy vọng rằng các nhóm AI xây dựng các hệ thống như Recall sẽ suy nghĩ kỹ hơn về những hệ quả này trong tương lai. Các ứng dụng như Signal không nên phải thực hiện 'một mẹo kỳ lạ' để duy trì quyền riêng tư và tính toàn vẹn của các dịch vụ của họ mà không có công cụ phát triển phù hợp. Những người quan tâm đến quyền riêng tư không nên bị buộc phải hy sinh khả năng tiếp cận trên bàn thờ của những khát vọng AI."

Tuy nhiên, như Lund đã nói, việc kích hoạt bảo mật màn hình của Signal trên thiết bị của bạn sẽ không bảo vệ khỏi việc chụp ảnh màn hình hoặc ghi âm của người khác sử dụng các trình đọc màn hình trên thiết bị macOS hoặc Linux.

Vào tháng 4, gần một năm sau khi được giới thiệu, Microsoft đã [bắt đầu triển khai](https://www.bleepingcomputer.com/news/microsoft/windows-11s-recall-ai-is-now-rolling-out-on-copilot-plus-pcs/) Windows Recall cho tất cả khách hàng đã cài đặt bản cập nhật Windows 11 KB5055627 trên các PC Copilot+.

Một tháng sau, công ty đã mở rộng tính khả dụng chung cho mọi người đã cài đặt các bản cập nhật Patch Tuesday tháng 5 năm 2025.