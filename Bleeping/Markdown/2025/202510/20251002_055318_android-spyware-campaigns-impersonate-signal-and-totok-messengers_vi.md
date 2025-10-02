# Chiến dịch phần mềm gián điệp Android mạo danh Signal và ToTok

![Chiến dịch phần mềm gián điệp Android mạo danh Signal và ToTok](https://www.bleepstatic.com/content/hl-images/2024/01/12/android-eyes.jpg)

Hai chiến dịch phần mềm gián điệp mới mà các nhà nghiên cứu gọi là ProSpy và ToSpy đã dụ dỗ người dùng Android bằng các bản nâng cấp hoặc plugin giả cho các ứng dụng nhắn tin Signal và ToTok để đánh cắp dữ liệu nhạy cảm.

Để tạo cảm giác hợp pháp cho các tệp độc hại, tác nhân đe dọa đã phân phối chúng thông qua các trang web mạo danh hai nền tảng liên lạc đó.

Signal là một ứng dụng nhắn tin mã hóa đầu cuối phổ biến với hơn 100 triệu lượt tải xuống trên Google Play.

ToTok được phát triển bởi công ty trí tuệ nhân tạo có trụ sở tại UAE, G42, và đã bị loại khỏi cửa hàng ứng dụng của Apple và Google vào năm 2019 sau những cáo buộc là công cụ do thám cho chính phủ UAE.

Hiện tại, ToTok có sẵn để tải xuống từ trang web chính thức và các cửa hàng ứng dụng bên thứ ba.

### Ẩn mình và duy trì

Các nhà nghiên cứu tại công ty an ninh mạng ESET đã phát hiện chiến dịch ProSpy vào tháng sáu nhưng họ tin rằng hoạt động có thể đã bắt đầu ít nhất từ năm 2024. Dựa trên phân tích của họ, các chiến dịch độc hại đang nhắm mục tiêu người dùng ở United Arab Emirates.

Trong quá trình điều tra, họ phát hiện "hai họ phần mềm gián điệp chưa được tài liệu hóa" giả danh Signal Encryption Plugin và một biến thể Pro của ứng dụng ToTok, none of which exist.

Kẻ điều hành chiến dịch phần mềm gián điệp đã phân phối các tệp APK độc hại thông qua các trang web mạo danh trang web chính thức của Signal (_https://signal.ct\[.\]ws_ và _https://encryption-plug-in-signal.com-ae\[.\]net/_) và Samsung Galaxy Store (_store.latestversion\[.\]ai_ và _https://store.appupdate\[.\]ai_).

![Trang web plugin Signal giả](https://www.bleepstatic.com/images/news/u/1220909/2025/October/signal-site.jpg)

**Trang web plugin Signal giả**  
_Nguồn: ESET_

BleepingComputer đã cố gắng truy cập các trang web lừa đảo nhưng hầu hết trong số chúng đã ngừng hoạt động và một trang chuyển hướng đến trang web chính thức của ToTok.

Khi được thực thi, các mẫu phần mềm độc hại ProSpy yêu cầu quyền truy cập vào danh bạ, SMS và tệp, đây là các quyền điển hình đối với các ứng dụng nhắn tin.

Khi hoạt động trên thiết bị, phần mềm độc hại trích xuất các dữ liệu sau:

* thông tin thiết bị (phần cứng, hệ điều hành, địa chỉ IP)
* tin nhắn SMS đã lưu, danh bạ
* tệp (âm thanh, tài liệu, hình ảnh, video)
* tệp sao lưu ToTok
* danh sách các ứng dụng đã cài đặt

Để ẩn mình, Signal Encryption Plugin sử dụng biểu tượng và nhãn 'Play Services' trên màn hình chính. Hơn nữa, khi chạm vào biểu tượng, màn hình thông tin của một ứng dụng Google Play Service hợp pháp sẽ mở ra.

Sơ đồ dưới đây giải thích cách một cuộc xâm nhập ProSpy hoạt động. Tác nhân đe dọa đã nỗ lực để tránh làm người dùng nghi ngờ bằng cách chuyển hướng họ đến trang tải xuống chính thức khi ứng dụng hợp pháp không có trên thiết bị.

![The ProSpy execution flow](https://www.bleepstatic.com/images/news/u/1220909/2025/October/prospy.jpg)

**The ProSpy execution flow**  
_Nguồn: ESET_

### Chiến dịch ToSpy có thể bắt nguồn từ 2022

Theo các nhà nghiên cứu, chiến dịch ToSpy vẫn đang tiếp diễn, dựa trên trạng thái hoạt động của cơ sở hạ tầng command-and-control (C2).

ESET lưu ý rằng hoạt động này có thể lùi về tận năm 2022, vì họ tìm thấy nhiều chỉ báo trỏ tới giai đoạn đó: một chứng chỉ nhà phát triển được tạo vào ngày 24 tháng 5 năm 2022, một tên miền được sử dụng để phân phối và làm C2 đăng ký vào ngày 18 tháng 5 cùng năm, và các mẫu được tải lên nền tảng quét VirusTotal vào ngày 30 tháng 6.

![Trang Galaxy Store giả](https://www.bleepstatic.com/images/news/u/1220909/2025/October/prospy.jpg)

**Trang Galaxy Store giả**  
_Nguồn: ESET_

Ứng dụng ToTok giả được phân phối trong chiến dịch này yêu cầu nạn nhân cấp quyền truy cập danh bạ và bộ nhớ, và thu thập dữ liệu liên quan, tập trung vào tài liệu, hình ảnh, video và bản sao lưu trò chuyện ToTok (.ttkmbackup files).

Báo cáo của ESET lưu ý rằng tất cả dữ liệu bị trích xuất đều được mã hóa trước bằng thuật toán mã hóa đối xứng AES ở chế độ CBC.

Để ẩn mình, ToSpy khởi chạy ứng dụng ToTok thật khi được mở, nếu nó có trên thiết bị.

Nếu ứng dụng không có, phần mềm độc hại cố gắng mở Huawei AppGallery (hoặc ứng dụng hợp pháp hoặc trình duyệt web mặc định) để người dùng có thể tải ứng dụng ToTok chính thức.

**The ToSpy execution flow**  
_Nguồn: ESET_

Cả hai họ phần mềm gián điệp đều sử dụng ba cơ chế duy trì trên các thiết bị bị nhiễm:

* Lạm dụng API hệ thống Android 'AlarmManager' để tự khởi động lại nếu bị đóng.
* Sử dụng một foreground service với thông báo liên tục để hệ thống coi nó là tiến trình ưu tiên cao.
* Đăng ký nhận sự kiện BOOT_COMPLETED để có thể khởi động lại phần mềm gián điệp khi thiết bị khởi động lại mà không cần tương tác của người dùng.

ESET đã chia sẻ danh sách toàn diện các [indicators of compromise](https://github.com/eset/malware-ioc/tree/master/prospytospy) (IoCs) liên quan đến các chiến dịch ProSpy và ToSpy, nhưng việc xác định trách nhiệm vẫn chưa kết luận được.

Người dùng Android được khuyến nghị chỉ tải ứng dụng từ các kho chính thức hoặc tin cậy, hoặc trực tiếp từ trang web của nhà phát hành. Họ nên giữ dịch vụ Play Protect ở trạng thái hoạt động trên thiết bị để vô hiệu hóa các mối đe dọa đã biết.