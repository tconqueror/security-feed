# Trust Wallet xác nhận mở rộng bị hack dẫn đến thiệt hại 7 triệu đô tiền mã hóa

![tin tặc](https://www.bleepstatic.com/content/hl-images/2024/02/13/crypto-hacker.jpg)

Trust Wallet xác nhận rằng một bản cập nhật Chrome extension bị xâm phạm phát hành vào ngày 24 tháng 12 đã dẫn đến việc mất 7 triệu đô tiền mã hóa sau khi người dùng báo cáo ví của họ bị rút sạch.

"So far, $7m affected by this hack. TrustWallet will cover. User funds are SAFU. Appreciate your understanding for any inconveniences caused," [đã đăng](http://x.com/cz%5Fbinance/status/2004397190819783013) Binance founder Changpeng "CZ" Zhao trên X.

"Nhóm đang vẫn điều tra cách kẻ tấn công có thể nộp phiên bản mới."

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Cùng lúc đó, BleepingComputer quan sát thấy các tác nhân đe dọa triển khai các tên miền lừa đảo hứa hẹn một bản sửa "lỗ hổng" giả, nhưng thay vào đó tiếp tục rút sạch ví của nạn nhân.

## Ví bị rút sau bản cập nhật đêm Giáng sinh

Vào ngày 24 tháng 12, nhiều người dùng tiền mã hóa bắt đầu báo cáo trên mạng xã hội rằng tiền bị rút khỏi ví của họ ngay sau khi tương tác với extension Trust Wallet trên Chrome. Hiện đã được xác nhận rằng ít nhất 7 triệu đô tiền mã hóa đã bị đánh cắp trong cuộc tấn công chuỗi cung ứng này.

Trust Wallet là một ví tiền mã hóa non-custodial được sử dụng rộng rãi, cho phép người dùng lưu trữ, quản lý và tương tác với tài sản số trên nhiều blockchain. Ví có sẵn dưới dạng ứng dụng di động và dưới dạng extension Chrome dùng để tương tác với các ứng dụng phi tập trung (dApps).

"Càng ngày càng có nhiều người phàn nàn về việc tiền biến mất khỏi extension trình duyệt ngay lập tức sau khi cho phép đơn giản... Mức thiệt hại đã vượt quá $2 triệu?" một người dùng [đã đăng](https://x.com/Aaleks%5Fcrypt/status/2004281742031528262) trước đó, đồng thời chia sẻ các bài viết từ những người tuyên bố là nạn nhân của bản cập nhật extension.

Chuyên gia an ninh Akinator cảnh báo mọi người tránh sử dụng extension Trust Wallet trên Chrome trong thời gian này:

[![Tweet cảnh báo người dùng](https://www.bleepstatic.com/images/news/u/1164866/2025/Dec/trust-wallet-chrome/tweet-alert.jpg)](https://x.com/0xakinator/status/2004273944694587785) 

**Security analyst @0xakinator alerts everyone on X**

BleepingComputer xác nhận rằng Trust Wallet đã phát hành phiên bản 2.68.0 của extension Chrome vào ngày 24 tháng 12, ngay trước khi các báo cáo về các vụ rút tiền bắt đầu xuất hiện.

Khi các phàn nàn và cảnh báo tăng lên trực tuyến, BleepingComputer đã liên hệ với Trust Wallet để làm rõ và xác nhận về khả năng có sự cố an ninh. Trong khi chúng tôi không nhận được phản hồi ngay lập tức, chúng tôi quan sát thấy rằng phiên bản 2.69 của Trust Wallet Chrome extension đã [bị phát hành lặng lẽ](https://chromewebstore.google.com/detail/trust-wallet/egjidjbpglichdcondbcbdnbeeppgdph?hl=en) ngay sau đó trên Chrome Web Store.

## Tên miền đáng ngờ được phát hiện trong phiên bản bị xâm phạm

Trong vài giờ sau khi xảy ra sự cố, các nhà nghiên cứu an ninh phát hiện mã đáng ngờ có trong phiên bản 2.68.0 của Trust Wallet Chrome extension.

[Theo](https://x.com/0xakinator/status/2004297673067704651) Akinator, logic đáng ngờ xuất hiện trong một tệp JavaScript đóng gói tên là 4482.js, chứa mã ép chặt dường như lấy cắp dữ liệu ví nhạy cảm và gửi ra máy chủ bên ngoài được lưu trữ tại: _api.metrics-trustwallet\[.\]com._

"Vậy đây là những gì đang xảy ra... Trong mã của Trust Wallet browser extension 4482.js một bản cập nhật gần đây đã thêm mã ẩn gửi dữ liệu ví ra ngoài một cách lặng lẽ," chuyên gia phân tích giải thích.

"Nó giả vờ là analytics, nhưng nó theo dõi hoạt động ví và kích hoạt khi một seed phrase được nhập. Dữ liệu được gửi tới _metrics-trustwallet\[.\]com,_ một tên miền được đăng ký vài ngày trước và hiện đã sập."  

**Tên miền đáng ngờ được thấy trong phiên bản extension 2.68.0 bị xâm phạm** (@0xakinator trên X)

Sự hiện diện của một endpoint "metrics" bên ngoài mới được đăng ký trong một extension trình duyệt ví là điều rất bất thường, vì extension có quyền truy cập đặc quyền vào các hoạt động ví và dữ liệu nhạy cảm.

Nhà nghiên cứu an ninh Andrew Mohawk, ban đầu hoài nghi về tuyên bố này, [cuối cùng đã xác nhận](http://x.com/AndrewMohawk/status/2004318649835049221) rằng endpoint liên quan đến việc rò rỉ bí mật.

**Kiểm tra yêu cầu mạng cho thấy seed phrase của ví bị rò rỉ** (Andrew Mohawk trên X)

Các ghi chú WHOIS công khai cho thấy tên miền mẹ metrics-trustwallet\[.\]com chỉ được đăng ký vài ngày trước khi xảy ra sự cố. Tính đến thời điểm viết bài, chưa có xác nhận công khai rằng tên miền này thuộc sở hữu hoặc được điều hành hợp pháp bởi Trust Wallet.

## Trust Wallet xác nhận sự cố an ninh

Tối hôm qua, Trust Wallet xác nhận rằng một "sự cố an ninh" đã ảnh hưởng đến phiên bản 2.68.0 của Chrome extension của họ, và khuyên người dùng cập nhật ngay lên phiên bản 2.69 để khắc phục vấn đề.

Tuy nhiên, Trust Wallet vẫn chưa trả lời các câu hỏi của BleepingComputer liên quan đến sự cố, bao gồm có bao nhiêu người bị ảnh hưởng và tổng số tiền mã hóa bị đánh cắp.

> We've identified a security incident affecting Trust Wallet Browser Extension version 2.68 only. Users with Browser Extension 2.68 should disable and upgrade to 2.69.  
>  
> Please refer to the official Chrome Webstore link here: <https://t.co/V3vMq31TKb>
> 
> — Trust Wallet (@TrustWallet) [December 25, 2025](https://twitter.com/TrustWallet/status/2004316503701958786?ref%5Fsrc=twsrc%5Etfw)

## Kẻ tấn công gia tăng bằng chiến dịch lừa đảo đồng thời

Trong khi người dùng hoảng loạn tìm kiếm thông tin và hướng dẫn, BleepingComputer quan sát thấy một chiến dịch lừa đảo song song tận dụng sự hoang mang hiện có.

Nhiều tài khoản X \[[1](https://archive.md/GA8rw), [2](https://archive.md/aeRCV)\] đã chỉ dẫn người dùng lo lắng đến một tên miền đáng ngờ: _fix-trustwallet\[.\]com_.

Trang web bắt chước tương tự thương hiệu Trust Wallet và [tuyên bố sửa](https://archive.md/iBVbz) một "lỗ hổng bảo mật" trong Trust Wallet. Tuy nhiên, sau khi nhấp nút "Update", người dùng được hiển thị một popup yêu cầu seed phrase phục hồi ví, thứ hoạt động như chìa khóa chính cho toàn quyền kiểm soát ví.

**Tên miền đáng ngờ 'fix-trustwallet\[.\]com'** (BleepingComputer)

Nhập seed phrase trên một trang như vậy sẽ cho phép kẻ tấn công ngay lập tức rút sạch tất cả tiền liên quan.

**Trang 'fix-trustwallet' bất hợp pháp yêu cầu seed phrase của ví** (BleepingComputer)

Dữ liệu WHOIS cho thấy _fix-trustwallet\[.\]com_ được đăng ký đầu tháng này, với cùng một nhà đăng ký như _metrics-trustwallet\[.\]com_, gợi ý rằng các tên miền có thể liên quan và có khả năng được vận hành bởi cùng một tác nhân hoặc nhóm đe dọa đứng sau cuộc tấn công rộng hơn.

## Người dùng nên làm gì

Trust Wallet khuyên người dùng extension Chrome đảm bảo họ đang chạy phiên bản 2.69 mới nhất đã được sửa và cho biết sự cố chỉ ảnh hưởng đến phiên bản Chrome extension 2.68.0. Người dùng chỉ dùng di động và tất cả các phiên bản extension trình duyệt khác, theo họ, không bị ảnh hưởng.

"Đối với người dùng chưa cập nhật lên Extension phiên bản 2.69, vui lòng không mở Browser Extension cho đến khi bạn đã cập nhật. Điều này có thể giúp đảm bảo an toàn cho ví của bạn và ngăn ngừa các vấn đề tiếp theo," tiếp tục Trust Wallet trong cùng một chuỗi X [thread](https://x.com/TrustWallet/status/2004355490734919980).

"Thực hiện theo hướng dẫn từng bước càng sớm càng tốt:  
  
Bước 1: KHÔNG mở Trust Wallet Browser Extension trên thiết bị desktop để đảm bảo an toàn cho ví của bạn và ngăn ngừa các vấn đề tiếp theo.  
  
Bước 2: Vào bảng Chrome Extensions trong trình duyệt Chrome của bạn bằng cách sao chép dòng sau vào thanh địa chỉ (lối tắt đến Trust Wallet Browser Extension chính thức): chrome://extensions/?id=egjidjbpglichdcondbcbdnbeeppgdph  
  
Bước 3: Chuyển công tắc sang "Off" bên dưới Trust Wallet nếu nó đang ở "On".  
  
Bước 4: Nhấp "Developer mode" ở góc phải trên.  
  
Bước 5: Nhấn "Update" ở góc trên bên trái.  
  
Bước 6. Kiểm tra số phiên bản: 2.69. Đây là phiên bản mới nhất và an toàn.  

"Đội Hỗ trợ Khách hàng của chúng tôi đã liên hệ với người dùng bị ảnh hưởng về các bước tiếp theo," [nói](https://x.com/TrustWallet/status/2004340002776555742) Trust Wallet, và khuyến khích những người khác có thắc mắc liên hệ tại: [https://twtholders.trustwallet.com](https://twtholders.trustwallet.com/)

Người dùng tin rằng ví của họ có thể đã bị xâm phạm được khuyến cáo ngay lập tức chuyển phần tiền còn lại sang ví mới tạo bằng seed phrase mới và coi bất kỳ cụm phục hồi (recovery phrase) nào từng bị lộ là không an toàn vĩnh viễn.