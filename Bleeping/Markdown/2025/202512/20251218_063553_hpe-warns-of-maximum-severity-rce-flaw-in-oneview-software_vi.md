# HPE cảnh báo lỗ hổng RCE mức độ tối đa trong phần mềm OneView

[![Hewlett Packard Enterprise HPE](https://www.bleepstatic.com/content/hl-images/2025/12/18/Hewlett_Packard_Enterprise_HPE.jpg)](https://www.bleepingcomputer.com/news/security/hpe-warns-of-hardcoded-passwords-in-aruba-access-points/)

Hewlett Packard Enterprise (HPE) đã vá một lỗ hổng mức độ tối đa trong phần mềm HPE OneView cho phép kẻ tấn công thực thi mã tùy ý từ xa.

OneView là phần mềm quản lý hạ tầng của HPE giúp quản trị viên CNTT đơn giản hóa hoạt động và tự động hóa quản lý máy chủ, bộ lưu trữ và thiết bị mạng từ một giao diện tập trung.

Lỗ hổng bảo mật nghiêm trọng này ([CVE-2025-37164](https://nvd.nist.gov/vuln/detail/CVE-2025-37164)) đã được nhà nghiên cứu bảo mật người Việt Nguyen Quoc Khanh (brocked200) báo cáo cho đội ngũ bảo mật của công ty.

[![Wiz](https://www.bleepstatic.com/content/webinar-images/Action1-970x250-watch-now.jpg)](/mgo/72/) 

Lỗ hổng ảnh hưởng tới tất cả các phiên bản OneView phát hành trước v11.00 và có thể bị tác nhân đe dọa chưa xác thực lợi dụng trong các cuộc tấn công chèn mã có độ phức tạp thấp để giành quyền thực thi mã từ xa trên các hệ thống chưa được vá.

"Một lỗ hổng bảo mật tiềm ẩn đã được xác định trong Hewlett Packard Enterprise OneView Software. Lỗ hổng này có thể bị khai thác, cho phép một người dùng từ xa chưa xác thực thực hiện thực thi mã từ xa," HPE cảnh báo trong một [thông báo hôm thứ Ba](https://support.hpe.com/hpesc/public/docDisplay?docId=hpesbgn04985en%5Fus&docLocale=en%5FUS#vulnerability-summary-1).

Không có biện pháp khắc phục tạm thời hay giảm nhẹ nào cho CVE-2025-37164, vì vậy các quản trị viên được khuyên vá các hệ thống bị ảnh hưởng càng sớm càng tốt.

HPE chưa xác nhận liệu lỗ hổng này đã bị nhắm mục tiêu trong các cuộc tấn công hay chưa và cho biết các tổ chức bị ảnh hưởng có thể nâng cấp lên OneView phiên bản 11.00 trở lên, có sẵn [qua Software Center của HPE](https://myenterpriselicense.hpe.com/cwp-ui/product-download-info/Z7550-63180/-/sw%5Ffree), để vá.

Trên các thiết bị chạy OneView từ phiên bản 5.20 đến 10.20, lỗ hổng có thể được khắc phục bằng cách triển khai một bản hotfix bảo mật, cần được áp dụng lại sau khi nâng cấp từ phiên bản 6.60 trở lên lên phiên bản 7.00.00, hoặc sau bất kỳ thao tác tái tạo hình ảnh (reimaging) HPE Synergy Composer nào.

Các bản tải xuống riêng biệt có sẵn cho [hotfix bảo mật cho virtual appliance](https://myenterpriselicense.hpe.com/cwp-ui/product-details/HPE%5FOV%5FCVE%5F37164%5FZ7550-98077/-/sw%5Ffree) và [hotfix bảo mật cho Synergy](https://support.hpe.com/hpesc/public/swd/detail?swCollectionId=MTX-64daeb5ed0df44a0) thông qua các trang hỗ trợ chuyên dụng.

Vào tháng Sáu, HPE đã vá tám lỗ hổng trong StoreOnce, giải pháp sao lưu dựa trên đĩa và khử trùng lặp của hãng, bao gồm một lỗ hổng bỏ qua xác thực mức độ nghiêm trọng cao và ba lỗ hổng thực thi mã từ xa.

Một tháng sau, vào tháng Bảy, đơn vị này cảnh báo về thông tin đăng nhập được mã hóa cứng (hardcoded credentials) trong Aruba Instant On Access Points có thể cho phép kẻ tấn công truy cập giao diện web sau khi vượt qua xác thực thiết bị tiêu chuẩn.

HPE có hơn 61.000 nhân viên trên toàn cầu và đã báo cáo doanh thu 30,1 tỷ đô la vào năm 2024. Sản phẩm và dịch vụ của công ty được sử dụng bởi hơn 55.000 tổ chức trên toàn thế giới, bao gồm 90% các công ty trong Fortune 500.