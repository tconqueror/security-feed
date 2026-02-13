# Plugin WordPress với 900k lượt cài đặt dễ bị lỗ hổng RCE nghiêm trọng

![WordPress plugin with 900k installs vulnerable to critical RCE flaw](https://www.bleepstatic.com/content/hl-images/2023/12/07/back.jpg)

Một lỗ hổng nghiêm trọng trong plugin WPvivid Backup & Migration cho WordPress, được cài đặt trên hơn 900.000 website, có thể bị khai thác để thực thi mã từ xa bằng cách tải lên các tệp tin tùy ý mà không cần xác thực.

Vấn đề bảo mật này được theo dõi với mã CVE-2026-1357 và nhận điểm nghiêm trọng 9.8. Nó ảnh hưởng đến tất cả các phiên bản plugin lên đến 0.9.123 và có thể dẫn đến việc chiếm quyền điều khiển website hoàn toàn.

Mặc dù mức độ nghiêm trọng của lỗ hổng, các nhà nghiên cứu tại công ty bảo mật WordPress Defiant cho biết chỉ các trang web có tùy chọn không mặc định "nhận bản sao lưu từ trang web khác" được bật mới bị ảnh hưởng nghiêm trọng.

[![Wiz](https://www.bleepstatic.com/c/w/Secured-Images-970x250.png)](https://www.wiz.io/lp/secure-images-101-a-visual-guide?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FHardened-Images-101-Digital-Poster&sfcid=701Py00000WFCeLIAX&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=Secured-Images-101) 

Hơn nữa, kẻ tấn công có cửa sổ khai thác 24 giờ, tương ứng với thời gian hiệu lực của khóa được tạo ra mà các trang web khác cần để gửi tệp sao lưu.

Yêu cầu này hạn chế phơi nhiễm thực tế; tuy nhiên, plugin này [thường được sử dụng](https://wordpress.org/plugins/wpvivid-backuprestore/#description) cho việc di chuyển trang web và chuyển bản sao lưu giữa các máy chủ, vì vậy các quản trị viên web rất có thể sẽ bật tính năng này vào một thời điểm nào đó, ít nhất là tạm thời.

Nhà nghiên cứu Lucas Montes (NiRoX) đã báo cáo lỗ hổng cho Defiant vào ngày 12 tháng 1. Nguyên nhân gốc rễ là do xử lý lỗi không đúng cách trong quá trình giải mã RSA, kết hợp với việc thiếu kiểm soát đường dẫn.

Cụ thể, khi hàm ‘_openssl_private_decrypt()_’ thất bại, plugin không dừng thực thi mà thay vào đó chuyển kết quả thất bại (false) đến quy trình AES (Rijndael).

Thư viện mã hóa xử lý điều này như một chuỗi byte null, tạo ra khóa mã hóa có thể dự đoán được mà kẻ tấn công có thể sử dụng để tạo các payload độc hại mà plugin sẽ chấp nhận.

Ngoài ra, plugin không kiểm soát đúng cách tên tệp tin được tải lên, cho phép duyệt thư mục. Điều này cho phép ghi tệp bên ngoài thư mục sao lưu dự định và tải lên các tệp PHP độc hại để thực thi mã từ xa.

Defiant đã thông báo cho nhà cung cấp WPVividPlugins vào ngày 22 tháng 1, sau khi xác thực minh chứng khai thác được cung cấp. Bản cập nhật bảo mật giải quyết [CVE-2026-1357](https://nvd.nist.gov/vuln/detail/CVE-2026-1357) đã được phát hành trong phiên bản 0.9.124 vào ngày 28 tháng 1.

Bản sửa lỗi bao gồm thêm kiểm tra để dừng thực thi nếu giải mã RSA thất bại, thêm kiểm soát tên tệp tin và chỉ cho phép tải lên các loại tệp sao lưu được cho phép như ZIP, GZ, TAR và SQL.

Người dùng plugin WPvivid Backup & Migration cho WordPress nên nhận thức được rủi ro liên quan đến lỗ hổng và nâng cấp lên phiên bản 0.9.124 càng sớm càng tốt.