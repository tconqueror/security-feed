# Windows 11 hiện hỗ trợ ứng dụng bên thứ ba để quản lý passkey gốc

![Windows 11 hiện hỗ trợ ứng dụng bên thứ ba cho quản lý passkey gốc](https://www.bleepstatic.com/content/hl-images/2023/10/09/Passkeys_passwordless.jpg)

Microsoft thông báo rằng xác thực không cần mật khẩu giờ đây dễ dàng hơn trên Windows 11 thông qua việc hỗ trợ gốc cho các trình quản lý passkey bên thứ ba, những trình quản lý đầu tiên được hỗ trợ là 1Password và Bitwarden.

Điều này khả thi sau khi nhóm bảo mật Windows làm việc cùng với các trình quản lý bên thứ ba để cải thiện xác thực không cần mật khẩu bằng cách phát triển một passkey API cho Windows 11.

Tính năng [mới](http://techcommunity.microsoft.com/blog/windows-itpro-blog/windows-11-expands-passkey-manager-support/4467572) này đã được giới thiệu cùng với bản cập nhật bảo mật tháng 11 năm 2025 cho [Windows 11](https://www.bleepingcomputer.com/news/microsoft/windows-11-kb5068861-and-kb5068865-cumulative-updates-released/), phát hành vào ngày hôm qua.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Passkey là một cơ chế xác thực an toàn tuân theo tiêu chuẩn FIDO2/WebAuthn, sử dụng mật mã khóa công khai-khóa riêng để ký thách thức cục bộ và xác minh phía máy chủ, thay vì dùng mật khẩu.

Khi người dùng đăng ký trên một trang web hoặc ứng dụng hỗ trợ passkey, Windows tạo một cặp khóa, với khóa riêng được lưu trữ an toàn trên Microsoft Password Manager, 1Password, hoặc Bitwarden.

![Bitwarden login with passkey Windows integration](https://www.bleepstatic.com/images/news/u/1220909/2025/November/Bitwarden.jpg)

**Bitwarden: đăng nhập bằng passkey — tích hợp với Windows**  
_Source: Microsoft_

Từ đó, khi cố gắng đăng nhập trên trang web hoặc ứng dụng đó, một thách thức sẽ được gửi đến Windows, và người dùng được yêu cầu xác thực bằng Windows Hello, vốn được bảo vệ bởi PIN và xác thực sinh trắc học.

Hệ thống được coi là vượt trội so với mật khẩu nhờ tính di động, thuận tiện hơn cho người dùng và không bị tấn công lừa đảo (phishing).

Microsoft đã thúc đẩy việc áp dụng passkey trên Windows, và việc bổ sung hỗ trợ ứng dụng bên thứ ba thông qua API mới mang lại nhiều linh hoạt hơn cho người dùng.

Bên cạnh hỗ trợ ứng dụng bên thứ ba, Microsoft cũng đã tích hợp Microsoft Password Manager từ Microsoft Edge một cách gốc vào Windows như một plugin để cho phép người dùng chọn trình quản lý passkey của họ.

Microsoft nhấn mạnh các lợi ích bảo mật sau cho phát triển này:

* Tạo, xác thực và quản lý passkey được bảo vệ bởi Windows Hello
* Đồng bộ có sẵn trên các thiết bị Windows khi đăng nhập vào Edge bằng cùng một tài khoản Microsoft
* Đồng bộ được bảo vệ bởi manager PIN và một cloud enclave
* Azure Managed Hardware Security Modules (HSMs) bảo vệ các khóa mã hóa
* Các hoạt động nhạy cảm chạy trong Azure Confidential Compute
* Khôi phục sử dụng Azure Confidential Ledger

**LinkedIn passkey được lưu trên Microsoft Password Manager**  
_Source: Microsoft_

Microsoft Edge [đã giới thiệu việc lưu và đồng bộ passkey](https://blogs.windows.com/msedgedev/2025/11/03/microsoft-edge-introduces-passkey-saving-and-syncing-with-microsoft-password-manager/) cùng với Microsoft Password Manager trước đó trong tháng này, trong phiên bản 142 trở lên, cho Windows 10 và các phiên bản mới hơn.

Bitwarden đã hỗ trợ lưu trữ và quản lý passkey từ tháng 11 năm 2023 và giới thiệu “[Log in with Passkeys](https://bitwarden.com/blog/log-into-bitwarden-with-a-passkey/)” vào tháng 1 năm 2024.

Trình quản lý mật khẩu phổ biến này đã thông báo tích hợp với Windows 11 qua một cập nhật trên thông báo ra mắt tính năng ban đầu của họ, lưu ý rằng tích hợp cấp hệ thống của họ trên hệ điều hành hiện đang ở giai đoạn beta.

Điều này có nghĩa là có thể tồn tại các giới hạn chức năng hoặc khả năng không ổn định cho đến khi đủ quy mô thử nghiệm và sửa lỗi.