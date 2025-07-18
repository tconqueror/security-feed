# Trình giải mã Phobos ransomware mới cho phép nạn nhân khôi phục tệp miễn phí

![Đôi tay cầm chìa khóa mạng](https://www.bleepstatic.com/content/hl-images/2022/10/09/cyber-key.jpg)

Cảnh sát Nhật Bản đã phát hành một trình giải mã cho Phobos và 8-Base ransomware, cho phép nạn nhân khôi phục tệp của họ miễn phí, với BleepingComputer xác nhận rằng nó giải mã tệp một cách thành công.

Phobos là một hoạt động ransomware-as-a-service được ra mắt vào tháng 12 năm 2018, cho phép các tác nhân đe dọa khác tham gia với vai trò là đối tác và sử dụng công cụ mã hóa của họ trong các cuộc tấn công. Đổi lại, bất kỳ khoản thanh toán nào cho tiền chuộc sẽ được chia sẻ giữa đối tác và các nhà điều hành.

Mặc dù hoạt động ransomware này không nhận được nhiều sự chú ý từ giới truyền thông như các hoạt động ransomware khác, Phobos được coi là một trong những hoạt động ransomware phân phối rộng rãi nhất, chịu trách nhiệm cho nhiều cuộc tấn công vào các doanh nghiệp trên toàn thế giới.

Năm 2023, một nhóm đối tác [đã ra mắt hoạt động 8-Base](https://www.bleepingcomputer.com/news/security/8base-ransomware-gang-escalates-double-extortion-attacks-in-june/) sử dụng một trình mã hóa Phobos đã được sửa đổi. Khác với các đối tác khác, nhóm này đã thực hiện extortion kép, trong đó họ mã hóa tệp và lấy cắp dữ liệu, đe dọa sẽ phát hành nếu không thanh toán tiền chuộc.

Năm 2024, một công dân Nga nghi ngờ là quản trị viên của hoạt động ransomware Phobos đã được [truy nã từ Hàn Quốc sang Hoa Kỳ](https://www.bleepingcomputer.com/news/security/us-charges-phobos-ransomware-admin-after-south-korea-extradition/) để đối mặt với các cáo buộc trong một bản cáo trạng 13 tội danh.

Năm nay, hoạt động [Phobos đã chịu một cú sốc lớn](https://www.bleepingcomputer.com/news/security/us-indicts-8base-ransomware-operators-for-phobos-encryption-attacks/), với một chiến dịch thực thi pháp luật quốc tế phối hợp nhằm bắt giữ và tịch thu 27 máy chủ. Phần của hoạt động này, bốn công dân Nga nghi ngờ là lãnh đạo nhóm ransomware 8Base đã bị bắt.

## Trình giải mã Phobos miễn phí

Cảnh sát Nhật Bản hiện đã phát hành một trình giải mã miễn phí cho các tổ chức và người có tệp bị mã hóa bởi các hoạt động ransomware Phobos và 8Base.

Mặc dù chưa rõ cách họ có thể tạo ra trình giải mã, nhưng nhiều người tin rằng điều này đã thành công nhờ thông tin thu thập được trong đợt gián đoạn hoạt động của băng nhóm ransomware trong năm nay.

Trình giải mã có thể được tải xuống từ [trang web của cảnh sát Nhật Bản](https://www.npa.go.jp/english/bureau/cyber/ransomdamagerecovery.html), với [hướng dẫn được chia sẻ bằng tiếng Anh](https://www.npa.go.jp/english/bureau/cyber/document/PhDec%5FGuideLine%5Fver1.0%5FEN.pdf). Trình giải mã cũng có sẵn trên nền tảng [NoMoreRansom](https://www.nomoreransom.org/en/decryption-tools.html) của Europol và được quảng bá bởi [Europol](https://x.com/EC3Europol/status/1945740250338185378) và [FBI](https://x.com/FBIBaltimore/status/1945896850965291036) để chứng minh tình trạng chính thức của nó.

Cần lưu ý rằng các trình duyệt web, bao gồm Google Chrome và Mozilla Firefox, đang phát hiện trình giải mã như phần mềm độc hại, khiến việc tải xuống và sử dụng khó khăn. Tuy nhiên, BleepingComputer đã thử nghiệm trình giải mã và không chỉ nó không độc hại mà còn giải mã thành công các tệp đã được mã hóa từ các trình mã hóa gần đây.

Trình giải mã hiện hỗ trợ các tệp đã được mã hóa với các phần mở rộng sau: "**.phobos**", "**.8base**", "**.elbie**", "**.faust**" và "**.LIZARD**".

Tuy nhiên, cảnh sát Nhật Bản cho biết một số phần mở rộng khác có thể được hỗ trợ, vì vậy bạn nên thử nghiệm trình giải mã ngay cả khi tệp của bạn không có những phần mở rộng được liệt kê.

Trong một thử nghiệm, BleepingComputer đã lây nhiễm một máy ảo bằng một biến thể ransomware Phobos gần đây thêm phần mở rộng **.LIZARD** vào tên tệp đã mã hóa, như được hiển thị dưới đây.

![Các tệp được mã hóa bởi biến thể ransomware Phobos "Lizard"](https://www.bleepstatic.com/images/news/ransomware/p/phobos/decryptor/encrypted-files.jpg)

**Các tệp được mã hóa bởi biến thể ransomware Phobos "Lizard"**  
_Nguồn: BleepingComputer_

Để giải mã tệp, khởi động trình giải mã và đồng ý với thỏa thuận cấp phép của nó. Nếu Windows không được cấu hình để hỗ trợ tên tệp dài, nó sẽ yêu cầu bạn cho phép nó kích hoạt cài đặt này và sau đó yêu cầu bạn khởi động lại trình giải mã.

Sau khi khởi động, bạn có thể chỉ định một đường dẫn đến các tệp bị mã hóa của mình và sau đó chọn một thư mục đầu ra nơi các tệp đã được giải mã sẽ được tạo ra. Khi sẵn sàng, nhấp vào nút **Giải mã** và trình giải mã sẽ cố gắng khôi phục các tệp của bạn vào thư mục đã chọn.

Cần lưu ý rằng bạn có thể chọn gốc của một ổ đĩa, và trình giải mã sẽ giải mã đệ quy các tệp, tái tạo cùng cấu trúc thư mục trong thư mục đích.

Khi hoàn tất, trình giải mã sẽ hiển thị số lượng tệp đã được giải mã thành công.

![Trình giải mã giải mã thành công tất cả các tệp trong thư mục](https://www.bleepstatic.com/images/news/ransomware/p/phobos/decryptor/decrypted-files-2.jpg)

**Trình giải mã giải mã thành công tất cả các tệp trong thư mục**  
_Nguồn: BleepingComputer_

BleepingComputer có thể xác nhận rằng trình giải mã đã giải mã thành công tất cả 150 tệp được mã hóa bởi biến thể LIZARD của ransomware Phobos.

**Tệp đã được giải mã**  
_Nguồn: BleepingComputer_

Các nạn nhân của Phobos và 8Base ransomware nên thử trình giải mã này, ngay cả khi tệp đã được mã hóa của họ không có một trong các phần mở rộng được liệt kê, vì nó vẫn có thể hoạt động.