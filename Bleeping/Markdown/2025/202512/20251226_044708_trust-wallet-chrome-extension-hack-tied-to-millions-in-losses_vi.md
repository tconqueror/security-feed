# Trust Wallet Chrome extension bị hack gây thiệt hại hàng triệu

![tin tặc](https://www.bleepstatic.com/content/hl-images/2025/08/18/bitcoin-crypto-hacker.jpg)

Nhiều người dùng Trust Wallet Chrome extension báo cáo rằng ví tiền điện tử của họ bị rút sạch sau khi cài đặt một bản cập nhật phần mở rộng bị xâm phạm được phát hành vào ngày 24 tháng 12, dẫn tới phản ứng khẩn cấp từ công ty và cảnh báo tới những người bị ảnh hưởng.

Cùng lúc đó, BleepingComputer quan sát thấy các tác nhân đe doạ khởi chạy các tên miền lừa đảo hứa hẹn một bản sửa "lỗ hổng" giả, nhưng thay vào đó tiếp tục rút tiền ví nạn nhân.

## Ví bị rút sau bản cập nhật đêm Giáng Sinh

Vào ngày 24 tháng 12, nhiều người dùng tiền điện tử bắt đầu báo cáo trên mạng xã hội rằng quỹ của họ bị rút khỏi ví ngay sau khi tương tác với Trust Wallet Chrome extension. Các nguồn ước tính tổn thất từ cuộc tấn công [vượt quá $6 million](https://x.com/PeckShieldAlert/status/2004382831158714735) giá trị tài sản tiền điện tử bị đánh cắp.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Trust Wallet là một ví tiền điện tử non-custodial được sử dụng rộng rãi cho phép người dùng lưu trữ, quản lý và tương tác với tài sản số trên nhiều blockchain. Ví có sẵn dưới dạng ứng dụng di động và dưới dạng Trust Wallet Chrome extension để tương tác với các ứng dụng phi tập trung (dApps).

"Mọi người ngày càng phàn nàn về tiền biến mất khỏi phần mở rộng trình duyệt ngay sau khi ủy quyền đơn giản... Số tiền thiệt hại đã vượt quá $2 million?" một người dùng đăng trước đó, trong khi chia sẻ các bài viết từ những người tự nhận là nạn nhân của bản cập nhật phần mở rộng.

Chuyên gia an ninh Akinator cảnh báo mọi người không sử dụng Trust Wallet Chrome extension trong thời gian này:

[![Tweet alerting users](https://www.bleepstatic.com/images/news/u/1164866/2025/Dec/trust-wallet-chrome/tweet-alert.jpg)](https://x.com/0xakinator/status/2004273944694587785) 

**Security analyst @0xakinator alerts everyone on X**

BleepingComputer xác nhận rằng Trust Wallet phát hành phiên bản 2.68.0 của Trust Wallet Chrome extension vào ngày 24 tháng 12, ngay trước khi các báo cáo về sự cố rút ví bắt đầu xuất hiện.

Khi các khiếu nại và cảnh báo leo thang trực tuyến, BleepingComputer đã liên hệ với Trust Wallet để làm rõ và xác nhận sự cố bảo mật có thể xảy ra. Mặc dù chúng tôi không nhận được phản hồi ngay lập tức, chúng tôi quan sát thấy phiên bản 2.69 của Trust Wallet Chrome extension đã [âm thầm được phát hành](https://chromewebstore.google.com/detail/trust-wallet/egjidjbpglichdcondbcbdnbeeppgdph?hl=en) sau đó trên Chrome Web Store.

## Phát hiện tên miền khả nghi trong phiên bản bị xâm phạm

Trong vài giờ sau sự cố, các nhà nghiên cứu bảo mật đã xác định mã khả nghi xuất hiện trong phiên bản 2.68.0 của Trust Wallet Chrome extension.

[Theo](https://x.com/0xakinator/status/2004297673067704651) Akinator, logic khả nghi xuất hiện trong một file JavaScript đóng gói tên là 4482.js, chứa mã nén chặt có vẻ như rò rỉ dữ liệu ví nhạy cảm tới một máy chủ bên ngoài được host tại: _api.metrics-trustwallet[.\]com._

"Vì vậy đây là những gì đang xảy ra... Trong code của Trust Wallet browser extension file 4482.js một bản cập nhật gần đây đã thêm mã ẩn lặng lẽ gửi dữ liệu ví ra ngoài," giải thích nhà phân tích.

"Nó giả vờ là analytics, nhưng nó theo dõi hoạt động ví và kích hoạt khi một seed phrase được nhập. Dữ liệu được gửi tới _metrics-trustwallet[.\]com,_ một domain được đăng ký vài ngày trước và hiện đã sập."  

**Suspicious domain seen in compromised extension version 2.68.0** (@0xakinator on X)

Sự xuất hiện của một endpoint "metrics" bên ngoài mới đăng ký trong một phần mở rộng ví trình duyệt là rất bất thường, xét tới quyền truy cập đặc quyền của phần mở rộng tới các thao tác ví và dữ liệu nhạy cảm.

Nhà nghiên cứu bảo mật Andrew Mohawk, ban đầu hoài nghi về tuyên bố, [cuối cùng đã xác nhận](http://x.com/AndrewMohawk/status/2004318649835049221) rằng endpoint đó liên quan tới việc rò rỉ bí mật.

**Network request inspection shows wallet seed phrase exfiltration** (Andrew Mohawk on X)

Bản ghi WHOIS công khai cho thấy domain mẹ metrics-trustwallet[.\]com chỉ được đăng ký vài ngày trước sự cố. Tại thời điểm viết bài, chưa có xác nhận công khai nào rằng domain này thuộc sở hữu hoặc được điều hành hợp pháp bởi Trust Wallet.

## Trust Wallet xác nhận sự cố bảo mật

Tối hôm qua, Trust Wallet xác nhận rằng một "sự cố bảo mật" đã ảnh hưởng tới phiên bản 2.68.0 của Trust Wallet Chrome extension, và khuyên người dùng cập nhật ngay lập tức lên phiên bản 2.69 để khắc phục vấn đề.

Tuy nhiên, Trust Wallet vẫn chưa trả lời các câu hỏi của BleepingComputer về việc liệu người dùng bị ảnh hưởng có được bồi thường hay các tùy chọn khắc phục cho những người ví bị rút tiền do sự cố này là gì.

> We've identified a security incident affecting Trust Wallet Browser Extension version 2.68 only. Users with Browser Extension 2.68 should disable and upgrade to 2.69.  
>  
> Please refer to the official Chrome Webstore link here: <https://t.co/V3vMq31TKb>
> 
> — Trust Wallet (@TrustWallet) [December 25, 2025](https://twitter.com/TrustWallet/status/2004316503701958786?ref%5Fsrc=twsrc%5Etfw)

## Kẻ tấn công gia tăng với chiến dịch lừa đảo đồng thời

Trong khi người dùng loay hoay tìm thông tin và hướng dẫn, BleepingComputer quan sát thấy một chiến dịch lừa đảo song song lợi dụng cơn hoảng loạn đang diễn ra.

Nhiều tài khoản X \[[1](https://archive.md/GA8rw), [2](https://archive.md/aeRCV)\] đã hướng người dùng lo lắng tới một website khả nghi host tại một domain lạ: _fix-trustwallet[.\]com_.

Trang này mạo danh thương hiệu Trust Wallet rất giống và [khẳng định sửa](https://archive.md/iBVbz) một "lỗ hổng bảo mật" trong Trust Wallet. Tuy nhiên sau khi nhấp nút "Update", người dùng được hiện một popup yêu cầu seed phrase phục hồi ví, vốn hoạt động như chìa khóa chính cho toàn bộ quyền kiểm soát ví.

**Suspicious 'fix-trustwallet.com' domain** (BleepingComputer)

Nhập seed phrase trên một trang như vậy sẽ cho phép kẻ tấn công ngay lập tức rút toàn bộ quỹ liên quan.

**Illicit 'fix-trustwallet' site asking for wallet seed phrases** (BleepingComputer)

Dữ liệu WHOIS cho thấy _fix-trustwallet.com_ được đăng ký đầu tháng này, với cùng registrar như _metrics-trustwallet.com_, gợi ý các domain có thể liên kết và có khả năng được điều hành bởi cùng một tác nhân đe doạ hoặc nhóm đứng sau cuộc tấn công rộng hơn.

## Người dùng nên làm gì

Trust Wallet khuyên người dùng phần mở rộng Chrome đảm bảo rằng họ đang chạy phiên bản vá mới nhất 2.69 và cho biết sự cố ảnh hưởng riêng phiên bản Chrome extension 2.68.0. Người dùng chỉ dùng mobile và tất cả các phiên bản phần mở rộng trình duyệt khác, theo họ, không bị ảnh hưởng.

"Đối với người dùng chưa cập nhật lên Extension version 2.69, vui lòng không mở Browser Extension cho tới khi bạn đã cập nhật. Điều này có thể giúp đảm bảo an toàn cho ví của bạn và ngăn ngừa các vấn đề tiếp theo," tiếp tục Trust Wallet trong cùng một thread trên X.

"Thực hiện theo hướng dẫn từng bước càng sớm càng tốt:  
  
Step 1: Do NOT open the Trust Wallet Browser Extension on your desktop device to ensure the security of your wallet and prevent further issues.  
  
Step 2: Go to Chrome Extensions panel in your Chrome browser by copying following to the address line (shortcut to the Official Trust Wallet Browser Extension): chrome://extensions/?id=egjidjbpglichdcondbcbdnbeeppgdph  
  
Step 3: Switch the toggle to "Off" below the Trust Wallet if it's still "On".  
  
Step 4: Click "Developer mode" in the upper right corner.  
  
Step 5: Press the "Update" on the left upper corner.  
  
Step 6\. Check the version number: 2.69\. This is the latest and secure version.  

"Nhóm Hỗ trợ Khách hàng của chúng tôi đã liên hệ với những người dùng bị ảnh hưởng về các bước tiếp theo. Vui lòng yêu cầu những người trong DM của bạn liên hệ với Support team tại đây: [https://twtholders.trustwallet.com](https://twtholders.trustwallet.com/)," Trust Wallet khuyên.

Những người tin rằng ví của họ có thể đã bị xâm phạm được khuyến cáo ngay lập tức chuyển số dư còn lại sang một ví mới được tạo bằng seed phrase mới và coi bất kỳ cụm phục hồi nào đã bị lộ trước đó là không an toàn vĩnh viễn.