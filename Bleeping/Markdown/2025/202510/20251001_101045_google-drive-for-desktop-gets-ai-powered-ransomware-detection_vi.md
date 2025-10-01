# Google Drive for desktop nhận diện mã độc tống tiền bằng AI

![Google Drive](https://www.bleepstatic.com/content/hl-images/2025/10/01/Google-Drive.jpg)

Google đã bắt đầu triển khai một tính năng bảo mật mới sử dụng AI cho Google Drive desktop, tính năng này sẽ tự động tạm dừng đồng bộ tệp khi phát hiện một cuộc tấn công mã độc tống tiền nhằm giảm thiểu ảnh hưởng.

Mặc dù tính năng này sẽ không ngăn mã độc tống tiền mã hóa các tệp trên máy tính bị nhiễm, nhưng tài liệu của người dùng được lưu trên Google Drive sẽ được bảo vệ và có thể dễ dàng khôi phục trên một thiết bị khác hoặc trên chính máy tính bị xâm phạm sau khi cuộc nhiễm mã độc đã được xử lý.

Công ty cho biết tính năng này sử dụng một "mô hình AI chuyên biệt" được huấn luyện trên "hàng triệu mẫu mã độc tống tiền thực tế" để nhanh chóng xác định và phản ứng với dấu hiệu cho thấy một tệp đã bị thay đổi một cách độc hại.

Bộ máy chống mã độc tống tiền này cũng có khả năng thích ứng với các biến thể mã độc tống tiền mới bằng cách kết hợp trí tuệ mối đe dọa mới từ dịch vụ quét mã độc trực tuyến VirusTotal và liên tục phân tích các thay đổi tệp.

"When Drive detects unusual activity that suggests a ransomware attack, it automatically pauses syncing of affected files, helping to prevent widespread data corruption across an organization's Drive and the disruption of work," [Google said](https://workspace.google.com/blog/product-announcements/ai-ransomware-detection-in-google-drive) on Tuesday.

"Users then receive an alert on their desktop and via email, guiding them to restore their files. Unlike traditional solutions that require complex re-imaging or costly third-party tools, the intuitive web interface in Drive allows users to easily restore multiple files to a previous, healthy state with just a few clicks."

![Google Drive ransomware notification](https://www.bleepstatic.com/images/news/u/1109292/2025/Google%20Drive%20ransomware%20notification.webp)

_Google Drive thông báo mã độc tống tiền (Google)_

Khả năng mới này được [bật theo mặc định](https://workspaceupdates.googleblog.com/2025/09/ransomware-detection-file-restoration-google-drive.html#:~:text=Ransomware%20detection%20will%20be%20on%20by%20default%20for%20users%20in%20your%20organization) cho tất cả người dùng Google Drive trên hệ thống Windows và macOS, nhưng quản trị viên CNTT có thể tắt phát hiện mã độc tống tiền (từ _Admin console > Apps > Google Workspace > Settings for Drive and Docs > Malware and Ransomware_) và khôi phục tệp (từ _Admin console > Apps > Google Workspace > Settings for Drive and Docs > Drive file restoration_) nếu cần.

Ngoài ra, mặc dù việc đồng bộ sẽ tự động bị tạm dừng trên các phiên bản cũ hơn, những người cũng muốn bật thông báo phát hiện mã độc tống tiền phải cài đặt Google Drive version 114 trở lên trên máy tính của họ.

Tính năng phát hiện mã độc tống tiền mới có sẵn cho người dùng Google Workspace với các gói Business Standard/Plus, Enterprise Starter/Standard/Plus, Education Standard/Plus và Frontline Standard/Plus. Khôi phục tệp có sẵn cho tất cả khách hàng Google Workspace, người đăng ký Workspace Individual, và người dùng có tài khoản Google cá nhân.

Google bổ sung rằng họ không sử dụng dữ liệu của khách hàng, chẳng hạn như prompts và kết quả sinh ra, để huấn luyện và tinh chỉnh các mô hình AI sinh tạo của mình hoặc cho mục đích quảng cáo mà không có sự cho phép.

Microsoft cũng cung cấp [ransomware detection and recovery](https://support.microsoft.com/en-gb/office/ransomware-detection-and-recovering-your-files-0d90ec50-6bfd-40f4-acc7-b8c12c73637f) cho người đăng ký Microsoft 365 sử dụng OneDrive để lưu trữ và đồng bộ tệp lên đám mây. Dropbox, một dịch vụ lưu trữ đám mây phổ biến khác, [có một tính năng tương tự](https://help.dropbox.com/security/ransomware-detection) có sẵn cho các đội với đăng ký Standard, Business, Advanced, hoặc Enterprise.