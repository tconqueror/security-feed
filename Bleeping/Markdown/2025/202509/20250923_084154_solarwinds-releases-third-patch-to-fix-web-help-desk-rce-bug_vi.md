# SolarWinds phát hành bản vá thứ ba để sửa lỗ hổng RCE trong Web Help Desk

![SolarWinds](https://www.bleepstatic.com/content/hl-images/2024/02/16/solarwinds_headpic.jpg)

SolarWinds đã phát hành một bản sửa lỗi (hotfix) cho một lỗ hổng nghiêm trọng trong Web Help Desk cho phép thực thi mã từ xa (RCE) mà không cần xác thực.

Được theo dõi với mã CVE-2025-26399, vấn đề bảo mật này là nỗ lực thứ ba của công ty để khắc phục một lỗ hổng cũ hơn được xác định là CVE-2024-28986 ảnh hưởng đến Web Help Desk (WHD) 12.8.3 và tất cả các phiên bản trước đó.

SolarWinds WHD là một bộ phần mềm help desk và quản lý ticket được các tổ chức vừa đến lớn sử dụng để theo dõi yêu cầu hỗ trợ IT, tự động hóa quy trình làm việc, quản lý tài sản và đảm bảo tuân thủ.

CVE-2025-26399 ảnh hưởng đến phiên bản WHD mới nhất 12.8.7 và do xử lý deserialization không an toàn trong thành phần AjaxProxy. Nếu khai thác thành công, kẻ tấn công không cần xác thực có thể chạy các lệnh trên máy chủ.

Trong một [thông báo bảo mật](http://documentation.solarwinds.com/en/success%5Fcenter/whd/content/release%5Fnotes/whd%5F12-8-7-hotfix-1%5Frelease%5Fnotes.htm), nhà cung cấp cho biết rằng "lỗ hổng này là một patch bypass của CVE-2024-28988, mà lại là một patch bypass của CVE-2024-28986."

Vào tháng 8 năm ngoái, U.S. Cybersecurity and Infrastructure Security Agency (CISA) đã đánh dấu lỗ hổng SolarWinds ban đầu là đã bị [lợi dụng trong các cuộc tấn công](https://www.bleepingcomputer.com/news/security/cisa-warns-critical-solarwinds-rce-bug-is-exploited-in-attacks/) và thêm nó vào danh mục Known Exploited Vulnerabilities (KEV).

Vấn đề bảo mật mới này đã được báo cáo cho SolarWinds thông qua Trend Micro Zero Day Initiative (ZDI). Tại thời điểm viết bài chưa có báo cáo công khai nào về việc các tác nhân đe dọa lợi dụng nó.

## Bản hotfix có sẵn

SolarWinds đã phát hành một hotfix giải quyết CVE-2025-26399, yêu cầu cài đặt Web Help Desk phiên bản 12.8.7. Để áp dụng bản cập nhật bảo mật, người dùng được khuyên làm theo các bước sau:

1. Dừng Web Help Desk
2. Điều hướng tới: <WebHelpDesk>/bin/webapps/helpdesk/WEB-INF/lib/ (thay thế <WebHelpDesk> tùy theo hệ điều hành)
3. Sao lưu rồi xóa: c3p0.jar
4. Sao lưu (vào thư mục riêng): whd-core.jar, whd-web.jar, whd-persistence.jar
5. Sao chép các JAR do hotfix cung cấp vào cùng thư mục /lib, ghi đè các tệp gốc: whd-core.jar, whd-web.jar, whd-persistence.jar, và thêm HikariCP.jar
6. Khởi động lại Web Help Desk

Hotfix chỉ có sẵn thông qua SolarWinds [Customer Portal](https://customerportal.solarwinds.com/). Thông tin thêm về cách nâng cấp WHD [có tại đây](https://documentation.solarwinds.com/en/success%5Fcenter/whd/content/helpdeskupgradewhd.htm).