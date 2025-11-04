# Microsoft sẽ loại bỏ Defender Application Guard khỏi Office

![Microsoft Defender](https://www.bleepstatic.com/content/hl-images/2023/10/11/Microsoft-Defender_for_Endpoint.jpg)

Microsoft có kế hoạch loại bỏ Defender Application Guard khỏi Office vào tháng 12 năm 2027, bắt đầu với bản phát hành tháng 2 năm 2026 của Office phiên bản 2602.

Microsoft Defender Application Guard for Office (MDAG) được thiết kế cho các phiên bản Windows 10 và Windows 11 Enterprise, bảo vệ thiết bị của người dùng bằng cách cô lập các tệp Word, PowerPoint và Excel không đáng tin cậy trong một container riêng có kích hoạt Hyper-V. Điều này giúp giữ hệ điều hành chủ an toàn, đảm bảo dữ liệu doanh nghiệp không bị kẻ tấn công xâm hại nếu một tệp hoặc trang web có hại.

Microsoft đã thông báo rằng họ [sẽ khai tử MDAG](https://www.bleepingcomputer.com/news/microsoft/microsoft-deprecates-defender-application-guard-for-office/) hai năm trước, vào tháng 11 năm 2023, khi đó họ cũng khuyến nghị sử dụng các rule giảm bề mặt tấn công của Defender for Endpoint, Protected View và Windows Defender Application Control làm các lựa chọn thay thế.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Redmond đã ngưng MDAG năm tháng sau đó, vào tháng 4 năm 2024, và cho biết các tệp Office giờ sẽ mở trong Protected View, một chế độ chỉ đọc nơi hầu hết các chức năng chỉnh sửa tài liệu bị vô hiệu hóa.

"Các tệp sẽ mở trong Protected View thay vào đó. Quản trị viên nên bật các rule ASR của Microsoft Defender for Endpoint và Windows Defender Application Control để duy trì bảo mật. Không cần hành động từ quản trị viên cho việc gỡ bỏ," Microsoft cho biết trong một [cập nhật Microsoft 365 message center](https://admin.microsoft.com/#/MessageCenter/:/messages/MC1182696) vào thứ Ba.

"Thay đổi này phù hợp với việc kết thúc hỗ trợ cho Windows 11 version 23H2 và giúp đơn giản hóa trải nghiệm bảo mật cho người dùng. Các tài liệu trước đây mở trong Application Guard giờ sẽ mở trong Protected View, duy trì khả năng bảo vệ mạnh mẽ trước các mối đe dọa."

![Application Guard for Office alert](https://www.bleepstatic.com/images/news/Microsoft/microsoft-office-application-guard.jpg)

_Cảnh báo Application Guard for Office (Microsoft)_

Theo một dòng thời gian được chia sẻ, việc gỡ bỏ sẽ bắt đầu với Office phiên bản 2602, cho Current Channel vào đầu tháng 2 năm 2026, cho Monthly Enterprise Channel vào tháng 4 năm 2026, và cho Semi-Annual Enterprise Channel vào tháng 7 năm 2026.

Microsoft ước tính rằng MDAG sẽ hoàn toàn bị gỡ bỏ khỏi Office với việc phát hành phiên bản 2612, sẽ được triển khai tới người dùng Current Channel vào đầu tháng 12 năm 2026, tới Monthly Enterprise Channel vào tháng 2 năm 2027, và tới Semi-Annual Enterprise Channel vào tháng 7 năm 2027.

Để duy trì khả năng bảo vệ trước các tài liệu Office độc hại, Microsoft khuyến nghị các quản trị viên CNTT:

* Bật Microsoft Defender for Endpoint ASR rules để chặn các hành vi rủi ro trong các tệp Office.
* Bật Windows Defender Application Control (WDAC) để đảm bảo chỉ mã đáng tin cậy, có chữ ký được chạy trên thiết bị.

Thông báo gỡ bỏ được đưa ra hai năm sau khi Redmond triển khai Application Guard for Office [cho tất cả khách hàng Microsoft 365](https://www.bleepingcomputer.com/news/security/microsoft-rolls-out-application-guard-for-office-to-all-customers/) có giấy phép được hỗ trợ.

MDAG chính thức được ra mắt như một phần của [xem trước giới hạn](https://www.bleepingcomputer.com/news/microsoft/office-365-to-prevent-malicious-docs-from-infecting-windows/) vào tháng 11 năm 2019, và nó chỉ có sẵn cho người dùng thương mại với giấy phép Microsoft 365 E5 hoặc Microsoft 365 E5 Security.