# Lỗi máy in Brother trong 689 mẫu thiết bị lộ thông tin đăng nhập quản trị mặc định

![Brother printer](https://www.bleepstatic.com/content/hl-images/2025/06/26/brother-printer.jpg)

Tổng cộng có 689 mẫu máy in từ Brother, cùng với 53 mẫu khác từ Fujifilm, Toshiba và Konica Minolta, đi kèm với một mật khẩu quản trị mặc định mà kẻ tấn công từ xa có thể tạo ra. Tệ hơn nữa, không có cách nào để khắc phục lỗi này thông qua firmware trong các máy in hiện có.

Lỗi này, được theo dõi dưới mã [CVE-2024-51978](https://nvd.nist.gov/vuln/detail/CVE-2024-51978), là một phần của tổng số tám lỗ hổng [được các nhà nghiên cứu của Rapid7 phát hiện](https://www.rapid7.com/blog/post/multiple-brother-devices-multiple-vulnerabilities-fixed/) trong quá trình kiểm tra dài hạn phần cứng của Brother.

| CVE            | Mô tả                                                                                 | Dịch vụ bị ảnh hưởng                              | CVSS           |
| -------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------ | -------------- |
| CVE-2024-51977 | Kẻ tấn công không xác thực có thể rò rỉ thông tin nhạy cảm.                        | HTTP (Cổng 80), HTTPS (Cổng 443), IPP (Cổng 631) | 5.3 (Trung bình)   |
| CVE-2024-51978 | Kẻ tấn công không xác thực có thể tạo ra mật khẩu quản trị mặc định của thiết bị. | HTTP (Cổng 80), HTTPS (Cổng 443), IPP (Cổng 631) | 9.8 (Nghiêm trọng) |
| CVE-2024-51979 | Kẻ tấn công đã xác thực có thể kích hoạt tràn bộ đệm dựa trên ngăn xếp.               | HTTP (Cổng 80), HTTPS (Cổng 443), IPP (Cổng 631) | 7.2 (Cao)     |
| CVE-2024-51980 | Kẻ tấn công không xác thực có thể buộc thiết bị mở một kết nối TCP.                | Web Services over HTTP (Cổng 80)                 | 5.3 (Trung bình)   |
| CVE-2024-51981 | Kẻ tấn công không xác thực có thể buộc thiết bị thực hiện một yêu cầu HTTP tùy ý.  | Web Services over HTTP (Cổng 80)                 | 5.3 (Trung bình)   |
| CVE-2024-51982 | Kẻ tấn công không xác thực có thể làm sập thiết bị.                                  | PJL (Cổng 9100)                                  | 7.5 (Cao)     |
| CVE-2024-51983 | Kẻ tấn công không xác thực có thể làm sập thiết bị.                                  | Web Services over HTTP (Cổng 80)                 | 7.5 (Cao)     |
| CVE-2024-51984 | Kẻ tấn công đã xác thực có thể tiết lộ mật khẩu của một dịch vụ bên ngoài đã được cấu hình. | LDAP, FTP                                        | 6.8 (Trung bình)   |

Lỗ hổng quan trọng này có thể kết hợp với các lỗ hổng khác được Rapid7 phát hiện để xác định mật khẩu quản trị, kiểm soát thiết bị, thực hiện một mã từ xa, làm sập chúng hoặc xoay vòng trong các mạng mà chúng kết nối.

Không phải tất cả các lỗi đều ảnh hưởng đến tất cả 689 mẫu máy in Brother, nhưng các nhà sản xuất khác, bao gồm Fujifilm (46 mẫu), Konica Minolta (6), Ricoh (5) và Toshiba (2), cũng bị ảnh hưởng.

![Số mẫu bị ảnh hưởng cho mỗi lỗ hổng](https://www.bleepstatic.com/images/news/u/1220909/2025/June/impact.jpg)

**Số mẫu bị ảnh hưởng cho mỗi lỗ hổng**  
_Nguồn: Rapid7_

## Tạo mật khẩu không an toàn

Mật khẩu mặc định trong các máy in bị ảnh hưởng được tạo ra trong quá trình sản xuất bằng cách sử dụng một thuật toán tùy chỉnh dựa trên số serial của thiết bị.

Theo một [phân tích kỹ thuật chi tiết](https://assets.contentstack.io/v3/assets/blte4f029e766e6b253/blt6495b3c6adf2867f/685aa980a26c5e2b1026969c/vulnerability-disclosure-whitepaper.pdf) của Rapid7, thuật toán tạo mật khẩu theo một quy trình dễ đảo ngược:

1. Lấy 16 ký tự đầu tiên của số serial.
2. Thêm 8 byte được lấy từ một bảng "muối" tĩnh.
3. Băm kết quả bằng SHA256.
4. Mã hóa Base64 hash.
5. Lấy tám ký tự đầu tiên và thay thế một số chữ cái bằng các ký tự đặc biệt.

Kẻ tấn công có thể rò rỉ số serial của máy in mục tiêu bằng nhiều phương pháp khác nhau hoặc bằng cách khai thác [CVE-2024-51977](https://nvd.nist.gov/vuln/detail/CVE-2024-51977). Sau đó, họ có thể sử dụng thuật toán để tạo ra mật khẩu quản trị mặc định và đăng nhập với tư cách quản trị viên.

Từ đó, họ có thể cấu hình lại máy in, truy cập các bản quét đã lưu, đọc danh bạ, khai thác [CVE-2024-51979](https://nvd.nist.gov/vuln/detail/CVE-2024-51979) để thực hiện mã từ xa, hoặc khai thác [CVE-2024-51984](https://nvd.nist.gov/vuln/detail/CVE-2024-51984) để thu thập thông tin xác thực.

Rapid7 đã bắt đầu quy trình công khai vào tháng 5 năm 2024 và được JPCERT/CC hỗ trợ trong việc phối hợp thông báo cho các nhà sản xuất khác.

Mặc dù tất cả các lỗi đã được khắc phục trong các bản cập nhật firmware do các nhà sản xuất bị ảnh hưởng cung cấp, nhưng trường hợp của CVE-2024-51978 thì phức tạp trong quản lý rủi ro.

Lỗ hổng này bắt nguồn từ logic tạo mật khẩu được sử dụng trong sản xuất phần cứng, do đó, bất kỳ thiết bị nào được sản xuất trước khi phát hiện sẽ có mật khẩu dễ đoán trừ khi người dùng thay đổi chúng.

"Brother đã chỉ ra rằng lỗ hổng này không thể được sửa chữa hoàn toàn trong firmware và đã yêu cầu thay đổi quy trình sản xuất của tất cả các mẫu bị ảnh hưởng," Rapid7 cho biết về CVE-2024-51978.

Người dùng các máy in Brother hiện có trong danh sách mẫu bị ảnh hưởng nên xem xét thiết bị của họ có khả năng bị tổn thương và ngay lập tức thay đổi mật khẩu quản trị mặc định, sau đó áp dụng các bản cập nhật firmware.

Nói chung, nên hạn chế truy cập vào giao diện quản trị của máy in qua các giao thức không an toàn và mạng bên ngoài.

Các thông báo bảo mật với hướng dẫn về những gì người dùng nên làm có sẵn cho [Brother](https://support.brother.com/g/b/faqend.aspx?c=us&lang=en&prod=group2&faqid=faq00100846%5F000), [Konica Minolta](https://www.konicaminolta.com/global-en/security/advisory/pdf/km-2025-0001.pdf), [Fujifilm](https://www.fujifilm.com/fbglobal/eng/company/news/notice/2025/0625%5Fannounce.html), [Ricoh](https://www.ricoh.com/products/security/vulnerabilities/vul?id=ricoh-2025-000007), và [Toshiba](https://www.toshibatec.com/information/20250625%5F02.html).