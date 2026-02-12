# Plugin WordPress với 900.000 lượt cài đặt dễ bị lỗ hổng RCE nghiêm trọng

![WordPress plugin with 900k installs vulnerable to critical RCE flaw](https://www.bleepstatic.com/content/hl-images/2023/12/07/back.jpg)

Một lỗ hổng nghiêm trọng trong plugin WPvivid Backup & Migration cho WordPress, được cài đặt trên hơn 900.000 trang web, có thể bị khai thác để thực thi mã từ xa bằng cách tải lên tệp tùy ý mà không cần xác thực.

Vấn đề bảo mật này được theo dõi là CVE-2026-1357 và nhận được điểm độ nghiêm trọng là 9.8. Nó ảnh hưởng đến tất cả các phiên bản của plugin lên đến 0.9.123 và có thể dẫn đến việc chiếm quyền kiểm soát hoàn toàn trang web.

Bất chấp mức độ nghiêm trọng của vấn đề, các nhà nghiên cứu tại công ty bảo mật WordPress Defiant cho biết chỉ các trang web có tùy chọn "nhận bản sao lưu từ trang web khác" không phải mặc định được bật mới bị ảnh hưởng nghiêm trọng.

[![Wiz](https://www.bleepstatic.com/c/w/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=AI-Agents-101)

Hơn nữa, kẻ tấn công có một cửa sổ khai thác 24 giờ, đó là thời hạn hiệu lực của khóa được tạo cần thiết cho các trang web khác để gửi tệp sao lưu.

Yêu cầu này hạn chế khả năng tiếp xúc thực tế; tuy nhiên, plugin này thường được [sử dụng](https://wordpress.org/plugins/wpvivid-backuprestore/#description) cho việc di chuyển trang web và chuyển bản sao lưu giữa các máy chủ, vì vậy quản trị viên trang web rất có thể sẽ bật tính năng này tại một thời điểm nào đó, ít nhất là tạm thời.

Nhà nghiên cứu Lucas Montes (NiRoX) đã báo cáo lỗ hổng cho Defiant vào ngày 12 tháng 1. Nguyên nhân gốc rễ là việc xử lý lỗi không đúng cách trong giải mã RSA, kết hợp với việc thiếu vệ sinh đường dẫn.

Cụ thể, khi hàm '_openssl\_private\_decrypt()_' thất bại, plugin không dừng thực thi và thay vào đó truyền kết quả thất bại (false) cho thói quen AES (Rijndael).

Thư viện mật mã xử lý điều này như một chuỗi byte null, tạo ra một khóa mã hóa có thể dự đoán được mà kẻ tấn công có thể sử dụng để tạo tải trọng độc hại mà plugin sẽ chấp nhận.

Ngoài ra, plugin không vệ sinh đúng tên tệp được tải lên, cho phép vượt qua thư mục. Điều này cho phép ghi tệp bên ngoài thư mục sao lưu dự định và tải lên tệp PHP độc hại để thực thi mã từ xa.

Defiant đã thông báo cho nhà cung cấp, WPVividPlugins, vào ngày 22 tháng 1, sau khi xác nhận bằng chứng khái niệm khai thác được cung cấp. Một bản cập nhật bảo mật giải quyết [CVE-2026-1357](https://nvd.nist.gov/vuln/detail/CVE-2026-1357) đã được phát hành trong phiên bản 0.9.124 vào ngày 28 tháng 1.

Bản sửa lỗi bao gồm việc thêm kiểm tra để dừng thực thi nếu giải mã RSA thất bại, thêm vệ sinh tên tệp và hạn chế tải lên chỉ cho các loại tệp sao lưu được phép, chẳng hạn như ZIP, GZ, TAR và SQL.

Người dùng plugin WordPress WPvivid Backup & Migration nên nhận thức được các rủi ro liên quan đến lỗ hổng và nâng cấp lên phiên bản 0.9.124 càng sớm càng tốt.