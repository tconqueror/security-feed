# Trust Wallet liên kết vụ trộm tiền điện tử trị giá $8,5 triệu với cuộc tấn công NPM Shai-Hulud

![Trust Wallet](https://www.bleepstatic.com/content/hl-images/2026/01/02/Trust-Wallet.jpg)

Trust Wallet tin rằng việc xâm phạm trình duyệt web của họ để đánh cắp khoảng $8,5 triệu từ hơn 2.500 ví tiền điện tử rất có khả năng liên quan đến một cuộc tấn công "trên toàn ngành" Sha1-Hulud vào tháng Mười Một.

Trust Wallet, một ví tiền điện tử được sử dụng bởi hơn 200 triệu người, cho phép người dùng lưu trữ, gửi và nhận Bitcoin, Ethereum, Solana và hàng nghìn loại tiền điện tử cũng như token kỹ thuật số khác thông qua tiện ích mở rộng trình duyệt web và ứng dụng di động miễn phí.

Như [BleepingComputer đã đưa tin trước đó](https://www.bleepingcomputer.com/news/security/trust-wallet-confirms-extension-hack-led-to-7-million-crypto-theft/), sự cố ngày 24 tháng 12 này đã dẫn đến việc hàng triệu đô la tiền điện tử bị đánh cắp từ các ví Trust Wallet bị xâm phạm của người dùng.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Sự việc xảy ra sau khi kẻ tấn công thêm một tệp JavaScript độc hại vào phiên bản 2.68.0 của tiện ích mở rộng Chrome của Trust Wallet, tệp này đã đánh cắp dữ liệu ví nhạy cảm và cho phép tác nhân đe dọa thực hiện các giao dịch trái phép.

"Các bí mật GitHub của Developer của chúng tôi đã bị lộ trong cuộc tấn công, điều này cho phép kẻ tấn công truy cập vào mã nguồn tiện ích mở rộng trình duyệt của chúng tôi và khoá API Chrome Web Store (CWS)," công ty [cho biết](https://trustwallet.com/blog/announcements/trust-wallet-browser-extension-v268-incident-community-update#:~:text=November%202025) trong một cập nhật vào thứ Ba.

"Kẻ tấn công đã có toàn quyền truy cập CWS API thông qua khóa bị rò rỉ, cho phép các bản build được tải lên trực tiếp mà không thông qua quy trình phát hành tiêu chuẩn của Trust Wallet, vốn yêu cầu phê duyệt nội bộ/đánh giá thủ công."

[![Trust Wallet attack](https://www.bleepstatic.com/images/news/u/1109292/2025/Trust-Wallet-attack.png)](https://x.com/TrustWallet/status/2006029263477117260)

Như Trust Wallet giải thích, ở giai đoạn tiếp theo của vụ tấn công, tác nhân đe dọa đã đăng ký tên miền metrics-trustwallet.com và tên miền phụ api.metrics-trustwallet.com để lưu trữ mã độc, sau đó được tham chiếu trong một phiên bản trojan hóa của tiện ích mở rộng Trust Wallet.

Phiên bản đã bị chỉnh sửa của tiện ích mở rộng chính thức được xây dựng bằng mã nguồn có được thông qua các bí mật Developer GitHub bị lộ, cho phép kẻ tấn công nhúng mã độc thu thập dữ liệu ví nhạy cảm mà không cần chèn mã theo cách truyền thống.

Sử dụng khóa CWS bị rò rỉ, kẻ tấn công đã xuất bản phiên bản 2.68 lên Chrome Web Store, phiên bản này tự động được phát hành sau khi vượt qua quy trình đánh giá, bỏ qua các thủ tục phê duyệt nội bộ của Trust Wallet.

Đáp trả sự cố, Trust Wallet đã thu hồi tất cả các API phát hành để chặn các cố gắng phát hành phiên bản mới và đảm bảo rằng tin tặc không thể đánh cắp thêm dữ liệu ví bằng cách báo cáo các tên miền độc hại cho nhà đăng ký NiceNIC, người đã nhanh chóng đình chỉ chúng.

Trust Wallet cũng đã [bắt đầu hoàn trả cho người dùng bị ảnh hưởng](https://www.bleepingcomputer.com/news/security/trust-wallet-says-7-million-crypto-theft-attack-drained-2-596-wallets/) và cảnh báo họ rằng các tác nhân đe dọa hiện đang mạo danh các tài khoản hỗ trợ Trust Wallet, đẩy các biểu mẫu bồi thường giả và chạy các chiêu lừa đảo qua quảng cáo Telegram.

## Chiến dịch phần mềm độc hại Shai-Hulud

Sha1-Hulud (cũng được biết đến là [Shai-Hulud 2.0](https://www.bleepingcomputer.com/news/security/shai-hulud-20-npm-malware-attack-exposed-up-to-400-000-dev-secrets/)) là một cuộc tấn công chuỗi cung ứng nhắm vào registry phần mềm npm, nơi liệt kê hơn 2 triệu gói.

Trong [đợt bùng phát Sha1-Hulud ban đầu](https://www.bleepingcomputer.com/news/security/self-propagating-supply-chain-attack-hits-187-npm-packages/) vào đầu tháng Chín, các tác nhân đe dọa đã xâm phạm hơn 180 gói npm bằng payload tự lan truyền và sử dụng nó để đánh cắp bí mật của nhà phát triển và khóa API bằng công cụ TruffleHog.

Shai-Hulud 2.0 phát triển theo cấp số nhân và [ảnh hưởng đến hơn 800 gói](https://www.bleepingcomputer.com/news/security/shai-hulud-malware-infects-500-npm-packages-leaks-secrets-on-github/) sau khi thêm hơn 27.000 gói độc hại vào kho npm, những gói này sử dụng mã độc để thu thập bí mật của nhà phát triển và CI/CD và công bố chúng trên GitHub.

Tổng cộng, Sha1-Hulud [đã phơi bày khoảng 400.000 bí mật thô](https://www.bleepingcomputer.com/news/security/shai-hulud-20-npm-malware-attack-exposed-up-to-400-000-dev-secrets/) và công bố dữ liệu bị đánh cắp trên hơn 30.000 repository GitHub, với hơn 60% token NPM bị rò rỉ vẫn còn hiệu lực tính đến ngày 1 tháng Mười Hai.

"Các kẻ tấn công đang hoàn thiện hoạt động thu thập thông tin xác thực sử dụng hệ sinh thái npm và GitHub," các nhà nghiên cứu bảo mật của Wiz [cảnh báo](https://www.wiz.io/blog/shai-hulud-2-0-aftermath-ongoing-supply-chain-attack) vào tháng trước.

"Với sự tinh vi ngày càng tăng và thành công cho đến nay của các kẻ tấn công, chúng tôi dự đoán sẽ tiếp tục có các cuộc tấn công, cả việc sử dụng các TTP tương tự và tận dụng kho thông tin xác thực đã thu thập được đến nay."