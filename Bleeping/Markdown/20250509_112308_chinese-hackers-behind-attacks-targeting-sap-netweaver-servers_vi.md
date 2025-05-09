+-+-+-+-+-+-
# Các tin tặc Trung Quốc đứng sau các cuộc tấn công nhắm vào máy chủ SAP NetWeaver

![SAP](https://www.bleepstatic.com/content/hl-images/2022/02/09/SAP.jpg)

Các nhà nghiên cứu an ninh Forescout Vedere Labs đã liên kết các cuộc tấn công đang diễn ra nhắm vào một lỗ hổng nghiêm trọng nhất ảnh hưởng đến các phiên bản SAP NetWeaver với một tác nhân đe dọa đến từ Trung Quốc.

SAP [đã phát hành một bản vá khẩn cấp ngoài chu kỳ](https://www.bleepingcomputer.com/news/security/sap-fixes-suspected-netweaver-zero-day-exploited-in-attacks/) vào ngày 24 tháng 4 để khắc phục lỗ hổng bảo mật cho phép tải lên tệp không xác thực (được theo dõi là [CVE-2025-31324](https://nvd.nist.gov/vuln/detail/CVE-2025-31324)) trong SAP NetWeaver Visual Composer, vài ngày sau khi công ty an ninh mạng [ReliaQuest](https://reliaquest.com/blog/threat-spotlight-reliaquest-uncovers-vulnerability-behind-sap-netweaver-compromise/) lần đầu tiên phát hiện lỗ hổng này bị nhắm đến trong các cuộc tấn công.

Việc khai thác thành công cho phép các kẻ tấn công không xác thực tải lên các tệp độc hại mà không cần đăng nhập, cho phép họ đạt được khả năng thực thi mã từ xa và có thể dẫn đến việc chiếm quyền hoàn toàn hệ thống.

ReliaQuest báo cáo rằng nhiều hệ thống của các khách hàng đã bị xâm nhập qua các tệp tải lên không được ủy quyền trên SAP NetWeaver, với các tác nhân đe dọa tải lên các shell JSP vào các thư mục công khai, cũng như công cụ Brute Ratel trong giai đoạn sau khai thác của các cuộc tấn công của họ. Các máy chủ SAP NetWeaver bị xâm phạm đã được vá đầy đủ, cho thấy rằng các kẻ tấn công đã sử dụng một khai thác zero-day.

Hoạt động khai thác này cũng đã được xác nhận bởi các công ty an ninh mạng khác, bao gồm watchTowr và [Onapsis](https://onapsis.com/blog/active-exploitation-of-sap-vulnerability-cve-2025-31324/), những người cũng xác nhận rằng các kẻ tấn công đang tải lên các backdoor shell web trên các phiên bản chưa được vá đang bị lộ ra trên mạng.

Mandiant [cũng đã quan sát thấy](https://www.linkedin.com/posts/charlescarmakal%5Factive-exploitation-of-sap-zero-day-vulnerability-activity-7321721880543965185-TK9Z/) các cuộc tấn công zero-day CVE-2025-31324 từ ít nhất giữa tháng 3 năm 2025, trong khi Onapsis đã cập nhật báo cáo ban đầu của mình để nói rằng honeypot của họ lần đầu tiên ghi nhận hoạt động trinh sát và thử nghiệm payload từ ngày 20 tháng 1, với các nỗ lực khai thác bắt đầu vào ngày 10 tháng 2.

Quỹ Shadowserver hiện đang [theo dõi 204 máy chủ SAP Netweaver](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=other%5Frange&d1=2025-04-25&d2=2025-05-08&source=http%5Fvulnerable&source=http%5Fvulnerable6&tag=cve-2025-31324%2B&dataset=unique%5Fips&limit=1000&group%5Fby=geo&stacking=stacked) đang bị lộ ra trên mạng và dễ bị tấn công CVE-2025-31324.

CTO Onyphe Patrice Auffret cũng đã nói với BleepingComputer vào cuối tháng 4 rằng "Khoảng 20 công ty Fortune 500/Global 500 đang bị tổn thương, và nhiều trong số đó đã bị xâm phạm," đồng thời cho biết tại thời điểm này, có 1,284 phiên bản dễ bị tổn thương đang bị lộ ra trên mạng, trong đó 474 phiên bản đã bị xâm phạm.

![Các phiên bản SAP NetWeaver dễ bị tổn thương bị lộ ra trên mạng](https://www.bleepstatic.com/images/news/u/1109292/2025/SAP_NetWeaver_vulnerable_exposed.jpg)

_Các phiên bản SAP NetWeaver dễ bị tổn thương bị lộ ra trên mạng (Quỹ Shadowserver)_

## ​Các cuộc tấn công gắn liền với tin tặc Trung Quốc

Các cuộc tấn công gần đây hơn vào ngày 29 tháng 4 đã được liên kết với một tác nhân đe dọa từ Trung Quốc được theo dõi bởi [Forescout's Vedere Labs](http://www.forescout.com/blog/threat-analysis-sap-vulnerability-exploited-in-the-wild-by-chinese-threat-actor/) với mã Chaya\_004.

Các cuộc tấn công này được phát động từ các địa chỉ IP sử dụng chứng chỉ tự kí khác thường giả mạo Cloudflare, nhiều trong số đó thuộc về các nhà cung cấp dịch vụ đám mây của Trung Quốc (ví dụ: Alibaba, Shenzhen Tencent, Dịch vụ đám mây Huawei và China Unicom).

Kẻ tấn công cũng đã triển khai các công cụ tiếng Trung trong quá trình tấn công, bao gồm một reverse shell dựa trên web (SuperShell) được phát triển bởi một nhà phát triển nói tiếng Trung.

"Như một phần trong cuộc điều tra của chúng tôi về việc khai thác đang diễn ra của lỗ hổng này, chúng tôi đã phát hiện ra cơ sở hạ tầng độc hại có khả năng thuộc về một tác nhân đe dọa từ Trung Quốc, mà chúng tôi hiện đang theo dõi là Chaya\_004 - theo quy ước của chúng tôi cho các tác nhân đe dọa không được đặt tên," Forescout cho biết.

"Cơ sở hạ tầng này bao gồm một mạng lưới máy chủ lưu trữ các backdoor Supershell, thường được triển khai trên các nhà cung cấp dịch vụ đám mây của Trung Quốc, và nhiều công cụ kiểm tra thâm nhập, nhiều trong số đó có nguồn gốc từ Trung Quốc."

Các quản trị viên SAP được khuyên nên ngay lập tức vá các phiên bản NetWeaver của họ, hạn chế quyền truy cập vào các dịch vụ tải lên siêu dữ liệu, theo dõi các hoạt động đáng ngờ trên máy chủ của họ và xem xét việc vô hiệu hóa dịch vụ Visual Composer nếu có thể.

CISA cũng đã [thêm vào](https://www.cisa.gov/news-events/alerts/2025/04/29/cisa-adds-one-known-exploited-vulnerability-catalog) lỗ hổng bảo mật CVE-2025-31324 vào [Danh sách các lỗ hổng đã được khai thác](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-31324&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=) của mình cách đây một tuần, yêu cầu các cơ quan liên bang của Mỹ phải bảo vệ hệ thống của họ chống lại các cuộc tấn công này trước ngày 20 tháng 5, theo yêu cầu của [Chỉ thị hoạt động ràng buộc (BOD) 22-01](https://www.cisa.gov/binding-operational-directive-22-01).

"Các loại lỗ hổng này là các vectơ tấn công thường xuyên của các tác nhân mạng độc hại và đặt ra rủi ro nghiêm trọng cho doanh nghiệp liên bang," CISA cảnh báo.