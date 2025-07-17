# Lỗi nghiêm trọng nhất trong Cisco ISE cho phép thực thi lệnh trước xác thực, hãy vá ngay

![Lỗi nghiêm trọng nhất trong Cisco ISE cho phép thực thi lệnh trước xác thực, hãy vá ngay](https://www.bleepstatic.com/content/hl-images/2025/03/04/Cisco-headpic.jpg)

Một lỗ hổng nghiêm trọng (CVE-2025-20337) trong Cisco's Identity Services Engine (ISE) có thể bị khai thác để cho phép một kẻ tấn công không xác thực lưu trữ các tệp độc hại, thực thi mã tùy ý hoặc có được quyền root trên các thiết bị dễ bị tổn thương.

Vấn đề bảo mật nhận được đánh giá mức độ nghiêm trọng cao nhất, 10 trên 10, và được gây ra bởi việc kiểm tra xác thực đầu vào do người dùng cung cấp không đầy đủ.

Nó được phát hiện bởi Kentaro Kawane, một nhà nghiên cứu tại dịch vụ an ninh mạng Nhật Bản GMO Cybersecurity bởi Ierae, và được báo cáo bởi Trend Micro's Zero Day Initiative (ZDI).

Một kẻ tấn công từ xa không xác thực có thể tận dụng bằng cách gửi yêu cầu API được tạo đặc biệt.

Lỗ hổng này đã được thêm vào thông qua một [cập nhật cho thông báo bảo mật](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-ise-unauth-rce-ZAd2GnJ6) cho CVE-2025-20281 và CVE-2025-20282, hai [lỗ hổng RCE tương tự](https://www.bleepingcomputer.com/news/security/cisco-warns-of-max-severity-rce-flaws-in-identity-services-engine/) cũng nhận được điểm số độ nghiêm trọng cao nhất, ảnh hưởng đến các phiên bản ISE và ISE-PIC 3.4 và 3.3.

"Những lỗ hổng này ảnh hưởng đến các phiên bản Cisco ISE và ISE-PIC 3.3 và 3.4, bất kể cấu hình thiết bị," nhà cung cấp lưu ý cho CVE-2025-20281 và CVE-2025-20337, đồng thời cho biết "những lỗ hổng này không ảnh hưởng đến các phiên bản Cisco ISE và ISE-PIC 3.2 hoặc trước đó."

Bất kỳ vấn đề bảo mật nào trong ba vấn đề này đều có thể bị khai thác độc lập.

Cisco cũng cảnh báo rằng khách hàng đã áp dụng bản vá cho CVE-2025-20281 và CVE-2025-20282 không được bảo vệ khỏi CVE-2025-20337, và cần nâng cấp lên ISE 3.3 Patch 7 hoặc ISE 3.4 Patch 2.

Các phiên bản sản phẩm dưới đây là những phiên bản duy nhất hiện được xác nhận để giải quyết tất cả ba lỗ hổng nghiêm trọng nhất. Không có giải pháp thay thế hoặc biện pháp giảm thiểu nào khác có sẵn.

![Bảng](https://www.bleepstatic.com/images/news/u/1220909/2025/July/table.png)

Mặc dù chưa có bất kỳ vụ khai thác nào trong ba lỗ hổng này được quan sát trong thực tế cho đến nay, nhưng đã khuyến nghị rằng các quản trị viên hệ thống thực hiện hành động ngay lập tức để giảm thiểu các rủi ro.

Cũng vào hôm qua, Cisco đã phát hành thêm bốn thông báo bao gồm các lỗ hổng khác trong sản phẩm của hãng, được tóm tắt như sau:

* [CVE-2025-20274](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-cuis-file-upload-UhNEtStm): Lỗ hổng tải lên tệp tùy ý mức độ nghiêm trọng cao ảnh hưởng đến Trung tâm Tình báo Hợp nhất của Cisco, bao gồm các bộ Unified CCX. Người dùng đã xác thực với quyền Thiết kế Báo cáo có thể tải lên các tệp độc hại và có thể thực thi chúng với quyền root. Đã được khắc phục trong các phiên bản 12.5(1) SU ES05 và 12.6(2) ES05.
* [CVE-2025-20272](http://Base%204.3%20CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:U/C:L/I:N/A:N/E:X/RL:X/RC:X): Lỗ hổng SQL injection mù mức độ nghiêm trọng trung bình trong Cisco Prime Infrastructure và EPNM. Người dùng có quyền thấp có thể khai thác API REST để trích xuất nội dung cơ sở dữ liệu không hợp pháp. Đã được giải quyết trong Prime Infrastructure 3.10.6 SU2 và các phiên bản EPNM 8.0.1 và 8.1.1.
* [CVE-2025-20283, CVE-2025-20284, CVE-2025-20285](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-ise-multi-3VpsXOxO): Lỗ hổng RCE đã xác thực và lỗ hổng vượt qua hạn chế truy cập IP mức độ nghiêm trọng trung bình trong Cisco ISE và ISE-PIC. Người dùng có quyền cao có thể thực thi các lệnh với quyền root hoặc đăng nhập từ các địa chỉ IP không được phép. Ảnh hưởng đến các phiên bản 3.3 và 3.4; đã được khắc phục trong 3.3 Patch 7 và 3.4 Patch 2.
* [CVE-2025-20288](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-cuis-ssrf-JSuDjeV): Lỗ hổng SSRF mức độ nghiêm trọng trung bình trong Cisco Unified Intelligence Center, có thể khai thác mà không cần xác thực. Cho phép các kẻ tấn công gửi các yêu cầu nội bộ tùy ý qua hệ thống bị ảnh hưởng. Ảnh hưởng đến các phiên bản 12.5 và 12.6, bao gồm các bộ Unified CCX. Đã được khắc phục trong 12.5(1) SU ES05 và 12.6(2) ES05.