# Microsoft vô hiệu hóa chức năng xem trước của File Explorer cho các tệp tải về để chặn các cuộc tấn công

![Microsoft](https://www.bleepstatic.com/content/hl-images/2025/04/24/Microsoft.jpg)

Microsoft cho biết File Explorer (trước đây là Windows Explorer) hiện tự động chặn tính năng xem trước cho các tệp được tải về từ Internet nhằm ngăn chặn các cuộc tấn công đánh cắp thông tin xác thực qua tài liệu độc hại.

Thay đổi này đã được áp dụng cho người dùng đã cài đặt bản cập nhật bảo mật Patch Tuesday tháng này trên các hệ thống Windows 11 và Windows Server.

Như Redmond [giải thích trong một tài liệu hỗ trợ](https://support.microsoft.com/en-us/topic/file-explorer-automatically-disables-the-preview-feature-for-files-downloaded-from-the-internet-56d55920-6187-4aae-a4f6-102454ef61fb) được xuất bản hôm thứ Tư này, chức năng xem trước sẽ bị vô hiệu theo mặc định chỉ đối với các tệp được xem trên chia sẻ tệp trong Internet Zone và những tệp được đánh dấu bằng Mark of the Web (MotW), cho thấy chúng đã được tải xuống bằng trình duyệt web, nhận dưới dạng tập tin đính kèm email, hoặc thu được từ các nguồn internet khác.

Khi cố gắng xem trước các tệp như vậy, ngăn xem trước của File Explorer sẽ hiển thị một thông báo cảnh báo nói rằng "Tệp bạn đang cố xem trước có thể gây hại cho máy tính của bạn. Nếu bạn tin tưởng tệp và nguồn nhận được, hãy mở nó để xem nội dung."

Sau khi cài đặt các bản cập nhật bảo mật Windows phát hành sau tháng 10 năm 2025, thay đổi này sẽ ngăn các tác nhân đe dọa lợi dụng lỗ hổng cho phép họ thu được NTLM hashes khi người dùng xem trước các tệp chứa thẻ HTML (chẳng hạn <link>, <src>, v.v.) tham chiếu tới các đường dẫn bên ngoài trên máy chủ do kẻ tấn công kiểm soát.

Vector tấn công này đặc biệt đáng lo ngại vì không đòi hỏi tương tác nào của người dùng ngoài việc chọn một tệp để xem trước và loại bỏ nhu cầu lừa mục tiêu phải mở hoặc thực thi tệp đó trên hệ thống của họ.

![File Explorer preview disabled for downloaded file](https://www.bleepstatic.com/images/news/u/1109292/2025/File_Explorer_blocking_preview.jpg)

_Chức năng xem trước của File Explorer bị vô hiệu cho tệp có MotW (BleepinComputer)_

"Bắt đầu từ các bản cập nhật bảo mật Windows được phát hành vào và sau ngày 14 tháng 10 năm 2025, File Explorer tự động vô hiệu hóa tính năng xem trước cho các tệp tải xuống từ internet," Microsoft [cho biết trong một tài liệu hỗ trợ](https://support.microsoft.com/en-us/topic/file-explorer-automatically-disables-the-preview-feature-for-files-downloaded-from-the-internet-56d55920-6187-4aae-a4f6-102454ef61fb) được xuất bản hôm thứ Tư này.

"Thay đổi này được thiết kế để tăng cường bảo mật bằng cách ngăn chặn một lỗ hổng có thể rò rỉ NTLM hashes khi người dùng xem trước các tệp có thể không an toàn."

Đối với hầu hết người dùng, không cần thực hiện hành động gì vì cơ chế bảo vệ được bật tự động cùng với bản cập nhật bảo mật tháng 10 năm 2025, và quy trình làm việc hiện tại hầu như không bị ảnh hưởng trừ khi bạn thường xuyên xem trước các tệp đã tải về.

Nếu bạn cần xem trước một tệp đáng tin cậy từ nguồn đã biết, bạn có thể tự tay bỏ chặn rào bảo mật Internet. Để làm điều đó, nhấp chuột phải vào tệp trong File Explorer, chọn Properties, và bấm nút "Unblock" ở dưới cùng của tab General.

Tuy nhiên, cần lưu ý rằng thay đổi này có thể không có hiệu lực ngay lập tức và có thể yêu cầu bạn đăng xuất rồi đăng nhập lại.

Khóa xem trước cũng có thể được bỏ cho tất cả các tệp trên chia sẻ tệp Internet Zone bằng cách sử dụng tab Security trong Internet Options control panel để thêm địa chỉ chia sẻ tệp vào Trusted sites hoặc khu vực bảo mật Local intranet.