# New CoPhish attack steals OAuth tokens via Copilot Studio agents

![New 'CoPhish' technique wraps OAuth phishing in Microsoft Copilot](https://www.bleepstatic.com/content/hl-images/2025/10/24/Microsoft_Copilot.jpg)

Một kỹ thuật lừa đảo mới có tên gọi 'CoPhish' lợi dụng các agent của Microsoft Copilot Studio để phát tán các yêu cầu cấp quyền OAuth giả mạo thông qua các miền hợp pháp và đáng tin cậy của Microsoft.

Kỹ thuật này được phát triển bởi các nhà nghiên cứu tại Datadog Security Labs, những người đã cảnh báo trong một báo cáo đầu tuần này rằng tính linh hoạt của Copilot Studio tạo ra các rủi ro lừa đảo mới chưa được ghi tài liệu.

Mặc dù CoPhish dựa vào kỹ thuật xã hội (social engineering), Microsoft đã xác nhận với BleepingComputer rằng họ dự định sửa các nguyên nhân cơ bản trong một bản cập nhật tương lai.

"We've investigated this report and are taking action to address it through future product updates," a Microsoft spokesperson told BleepingComputer.

"While this technique relies on social engineering, we remain committed to hardening our governance and consent experiences and are evaluating additional safeguards to help organizations prevent misuse."

## Copilot agents and OAuth phishing

Copilot Studio agents là các chatbot được lưu trữ trên _copilotstudio.microsoft.com_ mà người dùng có thể tạo và tùy chỉnh thông qua các "topics", là những quy trình công việc tự động hóa các tác vụ cụ thể.

Agents có thể được chia sẻ trên miền của Microsoft bằng cách bật tính năng "demo website". Vì URL là một địa chỉ hợp pháp, người dùng dễ mắc lừa và đăng nhập hơn.

The Login topic, which authenticates the user when starting a conversation with the chatbot, can be configured for specific actions, like requesting a verification code or redirecting to another location or service.

![](https://www.bleepstatic.com/images/news/u/1100723/MaliciousCopilot_SignInTopic_Datadog.png)

**Customizable sign-in topic in malicious agent**  
_nguồn: Datadog_

Katie Knowles, senior security researcher at Datadog, says that an attacker can customize the Login button with a malicious application that can be "either internal or external to the target environment," and could target an application admin even they don have access to the environment.

Việc nhắm vào một người dùng không có đặc quyền trong tenant hiện có thể thực hiện được nếu tác nhân đe dọa đã có mặt trong môi trường. Tuy nhiên, khi chính sách mặc định của Microsoft thay đổi, cuộc tấn công sẽ bị giới hạn chỉ còn quyền đọc/ghi OneNote và sẽ đóng lỗ hổng đối với dịch vụ email, chat và lịch.

Knowles nói rằng ngay cả sau cập nhật của Microsoft, vẫn có thể để một kẻ tấn công bên ngoài "nhắm vào một Application Administrator bằng một ứng dụng đăng ký bên ngoài," vì những thay đổi không áp dụng cho các vai trò có đặc quyền cao.

Người dùng có quyền quản trị trong tenant có thể phê duyệt quyền mà các ứng dụng nội bộ hoặc bên ngoài yêu cầu, ngay cả khi chúng không được xác minh (ví dụ: được gắn nhãn là không được phát hành bởi Microsoft hoặc tổ chức của họ).

Nhà nghiên cứu của Datadog cho biết một cuộc tấn công CoPhish bắt đầu bằng việc tác nhân đe dọa tạo một ứng dụng multi-tenant độc hại với sign-in topic được cấu hình để chuyển hướng tới nhà cung cấp xác thực và thu thập session token.

Việc lấy session token có thể thực hiện được bằng cách cấu hình một yêu cầu HTTP tới một Burp Collaborator URL và gửi biến access token trong header "token".

![Adding the required actions to the sign-in topic](https://www.bleepstatic.com/images/news/u/1220909/2025/October/forwarding.jpg)

**Adding the required actions to the sign-in topic**  
_nguồn: Datadog_

"The application ID (or client ID), secret, and authentication provider URLs are used to configure the agent's sign-in settings," Knowles says in a [report](https://securitylabs.datadoghq.com/articles/cophish-using-microsoft-copilot-studio-as-a-wrapper/) this week.

Cần lưu ý rằng hành động chuyển hướng khi người dùng nạn nhân bấm nút Login có thể được cấu hình để chuyển tới bất kỳ URL độc hại nào, và URL quy trình cấp quyền ứng dụng chỉ là một khả năng cho kẻ tấn công.

## CoPhish attack on Admins

After activating the malicious agent's demo website, an attacker can distribute it to targets in email phishing campaigns or over Team messages.

Vì URL là hợp pháp và thiết kế trang khá giống dịch vụ, người dùng có thể nghĩ rằng đó chỉ là một dịch vụ Microsoft Copilot khác. Knowles nói một manh mối có thể làm dấy lên nghi ngờ là biểu tượng "Microsoft Power Platform", thứ dễ bị bỏ qua.

**The Microsoft-hosted page and Login button**  
_nguồn: Datadog_

Một admin mắc bẫy và chấp nhận các quyền của ứng dụng độc hại sẽ được đưa đến OAuth redirect URL \[token.botframework.com\] để xác thực kết nối bot.

"This may seem atypical, but it’s a standard part of the Copilot Studio authentication process using a valid domain," the Datadog researchers says.

Sau khi hoàn tất quá trình xác thực, người dùng sẽ không nhận được thông báo rằng session token của họ đã bị chuyển tiếp tới Burp Collaborator và phiên làm việc của họ bị chiếm đoạt, nhưng họ vẫn có thể trò chuyện với agent.

Hơn nữa, vì token được gửi từ Copilot sử dụng các địa chỉ IP của Microsoft, kết nối tới kẻ tấn công sẽ không hiển thị trong lưu lượng web của người dùng.

Dưới đây là sơ đồ tổng quan về cách cuộc tấn công CoPhish hoạt động và các bước từ khi người dùng nạn nhân truy cập ứng dụng độc hại tới khi kẻ tấn công nhận được token.

**Cophish attack flow diagram**  
_nguồn: Datadog_

Microsoft told BleepingComputer that customers can protect against CoPhish attacks by limiting administrative privileges, reducing application permissions, and enforcing governance policies.

Datadog provides a set of security considerations that include implementing a strong application consent policy that would cover any gaps in Microsoft's default baseline configuration.

The cloud monitoring and security company also advises organizations to disable user application creation defaults, and closely monitor application consent via Entra ID and Copilot Studio agent creation events.