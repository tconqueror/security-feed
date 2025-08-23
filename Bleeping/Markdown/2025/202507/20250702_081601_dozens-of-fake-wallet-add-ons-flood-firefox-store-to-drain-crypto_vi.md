# Hàng chục tiện ích giả mạo ví tràn ngập cửa hàng Firefox để đánh cắp crypto

![Hàng chục tiện ích giả mạo ví tràn ngập cửa hàng Firefox để đánh cắp crypto](https://www.bleepstatic.com/content/hl-images/2024/03/22/Firefox-headpic.jpg)

Hơn 40 tiện ích giả mạo trong cửa hàng tiện ích chính thức của Firefox đang giả dạng ví cryptocurrency phổ biến từ các nhà cung cấp đáng tin cậy để đánh cắp thông tin đăng nhập ví và dữ liệu nhạy cảm.

Một số tiện ích này giả làm ví từ Coinbase, MetaMask, Trust Wallet, Phantom, Exodus, OKX, Keplr và MyMonero, và bao gồm mã độc gửi thông tin bị đánh cắp đến các máy chủ do kẻ tấn công kiểm soát.

![Tiện ích ví giả](https://www.bleepstatic.com/images/news/u/1220909/2025/June/ext2.jpg)

**Tiện ích ví giả trên cửa hàng tiện ích Firefox**  
_Nguồn: BleepingComputer_

Các nhà nghiên cứu từ Koi security đã phát hiện ra các tiện ích rủi ro này cùng với bằng chứng cho thấy rằng đứng sau chiến dịch này là một nhóm mối đe dọa nói tiếng Nga.

Trong một [báo cáo](https://blog.koi.security/foxywallet-40-malicious-firefox-extensions-exposed-4c14419de486) được chia sẻ với BleepingComputer, các nhà nghiên cứu cho biết nhiều tiện ích mở rộng trình duyệt này là bản sao của các phiên bản mã nguồn mở của các ví hợp pháp với logic độc hại được thêm vào.

Koi security đưa ra các ví dụ về các trình lắng nghe sự kiện 'input' và 'click' trong mã, theo dõi các dữ liệu nhạy cảm được nhập từ nạn nhân.

![Mã độc trong các tiện ích](https://www.bleepstatic.com/images/news/u/1220909/2025/June/1.jpg)

**Mã độc trong các tiện ích**  
_Nguồn: Koi Security_

Mã kiểm tra các chuỗi đầu vào dài hơn 30 ký tự để lọc các khóa/địa chỉ ví hợp lý, và thu thập dữ liệu cho kẻ tấn công.

Các hộp thoại lỗi bị ẩn khỏi người dùng bằng cách đặt độ mờ thành 0 cho bất kỳ phần tử nào có thể cảnh báo người dùng về hoạt động này.

Seed phrases (cụm từ khôi phục/nhớ) là khóa chính thường gồm nhiều từ, cho phép người dùng khôi phục hoặc chuyển ví sang thiết bị mới.

Lấy được cụm từ seed của ai đó sẽ cho phép đánh cắp tất cả tài sản cryptocurrency trong ví. Việc đánh cắp này xuất hiện như một giao dịch hợp lệ và không thể đảo ngược.

Chiến dịch đã hoạt động từ ít nhất tháng Tư và các tiện ích mới dường như liên tục được thêm vào cửa hàng Firefox. Các nhà nghiên cứu cho biết các mục độc hại mới nhất gần đây nhất là vào cuối tuần trước.

Để xây dựng lòng tin, kẻ tấn công sử dụng logo thật của các thương hiệu mà họ giả mạo và nhiều tiện ích có hàng trăm đánh giá năm sao giả. Một số trong số đó cũng có một số lượng lớn đánh giá một sao báo cáo về lừa đảo, có khả năng từ những người dùng đã mất cryptocurrency của họ.

**Tiện ích giả Metamask trên cửa hàng Firefox**  
_Nguồn: BleepingComputer_

Mặc dù hầu hết các đánh giá của người dùng rõ ràng là giả (chúng vượt xa con số cài đặt), nhưng nhiều người dùng không chú ý đến chi tiết vẫn có thể bị lừa cài đặt chúng và rủi ro cụm từ seed của họ bị đánh cắp.

Mozilla đã phát triển một [hệ thống phát hiện sớm cho các tiện ích lừa đảo crypto](https://www.bleepingcomputer.com/news/security/mozilla-launches-new-system-to-detect-firefox-crypto-drainer-add-ons/). Nó dựa vào các chỉ số tự động để đánh giá mức độ rủi ro. Nếu một ngưỡng nhất định được đạt tới, các nhà đánh giá con người sẽ phân tích bản đăng ký và chặn nếu nó độc hại.

Koi Security đã thông báo cho BleepingComputer rằng họ đã báo cáo các phát hiện này tới cửa hàng Firefox bằng công cụ báo cáo chính thức, nhưng các tiện ích giả vẫn tiếp tục có sẵn tại thời điểm viết bài.

BleepingComputer đã liên hệ với Mozilla để xin bình luận về vấn đề này nhưng một tuyên bố không ngay lập tức có sẵn.