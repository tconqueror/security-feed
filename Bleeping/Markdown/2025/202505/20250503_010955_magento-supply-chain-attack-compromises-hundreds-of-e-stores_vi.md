# Cuộc tấn công chuỗi cung ứng Magento làm lộ hàng trăm cửa hàng điện tử

![Magecart](https://www.bleepstatic.com/content/hl-images/2023/10/09/magecart.jpg)

Một cuộc tấn công chuỗi cung ứng liên quan đến 21 tiện ích mở rộng Magento đã làm lộ từ 500 đến 1.000 cửa hàng thương mại điện tử, bao gồm một cửa hàng thuộc về một tập đoàn đa quốc gia trị giá 40 tỷ USD.

Các nhà nghiên cứu của Sansec, người phát hiện ra cuộc tấn công, báo cáo rằng một số tiện ích mở rộng đã bị cài đặt backdoor từ tận năm 2019, nhưng mã độc chỉ được kích hoạt vào tháng 4 năm 2025.

"Nhiều nhà cung cấp đã bị hack trong một cuộc tấn công chuỗi cung ứng phối hợp, Sansec đã phát hiện ra 21 ứng dụng có cùng một backdoor," [Sansec giải thích](http://sansec.io/research/license-backdoor).

"Thật kỳ lạ, malware đã được chèn vào cách đây 6 năm, nhưng chỉ mới hoạt động tuần này khi kẻ tấn công chiếm quyền kiểm soát hoàn toàn các máy chủ thương mại điện tử."

Sansec cho biết các tiện ích mở rộng bị xâm phạm đến từ các nhà cung cấp Tigren, Meetanshi và MGS:

* Tigren Ajaxsuite
* Tigren Ajaxcart
* Tigren Ajaxlogin
* Tigren Ajaxcompare
* Tigren Ajaxwishlist
* Tigren MultiCOD
* Meetanshi ImageClean
* Meetanshi CookieNotice
* Meetanshi Flatshipping
* Meetanshi FacebookChat
* Meetanshi CurrencySwitcher
* Meetanshi DeferJS
* MGS Lookbook
* MGS StoreLocator
* MGS Brand
* MGS GDPR
* MGS Portfolio
* MGS Popup
* MGS DeliveryTime
* MGS ProductTabs
* MGS Blog

Sansec cũng đã phát hiện một phiên bản bị xâm phạm của tiện ích mở rộng Weltpixel GoogleTagManager nhưng không thể xác nhận liệu điểm xâm phạm nằm ở nhà cung cấp hay trang web.

Trong tất cả các trường hợp quan sát, các tiện ích mở rộng bao gồm một backdoor PHP được thêm vào một tệp kiểm tra giấy phép (License.php hoặc LicenseApi.php) mà tiện ích mở rộng sử dụng.

![Kiểm tra yêu cầu HTTP cho xác thực hợp lệ dựa trên khóa mã hóa](https://www.bleepstatic.com/images/news/security/m/magento/extension-backdoor/admin-check.png)

**Kiểm tra yêu cầu HTTP cho xác thực hợp lệ dựa trên khóa mã hóa**  
_Nguồn: BleepingComputer_

Nếu kiểm tra thành công, backdoor sẽ cho phép truy cập vào các chức năng quản trị khác trong tệp, bao gồm một chức năng cho phép người dùng từ xa tải lên một giấy phép mới và lưu nó dưới dạng tệp.

![Chạy một chức năng quản trị được chỉ định trong yêu cầu HTTP](https://www.bleepstatic.com/images/news/security/m/magento/extension-backdoor/check-license.png)

**Chạy một chức năng quản trị được chỉ định trong yêu cầu HTTP**  
_Nguồn: BleepingComputer_

Tệp này sau đó được bao gồm bằng cách sử dụng hàm PHP “include\_once()”, hàm này tải tệp và tự động thực thi bất kỳ mã nào bên trong tệp giấy phép đã tải lên.

**Hàm mà thực thi mã trong tệp được tải lên**  
_Nguồn: BleepingComputer_

Các phiên bản trước của backdoor không yêu cầu xác thực, nhưng các phiên bản mới hơn sử dụng một khóa mã hóa cứng.

Sansec đã cho BleepingComputer biết rằng backdoor này đã được sử dụng để tải lên một webshell đến một trong những trang web của khách hàng của họ.

Với khả năng tải lên và chạy bất kỳ mã PHP nào, những hậu quả tiềm tàng của cuộc tấn công bao gồm đánh cắp dữ liệu, chèn skimmer, tạo tài khoản quản trị tùy ý và nhiều hơn nữa.

Sansec đã liên hệ với ba nhà cung cấp, cảnh báo họ về backdoor đã phát hiện. Công ty an ninh mạng cho biết MGS không phản hồi, Tigren phủ nhận bị xâm phạm và tiếp tục phân phối các tiện ích mở rộng có backdoor, và Meetanshi thừa nhận đã xảy ra rò rỉ máy chủ nhưng không xác nhận việc xâm phạm tiện ích mở rộng.

BleepingComputer đã xác nhận độc lập rằng backdoor này xuất hiện trong tiện ích mở rộng MGS StoreLocator, có thể tải về miễn phí từ trang web của họ. Chúng tôi chưa xác nhận liệu backdoor có tồn tại trong các tiện ích mở rộng khác được Sansec báo cáo hay không.

Người dùng của các tiện ích mở rộng được đề cập được khuyến nghị thực hiện quét máy chủ hoàn toàn để tìm các chỉ số xâm phạm mà Sansec đã chia sẻ trong báo cáo của họ và, nếu có thể, khôi phục trang web từ một bản sao lưu sạch đã biết.

Sansec đã bình luận về sự kỳ lạ của backdoor khi nằm im trong sáu năm và chỉ kích hoạt giờ đây và hứa hẹn sẽ cung cấp thêm thông tin từ cuộc điều tra đang diễn ra của họ.

BleepingComputer đã liên hệ với ba nhà cung cấp, nhưng chưa nhận được phản hồi tại thời điểm này.