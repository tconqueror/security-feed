# SonicWall khuyến nghị các quản trị viên vá lỗi RCE quan trọng trong các thiết bị SMA 100

![SonicWall](https://www.bleepstatic.com/content/hl-images/2025/02/14/SonicWall.jpg)

SonicWall khuyến nghị khách hàng vá các thiết bị SMA 100 series để khắc phục lỗ hổng tải lên tệp tùy ý đã được xác thực nghiêm trọng có thể khiến kẻ tấn công thực hiện mã từ xa.

Lỗi bảo mật (được theo dõi dưới mã CVE-2025-40599) do lỗ hổng tải lên tệp không giới hạn trong giao diện quản lý web của các thiết bị, cho phép các tác nhân đe dọa từ xa có quyền quản trị tải lên các tệp tùy ý vào hệ thống.

"SonicWall mạnh mẽ khuyến cáo rằng người dùng sản phẩm SMA 100 series (SMA 210, 410 và 500v) nâng cấp lên phiên bản đã được khắc phục được chỉ định để khắc phục lỗ hổng này," công ty [nói](https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2025-0014). "Lỗ hổng này không ảnh hưởng đến các sản phẩm SonicWall SSL VPN SMA1000 series hoặc SSL-VPN chạy trên các tường lửa SonicWall."

Trong khi kẻ tấn công cần có quyền quản trị để khai thác thành công CVE-2025-40599 và SonicWall chưa tìm thấy bằng chứng cho thấy lỗ hổng này đang bị khai thác tích cực, họ vẫn cảnh báo khách hàng phải bảo mật thiết bị của mình, vì các thiết bị SMA 100 đã bị nhắm đến trong [các cuộc tấn công sử dụng thông tin xác thực đã bị xâm phạm](https://www.bleepingcomputer.com/news/security/sonicwall-sma-devices-hacked-with-overstep-rootkit-tied-to-ransomware/).

Như các nhà nghiên cứu Nhóm tình báo đe dọa Google (GTIG) [cảnh báo tuần trước](https://www.bleepingcomputer.com/news/security/microsoft-sharepoint-servers-also-targeted-in-ransomware-attacks/), một tác nhân đe dọa chưa xác định, được theo dõi dưới mã UNC6148, đã triển khai một phần mềm độc hại rootkit mới có tên là OVERSTEP trên các thiết bị SonicWall SMA 100 Series đã được vá đầy đủ. GTIG tin rằng UNC6148 tham gia vào các cuộc tấn công đánh cắp dữ liệu và tống tiền, và có thể cũng triển khai ransomware Abyss (cũng được theo dõi dưới mã VSOCIETY).

Trong quá trình điều tra những cuộc tấn công này, các nhà điều tra đã tìm thấy bằng chứng cho thấy tác nhân đe dọa đã đánh cắp thông tin xác thực của thiết bị được nhắm đến vào tháng 1 bằng cách khai thác nhiều lỗ hổng ([CVE-2021-20038](https://nvd.nist.gov/vuln/detail/CVE-2021-20038), [CVE-2024-38475](https://nvd.nist.gov/vuln/detail/CVE-2024-38475), [CVE-2021-20035](https://nvd.nist.gov/vuln/detail/CVE-2021-20035), [CVE-2021-20039](https://nvd.nist.gov/vuln/detail/CVE-2021-20039), [CVE-2025-32819](https://nvd.nist.gov/vuln/detail/CVE-2025-32819)).

SonicWall 'mạnh mẽ' khuyên các khách hàng sử dụng thiết bị SMA 100 ảo hoặc vật lý kiểm tra chúng để phát hiện các chỉ số xâm phạm (IoCs) từ báo cáo của GTIG bằng cách kiểm tra các quyền truy cập không được phép và xem lại nhật ký thiết bị và lịch sử kết nối cho các hoạt động đáng ngờ. Nếu họ phát hiện bất kỳ bằng chứng nào về tổn thất, các quản trị viên được khuyến nghị nên liên hệ ngay với Bộ phận Hỗ trợ của SonicWall để được trợ giúp.

Để bảo mật thiết bị của mình, người dùng nên hạn chế quyền truy cập quản lý từ xa trên các giao diện bên ngoài, đặt lại tất cả mật khẩu và thiết lập lại liên kết OTP (Mật khẩu một lần) cho cả người dùng và quản trị viên. Họ cũng nên áp dụng xác thực đa yếu tố (MFA) và bật Tường lửa Ứng dụng Web (WAF).

Đầu năm nay, SonicWall đã chỉ ra các lỗ hổng bảo mật khác đã bị khai thác trong các cuộc tấn công nhắm vào thiết bị Truy cập Di động Bảo mật (SMA) của họ.

Vào tháng 5, công ty đã [kêu gọi khách hàng](https://www.bleepingcomputer.com/news/security/sonicwall-urges-admins-to-patch-vpn-flaw-exploited-in-attacks/) vá ba lỗ hổng bảo mật (CVE-2025-32819, CVE-2025-32820 và CVE-2025-32821) có thể được liên kết với nhau để đạt được quyền thực hiện mã từ xa với tư cách là root, một trong số đó đã được gán là bị khai thác trong các cuộc tấn công.

Một tháng trước, SonicWall [đánh dấu một lỗ hổng SMA100 khác](https://www.bleepingcomputer.com/news/security/cisa-tags-sonicwall-vpn-flaw-as-actively-exploited-in-attacks/) (CVE-2021-20035) là bị khai thác trong các cuộc tấn công thực hiện mã từ xa [kể từ ít nhất tháng 1 năm 2025](https://www.bleepingcomputer.com/news/security/sonicwall-sma-vpn-devices-targeted-in-attacks-since-january/).