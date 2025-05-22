+-
# Tin tặc sử dụng các ứng dụng Ledger giả để đánh cắp seed phrases của người dùng Mac

![Tin tặc sử dụng các ứng dụng Ledger giả để đánh cắp seed phrases của người dùng Mac](https://www.bleepstatic.com/content/hl-images/2023/12/14/blocks-1.jpg)

Các chiến dịch tội phạm mạng đang sử dụng các ứng dụng Ledger giả để nhắm đến người dùng macOS và tài sản kỹ thuật số của họ bằng cách triển khai phần mềm độc hại nhằm đánh cắp seed phrases bảo vệ quyền truy cập vào ví tiền điện tử kỹ thuật số.

Ledger là một ví phần cứng phổ biến được thiết kế để lưu trữ tiền điện tử ngoại tuyến (cold storage) và theo cách an toàn.

Một seed hoặc phrases phục hồi là một tập hợp 12 hoặc 24 từ ngẫu nhiên cho phép khôi phục tài sản kỹ thuật số nếu ví bị mất hoặc mật khẩu truy cập bị quên. Do đó, nó được dự định lưu trữ một cách ngoại tuyến và riêng tư.

Trong các cuộc tấn công như vậy được nêu bật trong một [báo cáo của Moonlock Lab](https://moonlock.com/anti-ledger-malware), ứng dụng độc hại giả mạo ứng dụng Ledger nhằm đánh lừa người dùng nhập seed phrase của họ vào một trang lừa đảo.

Moonlock Lab cho biết họ đã theo dõi những cuộc tấn công này kể từ tháng 8 năm 2024, khi các ứng dụng clone chỉ có thể "đánh cắp mật khẩu, ghi chú và chi tiết ví để có cái nhìn về tài sản của ví." Thông tin này sẽ không đủ để truy cập vào các quỹ, mặc dù vậy.

Với bản cập nhật gần đây tập trung vào việc đánh cắp seed phrase, tội phạm mạng có thể làm rỗng ví của các nạn nhân.

## Sự phát triển của các chiến dịch Ledger

Vào tháng 3, Moonlock Lab đã phát hiện ra một tác nhân đe dọa sử dụng bí danh 'Rodrigo' triển khai một phần mềm đánh cắp mới trên macOS có tên 'Odyssey.'

Phần mềm độc hại mới thay thế ứng dụng Ledger Live hợp pháp trên thiết bị của nạn nhân để làm cho cuộc tấn công hiệu quả hơn.

Phần mềm độc hại đã nhúng một trang lừa đảo bên trong một ứng dụng Ledger giả mạo yêu cầu nạn nhân nhập seed phrase 24 từ của họ để khôi phục tài khoản sau khi hiển thị một thông báo "lỗi nghiêm trọng" giả mạo.

![Trang lừa đảo seed phrase](https://www.bleepstatic.com/images/news/u/1220909/2025/May/phishing.jpg)

**Trang lừa đảo seed phrase**  
_Nguồn: Moonlock Lab_

Odyssey cũng có thể đánh cắp tên người dùng macOS và xuất tất cả dữ liệu được cung cấp thông qua các trường lừa đảo tới máy chủ chỉ huy và kiểm soát (C2) của Rodrigo.

Tính hiệu quả của mảnh phần mềm độc hại mới này nhanh chóng thu hút sự chú ý trên các diễn đàn ngầm, dẫn đến các cuộc tấn công bắt chước bởi phần mềm AMOS đã triển khai các tính năng tương tự.

Tháng trước, một chiến dịch AMOS mới đã được xác định sử dụng một tệp DMG có tên 'JandiInstaller.dmg,' vượt qua Gatekeeper để cài đặt một ứng dụng clone Ledger Live đã bị trojan hóa hiển thị các màn hình lừa đảo kiểu Rodrigo.

![AMOS giả mạo terminal của Apple](https://www.bleepstatic.com/images/news/u/1220909/2025/May/amos.jpg)

**Thông báo cài đặt phần mềm độc hại AMOS**  
_Nguồn: Moonlock Lab_

Các nạn nhân bị rơi vào mẹo và nhập seed phrase 24 từ của họ vào AMOS nhận được thông điệp "Ứng dụng bị hỏng" lừa dối để giảm sự nghi ngờ và cho phép các kẻ tấn công đủ thời gian để lấy cắp tài sản.

Khoảng cùng lúc đó, một tác nhân đe dọa riêng biệt sử dụng tài khoản '@mentalpositive' đã bắt đầu quảng cáo một module "chống Ledger" trên các diễn đàn dark web, mặc dù Moonlock không thể tìm thấy các phiên bản hoạt động của nó.

Tháng này, các nhà nghiên cứu tại Jamf, một công ty cung cấp phần mềm cho các tổ chức để quản lý thiết bị Apple, [đã phát hiện](https://www.jamf.com/blog/pyinstaller-malware-jamf-threat-labs/) một chiến dịch khác mà trong đó một nhị phân Packaged bằng PyInstaller trong tệp DMG đã tải một trang lừa đảo được tải qua iframe trong giao diện giả mạo Ledger Live để đánh cắp seed phrases của người dùng.

Tương tự như chiến dịch đánh cắp AMOS, các cuộc tấn công mà Jamf phát hiện theo một cách tiếp cận lai, nhắm mục tiêu dữ liệu duyệt web, cấu hình ví "nóng", và thông tin hệ thống song song với các cuộc lừa đảo nhắm vào Ledger.

**Mã của ứng dụng phần mềm độc hại**  
_Nguồn: Moonlock Lab_

Để giữ cho ví Ledger của bạn an toàn, chỉ tải ứng dụng Ledger Live từ trang web chính thức và luôn kiểm tra trước khi nhập seed phrase của bạn, điều này chỉ nên xảy ra khi mất quyền truy cập vào ví vật lý.

Bạn chỉ cần sử dụng seed phrase khi bạn phục hồi ví của mình hoặc thiết lập thiết bị mới. Ngay cả trong trường hợp đó, cụm từ được nhập trên thiết bị Ledger vật lý, chứ không phải trên ứng dụng hoặc bất kỳ trang web nào.