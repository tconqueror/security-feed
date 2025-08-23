# Cisco cảnh báo rằng Unified CM có thông tin đăng nhập SSH root cứng

![Cisco](https://www.bleepstatic.com/content/hl-images/2025/03/04/Cisco-headpic.jpg)

Cisco đã loại bỏ một tài khoản backdoor khỏi Unified Communications Manager (Unified CM), mà sẽ cho phép các kẻ tấn công từ xa đăng nhập vào các thiết bị chưa được vá với quyền root.

Cisco Unified Communications Manager (CUCM), trước đây được gọi là Cisco CallManager, đóng vai trò là hệ thống điều khiển trung tâm cho các hệ thống điện thoại IP của Cisco, quản lý định tuyến cuộc gọi, quản lý thiết bị và các tính năng điện thoại.

Lỗ hổng (được theo dõi là [CVE-2025-20309](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-cucm-ssh-m4UBdpE7)) được đánh giá là cực kỳ nghiêm trọng, và nó được gây ra bởi thông tin xác thực của người dùng tĩnh cho tài khoản root, mà đã được sử dụng trong quá trình phát triển và kiểm tra.

Theo một thông báo bảo mật của Cisco được phát hành vào thứ Tư, CVE-2025-20309 ảnh hưởng đến Cisco Unified CM và các phiên bản đặc biệt của Unified CM SME 15.0.1.13010-1 đến 15.0.1.13017-1, bất kể cấu hình thiết bị.

Công ty cũng cho biết không có biện pháp khắc phục nào có thể giải quyết lỗ hổng này. Quản trị viên chỉ có thể khắc phục lỗ hổng và loại bỏ tài khoản backdoor bằng cách nâng cấp các thiết bị dễ bị tổn thương lên Cisco Unified CM và Unified CM SME 15SU3 (tháng 7 năm 2025) hoặc bằng cách áp dụng tệp vá CSCwp27755 [có sẵn ở đây](https://software.cisco.com/download/home/286331940/type/286319173/release/COP-Files).

"Một lỗ hổng trong Cisco Unified Communications Manager (Unified CM) và Cisco Unified Communications Manager Session Management Edition (Unified CM SME) có thể cho phép một kẻ tấn công từ xa không được xác thực đăng nhập vào một thiết bị bị ảnh hưởng bằng cách sử dụng tài khoản root, mà có thông tin xác thực tĩnh mặc định không thể thay đổi hoặc xóa," Cisco [giải thích](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-cucm-ssh-m4UBdpE7).

Sau khi khai thác thành công, các kẻ tấn công có thể truy cập vào các hệ thống dễ bị tổn thương và thực thi lệnh tùy ý với quyền root.

Mặc dù Nhóm Phản ứng Sự cố Bảo mật Sản phẩm Cisco (PSIRT) chưa biết đến mã chứng minh khái niệm có sẵn trực tuyến hoặc khai thác trong các cuộc tấn công, công ty đã phát hành các chỉ dẫn về các dấu hiệu bị xâm phạm để giúp xác định các thiết bị bị ảnh hưởng.

Như Cisco đã nêu, việc khai thác CVE-2025-20309 sẽ dẫn đến một mục ghi log vào /var/log/active/syslog/secure cho người dùng root với quyền root. Vì việc ghi log sự kiện này được bật mặc định, các quản trị viên có thể thu hồi các log để tìm kiếm các nỗ lực khai thác bằng cách chạy lệnh sau từ dòng lệnh: `file get activelog syslog/secure`.

Đây không phải là tài khoản backdoor đầu tiên mà Cisco phải loại bỏ khỏi các sản phẩm của mình trong những năm gần đây, với thông tin đăng nhập cứng trước đó được tìm thấy trong [IOS XE](https://www.bleepingcomputer.com/news/security/cisco-removes-backdoor-account-from-ios-xe-software/), [Dịch vụ Ứng dụng Khu vực Rộng (WAAS)](https://www.bleepingcomputer.com/news/security/cisco-removes-backdoor-account-fourth-in-the-last-four-months/), [Kiến trúc Mạng Kỹ thuật số (DNA) Center](https://www.bleepingcomputer.com/news/security/hardcoded-password-found-in-cisco-enterprise-software-again/), và phần mềm [Người phản ứng Khẩn cấp](https://www.bleepingcomputer.com/news/security/cisco-fixes-hard-coded-root-credentials-in-emergency-responder/).

Gần đây hơn, Cisco [cảnh báo các quản trị viên vào tháng 4](https://www.bleepingcomputer.com/news/security/cisco-warns-of-cslu-backdoor-admin-account-used-in-attacks/) để vá lỗ hổng quan trọng của Cisco Smart Licensing Utility (CSLU) mà phơi bày một tài khoản quản trị viên backdoor tích hợp được sử dụng trong các cuộc tấn công. Một tháng sau, công ty [đã loại bỏ một JSON Web Token (JWT) cứng](https://www.bleepingcomputer.com/news/security/cisco-fixes-max-severity-ios-xe-flaw-letting-attackers-hijack-devices/) cho phép các kẻ tấn công từ xa không được xác thực chiếm quyền kiểm soát các thiết bị IOS XE.