# GitHub bắt buộc 2FA và token thời hạn ngắn để tăng cường bảo mật chuỗi cung ứng npm

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjZQ-xcQ5PKzdd6Juz8x%5F31GctkkivtZYfhVKlnZ5tFKbTtwJTtmajAEiqsdZZslnaRPS9Vd3LH4mQTo9agSCG6%5FcEuoUU%5F7WCvb1e-MmDytS4hQ1x1xur0u-DTQOYAydatYghaAZjPeBttRMTKNJKmJjWtvxfYOE1UvyltBh-K5fRWNwXIsLh-lv7af27Q/s728-rw-e365/github-npm.jpg)

GitHub vào thứ Hai [thông báo](https://github.blog/security/supply-chain-security/our-plan-for-a-more-secure-npm-supply-chain/) rằng họ sẽ thay đổi các tùy chọn xác thực và xuất bản "trong tương lai gần" để đối phó với một làn sóng gần đây của các [cuộc tấn công chuỗi cung ứng](https://thehackernews.com/2025/09/20-popular-npm-packages-with-2-billion.html) nhắm vào hệ sinh thái npm, bao gồm cả cuộc tấn công Shai-Hulud.

Điều này bao gồm các bước nhằm giải quyết các mối đe dọa do lạm dụng token và phần mềm độc hại tự sao chép bằng cách cho phép xuất bản cục bộ với yêu cầu xác thực hai yếu tố (2FA), các [granular tokens](https://docs.npmjs.com/about-access-tokens#about-granular-access-tokens) sẽ có thời hạn giới hạn bảy ngày, và [trusted publishing](https://repos.openssf.org/trusted-publishers-for-all-package-repositories), cho phép khả năng xuất bản an toàn các gói npm trực tiếp từ các workflow CI/CD bằng OpenID Connect (OIDC).

Trusted publishing, ngoài việc loại bỏ nhu cầu sử dụng npm tokens, thiết lập niềm tin mật mã bằng cách xác thực mỗi lần xuất bản sử dụng thông tin xác thực workflow có thời hạn ngắn và không thể bị rút trộm hoặc tái sử dụng. Quan trọng hơn, npm CLI tự động tạo và xuất bản các chứng nhận nguồn gốc (provenance attestations) cho gói.

"Every package published via trusted publishing includes cryptographic proof of its source and build environment," GitHub đã [nhấn mạnh](https://github.blog/changelog/2025-07-31-npm-trusted-publishing-with-oidc-is-generally-available/) vào cuối tháng 7 năm 2025. "Người dùng của bạn có thể xác minh nơi và cách gói được xây dựng, tăng sự tin tưởng vào chuỗi cung ứng của bạn."

[](https://thehackernews.uk/exec-guide-d)

Để hỗ trợ những thay đổi này, công ty thuộc sở hữu Microsoft cho biết họ sẽ thực hiện các bước sau -

* Loại bỏ các legacy classic tokens.
* Loại bỏ time-based one-time password (TOTP) 2FA, di chuyển người dùng sang 2FA dựa trên FIDO.
* Giới hạn granular tokens có quyền xuất bản với thời hạn ngắn hơn.
* Thiết lập quyền xuất bản mặc định để không cho phép tokens, khuyến khích sử dụng trusted publishers hoặc xuất bản cục bộ bắt buộc 2FA.
* Gỡ bỏ tùy chọn bỏ qua 2FA cho việc xuất bản gói cục bộ.
* Mở rộng các nhà cung cấp đủ điều kiện cho trusted publishing.

Sự phát triển này diễn ra một tuần sau khi một cuộc tấn công chuỗi cung ứng có tên mã Shai-Hulud đã [chèn](https://thehackernews.com/2025/09/40-npm-packages-compromised-in-supply.html) một loại worm tự sao chép vào hàng trăm gói npm, quét máy của các nhà phát triển để tìm các bí mật nhạy cảm và truyền chúng đến một máy chủ do kẻ tấn công kiểm soát.

"Bằng cách kết hợp tự sao chép với khả năng đánh cắp nhiều loại bí mật (không chỉ tokens npm), con worm này có thể đã cho phép một chuỗi tấn công vô tận nếu không có hành động kịp thời từ GitHub và các duy trì mã nguồn mở," Xavier René-Corail của GitHub cho biết.

### Npm Package bao gồm mã QR

Thông tin được công bố trong bối cảnh công ty bảo mật chuỗi cung ứng phần mềm Socket nói rằng họ đã xác định một gói npm độc hại có tên [fezbox](https://www.npmjs.com/package/fezbox) có khả năng thu thập mật khẩu trình duyệt bằng một kỹ thuật steganography mới. Gói này hiện không còn có thể tải xuống từ npm. Nó đã thu hút tổng cộng [476 lượt tải](https://npm-stat.com/charts.html?package=fezbox) kể từ khi nó [được xuất bản lần đầu](https://secure.software/npm/packages/fezbox/versions) vào ngày 21 tháng 8, 2025.

"Trong gói này, tác nhân đe dọa (bí danh npm janedu; email đăng ký janedu0216@gmail[.]com) thực thi một payload bên trong một mã QR để đánh cắp thông tin đăng nhập tên người dùng và mật khẩu từ cookie web, trong trình duyệt," nhà nghiên cứu bảo mật Olivia Brown [cho biết](https://socket.dev/blog/malicious-fezbox-npm-package-steals-browser-passwords-from-cookies-via-innovative-qr-code).

[](https://thehackernews.uk/cis-security-suite)

Fezbox tuyên bố là một tiện ích JavaScript bao gồm các hàm trợ giúp phổ biến. Nhưng thực tế, nó chứa mã ẩn để lấy một mã QR từ một URL từ xa, phân tích mã QR, và thực thi payload JavaScript chứa trong URL đó.

Phần payload cố gắng đọc [document.cookie](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie), trích xuất thông tin tên người dùng và mật khẩu từ cookie, và truyền thông tin đến một máy chủ bên ngoài ("my-nest-app-production>.up.railway[.]app") thông qua một yêu cầu HTTPS POST.

"Hầu hết ứng dụng hiện nay không còn lưu mật khẩu ở dạng thuần trong cookie nữa, vì vậy khó nói phần mềm độc hại này sẽ thành công đến đâu trong mục tiêu của nó," Brown lưu ý. "Tuy nhiên, việc sử dụng mã QR để che giấu thêm là một thủ thuật sáng tạo của tác nhân đe dọa. Kỹ thuật này cho thấy các tác nhân đe dọa tiếp tục cải tiến các phương pháp che giấu và tại sao việc có một công cụ chuyên dụng để kiểm tra các phụ thuộc của bạn lại quan trọng hơn bao giờ hết."