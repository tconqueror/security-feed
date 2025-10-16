# Microsoft ra mắt Copilot Actions cho các tác vụ Windows do AI đại diện điều khiển

![Microsoft Copilot](https://www.bleepstatic.com/content/hl-images/2025/10/15/microsoft-copilot.jpg)

Microsoft thông báo hôm nay về một tính năng Copilot mới trên Windows 11 có tên Copilot Actions cho phép các tác nhân AI thực hiện các tác vụ thật trên các tệp và ứng dụng cục bộ.

Tính năng sẽ được triển khai sớm cho Windows Insiders trong [Copilot Labs](https://copilot.microsoft.com/labs), mở rộng Copilot Actions trên web được giới thiệu vào tháng Năm và đưa chúng ta tiến thêm một bước gần hơn với tầm nhìn của Microsoft về việc tích hợp AI trực tiếp vào môi trường desktop của Windows.

"Copilot Actions là một tác nhân AI hoàn thành các tác vụ cho bạn bằng cách tương tác với các ứng dụng và tệp của bạn, sử dụng khả năng nhìn và suy luận nâng cao để nhấp, gõ và cuộn như một con người," [giải thích Microsoft](https://blogs.windows.com/windowsexperience/?p=179965).

"Điều này biến các tác nhân từ những trợ lý thụ động thành cộng tác viên kỹ thuật số chủ động có thể thực hiện các tác vụ phức tạp để tăng hiệu quả và năng suất — như cập nhật tài liệu, tổ chức tệp, đặt vé hoặc gửi email."

![Microsoft Copilot Actions working on a local video](https://www.bleepstatic.com/images/news/Microsoft/windows-11/c/copilot/copilot-actions/copilot-actions.jpg)

**Microsoft Copilot Actions đang làm việc trên một video cục bộ**  
_Source: Microsoft_

Mỗi ứng dụng "agentic" sẽ quản lý Agent Workspace riêng của nó, cung cấp một môi trường cô lập nơi tác nhân hoạt động độc lập với desktop của người dùng. Điều này đảm bảo rằng các tác nhân hoạt động thay mặt cho các ứng dụng khác nhau vẫn bị cô lập với nhau.

Microsoft nói với BleepingComputer rằng sẽ không có thay đổi về yêu cầu phần cứng cho Windows 11 và họ đang tối ưu hóa các workspace để giảm thiểu bất kỳ ảnh hưởng nào đến hiệu suất của Windows.

## Bảo mật các tác nhân Copilot

Microsoft cho biết họ đang bảo mật các tác nhân Copilot thông qua bốn nguyên tắc bảo mật và quyền riêng tư: sử dụng các tài khoản tác nhân riêng biệt, giới hạn quyền hạn của tác nhân trên tệp và thư mục, đảm bảo tin cậy vận hành thông qua các tác nhân được ký kỹ thuật số, và đảm bảo rằng các tác nhân được quản trị theo [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/p/?LinkId=521839) và [Responsible AI Standard](https://www.microsoft.com/en-us/privacy/privacy-report?msockid=12b6fb88e4a76d9418ededaae5266c63).

Mỗi tác nhân AI sẽ chạy dưới tài khoản "standard" Windows riêng biệt, có nghĩa là nó không có quyền quản trị. Vì mỗi tác nhân sử dụng tài khoản của riêng mình, Windows có thể giới hạn các tác nhân dựa trên quy tắc truy cập ứng dụng và hệ thống tệp.

Khi ra mắt, các tác nhân chỉ có quyền truy cập vào các thư mục dữ liệu chuẩn của Windows, như Documents, Downloads, Desktop và Pictures, và các "nguồn lực" khác có sẵn cho tất cả các tài khoản. Quyền truy cập vào các vị trí tệp khác có thể được cấu hình bằng cách sử dụng access control lists (ACLs) của Windows.

BleepingComputer đã hỏi Microsoft liệu họ có thêm cách dễ dàng hơn để quản lý quyền truy cập hệ thống tệp cho các tác nhân hay không và được biết rằng các kiểm soát bảo mật chi tiết hơn sẽ được ra mắt vào thời điểm sau.

Microsoft còn nói với BleepingComputer rằng mỗi Agent Workspace, nơi Copilot Actions thực hiện các tác vụ của nó, được triển khai như một Windows Remote Desktop child session, thay vì như một máy ảo hoặc trong Windows Sandbox.

Một Windows Remote Desktop child session là một môi trường desktop riêng biệt, cô lập gắn với phiên hiện có của người dùng, ngăn tác nhân trực tiếp xem hoặc tương tác với desktop của người dùng.

"Mỗi ứng dụng agentic sẽ quản lý workspace tác nhân của họ. Vì mục đích cô lập, sẽ không có sự chồng chéo của workspace giữa các ứng dụng," Microsoft nói với BleepingComputer.

Mặc dù tác nhân AI không thể truy cập desktop của người dùng, Microsoft dự định triển khai một cách để người dùng ủy quyền, giám sát và kiểm soát các hành động của tác nhân trong workspace.

Copilot Actions được tắt theo mặc định và phải được bật thủ công bằng cách vào **Settings** \> **System** \> **AI components** \> **Agent tools** \> **Experimental agentic features**.

![Enabling Copilot Actions in Windows 11](https://www.bleepstatic.com/images/news/Microsoft/windows-11/c/copilot/copilot-actions/enable-copilot-actions.jpg)

**Bật Copilot Actions trong Windows 11**  
_Source: Microsoft_

Để tăng cường bảo mật, các tác nhân được ký số (cryptographically signed), cho phép Microsoft thu hồi chứng chỉ tác nhân bị xâm phạm hoặc độc hại khi phát hiện.

Theo Microsoft, những tính năng này là một phần của Secure Future Initiative, và phản hồi từ chương trình xem trước sẽ giúp hướng dẫn việc phát triển tính năng trước khi phát hành đầy đủ vào cuối năm nay.