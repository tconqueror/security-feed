# Microsoft triển khai BitLocker tăng tốc phần cứng trên Windows 11

![Microsoft triển khai BitLocker tăng tốc phần cứng trên Windows 11](https://www.bleepstatic.com/content/hl-images/2024/08/13/Windows_BitLocker.jpg)

Microsoft đang triển khai BitLocker tăng tốc phần cứng trên Windows 11 để giải quyết các mối lo ngại ngày càng tăng về hiệu năng và bảo mật bằng cách tận dụng khả năng của SoC và CPU.

BitLocker là tính năng mã hóa toàn bộ ổ đĩa mặc định trên Windows, bảo vệ dữ liệu khỏi bị đọc nếu không có xác thực thích hợp. Trong quá trình khởi động thiết bị bình thường, nó dựa vào Trusted Platform Module (TPM) để quản lý khóa mã hóa một cách an toàn và tự động mở khóa ổ đĩa.

Microsoft cho biết khi bộ nhớ không biến đổi theo chuẩn non-volatile memory express (NVMe) trở nên nhanh hơn, các phép toán mật mã của BitLocker có tác động hiệu năng ngày càng rõ rệt đối với các hoạt động chơi game và chỉnh sửa video.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Với tăng tốc phần cứng, các phép toán mật mã khối lớn có thể được chuyển tải sang các thành phần SoC được trang bị HSM và TEE, cải thiện đáng kể hiệu năng mật mã. Điều này sẽ giảm sử dụng CPU và cải thiện hiệu năng hệ thống tổng thể.

"Khi bật BitLocker, các thiết bị được hỗ trợ với ổ NVMe cùng một trong các SoC mới có khả năng offload mật mã sẽ sử dụng BitLocker tăng tốc phần cứng với thuật toán XTS-AES-256 theo mặc định," [Microsoft giải thích](https://techcommunity.microsoft.com/blog/windows-itpro-blog/announcing-hardware-accelerated-bitlocker/4474609).

"Điều này bao gồm mã hóa thiết bị tự động, bật BitLocker thủ công, bật theo chính sách, hoặc bật bằng script với một số ngoại lệ."

Trong các bài kiểm tra thực tế, BitLocker tăng tốc phần cứng tiêu tốn khoảng 70% ít chu kỳ CPU trên mỗi I/O so với BitLocker chạy phần mềm, mặc dù kết quả thay đổi tùy theo phần cứng.

Bên cạnh lợi ích về hiệu năng, BitLocker giờ đây sử dụng khóa được bảo vệ phần cứng, giảm thiểu việc lộ khóa trước các tấn công nhắm vào CPU và bộ nhớ và tăng cường an ninh tổng thể cùng với bảo vệ khóa dựa trên Trusted Platform Module (TPM).

Microsoft cho biết điều này đưa cơ chế đến gần hơn với mục tiêu loại bỏ khóa BitLocker khỏi CPU và bộ nhớ.

![Microsoft](https://www.bleepstatic.com/images/news/u/1220909/2025/December/diagram(1).jpg)

_Nguồn: Microsoft_

BitLocker mới có sẵn bắt đầu từ Windows 11 24H2, nếu đã cài các bản cập nhật tháng Chín, và trên Windows 11 25H2.

Hỗ trợ ban đầu sẽ xuất hiện trên các hệ thống Intel vPro sử dụng bộ xử lý Intel Core Ultra Series 3 (“Panther Lake”), nhưng các nhà cung cấp SoC khác sẽ được thêm dần.

Người dùng có thể kiểm tra chế độ BitLocker bằng cách chạy lệnh _manage-bde -status_ và kiểm tra thông tin 'Hardware accelerated' dưới Encryption Method.

Microsoft lưu ý rằng BitLocker mặc định ở chế độ dựa trên phần mềm nếu các thuật toán không được hỗ trợ được sử dụng, kích thước khóa được chỉ định thủ công, chính sách doanh nghiệp yêu cầu kích thước khóa hoặc thuật toán không được hỗ trợ, và khi chế độ FIPS được bật và SoC không báo cáo khả năng offload mật mã được chứng nhận FIPS và khả năng bọc khóa.