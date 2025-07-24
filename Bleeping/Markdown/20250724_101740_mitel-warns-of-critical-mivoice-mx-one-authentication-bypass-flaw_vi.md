# Mitel cảnh báo về lỗ hổng vượt qua xác thực nghiêm trọng trong MiVoice MX-ONE

![Mitel](https://www.bleepstatic.com/content/hl-images/2025/07/24/Mitel.jpg)

Mitel Networks đã phát hành cập nhật bảo mật để sửa chữa lỗ hổng nghiêm trọng về xác thực vượt qua ảnh hưởng đến nền tảng truyền thông doanh nghiệp MiVoice MX-ONE của họ.

MX-ONE là hệ thống truyền thông dựa trên SIP của công ty, có thể mở rộng để hỗ trợ hàng trăm nghìn người dùng.

Lỗ hổng bảo mật nghiêm trọng này do một lỗ hổng kiểm soát truy cập không đúng cách được phát hiện trong thành phần Quản lý cấp phát MiVoice MX-ONE và vẫn chưa được gán ID CVE. Kẻ tấn công không xác thực có thể khai thác nó trong các cuộc tấn công có độ phức tạp thấp mà không yêu cầu tương tác của người dùng để giành quyền truy cập trái phép vào tài khoản quản trị trên các hệ thống chưa được vá.

Theo Mitel, lỗ hổng này ảnh hưởng đến MiVoice MX-ONE chạy các phiên bản từ 7.3 (7.3.0.0.50) đến 7.8 SP1 (7.8.1.0.14) và đã được vá trong các phiên bản 7.8 (MXO-15711_78SP0) và 7.8 SP1 (MXO-15711_78SP1).

"Không để lộ dịch vụ MX-ONE ra công khai trên internet. Đảm bảo rằng hệ thống MX-ONE được triển khai trong một mạng tin cậy. Rủi ro có thể được giảm bớt bằng cách hạn chế quyền truy cập vào dịch vụ Quản lý cấp phát," [Mitel cho biết](https://www.mitel.com/support/security-advisories/mitel-product-security-advisory-misa-2025-0009).

Khách hàng đang chạy phiên bản MiVoice MX-ONE từ 7.3 trở lên được khuyên nên gửi yêu cầu vá cho công ty thông qua đối tác dịch vụ được ủy quyền của họ.

Hôm nay, Mitel cũng đã công bố một [lỗ hổng SQL injection độ nghiêm trọng cao](https://www.mitel.com/support/security-advisories/mitel-product-security-advisory-misa-2025-0008) (CVE-2025-52914) trong nền tảng cộng tác MiCollab của họ, có thể bị lạm dụng để thực thi các lệnh cơ sở dữ liệu SQL tùy ý trên các thiết bị chưa được vá.

Trong khi hai lỗi bảo mật này chưa được gán nhãn là đã bị khai thác trong thực tế, CISA [đã cảnh báo các cơ quan liên bang của Hoa Kỳ](https://www.bleepingcomputer.com/news/security/cisa-warns-of-critical-oracle-mitel-flaws-exploited-in-attacks/) vào tháng Giêng về lỗ hổng truy cập đường dẫn MiCollab (CVE-2024-55550) đã được sử dụng trong các cuộc tấn công và cho phép các kẻ tấn công đã xác thực với quyền quản trị đọc các tệp tùy ý trên các máy chủ dễ bị tấn công.

Một tháng trước đó, công ty đã [vá một lỗi zero-day đọc tệp tùy ý trong MiCollab](https://www.bleepingcomputer.com/news/security/mitel-micollab-zero-day-flaw-gets-proof-of-concept-exploit/) (CVE-2024-41713) được phát hiện bởi các nhà nghiên cứu của watchTowr Labs, có thể cho phép kẻ tấn công truy cập các tệp trên hệ thống tệp của máy chủ.

Sản phẩm của Mitel được hơn 60.000 khách hàng và hơn 75 triệu người dùng sử dụng trong nhiều lĩnh vực khác nhau, bao gồm giáo dục, y tế, dịch vụ tài chính, sản xuất và chính phủ.