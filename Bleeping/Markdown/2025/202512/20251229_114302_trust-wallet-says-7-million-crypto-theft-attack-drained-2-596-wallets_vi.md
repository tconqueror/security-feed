# Trust Wallet thông báo 2,596 ví bị rút sạch trong vụ đánh cắp tiền điện tử trị giá 7 triệu USD

![Trust Wallet](https://www.bleepstatic.com/content/hl-images/2025/12/29/Trust-Wallet.jpg)

Trust Wallet cho biết các kẻ tấn công đã xâm phạm phần mở rộng trình duyệt của họ ngay trước lễ Giáng Sinh và đã rút khoảng 7 triệu USD từ gần 3.000 địa chỉ ví tiền điện tử.

Ví tiền điện tử (được hơn 200 triệu người sử dụng theo trang web chính thức của nó) cho phép người dùng lưu trữ, gửi, nhận và quản lý Bitcoin, Ethereum, Solana và hàng nghìn loại tiền điện tử và token kỹ thuật số khác bằng phần mở rộng trình duyệt và ứng dụng di động iOS và Android miễn phí.

Trust Wallet ra mắt vào năm 2017 và được Binance mua lại vào năm sau đó. Mặc dù vậy, nó vẫn hoạt động như một ứng dụng ví riêng biệt, phi tập trung.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Như BleepingComputer đã đưa tin đầu tiên, sự cố ngày 24 tháng 12 đã dẫn đến việc khoảng 7 triệu USD bị đánh cắp từ các ví bị xâm phạm sau khi phiên bản 2.68.0 của phần mở rộng Chrome bị tấn công, với việc các kẻ tấn công thêm một tệp JavaScript độc hại để trích xuất dữ liệu ví nhạy cảm.

Trust Wallet đã xác nhận vụ hack sau khi BleepingComputer liên hệ để xác minh và khuyên người dùng ngay lập tức cập nhật lên phiên bản 2.69 để chặn các nỗ lực đánh cắp tiền điện tử tiếp theo.

"Phiên bản phần mở rộng độc hại v2.68 KHÔNG được phát hành thông qua quy trình thủ công nội bộ của chúng tôi. Những phát hiện hiện tại cho thấy có khả năng nó đã được phát hành từ bên ngoài thông qua Chrome Web Store API key, vượt qua các kiểm tra phát hành tiêu chuẩn của chúng tôi," CEO Eowyn Chen giải thích.

"Một giả thuyết đang được làm việc (vẫn đang điều tra): Hacker đã sử dụng một Chrome Web Store API key bị rò rỉ để gửi phiên bản phần mở rộng độc hại v2.68\. Điều này đã vượt qua quy trình rà soát của Chrome Web Store và được phát hành vào ngày Dec 24, 2025 lúc 12:32 UTC."

Để ứng phó với sự cố, Trust Wallet đã hết hạn tất cả các API phát hành để chặn mọi cố gắng phát hành phiên bản mới trong hai tuần tới. Họ cũng đảm bảo rằng kẻ tấn công không thể đánh cắp thêm dữ liệu ví bằng cách báo cáo tên miền trích xuất độc hại cho NiceNIC, nhà đăng ký, và tên miền này đã bị đình chỉ ngay lập tức.

Tuy nhiên, như BleepingComputer phát hiện, các kẻ tấn công đã tăng cường nỗ lực, triển khai một chiến dịch lừa đảo lợi dụng hoảng loạn diễn ra, sử dụng một trang web mạo danh Trust Wallet và yêu cầu người dùng cung cấp cụm phục hồi (seed phrase) ví của họ để nhận "một bản cập nhật quan trọng đã lên lịch với các cải tiến bảo mật."

![Malicious fix-trustwallet[.]com domain (BleepingComputer)](https://www.bleepstatic.com/images/news/u/1164866/2025/Dec/trust-wallet-chrome/fix-trustwallet-1.jpg)

_Malicious fix-trustwallet[.]com domain (BleepingComputer)_

## Hàng nghìn ví tiền điện tử bị rút sạch

Kể từ đó, Trust Wallet đã tiết lộ rằng các kẻ tấn công đã đánh cắp tiền điện tử từ gần 3.000 ví và cho biết họ dự định hoàn trả cho tất cả người dùng bị ảnh hưởng.

"Cho đến nay, chúng tôi đã xác định 2,596 địa chỉ ví bị ảnh hưởng. Từ nhóm này, chúng tôi đã nhận khoảng 5,000 yêu cầu bồi thường cho thấy có một số lượng lớn các gửi yêu cầu giả hoặc gửi trùng lặp cố gắng truy cập bồi thường của nạn nhân," Chen bổ sung vào thứ Hai.

"Vì lý do này, việc xác minh chính xác quyền sở hữu ví là rất quan trọng để đảm bảo tiền được trả lại cho đúng người. Nhóm của chúng tôi đang làm việc chăm chỉ để xác minh các yêu cầu; kết hợp nhiều điểm dữ liệu để phân biệt nạn nhân hợp lệ với các tác nhân độc hại."

Cùng lúc với cuộc điều tra, Trust Wallet cũng đã bắt đầu hoàn trả cho người dùng bị ảnh hưởng, yêu cầu họ gửi thông tin liên hệ, các địa chỉ ví bị xâm phạm, địa chỉ của hacker và các hash giao dịch rút tiền từ ví trên một biểu mẫu yêu cầu bồi thường chuyên dụng, đồng thời cảnh báo họ không chia sẻ "bất kỳ private keys, seed phrases, hoặc mật khẩu nào."

"Để bắt đầu quy trình bồi thường, người dùng bị ảnh hưởng vui lòng hoàn thành biểu mẫu này: https://be-support.trustwallet.com để giúp chúng tôi xử lý trường hợp của bạn. Nhóm hỗ trợ của chúng tôi đang ưu tiên tất cả các nạn nhân từ sự cố và đã bắt đầu xem xét các gửi yêu cầu," họ nói.

"Chúng tôi xin lỗi và thừa nhận rằng tình huống này đã gây phiền toái và gián đoạn. Chúng tôi đang làm việc suốt ngày đêm để hoàn tất chi tiết quy trình bồi thường và mỗi trường hợp đều cần được xác minh cẩn thận để đảm bảo chính xác và an toàn."

Công ty cảnh báo người dùng rằng các tác nhân đe dọa hiện đang mạo danh các tài khoản hỗ trợ, chạy lừa đảo qua quảng cáo Telegram và đẩy các biểu mẫu bồi thường giả.

Trust Wallet cũng cảnh báo người dùng luôn xác minh các liên kết, không bao giờ chia sẻ cụm phục hồi của họ và chỉ sử dụng các kênh liên lạc chính thức của Trust Wallet.