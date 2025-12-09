# Fortinet cảnh báo về lỗ hổng bỏ qua xác thực đăng nhập FortiCloud SSO nghiêm trọng

![Fortinet](https://www.bleepstatic.com/content/hl-images/2025/04/09/Fortinet.jpg)

Fortinet đã phát hành các bản cập nhật bảo mật để khắc phục hai lỗ hổng nghiêm trọng trong FortiOS, FortiWeb, FortiProxy và FortiSwitchManager có thể cho phép kẻ tấn công bỏ qua xác thực FortiCloud SSO.

Kẻ tấn công có thể khai thác hai lỗ hổng bảo mật được theo dõi là CVE-2025-59718 (FortiOS, FortiProxy, FortiSwitchManager) và CVE-2025-59719 (FortiWeb) bằng cách lợi dụng việc xác minh chữ ký mật mã không đúng cách trong các sản phẩm dễ bị tổn thương thông qua một thông điệp SAML được chế tạo độc hại.

Tuy nhiên, theo Fortinet giải thích trong một khuyến cáo được công bố hôm nay, tính năng FortiCloud dễ bị tấn công không được bật theo mặc định khi thiết bị chưa được đăng ký với FortiCare.

"Please note that the FortiCloud SSO login feature is not enabled in default factory settings," Fortinet said. "However, when an administrator registers the device to FortiCare from the device's GUI, unless the administrator disables the toggle switch 'Allow administrative login using FortiCloud SSO' in the registration page, FortiCloud SSO login is enabled upon registration."

Để bảo vệ hệ thống khỏi các cuộc tấn công khai thác những lỗ hổng này, quản trị viên được khuyến cáo tạm thời vô hiệu hóa tính năng đăng nhập FortiCloud (nếu đã bật) cho đến khi nâng cấp lên phiên bản không còn lỗ hổng.

Để vô hiệu hóa đăng nhập FortiCloud, điều hướng tới System -> Settings và chuyển "Allow administrative login using FortiCloud SSO" sang Off. Ngoài ra, bạn có thể chạy lệnh sau từ giao diện dòng lệnh:

```
config system global
set admin-forticloud-sso-login disable
end
```

Hôm nay, công ty cũng đã vá một lỗ hổng thay đổi mật khẩu không được xác minh ([CVE-2025-59808](https://fortiguard.fortinet.com/psirt/FG-IR-25-599)) cho phép kẻ tấn công "who gained access to a victim's user account to reset the account credentials without being prompted for the account's password," và một lỗ hổng khác có thể cho phép tin tặc xác thực bằng cách sử dụng hash thay cho mật khẩu ([CVE-2025-64471](https://fortiguard.fortinet.com/psirt/FG-IR-25-984)).

Các lỗ hổng bảo mật của Fortinet thường xuyên bị khai thác (thường là zero days) trong cả các cuộc tấn công ransomware và gián điệp mạng.

Ví dụ, Fortinet [disclosed](http://www.fortinet.com/blog/psirt-blogs/importance-of-patching-an-analysis-of-the-exploitation-of-n-day-vulnerabilities) vào tháng Hai rằng nhóm hacker Trung Quốc Volt Typhoon đã cài cửa hậu vào mạng lưới quân sự của [Dutch Ministry of Defence](https://www.bleepingcomputer.com/news/security/chinese-hackers-infect-dutch-military-network-with-malware/) sử dụng phần mềm độc hại Coathanger remote access trojan (RAT) tùy chỉnh sau khi khai thác hai lỗ hổng FortiOS SSL VPN (CVE-2023-27997 and CVE-2022-42475).

Gần đây hơn, vào tháng Tám, Fortinet đã vá [một lỗ hổng chèn lệnh](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-fortisiem-pre-auth-rce-flaw-with-exploit-in-the-wild/) (CVE-2025-25256) có mã khai thác công khai trong giải pháp giám sát bảo mật FortiSIEM, một ngày sau khi công ty an ninh mạng GreyNoise báo cáo một [sự tăng đột biến lớn trong các cuộc tấn công brute-force](https://www.bleepingcomputer.com/news/security/spike-in-fortinet-vpn-brute-force-attacks-raises-zero-day-concerns/) nhắm vào Fortinet SSL VPNs.

Vào tháng Mười Một, Fortinet [warned of a FortiWeb zero-day](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-new-fortiweb-zero-day-exploited-in-attacks/) (CVE-2025-58034) đang bị khai thác tích cực trong các cuộc tấn công, một tuần sau khi [confirming](https://www.bleepingcomputer.com/news/security/fortinet-confirms-silent-patch-for-fortiweb-zero-day-exploited-in-attacks/) rằng họ đã lặng lẽ vá một zero-day FortiWeb khác (CVE-2025-64446) vốn bị khai thác trên quy mô lớn.