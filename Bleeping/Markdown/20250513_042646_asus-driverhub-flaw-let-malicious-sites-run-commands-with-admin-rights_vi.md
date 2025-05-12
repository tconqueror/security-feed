# Lỗ hổng DriverHub của ASUS cho phép các trang web độc hại thực thi lệnh với quyền admin

![ASUS](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

Tiện ích quản lý driver ASUS DriverHub đã bị lỗ hổng thực thi mã từ xa nghiêm trọng cho phép các trang web độc hại thực thi lệnh trên các thiết bị có phần mềm này được cài đặt.

Lỗ hổng này được phát hiện bởi một nhà nghiên cứu an ninh mạng độc lập từ New Zealand có tên là Paul (có biệt danh là "[MrBruh](https://mrbruh.com/asusdriverhub/)"), người đã phát hiện ra rằng phần mềm này có xác thực kém đối với các lệnh được gửi đến dịch vụ nền DriverHub.

Điều này cho phép nhà nghiên cứu tạo ra một chuỗi khai thác sử dụng các lỗ hổng được theo dõi với số [CVE-2025-3462](https://nvd.nist.gov/vuln/detail/CVE-2025-3462) và [CVE-2025-3463](https://nvd.nist.gov/vuln/detail/CVE-2025-3463) mà khi kết hợp lại, đạt được việc bỏ qua nguồn gốc và kích hoạt thực thi mã từ xa trên mục tiêu.

## Vấn đề với DriverHub

DriverHub là công cụ quản lý driver chính thức của ASUS, được cài đặt tự động khi lần đầu tiên khởi động hệ thống khi sử dụng một số bo mạch chủ của ASUS.

Phần mềm này chạy ở chế độ nền, tự động phát hiện và tải xuống các phiên bản driver mới nhất cho mô hình bo mạch chủ và chipset được phát hiện.

Khi đã cài đặt, công cụ này vẫn hoạt động và chạy ở chế độ nền thông qua một dịch vụ cục bộ trên cổng 53000, liên tục kiểm tra các bản cập nhật driver quan trọng.

Trong khi đó, hầu hết người dùng thậm chí không biết rằng một dịch vụ như vậy đang chạy liên tục trên hệ thống của họ.

Dịch vụ này kiểm tra Header nguồn gốc của các yêu cầu HTTP vào để từ chối bất kỳ thứ gì không đến từ 'driverhub.asus.com.'

Tuy nhiên, kiểm tra này được thực hiện kém, vì bất kỳ trang web nào bao gồm chuỗi đó cũng được chấp nhận ngay cả khi không khớp chính xác với cổng thông tin chính thức của ASUS.

Vấn đề thứ hai nằm ở điểm cuối UpdateApp, cho phép DriverHub tải xuống và chạy các tệp .exe từ các URL ".asus.com" mà không có sự xác nhận từ người dùng.

![Cài đặt BIOS liên quan đến DriverHub (Được kích hoạt theo mặc định)](https://www.bleepstatic.com/images/news/u/1220909/2025/May/bios.jpg)

**Cài đặt BIOS liên quan đến DriverHub (Được bật theo mặc định)**  
_Nguồn: MrBruh_

## Luồng tấn công ẩn danh

Một kẻ tấn công có thể nhắm mục tiêu vào bất kỳ người dùng nào có ASUS DriverHub đang chạy trên hệ thống của họ để khiến họ truy cập vào một trang web độc hại trên trình duyệt của họ. Trang web này sau đó gửi "các yêu cầu UpdateApp" đến dịch vụ cục bộ tại 'http://127.0.0.1:53000.'

Bằng cách giả mạo Header nguồn gốc đến một cái gì đó như 'driverhub.asus.com.mrbruh.com,' kiểm tra xác thực yếu này bị bỏ qua, vì vậy DriverHub chấp nhận các lệnh.

Trong phần trình diễn của nhà nghiên cứu, các lệnh yêu cầu phần mềm tải xuống trình cài đặt 'AsusSetup.exe' hợp pháp được ký bởi ASUS từ cổng tải xuống của nhà cung cấp, cùng với một tệp .ini độc hại và tải trọng .exe.

Trình cài đặt được ký bởi ASUS được chạy âm thầm với quyền admin và sử dụng thông tin cấu hình trong tệp .ini. Tệp ini này chỉ đạo trình cài đặt driver hợp pháp của ASUS khởi chạy tệp thi hành độc hại.

Cuộc tấn công cũng trở nên khả thi bởi vì công cụ này không xóa các tệp không vượt qua kiểm tra chữ ký, như tệp .ini và tải trọng, vẫn được giữ lại trên máy chủ sau khi tải về.

## Phản hồi của ASUS và hành động của người dùng

ASUS đã nhận được báo cáo của nhà nghiên cứu vào ngày 8 tháng 4 năm 2025 và đã thực hiện một bản sửa lỗi vào ngày 18 tháng 4, sau khi xác nhận nó với MrBruh vào ngày hôm trước. Gã khổng lồ phần cứng đã không đề nghị nhà nghiên cứu bất kỳ phần thưởng nào cho việc công bố của anh.

Mô tả CVE, mà nhà cung cấp Đài Loan đã gửi, phần nào làm giảm mức độ nghiêm trọng của vấn đề với tuyên bố sau: 

"Vấn đề này chỉ giới hạn ở các bo mạch chủ và không ảnh hưởng đến máy tính xách tay, máy tính để bàn hoặc các điểm cuối khác," mô tả CVE ghi rõ.

Điều này gây nhầm lẫn, vì các CVE đã đề cập ảnh hưởng đến máy tính xách tay và máy tính để bàn có DriverHub được cài đặt.

Tuy nhiên, ASUS rõ ràng hơn trong thông báo bảo mật của mình, khuyên người dùng nhanh chóng áp dụng bản cập nhật mới nhất. 

"Bản cập nhật này bao gồm các bản cập nhật bảo mật quan trọng và ASUS rất khuyến nghị người dùng cập nhật phiên bản cài đặt ASUS DriverHub của họ lên phiên bản mới nhất," [đọc thông báo](https://www.asus.com/content/asus-product-security-advisory/).

"Các bản cập nhật phần mềm mới nhất có thể được truy cập bằng cách mở ASUS DriverHub, sau đó nhấn nút "Cập nhật ngay"."

MrBruh nói rằng anh theo dõi các bản cập nhật minh bạch chứng chỉ và không tìm thấy chứng chỉ TLS nào khác chứa chuỗi "driverhub.asus.com", cho thấy nó không bị khai thác trong môi trường thực.

Nếu bạn không thoải mái với một dịch vụ nền tự động tải xuống các tệp có khả năng nguy hiểm khi truy cập các trang web, bạn có thể vô hiệu hóa DriverHub từ cài đặt BIOS của mình.