# Chiêu trò sửa lỗi giả mạo khiến người dùng cài đặt Shamos infostealer mới

![Apple](https://www.bleepstatic.com/content/hl-images/2023/09/11/apple_triangle.jpg)

Một loại malware infostealer mới nhắm vào các thiết bị Mac, có tên là 'Shamos,' đang mục tiêu vào các thiết bị Mac trong các cuộc tấn công ClickFix giả mạo các hướng dẫn và sửa lỗi.

Malware mới này, là một biến thể của Atomic macOS Stealer (AMOS), được phát triển bởi nhóm tội phạm mạng "COOKIE SPIDER," và được sử dụng để đánh cắp dữ liệu và thông tin tài khoản được lưu trữ trong các trình duyệt web, các mục Keychain, Apple Notes, và ví tiền điện tử.

CrowdStrike, đơn vị phát hiện Shamos, [báo cáo](https://www.crowdstrike.com/en-us/blog/falcon-prevents-cookie-spider-shamos-delivery-macos/) rằng malware đã cố gắng lây nhiễm hơn ba trăm môi trường trên toàn thế giới mà họ theo dõi kể từ tháng 6 năm 2025.

## Được quảng bá thông qua các cuộc tấn công ClickFix

Các nạn nhân bị lừa đảo thông qua quảng cáo độc hại hoặc các kho GitHub giả mạo, sử dụng các cuộc tấn công ClickFix khiến người dùng thực hiện các lệnh shell trong macOS Terminal.

Các tác nhân đe dọa khuyến khích người dùng chạy những lệnh này để cài đặt phần mềm hoặc sửa các lỗi giả mạo, nhưng khi được thực thi, chúng thực sự tải xuống và thực hiện malware trên thiết bị.

![Malicious GitHub repository](https://www.bleepstatic.com/images/news/u/1220909/2025/August/github.jpeg)

**Kho GitHub độc hại**  
_Nguồn: CrowdStrike_

Các quảng cáo hoặc trang giả mạo (mac-safer\[.\]com, rescue-mac\[.\]com) tuyên bố cung cấp sự trợ giúp cho các vấn đề macOS mà mọi người có khả năng tìm kiếm, chứa hướng dẫn chỉ dẫn họ sao chép và dán lệnh để sửa chữa vấn đề.

![Malicious sponsored results on Google Search](https://www.bleepstatic.com/images/news/u/1220909/2025/August/sponsored.jpg)

**Kết quả được tài trợ độc hại trên Google Search**  
_Nguồn: CrowdStrike_

Thay vì sửa chữa điều gì đó, lệnh này giải mã một URL mã hóa Base64 và lấy một script Bash độc hại từ một máy chủ từ xa.

**Hướng dẫn giả mạo để sửa lỗi máy in trên macOS**  
_Nguồn: CrowdStrike_

Script này ghi lại mật khẩu của người dùng, tải xuống tệp thực thi Shamos mach-O, và chuẩn bị và thực hiện malware bằng cách sử dụng 'xattr' ( loại bỏ cờ kiểm dịch) và 'chmod' (biến nhị phân thành khả thi thực thi) để vượt qua Gatekeeper.

## Lấy cắp dữ liệu của Shamos

Sau khi được thực thi trên thiết bị, Shamos thực hiện các lệnh chống VM để xác minh rằng nó không chạy trên một sandbox, sau đó thực hiện các lệnh AppleScript để thu thập thông tin và thu thập dữ liệu.

Shamos tìm kiếm dữ liệu nhạy cảm trên thiết bị, bao gồm các tập tin ví tiền điện tử, dữ liệu keychain, dữ liệu Apple Notes, và thông tin được lưu trữ trên trình duyệt của nạn nhân.

Sau khi thu thập tất cả, nó đóng gói chúng vào một tệp nén có tên 'out.zip' và truyền chúng đến kẻ tấn công bằng cách sử dụng curl.

Trong các trường hợp mà malware chạy với quyền sudo, nó cũng tạo một tệp Plist (com.finder.helper.plist) và lưu trữ nó trong thư mục LaunchDaemons của người dùng, đảm bảo sự tồn tại thông qua việc thực thi tự động khi khởi động hệ thống.

CrowdStrike cũng lưu ý rằng Shamos có thể tải xuống các tải trọng bổ sung vào thư mục chính của nạn nhân, và đã quan sát thấy một số trường hợp mà các tác nhân đe dọa đã thả ứng dụng ví Ledger Live giả mạo và một mô-đun botnet.

Người dùng MacOS được khuyến cáo không bao giờ thực hiện các lệnh trên hệ thống của họ mà họ tìm thấy trực tuyến nếu họ không hoàn toàn hiểu chúng làm gì.

Điều này cũng áp dụng cho các kho GitHub, vì nền tảng này không may là một nơi chứa nhiều dự án độc hại nhằm nhiễm độc cho người dùng vô tình.

Khi gặp vấn đề với macOS, tốt hơn hết là bạn nên tránh các kết quả tìm kiếm được tài trợ và thay vào đó tìm kiếm sự giúp đỡ trong các diễn đàn cộng đồng của Apple, nơi có sự kiểm soát của Apple, hoặc sử dụng Trợ giúp tích hợp trong hệ thống (Cmd + Space → "Help").

Các cuộc tấn công ClickFix đã trở thành một chiến thuật phổ biến trong việc phân phối malware, với các tác nhân đe dọa sử dụng chúng trong các [video TikTok](https://www.bleepingcomputer.com/news/security/tiktok-videos-now-push-infostealer-malware-in-clickfix-attacks/), [ngụy trang thành captchas](https://www.bleepingcomputer.com/news/security/iclicker-hack-targeted-students-with-malware-via-fake-captcha/), hoặc như là các sửa lỗi cho các [lỗi Google Meet giả mạo](https://www.bleepingcomputer.com/news/security/fake-google-meet-conference-errors-push-infostealing-malware/). 

Chiến thuật này đã được chứng minh là rất hiệu quả trong việc triển khai malware đến mức nó đã được sử dụng trong các [cuộc tấn công ransomware](https://www.bleepingcomputer.com/news/security/interlock-ransomware-gang-pushes-fake-it-tools-in-clickfix-attacks/) và thậm chí bởi các [tác nhân đe dọa được nhà nước hỗ trợ](https://www.bleepingcomputer.com/news/security/state-sponsored-hackers-embrace-clickfix-social-engineering-tactic/).