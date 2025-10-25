# Kỹ thuật mới 'CoPhish' đóng gói lừa đảo OAuth trong Microsoft Copilot

![Kỹ thuật mới 'CoPhish' đóng gói lừa đảo OAuth trong Microsoft Copilot](https://www.bleepstatic.com/content/hl-images/2025/10/24/Microsoft_Copilot.jpg)

Một kỹ thuật lừa đảo mới gọi là 'CoPhish' lợi dụng các agent trong Microsoft Copilot Studio để gửi các yêu cầu đồng ý OAuth giả mạo thông qua các miền hợp pháp và đáng tin cậy của Microsoft.

Kỹ thuật này được phát triển bởi các nhà nghiên cứu tại Datadog Security Labs, những người đã cảnh báo trong một báo cáo đầu tuần này rằng tính linh hoạt của Copilot Studio tạo ra những rủi ro lừa đảo mới chưa được tài liệu hóa.

Mặc dù CoPhish dựa vào kỹ thuật tấn công xã hội, Microsoft đã xác nhận với BleepingComputer rằng họ dự định sửa các nguyên nhân gốc rễ trong một bản cập nhật tương lai.

"Chúng tôi đã điều tra báo cáo này và đang hành động để khắc phục thông qua các bản cập nhật sản phẩm trong tương lai," một phát ngôn viên của Microsoft nói với BleepingComputer.

"Mặc dù kỹ thuật này dựa vào tấn công xã hội, chúng tôi vẫn cam kết tăng cường quản trị và trải nghiệm đồng ý và đang đánh giá các biện pháp bảo vệ bổ sung để giúp các tổ chức ngăn chặn việc lạm dụng."

## Các agent Copilot và lừa đảo OAuth

Copilot Studio agents là các chatbot được lưu trữ trên _copilotstudio.microsoft.com_ mà người dùng có thể tạo và tùy chỉnh thông qua các "chủ đề", là các luồng công việc tự động hóa các tác vụ cụ thể.

Các agent có thể được chia sẻ trên miền của Microsoft bằng cách bật tính năng "demo website". Bởi vì URL là một URL hợp pháp, người dùng dễ bị lừa và đăng nhập hơn.

Chủ đề Đăng nhập (Login topic), vốn xác thực người dùng khi bắt đầu cuộc hội thoại với chatbot, có thể được cấu hình cho các hành động cụ thể, như yêu cầu mã xác minh hoặc chuyển hướng đến vị trí hoặc dịch vụ khác.

![](https://www.bleepstatic.com/images/news/u/1100723/MaliciousCopilot_SignInTopic_Datadog.png)

**Chủ đề đăng nhập có thể tùy chỉnh trong agent độc hại**  
_source: Datadog_

Katie Knowles, nhà nghiên cứu an ninh cấp cao tại Datadog, cho biết rằng kẻ tấn công có thể tùy chỉnh nút Đăng nhập với một ứng dụng độc hại có thể là "nội bộ hoặc bên ngoài môi trường mục tiêu," và có thể nhắm tới một quản trị viên ứng dụng ngay cả khi họ không có quyền truy cập vào môi trường.

Nhắm tới một người dùng không có quyền đặc biệt trong tenant hiện đang khả thi nếu tác nhân đe dọa đã có mặt trong môi trường. Tuy nhiên, khi chính sách mặc định của Microsoft thay đổi, cuộc tấn công sẽ chỉ bị giới hạn ở quyền đọc/ghi OneNote và sẽ đóng khoảng trống cho các dịch vụ email, chat và lịch.

Knowles nói rằng ngay cả sau bản cập nhật của Microsoft, một kẻ tấn công bên ngoài vẫn có thể "nhắm tới một Application Administrator với một ứng dụng đăng ký từ bên ngoài," vì các thay đổi không áp dụng cho các vai trò có đặc quyền cao.

Người dùng có đặc quyền quản trị trong tenant có thể phê duyệt các quyền được yêu cầu bởi ứng dụng nội bộ hoặc bên ngoài, ngay cả khi chúng không được xác thực (ví dụ: được đánh dấu là không được xuất bản bởi Microsoft hoặc tổ chức của họ).

Nhà nghiên cứu Datadog cho biết một cuộc tấn công CoPhish bắt đầu bằng việc tác nhân đe dọa tạo một ứng dụng đa tenant độc hại với chủ đề đăng nhập được cấu hình để chuyển hướng tới nhà cung cấp xác thực và thu thập token phiên.

Việc lấy token phiên có thể thực hiện được bằng cách cấu hình một yêu cầu HTTP tới một Burp Collaborator URL và gửi biến access token trong header "token".

![Adding the required actions to the sign-in topic](https://www.bleepstatic.com/images/news/u/1220909/2025/October/forwarding.jpg)

**Thêm các hành động cần thiết vào chủ đề đăng nhập**  
_Source: Datadog_

"ID ứng dụng (hoặc client ID), secret, và các URL nhà cung cấp xác thực được dùng để cấu hình cài đặt đăng nhập của agent," Knowles nói trong một [báo cáo](https://securitylabs.datadoghq.com/articles/cophish-using-microsoft-copilot-studio-as-a-wrapper/) tuần này.

Cần lưu ý rằng hành động chuyển hướng khi người dùng nạn nhân nhấp vào nút Đăng nhập có thể được cấu hình để chuyển hướng tới bất kỳ URL độc hại nào, và URL quy trình đồng ý ứng dụng chỉ là một khả năng đối với kẻ tấn công.

## Cuộc tấn công CoPhish nhắm vào quản trị viên

Sau khi kích hoạt trang web demo của agent độc hại, kẻ tấn công có thể phân phối nó tới các mục tiêu qua chiến dịch lừa đảo email hoặc qua tin nhắn Teams.

Do URL là hợp pháp và thiết kế của trang, người dùng có thể nghĩ rằng đó chỉ là một dịch vụ Microsoft Copilot khác. Knowles cho biết một dấu hiệu có thể khiến nghi ngờ là biểu tượng "Microsoft Power Platform", thứ dễ bị bỏ qua.

**Trang được lưu trữ bởi Microsoft và nút Đăng nhập**  
_Source: Datadog_

Một quản trị viên nếu bị mắc lừa và chấp nhận quyền của ứng dụng độc hại sẽ được đưa đến OAuth redirect URL [token.botframework.com] để xác thực kết nối bot.

"Điều này có thể có vẻ bất thường, nhưng nó là một phần tiêu chuẩn của quá trình xác thực Copilot Studio sử dụng một miền hợp lệ," các nhà nghiên cứu Datadog nói.

Sau khi hoàn tất quá trình xác thực, người dùng sẽ không nhận được thông báo về việc token phiên của họ bị chuyển tiếp tới Burp Collaborator và phiên của họ bị chiếm đoạt, nhưng họ sẽ có thể trò chuyện với agent.

Hơn nữa, vì token đã được gửi từ Copilot sử dụng các địa chỉ IP của Microsoft, kết nối tới kẻ tấn công sẽ không hiển thị trong lưu lượng web của người dùng.

Dưới đây là một sơ đồ hình ảnh về cách hoạt động của cuộc tấn công CoPhish và các bước từ việc người dùng nạn nhân truy cập ứng dụng độc hại tới khi kẻ tấn công nhận được token.

**Sơ đồ luồng tấn công Cophish**  
_Source: Datadog_

Microsoft nói với BleepingComputer rằng khách hàng có thể bảo vệ chống các cuộc tấn công CoPhish bằng cách giới hạn đặc quyền quản trị, giảm quyền ứng dụng và thực thi các chính sách quản trị.

Datadog cung cấp một tập hợp các cân nhắc an ninh bao gồm việc triển khai chính sách đồng ý ứng dụng chặt chẽ mà sẽ che các khoảng trống trong cấu hình cơ bản mặc định của Microsoft.

Công ty giám sát và an ninh đám mây cũng khuyên các tổ chức nên vô hiệu hóa mặc định tạo ứng dụng bởi người dùng, và theo dõi chặt chẽ việc đồng ý ứng dụng thông qua Entra ID và các sự kiện tạo agent của Copilot Studio.