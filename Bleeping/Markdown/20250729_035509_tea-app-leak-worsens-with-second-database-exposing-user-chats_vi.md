# Rò rỉ dữ liệu ứng dụng Tea trở nên tồi tệ hơn với cơ sở dữ liệu thứ hai phơi bày trò chuyện của người dùng

![Logo Tea](https://www.bleepstatic.com/content/hl-images/2025/07/28/tea-header.jpg)

Vụ rò rỉ dữ liệu ứng dụng Tea đã phát triển thành một vụ rò rỉ lớn hơn, với dữ liệu bị đánh cắp hiện được chia sẻ trên các diễn đàn hacking và một cơ sở dữ liệu thứ hai được phát hiện, mà được cho là chứa 1,1 triệu tin nhắn riêng tư được trao đổi giữa các thành viên của ứng dụng.

Ứng dụng Tea là một nền tảng an toàn cho hẹn hò chỉ dành cho phụ nữ, nơi các thành viên có thể chia sẻ đánh giá về nam giới, với quyền truy cập vào nền tảng chỉ được cấp sau khi cung cấp ảnh tự chụp và xác minh ID chính phủ.

Vào thứ Sáu, một người dùng ẩn danh đã đăng trên 4chan rằng Tea đã sử dụng một bucket lưu trữ Firebase không an toàn để lưu trữ giấy phép lái xe và ảnh tự chụp được các thành viên tải lên để xác minh họ là phụ nữ, cũng như hình ảnh và ảnh được chia sẻ trong các bình luận.

Người dùng đã chia sẻ một script Python mà có thể được sử dụng để tải dữ liệu từ bucket lưu trữ hiện đã được bảo mật.

Tổng cộng, hơn 59 GB dữ liệu đã bị lộ trong vụ rò rỉ này, với Tea xác nhận trong một tuyên bố công khai rằng nó ảnh hưởng đến người dùng đã đăng ký trước năm 2024.

"Hệ thống lưu trữ dữ liệu cũ đã bị xâm phạm, dẫn đến việc truy cập trái phép vào một tập dữ liệu từ trước tháng 2 năm 2024," đọc thông báo [rò rỉ bảo mật](https://www.teaforwomen.com/cyberincident).

"Tập dữ liệu này bao gồm khoảng 72,000 hình ảnh, bao gồm khoảng 13,000 ảnh tự chụp và giấy tờ tùy thân do người dùng gửi trong quá trình xác minh tài khoản và khoảng 59,000 hình ảnh có thể xem công khai trong ứng dụng từ các bài đăng, bình luận và tin nhắn trực tiếp."

Nền tảng này cho biết rằng ảnh tự chụp không được xóa như mong đợi để tuân thủ các yêu cầu của cơ quan thực thi pháp luật liên quan đến việc ngăn chặn bắt nạt qua mạng.

Các tội phạm mạng hiện đã bắt đầu chia sẻ các torrent dữ liệu rò rỉ trên các diễn đàn hacking, có khả năng phơi bày các thành viên của ứng dụng trước các cuộc tấn công kỹ xã hội.

BleepingComputer đã xác nhận rằng dữ liệu được chia sẻ chứa giấy phép lái xe, ảnh tự chụp, và các tệp đính kèm tin nhắn.

Để làm cho vấn đề tồi tệ hơn, [404 Media hiện báo cáo](https://www.404media.co/a-second-tea-breach-reveals-users-dms-about-abortions-and-cheating/) rằng một cơ sở dữ liệu bổ sung đã được phát hiện chứa 1,1 triệu tin nhắn riêng tư được gửi giữa người dùng trên nền tảng Tea.

Cơ sở dữ liệu này chứa dữ liệu gần đây hơn, từ năm 2023 đến tuần trước, và được cho là bao gồm các tin nhắn thảo luận về các chủ đề nhạy cảm, chẳng hạn như những cuộc thảo luận về phá thai, chồng lừa dối và bạn trai hai lòng.

Theo 404 Media, có khả năng nhận dạng người dùng dựa trên hồ sơ mạng xã hội, số điện thoại hoặc các thông tin cá nhân khác được tiết lộ trong các tin nhắn.

Điều mà lẽ ra phải là một không gian an toàn cho phụ nữ giờ đây đã trở thành một công cụ để làm nhục họ, với một người thậm chí đã tạo ra một trang web theo phong cách “facesmash” nơi mà du khách có thể đánh giá các bức ảnh tự chụp bị phơi bày trong dữ liệu rò rỉ.

Tea cho biết họ đang tiếp tục làm việc với các chuyên gia an ninh mạng từ bên thứ ba để kiểm soát sự việc và tiến hành cuộc điều tra về cuộc tấn công.

Ứng dụng cho biết họ cũng đã thông báo cho cơ quan thực thi pháp luật, những người đang hỗ trợ trong cuộc điều tra.