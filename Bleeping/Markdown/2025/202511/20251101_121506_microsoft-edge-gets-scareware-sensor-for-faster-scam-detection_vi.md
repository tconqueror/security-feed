# Microsoft Edge có cảm biến scareware để phát hiện lừa đảo nhanh hơn

![Microsoft Edge](https://www.bleepstatic.com/content/hl-images/2025/09/26/Microsoft_Edge.jpg)

Microsoft đang giới thiệu một cảm biến scareware mới cho trình duyệt web Microsoft Edge, giúp phát hiện các trang lừa đảo nhanh hơn và đảm bảo rằng Defender SmartScreen chặn chúng kịp thời.

Trong các vụ lừa đảo scareware (còn được gọi là [lừa đảo hỗ trợ kỹ thuật](https://www.bleepingcomputer.com/tag/tech-support-scam/)), kẻ gian sử dụng các trang đích mang tính cưỡng ép để lừa nạn nhân tin rằng thiết bị của họ đã bị xâm nhập bởi phần mềm độc hại và cố gắng chiếm quyền truy cập từ xa bằng cách gây áp lực để họ gọi đến một số hỗ trợ kỹ thuật giả.

Defender SmartScreen của Microsoft, vốn bảo vệ người dùng Edge khỏi những chiêu trò này, chỉ kích hoạt sau khi một trang lạm dụng được thêm vào chỉ mục các trang web độc hại của nó, trong khi [built-in Edge scareware blocker](https://www.bleepingcomputer.com/news/microsoft/microsoft-tests-edge-scareware-blocker-to-block-tech-support-scams/) (được giới thiệu tại hội nghị Ignite tháng 11 năm 2024 (http://blogs.windows.com/msedgedev/2024/11/19/microsoft-edge-for-business-transform-your-workday-ignite-2024#detect-scams) và đã được bật theo mặc định kể từ tháng Hai (https://www.bleepingcomputer.com/news/microsoft/microsoft-edge-update-adds-ai-powered-scareware-blocker/) trên hầu hết máy tính) cung cấp lớp bảo vệ bổ sung bằng cách phát hiện dấu hiệu của những vụ lừa đảo này theo thời gian thực sử dụng mô hình máy học cục bộ.

Sau khi phát hiện một trang lừa đảo hỗ trợ kỹ thuật theo thời gian thực, scareware blocker dựa trên AI/ML sẽ cảnh báo người dùng và cho phép họ tiếp tục tải trang web nếu họ tin rằng nó an toàn. Bộ chặn sẽ thoát chế độ toàn màn hình, hiển thị cảnh báo, dừng âm thanh lớn và hiển thị ảnh thu nhỏ của trang.

Người dùng cũng có thể báo cáo các trang lừa đảo để bảo vệ người khác bằng cách chia sẻ thông tin chẩn đoán và ảnh chụp màn hình với Microsoft, giúp dịch vụ SmartScreen phát hiện các đợt bùng phát scareware.

Khi cảm biến mới được bật, SmartScreen sẽ được thông báo để lập chỉ mục các trang lừa đảo nhanh hơn, đảm bảo rằng người dùng Edge trên toàn thế giới được cảnh báo về các vụ lừa đảo sớm hơn.

![Edge scareware blocker SmartScreen setting](https://www.bleepstatic.com/images/news/u/1109292/2025/edge-scareware-blocker-smartscreen-setting.jpg)

_Cài đặt SmartScreen cho Edge scareware blocker (Microsoft)_

"Bắt đầu từ tháng 11, nếu Scareware blocker phát hiện một trang toàn màn hình đáng ngờ, cảm biến scareware mới trong Edge 142 có thể thông báo cho SmartScreen về khả năng lừa đảo ngay lập tức, mà không chia sẻ ảnh chụp màn hình hoặc bất kỳ dữ liệu bổ sung nào ngoài những gì SmartScreen đã nhận," [cho biết Principal PM Manager Rob Franco](https://blogs.windows.com/msedgedev/2025/10/31/protecting-more-edge-users-with-expanded-scareware-blocker-availability-and-real-time-protection/), người đang làm việc trong nhóm Microsoft Edge Enterprise and Security.

"Báo cáo theo thời gian thực này giúp SmartScreen nhận được cảnh báo ngay lập tức để xác nhận các vụ lừa đảo nhanh hơn và chặn chúng trên toàn cầu. Sau này, chúng tôi sẽ thêm nhiều tín hiệu phát hiện ẩn danh hơn để giúp Edge nhận diện các mẫu lừa đảo lặp lại."

Cảm biến scareware mới này đang được triển khai trong Microsoft Edge 142, ban đầu bị vô hiệu hóa, nhưng Microsoft dự định sẽ bật nó cho tất cả người dùng đã kích hoạt SmartScreen để giúp phát hiện thêm nhiều vụ lừa đảo.

Microsoft cho biết người dùng Edge đã báo cáo scareware vượt xa các popup "Virus Alert!" thông thường, bao gồm các chiêu trò sử dụng bảng điều khiển giả và màn hình xanh.

"Gần đây, người dùng báo cáo các vụ lừa đảo mạo danh cơ quan thực thi pháp luật, buộc tội họ phạm tội và yêu cầu thanh toán để mở khóa PC," Franco bổ sung. "Khi Scareware blocker phát hiện vụ lừa đảo đó, nó vẫn chưa bị Defender SmartScreen hoặc các dịch vụ khác như Google Safe Browsing chặn."