# Các băng nhóm Ransomware tham gia các cuộc tấn công SAP NetWeaver đang diễn ra

![SAP](https://www.bleepstatic.com/content/hl-images/2025/05/14/SAP.jpg)

Các băng nhóm ransomware đã tham gia các cuộc tấn công SAP NetWeaver đang diễn ra, khai thác một lỗ hổng nghiêm trọng tối đa cho phép các tác nhân đe dọa thực hiện mã từ xa trên các máy chủ bị tổn thương.

SAP [đã phát hành các bản vá khẩn cấp](https://www.bleepingcomputer.com/news/security/sap-fixes-suspected-netweaver-zero-day-exploited-in-attacks/) vào ngày 24 tháng 4 để giải quyết lỗ hổng bảo mật tải lên tệp không xác thực của NetWeaver Visual Composer ([CVE-2025-31324](https://nvd.nist.gov/vuln/detail/CVE-2025-31324)), vài ngày sau khi nó được công ty an ninh mạng ReliaQuest đánh dấu lần đầu tiên là mục tiêu trong tự nhiên.

Việc khai thác thành công cho phép các tác nhân đe dọa tải lên các tệp độc hại mà không cần yêu cầu thông tin đăng nhập, có thể dẫn đến việc chiếm đoạt hoàn toàn hệ thống.

Hôm nay, trong một bản cập nhật cho bản thông báo ban đầu của họ, [ReliaQuest](https://reliaquest.com/blog/threat-spotlight-reliaquest-uncovers-vulnerability-behind-sap-netweaver-compromise/)[đã tiết lộ](https://reliaquest.com/blog/threat-spotlight-reliaquest-uncovers-vulnerability-behind-sap-netweaver-compromise/) rằng các hoạt động ransomware RansomEXX và BianLian cũng đã tham gia vào các cuộc tấn công này.

"Phân tích liên tục đã phát hiện ra các bằng chứng cho thấy sự tham gia của nhóm ransomware Nga 'BianLian' và các nhà điều hành của gia đình ransomware 'RansomEXX' (được Microsoft theo dõi là 'Storm-2460')," công ty an ninh mạng cho biết. "Những phát hiện này cho thấy sự quan tâm rộng rãi trong việc khai thác lỗ hổng này trên nhiều nhóm đe dọa."

ReliaQuest liên kết BianLian với ít nhất một sự cố với "mức độ tự tin trung bình" dựa trên một địa chỉ IP mà các nhà điều hành băng nhóm ransomware đã sử dụng trong quá khứ để lưu trữ một trong những máy chủ chỉ huy và kiểm soát (C2) của họ.

Trong các cuộc tấn công RansomEXX, các tác nhân đe dọa đã triển khai backdoor mô-đun PipeMagic của băng nhóm và khai thác lỗ hổng Windows CLFS CVE-2025-29824 [đã bị lạm dụng trong các sự cố trước đó](https://www.bleepingcomputer.com/news/security/microsoft-windows-clfs-zero-day-exploited-by-ransomware-gang/) liên quan đến hoạt động ransomware này.

"Phần mềm độc hại đã được triển khai chỉ vài giờ sau khi khai thác toàn cầu liên quan đến các webshell helper.jsp và cache.jsp. Mặc dù nỗ lực ban đầu thất bại, một cuộc tấn công tiếp theo đã liên quan đến việc triển khai khung C2 Brute Ratel bằng cách sử dụng thực thi tác vụ MSBuild inline," ReliaQuest thêm vào.

## Cũng bị khai thác bởi các nhóm hacker Trung Quốc

Các nhà nghiên cứu bảo mật Forescout Vedere Labs cũng đã [liên kết các cuộc tấn công đang diễn ra này](https://www.bleepingcomputer.com/news/security/chinese-hackers-behind-attacks-targeting-sap-netweaver-servers/) với một tác nhân đe dọa Trung Quốc mà họ theo dõi là Chaya\_004, trong khi EclecticIQ [đã báo cáo vào thứ Ba](https://blog.eclecticiq.com/china-nexus-nation-state-actors-exploit-sap-netweaver-cve-2025-31324-to-target-critical-infrastructures) rằng ba APT Trung Quốc khác (tức là UNC5221, UNC5174, và CL-STA-0048) cũng đang nhắm mục tiêu đến các phiên bản NetWeaver chưa được vá chống lại CVE-2025-31324.

Dựa trên các tệp bị lộ được tìm thấy trong một thư mục có sẵn công khai trên một trong những máy chủ không an toàn của các kẻ tấn công này, Forescout cho biết họ đã thực hiện backdoor ít nhất 581 phiên bản SAP NetWeaver (bao gồm cơ sở hạ tầng quan trọng ở Vương quốc Anh, Hoa Kỳ và Ả Rập Saudi) và dự định nhắm mục tiêu đến thêm 1.800 miền khác.

"Quyền truy cập backdoor bền vững vào các hệ thống này cung cấp một chỗ đứng cho các APT liên kết với Trung Quốc, có thể cho phép các mục tiêu chiến lược của Cộng hòa Nhân dân Trung Hoa (PRC), bao gồm lợi thế quân sự, tình báo hoặc kinh tế," Forescout cho biết.

"Các hệ thống SAP bị xâm phạm cũng được kết nối chặt chẽ với mạng nội bộ của hệ thống điều khiển công nghiệp (ICS) mà đặt ra rủi ro di chuyển bên, có thể gây gián đoạn dịch vụ cho hoạt động gián điệp lâu dài."

Vào thứ Hai, SAP cũng đã vá một lỗ hổng NetWeaver thứ hai ([CVE-2025-42999](https://www.cve.org/CVERecord?id=CVE-2025-42999)) liên kết trong các cuộc tấn công này như một zero-day từ tháng Ba để thực hiện các lệnh tùy ý từ xa.

Để chặn các nỗ lực xâm nhập, các quản trị viên SAP nên ngay lập tức vá các máy chủ NetWeaver của họ hoặc xem xét việc vô hiệu hóa dịch vụ Visual Composer nếu không thể nâng cấp. Giới hạn quyền truy cập vào các dịch vụ tải lên metadata và theo dõi các hoạt động đáng ngờ trên máy chủ của họ cũng rất được khuyến nghị.

CISA [đã thêm](https://www.cisa.gov/news-events/alerts/2025/04/29/cisa-adds-one-known-exploited-vulnerability-catalog) lỗ hổng CVE-2025-31324 vào [Catalog lỗ hổng đã biết bị khai thác](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-31324&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=) của họ hai tuần trước, yêu cầu các cơ quan liên bang đảm bảo an toàn cho các máy chủ của họ trước ngày 20 tháng 5, theo yêu cầu của [Chỉ thị hoạt động ràng buộc (BOD) 22-01](https://www.cisa.gov/binding-operational-directive-22-01).