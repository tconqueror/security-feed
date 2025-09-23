# GitHub bắt buộc 2FA và token ngắn hạn để củng cố bảo mật chuỗi cung ứng npm

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjZQ-xcQ5PKzdd6Juz8x%5F31GctkkivtZYfhVKlnZ5tFKbTtwJTtmajAEiqsdZZslnaRPS9Vd3LH4mQTo9agSCG6%5FcEuoUU%5F7WCvb1e-MmDytS4hQ1x1xur0u-DTQOYAydatYghaAZjPeBttRMTKNJKmJjWtvxfYOE1UvyltBh-K5fRWNwXIsLh-lv7af27Q/s728-rw-e365/github-npm.jpg)

GitHub vào thứ Hai [announced](https://github.blog/security/supply-chain-security/our-plan-for-a-more-secure-npm-supply-chain/) rằng họ sẽ thay đổi các tùy chọn xác thực và xuất bản "trong tương lai gần" để đối phó với một [làn sóng gần đây](https://thehackernews.com/2025/08/malicious-nx-packages-in-s1ngularity.html) các [cuộc tấn công chuỗi cung ứng](https://thehackernews.com/2025/09/20-popular-npm-packages-with-2-billion.html) nhắm vào hệ sinh thái npm, bao gồm cả cuộc tấn công [Shai-Hulud](https://thehackernews.com/2025/09/40-npm-packages-compromised-in-supply.html).

Điều này bao gồm các bước để giải quyết các mối đe dọa do lạm dụng token và phần mềm độc hại tự sao chép bằng cách cho phép xuất bản cục bộ với yêu cầu xác thực hai yếu tố (2FA), [granular tokens](https://docs.npmjs.com/about-access-tokens#about-granular-access-tokens) sẽ có thời hạn giới hạn là bảy ngày, và [trusted publishing](https://repos.openssf.org/trusted-publishers-for-all-package-repositories), cho phép khả năng xuất bản an toàn các gói npm trực tiếp từ quy trình CI/CD bằng OpenID Connect (OIDC).

Trusted publishing, ngoài việc loại bỏ nhu cầu về npm tokens, thiết lập niềm tin mật mã bằng cách xác thực mỗi lần xuất bản sử dụng chứng thực ngắn hạn, đặc thù cho workflow và không thể bị lấy cắp hay tái sử dụng. Thậm chí quan trọng hơn, npm CLI tự động tạo và xuất các khai nhận provenance cho gói.

"Every package published via trusted publishing includes cryptographic proof of its source and build environment," GitHub [noted](https://github.blog/changelog/2025-07-31-npm-trusted-publishing-with-oidc-is-generally-available/) vào cuối tháng 7 năm 2025. "Your users can verify where and how your package was built, increasing trust in your supply chain."

[](https://thehackernews.uk/exec-guide-d)

Để hỗ trợ những thay đổi này, công ty thuộc Microsoft cho biết họ sẽ thực hiện các bước sau -

* Deprecate legacy classic tokens.
* Deprecate time-based one-time password (TOTP) 2FA, migrating users to FIDO-based 2FA.
* Limit granular tokens with publishing permissions to a shorter expiration.
* Set publishing access to disallow tokens by default, encouraging usage of trusted publishers or 2FA-enforced local publishing.
* Remove the option to bypass 2FA for local package publishing.
* Expand eligible providers for trusted publishing.

Sự phát triển này diễn ra một tuần sau một cuộc tấn công chuỗi cung ứng có tên mã Shai-Hulud đã [injected](https://thehackernews.com/2025/09/40-npm-packages-compromised-in-supply.html) một con sâu tự sao chép vào hàng trăm gói npm, con sâu này quét các máy của nhà phát triển để tìm các bí mật nhạy cảm và truyền chúng đến một máy chủ do kẻ tấn công kiểm soát.

"By combining self-replication with the capability to steal multiple types of secrets (and not just npm tokens), this worm could have enabled an endless stream of attacks had it not been for timely action from GitHub and open source maintainers," Xavier René-Corail của GitHub cho biết.

### Gói npm bao gồm payload dựa trên mã QR

Thông tin được tiết lộ trong bối cảnh công ty bảo mật chuỗi cung ứng phần mềm Socket cho biết họ đã xác định một gói npm độc hại tên là fezbox có khả năng thu thập mật khẩu trình duyệt bằng một kỹ thuật steganography mới. Gói này hiện không còn có thể tải xuống từ npm. Nó đã thu hút tổng cộng [476 downloads](https://npm-stat.com/charts.html?package=fezbox) kể từ khi được [first published](https://secure.software/npm/packages/fezbox/versions) vào ngày 21 tháng 8 năm 2025.

"In this package, the threat actor (npm alias janedu; registration email janedu0216@gmail[.]com) executes a payload within a QR code to steal username and password credentials from web cookies, within the browser," nhà nghiên cứu bảo mật Olivia Brown [said](https://socket.dev/blog/malicious-fezbox-npm-package-steals-browser-passwords-from-cookies-via-innovative-qr-code).

[](https://thehackernews.uk/cis-security-suite)

Fezbox tuyên bố là một tiện ích JavaScript gồm các hàm trợ giúp thông thường. Nhưng thực tế, nó chứa mã tinh vi để lấy một mã QR từ một URL từ xa, phân tích mã QR, và thực thi payload JavaScript chứa trong URL đó.

Payload, về phần nó, cố gắng đọc document.cookie, trích xuất thông tin tên người dùng và mật khẩu từ cookie, và truyền thông tin tới một máy chủ bên ngoài ("my-nest-app-production>.up.railway[.]app") thông qua một yêu cầu HTTPS POST.

"Most applications no longer store literal passwords in cookies, so it's difficult to say how successful this malware would be at its goal," Brown lưu ý. "However, the use of a QR code for further obfuscation is a creative twist by the threat actor. This technique demonstrates how threat actors continue to improve their obfuscation techniques and why having a dedicated tool to check your dependencies is more important than ever."