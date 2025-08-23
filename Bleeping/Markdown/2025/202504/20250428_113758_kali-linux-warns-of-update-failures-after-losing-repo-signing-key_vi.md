# Kali Linux cảnh báo về sự cố cập nhật sau khi mất khóa ký của repo

![Kali](https://www.bleepstatic.com/content/hl-images/2025/04/28/KALI.jpg)

Offensive Security đã cảnh báo người dùng Kali Linux cần cài đặt thủ công một khóa ký repo Kali mới để tránh gặp phải sự cố cập nhật.

Thông báo này được đưa ra sau khi OffSec mất khóa ký repo cũ (ED444FF07D8D0BF6) và buộc phải tạo một khóa mới (ED65462EC8D5E4C5) được ký bởi các nhà phát triển Kali Linux sử dụng chữ ký có sẵn trên [máy chủ khóa OpenPGP của Ubuntu](https://keyserver.ubuntu.com/pks/lookup?search=827C8569F2518CC677FECA1AED65462EC8D5E4C5&fingerprint=on&op=index). Tuy nhiên, do khóa này không bị xâm phạm, nên khóa cũ không bị xóa khỏi keyring.

Trên những hệ thống vẫn sử dụng khóa cũ, người dùng sẽ thấy thông báo "Thiếu khóa 827C8569F2518CC677FECA1AED65462EC8D5E4C5, cần thiết để xác minh chữ ký" khi cố gắng lấy danh sách các gói phần mềm mới nhất.

Mặc dù OffSec không chia sẻ ngày mà họ nhận ra khóa đã bị mất, công ty đã cho biết repo Kali Linux đã bị đông lạnh vào ngày 18 tháng 2.

"Trong những ngày tới, hầu hết mọi hệ thống Kali sẽ không thể cập nhật. \[..\] Đây không chỉ là bạn, mà là tất cả mọi người, và hoàn toàn là lỗi của chúng tôi. Chúng tôi đã mất quyền truy cập vào khóa ký của kho lưu trữ, vì vậy chúng tôi phải tạo một cái mới," công ty [nói](https://www.kali.org/blog/new-kali-archive-signing-key/).

"Đồng thời, chúng tôi đã đông lạnh kho lưu trữ (bạn có thể đã nhận thấy rằng không có cập nhật nào kể từ thứ Sáu ngày 18), vì vậy không ai bị ảnh hưởng. Nhưng chúng tôi sẽ mở khóa kho lưu trữ trong tuần này, và nó hiện giờ đã được ký bằng khóa mới."

Để tránh gặp phải những vấn đề cập nhật này, OffSec khuyên người dùng nên tải xuống và cài đặt thủ công khóa ký repo mới bằng cách sử dụng lệnh sau:

```
sudo wget https://archive.kali.org/archive-keyring.gpg -O /usr/share/keyrings/kali-archive-keyring.gpg
```

OffSec cũng cung cấp chi tiết về cách kiểm tra rằng checksum của tệp khớp và xem nội dung của keyring đã được cập nhật. Những người không tin tưởng vào việc cập nhật keyring thủ công cũng có thể cài đặt lại Kali trên hệ thống của họ bằng cách sử dụng hình ảnh đã được cập nhật với keyring mới.

Đây không phải là lần đầu tiên người dùng Kali Linux phải cập nhật keyring của họ thủ công để tránh gặp phải các vấn đề cập nhật. Vào tháng 2 năm 2018, các nhà phát triển Kali cũng đã [để cho khóa GPG hết hạn](https://x.com/kalilinux/status/959515084157538304) và yêu cầu người dùng cập nhật khóa mới thủ công.

"Nếu bạn không cập nhật Kali thường xuyên (\*cough\*), thì gói archive-keyring của bạn đã lỗi thời, và bạn sẽ gặp phải sự không khớp về khóa khi làm việc với các kho lưu trữ của chúng tôi. Rất tiếc cho bạn, nhưng ít nhất bạn có thể cập nhật thủ công," đội ngũ Kali đã nói vào thời điểm đó.