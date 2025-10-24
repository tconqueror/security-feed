# Các tuyên bố giả về cái chết trên LastPass được dùng để xâm nhập kho mật khẩu

![Các tuyên bố giả về cái chết trên LastPass được dùng để xâm nhập kho mật khẩu](https://www.bleepstatic.com/content/hl-images/2024/01/03/LastPass-headpic.jpg)

LastPass đang cảnh báo khách hàng về một chiến dịch lừa đảo gửi email kèm yêu cầu truy cập vào kho mật khẩu như một phần của quy trình thừa kế di sản.

Hoạt động bắt đầu vào giữa tháng Mười, và các miền cùng cơ sở hạ tầng được sử dụng cho thấy thủ phạm là một nhóm có động cơ tài chính có tên [CryptoChameleon](https://www.bleepingcomputer.com/news/security/hackers-target-fcc-crypto-firms-in-advanced-okta-phishing-attacks/) (UNC5356).

CryptoChamemelon sử dụng một bộ công cụ phishing chuyên đánh cắp tiền điện tử, nhắm vào nhiều ví như Binance, Coinbase, Kraken và Gemini, dùng các trang đăng nhập giả mạo Okta, Gmail, iCloud và Outlook.

Người dùng LastPass bị cùng nhóm này nhắm tới [lần nữa vào tháng Tư 2024](https://www.bleepingcomputer.com/news/security/cybercriminals-pose-as-lastpass-staff-to-hack-password-vaults/), nhưng [chiến dịch mới nhất](https://blog.lastpass.com/posts/possible-cryptochameleon-social-engineering-campaign-targeting-lastpass-customers-and-more) dường như rộng hơn và được nâng cấp, hiện còn nhắm tới cả passkeys.

Các email phishing gửi tới người dùng LastPass tuyên bố rằng một thành viên gia đình đã yêu cầu truy cập vào kho LastPass của họ bằng cách tải lên giấy chứng tử.

![Tin nhắn phishing do CryptoChameleon gửi](https://www.bleepstatic.com/images/news/u/1220909/2025/October/messege.jpg)

**Tin nhắn phishing do CryptoChameleon gửi**  
_Source: LastPass_

Quy trình thừa kế của LastPass là một tính năng truy cập khẩn cấp cho phép những người được tài khoản chỉ định yêu cầu truy cập vào kho của họ trong trường hợp tử vong hoặc mất năng lực hành vi.

Khi một yêu cầu như vậy được mở, chủ tài khoản nhận được một email, và sau khi thời gian chờ hết hạn, quyền truy cập tự động được cấp cho liên hệ đó.

Yêu cầu thừa kế giả mạo bao gồm một số ID đại lý để tăng tính hợp pháp, thúc giục người nhận hành động và hủy bỏ nó nếu họ không chết bằng cách nhấp vào một liên kết.

Tuy nhiên, liên kết đó chuyển hướng họ đến một trang giả mạo trên _lastpassrecovery[.]com_ có biểu mẫu đăng nhập nơi nạn nhân có thể nhập master password của họ.

LastPass cho biết trong một số trường hợp, tác nhân đe dọa đã gọi cho nạn nhân mạo danh nhân viên LastPass và hướng dẫn họ nhập thông tin xác thực trên trang phishing.

Công ty nói rằng một yếu tố then chốt trong cuộc tấn công của CryptoChameleon nhắm tới người dùng của họ là việc sử dụng các miền phishing tập trung vào passkey như _mypasskey[.]info_ và _passkeysetup[.]com_, cho thấy nỗ lực đánh cắp passkeys của người dùng.

Passkeys là một tiêu chuẩn xác thực không dùng mật khẩu dựa trên các giao thức FIDO2 / WebAuthn, sử dụng mật mã bất đối xứng thay vì mật khẩu phải ghi nhớ.

Các trình quản lý mật khẩu hiện đại như LastPass, 1Password, Dashlane và Bitwarden hiện lưu trữ và đồng bộ passkeys trên các thiết bị, và các tác nhân đe dọa đã bắt đầu nhắm mục tiêu trực tiếp vào chúng.

Năm 2022, LastPass đã chịu một cuộc xâm phạm dữ liệu lớn nơi kẻ tấn công [đã đánh cắp các bản sao lưu kho được mã hóa](https://www.bleepingcomputer.com/news/security/lastpass-hackers-stole-customer-vault-data-in-cloud-storage-breach/). Sự cố này có liên quan đến các [cuộc tấn công có mục tiêu](https://www.bleepingcomputer.com/news/security/lastpass-devops-engineer-hacked-to-steal-password-vault-data-in-2022-breach/) tiếp theo, dẫn đến mất mát khoảng [$4.4 million in cryptocurrency](https://www.bleepingcomputer.com/news/security/lastpass-breach-linked-to-theft-of-44-million-in-crypto/).