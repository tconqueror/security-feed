# Cisco cảnh báo về các lỗ hổng RCE nghiêm trọng tối đa trong Cisco Identity Services Engine

![Cisco](https://www.bleepstatic.com/content/hl-images/2025/03/04/Cisco_headpic.jpg)

Cisco đã phát hành một thông báo để cảnh báo về hai lỗ hổng thực thi mã từ xa (RCE) nghiêm trọng, không cần xác thực, ảnh hưởng đến Cisco Identity Services Engine (ISE) và Passive Identity Connector (ISE-PIC).

Các lỗ hổng này được theo dõi dưới [CVE-2025-20281](https://nvd.nist.gov/vuln/detail/CVE-2025-20281) và [CVE-2025-20282](https://nvd.nist.gov/vuln/detail/CVE-2025-20282), được đánh giá có độ nghiêm trọng tối đa (điểm số CVSS: 10.0). Lỗ hổng đầu tiên ảnh hưởng đến các phiên bản ISE và ISE-PIC 3.4 và 3.3, trong khi lỗ hổng thứ hai chỉ ảnh hưởng đến phiên bản 3.4.

Nguyên nhân gốc rễ của CVE-2025-20281 là do xác thực không đủ đối với đầu vào do người dùng cung cấp trong một API bị lộ cụ thể. Điều này cho phép một kẻ tấn công từ xa, không cần xác thực, gửi một yêu cầu API được chế tạo đặc biệt để thực thi các lệnh hệ điều hành tùy ý với quyền người dùng root.

Vấn đề thứ hai, CVE-2025-20282, được gây ra bởi việc xác thực tệp kém trong một API nội bộ, cho phép các tệp được ghi vào các thư mục có quyền ưu đãi. Lỗ hổng cho phép những kẻ tấn công từ xa không cần xác thực tải lên các tệp tùy ý vào hệ thống mục tiêu và thực thi chúng với quyền root.

Cisco Identity Services Engine (ISE) là một nền tảng quản lý chính sách bảo mật mạng và kiểm soát truy cập được các tổ chức sử dụng để quản lý các kết nối mạng của họ, đóng vai trò như một công cụ kiểm soát truy cập mạng (NAC), quản lý danh tính và thực thi chính sách.

Sản phẩm này thường được sử dụng bởi các doanh nghiệp lớn, tổ chức chính phủ, trường đại học và nhà cung cấp dịch vụ, nằm trung tâm của mạng doanh nghiệp.

Hai lỗ hổng ảnh hưởng đến nó có thể cho phép hoàn toàn xâm phạm và chiếm đoạt từ xa thiết bị mục tiêu mà không cần xác thực hoặc tương tác của người dùng.

Cisco [đã lưu ý trong thông báo](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-ise-unauth-rce-ZAd2GnJ6) rằng họ không biết về bất kỳ trường hợp khai thác tích cực nào cho hai lỗ hổng này, nhưng việc cài đặt các bản cập nhật mới nên được ưu tiên.

Người dùng được khuyến nghị nâng cấp lên 3.3 Patch 6 (ise-apply-CSCwo99449\_3.3.0.430\_patch4) và 3.4 Patch 2 (ise-apply-CSCwo99449\_3.4.0.608\_patch1) hoặc mới hơn. Không có giải pháp nào được cung cấp để giảm thiểu các lỗ hổng, vì vậy việc áp dụng các bản cập nhật bảo mật là giải pháp được khuyến nghị.

Cisco cũng [đã công bố một thông báo riêng](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-ise-auth-bypass-mVfKVQAU) liên quan đến một lỗ hổng vượt qua xác thực có độ nghiêm trọng trung bình, được theo dõi là [CVE-2025-20264](https://nvd.nist.gov/vuln/detail/CVE-2025-20264), cũng ảnh hưởng đến ISE.

Lỗ hổng này được gây ra bởi việc thực thi không đủ phép quyền cho người dùng được tạo thông qua tích hợp SAML SSO với nhà cung cấp danh tính bên ngoài. Một kẻ tấn công có quyền xác thực SSO hợp lệ có thể gửi một chuỗi các lệnh cụ thể để sửa đổi cài đặt hệ thống hoặc thực hiện khởi động lại hệ thống.

CVE-2025-20264 ảnh hưởng đến tất cả các phiên bản của ISE cho đến nhánh 3.4. Các bản sửa lỗi đã được cung cấp trong 3.4 Patch 2 và 3.3 Patch 5. Nhà cung cấp đã hứa sẽ sửa lỗ hổng cho 3.2 với việc phát hành 3.2 Patch 8, dự kiến vào tháng 11 năm 2025.

ISE 3.1 và các phiên bản trước cũng bị ảnh hưởng nhưng không còn được hỗ trợ, và người dùng được khuyến nghị chuyển sang nhánh phát hành mới hơn.