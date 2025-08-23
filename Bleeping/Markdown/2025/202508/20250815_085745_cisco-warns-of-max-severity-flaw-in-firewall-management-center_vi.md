# Cisco cảnh báo về lỗ hổng nghiêm trọng tối đa trong Firewall Management Center

![Cisco cảnh báo về lỗ hổng nghiêm trọng tối đa trong Firewall Management Center](https://www.bleepstatic.com/content/hl-images/2025/03/04/Cisco_headpic.jpg)

Cisco đang cảnh báo về một lỗ hổng thực thi mã từ xa (RCE) nghiêm trọng trong hệ thống RADIUS của phần mềm Cisco Secure Firewall Management Center (FMC).

Cisco FMC là nền tảng quản lý cho các sản phẩm Secure Firewall của nhà cung cấp, cung cấp giao diện tập trung dựa trên web hoặc SSH cho phép quản trị viên cấu hình, giám sát và cập nhật các tường lửa của Cisco.

RADIUS trong FMC là một phương thức xác thực bên ngoài tùy chọn cho phép kết nối với máy chủ Remote Authentication Dial-In User Service thay vì các tài khoản cục bộ.

Cấu hình này thường được sử dụng trong các mạng doanh nghiệp và chính phủ nơi mà các quản trị viên muốn kiểm soát đăng nhập tập trung và kế toán cho việc truy cập thiết bị mạng.

Lỗ hổng được công bố gần đây được theo dõi với mã CVE-2025-20265 và nhận được điểm độ nghiêm trọng tối đa là 10 trên 10.

Có thể khai thác lỗ hổng này để cho phép một kẻ tấn công từ xa không xác thực gửi đầu vào được định dạng đặc biệt khi nhập thông tin đăng nhập trong bước xác thực RADIUS.

Kẻ thù do đó có thể đạt được thực thi lệnh shell tùy ý với quyền nâng cao.

“Lỗ hổng trong việc thực hiện hệ thống RADIUS của Cisco Secure Firewall Management Center (FMC) có thể cho phép một kẻ tấn công từ xa không xác thực tiêm các lệnh shell tùy ý mà được thực thi bởi thiết bị,” [cảnh báo Cisco trong thông báo bảo mật](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-fmc-radius-rce-TNBKf79).

“Lỗ hổng này là do thiếu xử lý đúng đắn đầu vào của người dùng trong giai đoạn xác thực,” nhà cung cấp cho biết. CVE-2025-20265 ảnh hưởng đến các phiên bản FMC 7.0.7 và 7.7.0 khi xác thực RADIUS được kích hoạt cho giao diện quản lý dựa trên web, quản lý SSH, hoặc cả hai.

Cisco đã phát hành các bản cập nhật phần mềm miễn phí để giải quyết vấn đề. Bản sửa lỗi đã được phát hành qua các kênh thường xuyên cho khách hàng có hợp đồng dịch vụ hợp lệ.

Nếu bản vá không thể được cài đặt, biện pháp khắc phục mà Cisco khuyến nghị là vô hiệu hóa xác thực RADIUS và thay thế bằng một phương pháp khác (ví dụ: tài khoản người dùng cục bộ, LDAP bên ngoài hoặc SAML single sign-on).

Cisco lưu ý rằng biện pháp khắc phục này đã được thử nghiệm thành công, nhưng khách hàng phải xác minh tính áp dụng và tác động mà nó có trong môi trường của họ.

Lỗ hổng này đã được nhà nghiên cứu bảo mật của Cisco, Brandon Sakai, phát hiện nội bộ, và nhà cung cấp không biết về việc lỗ hổng này bị khai thác ngoài thực tế.

Cùng với CVE-2025-20265, Cisco cũng đã phát hành các bản sửa lỗi cho 13 lỗ hổng mức độ nghiêm trọng cao trên nhiều sản phẩm, không có lỗ hổng nào được đánh dấu là đang bị khai thác:

* [CVE-2025-20217](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-ftd-dos-SvKhtjgt) – Secure Firewall Threat Defense Snort 3 từ chối dịch vụ.
* [CVE-2025-20222](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-fp2k-IPsec-dos-tjwgdZCO) – ASA & Secure FTD (Firepower 2100) IPv6 qua IPsec từ chối dịch vụ.
* [CVE-2025-20148](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-fmc-html-inj-MqjrZrny) – Secure Firewall Management Center tiêm HTML.
* [CVE-2025-20244](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-vpnwebs-dos-hjBhmBsX) – ASA & Secure FTD Remote Access VPN máy chủ web từ chối dịch vụ.
* [CVE-2025-20133, CVE-2025-20243](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-vpn-dos-mfPekA6e) – ASA & Secure FTD Remote Access SSL VPN từ chối dịch vụ.
* [CVE-2025-20134](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-ssltls-dos-eHw76vZe) – ASA & Secure FTD chứng chỉ SSL/TLS từ chối dịch vụ.
* [CVE-2025-20136](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-nat-dns-dos-bqhynHTM) – ASA & Secure FTD NAT DNS kiểm tra từ chối dịch vụ.
* [CVE-2025-20251](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-http-file-hUyX2jL4) – ASA & Secure FTD máy chủ web VPN từ chối dịch vụ.
* [CVE-2025-20224, CVE-2025-20225](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asa-ftd-ios-dos-DOESHWHy) – IOS, IOS XE, ASA & Secure FTD IKEv2 từ chối dịch vụ.
* [CVE-2025-20263](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asa-buffer-overflow-PyRUhWBC) – ASA & Secure FTD dịch vụ web từ chối dịch vụ.
* [CVE-2025-20127](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-3100%5F4200%5Ftlsdos-2yNSCd54) – ASA & Secure FTD (Firepower 3100/4200) mã hóa TLS 1.3 từ chối dịch vụ.

Nhà cung cấp cho biết rằng không có biện pháp nào cho bất kỳ vấn đề bảo mật nào ở trên ngoại trừ CVE-2025-20127, nơi mà khuyến nghị là loại bỏ mã hóa TLS 1.3.

Đối với tất cả các vấn đề khác, nhà cung cấp khuyến nghị cài đặt các bản cập nhật mới nhất có sẵn.