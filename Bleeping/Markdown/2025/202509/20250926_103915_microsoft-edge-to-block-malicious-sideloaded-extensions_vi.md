# Microsoft Edge sẽ chặn các tiện ích mở rộng sideload độc hại

![Microsoft Edge](https://www.bleepstatic.com/content/hl-images/2025/09/26/Microsoft_Edge.jpg)

Microsoft đang dự định giới thiệu một tính năng bảo mật mới cho Edge nhằm bảo vệ người dùng khỏi các tiện ích mở rộng độc hại được sideload vào trình duyệt web.

Edge cho phép các nhà phát triển [cài đặt tiện ích mở rộng cục bộ](https://learn.microsoft.com/en-us/microsoft-edge/extensions/getting-started/extension-sideloading#locally-installing-and-running-an-extension) (còn được gọi là sideloading) để thử nghiệm trước khi xuất bản chúng lên cửa hàng [Microsoft Edge Add-ons](https://microsoftedge.microsoft.com/) bằng cách bật tùy chọn "Developer Mode" trên trang quản lý Extensions management page và nhấp nút "Load unpacked".

Tuy nhiên, người dùng cũng có thể sideload các tiện ích mở rộng từ bên thứ ba không được phân phối qua các kênh chính thức và không được quét để phát hiện phần mềm độc hại.

Mặc dù người dùng có thể gỡ bỏ các tiện ích mở rộng nguy hiểm thông qua tab Extensions management bằng cách nhấp vào liên kết "Remove" trên thẻ tiện ích mở rộng, nhưng thường thì đã quá muộn nếu kẻ tấn công lừa người dùng cài đặt chúng, như được thể hiện qua các cuộc tấn công đã ảnh hưởng tới hàng trăm nghìn người dùng trong những năm gần đây và đôi khi còn có thể [force-install malicious extensions](https://www.bleepingcomputer.com/news/security/malware-force-installs-chrome-extensions-on-300-000-browsers-patches-dlls/) được lưu trữ trên các cửa hàng add-on chính thức.

Tuy nhiên, như Redmond đã tiết lộ vào thứ Năm trên Microsoft 365 roadmap, "Microsoft Edge sẽ phát hiện và thu hồi các tiện ích mở rộng sideload độc hại."

Mặc dù công ty không cung cấp thêm chi tiết về cách xác định các tiện ích mở rộng nguy hiểm này, tính năng bảo mật mới dự kiến sẽ ra mắt vào tháng Mười Một cho các multi-tenant instances tiêu chuẩn trên toàn cầu.

Trong những tháng gần đây, Microsoft đã cập nhật "Publish API for Edge extension developers" để nâng cao bảo mật cho các tài khoản nhà phát triển và quy trình cập nhật tiện ích mở rộng trình duyệt. Họ cũng đã bắt đầu thử nghiệm một tính năng mới nhằm cảnh báo người dùng về các tiện ích mở rộng gây ảnh hưởng tiêu cực tới hiệu suất của Edge.

Vào tháng Hai, hãng cũng giới thiệu một AI-powered scareware blocker cho trình duyệt Edge, tính năng này sử dụng machine learning (ML) để phát hiện các tech support scams bằng cách nhận diện các dấu hiệu của scam scareware trong thời gian thực sử dụng một mô hình học máy cục bộ.

Trong tháng này, Microsoft đã bắt đầu triển khai HTTPS-First Mode trong Microsoft Edge, tính năng tự động nâng cấp kết nối HTTP lên HTTPS khi có thể. Ngoài ra, bắt đầu từ Edge v140 (phát hành vào tháng Tám), trình duyệt sẽ tự động loại bỏ các sleeping tabs để tiết kiệm bộ nhớ.