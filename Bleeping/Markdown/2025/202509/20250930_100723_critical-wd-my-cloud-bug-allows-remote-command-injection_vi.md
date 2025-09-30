# Lỗ hổng nghiêm trọng WD My Cloud cho phép chèn lệnh từ xa

![Lỗ hổng nghiêm trọng WD My Cloud cho phép chèn lệnh từ xa](https://www.bleepstatic.com/content/hl-images/2021/12/09/Western_Digital_headpic.jpg)

Western Digital đã phát hành các bản cập nhật firmware cho nhiều mẫu My Cloud NAS để vá một lỗ hổng mức nghiêm trọng có thể bị khai thác từ xa để thực thi các lệnh hệ thống tùy ý.

Được theo dõi là [CVE-2025-30247](https://nvd.nist.gov/vuln/detail/cve-2025-30247), lỗ hổng là một chèn lệnh hệ điều hành trong giao diện người dùng của My Cloud và có thể bị lợi dụng thông qua các yêu cầu HTTP POST được chế tạo đặc biệt gửi tới các endpoints dễ bị tổn thương.

Lỗ hổng đã được một nhà nghiên cứu bảo mật sử dụng bí danh “w1th0ut” báo cáo cho Western Digital. Nhà sản xuất thiết bị lưu trữ đã phát hành [firmware version 5.31.108](https://www.westerndigital.com/support/product-security/wdc-25006-western-digital-my-cloud-os-5-firmware-5-31-108) để khắc phục vấn đề này, lỗi ảnh hưởng tới tất cả các phiên bản trước cho các mẫu sau:

* My Cloud PR2100
* My Cloud PR4100
* My Cloud EX4100
* My Cloud EX2 Ultra
* My Cloud Mirror Gen 2
* My Cloud DL2100
* My Cloud EX2100
* My Cloud DL4100
* My Cloud WDBCTLxxxxxx-10

Cần lưu ý rằng hai thiết bị My Cloud DL4100 và My Cloud DL2100 đã hết hỗ trợ (EoS) và bản cập nhật có thể không khả dụng, vì [thông báo bảo mật](https://www.westerndigital.com/support/product-security/wdc-25006-western-digital-my-cloud-os-5-firmware-5-31-108) từ công ty không cung cấp các biện pháp giảm thiểu cho các sản phẩm EoS.

My Cloud là giải pháp lưu trữ gắn mạng (NAS) của Western Digital, thường được sử dụng bởi các doanh nghiệp nhỏ, văn phòng tại nhà và cá nhân muốn lưu trữ dữ liệu trên đám mây cá nhân và truy cập từ bất kỳ thiết bị nào.

Mặc dù không nhằm sử dụng trong các môi trường quan trọng hoặc doanh nghiệp, chúng vẫn phổ biến trong đối tượng người tiêu dùng nói chung vì cung cấp khả năng truy cập từ xa dễ dàng tới tệp qua ứng dụng di động hoặc trình duyệt, truyền phát media và sao lưu tự động.

Việc khai thác CVE-2025-30247 để chạy các lệnh shell có thể dẫn đến truy cập trái phép vào tệp, sửa đổi, xóa, liệt kê người dùng, thay đổi cấu hình hoặc thậm chí thực thi các nhị phân.

Trước đây, tin tặc đã lợi dụng các lỗ hổng tương tự trên các thiết bị NAS để thu thập dữ liệu nhạy cảm, xây dựng botnet, sử dụng chúng làm proxy, hoặc triển khai ransomware và tống tiền người dùng.

Người dùng My Cloud nên ưu tiên vá lên 5.31.108 càng sớm càng tốt. Nếu không thể thực hiện ngay, khuyến nghị người dùng tắt kết nối thiết bị khỏi Internet cho đến khi có thể áp dụng bản cập nhật.

Ngay cả khi ngoại tuyến, các thiết bị My Cloud vẫn có thể hoạt động như trung tâm lưu trữ cục bộ ở chế độ LAN, mặc dù các tệp lưu trên dịch vụ đám mây của Western Digital sẽ không thể truy cập được.

Người dùng đã bật cập nhật tự động trong cài đặt thiết bị của họ có thể đã nhận được bản cập nhật [kể từ ngày 23 tháng 9, 2025](https://os5releasenotes.mycloud.com/#/). Khuyến nghị kiểm tra để đảm bảo bạn đang chạy phiên bản mới nhất.

Cập nhật thủ công là có thể ([hướng dẫn ở đây](https://support-en.wd.com/app/answers/detailweb/a%5Fid/31757/~/update-firmware-on-my-cloud-os-5-automatically-or-manually)) bằng cách lấy hình ảnh firmware đúng cho mẫu thiết bị của bạn [từ đây](https://www.westerndigital.com/support/product-list?productName=3779) và sau đó điều hướng đến Cài đặt > Cập nhật Firmware > Cập nhật từ tệp > chọn tệp BIN đã tải xuống.

Thiết bị sẽ cần khởi động lại để bản cập nhật có hiệu lực, và thiết bị phải được cắm điện trong suốt quá trình để ngăn ngừa hỏng dữ liệu.