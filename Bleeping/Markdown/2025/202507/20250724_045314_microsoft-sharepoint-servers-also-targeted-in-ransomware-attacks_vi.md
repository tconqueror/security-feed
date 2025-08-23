# Microsoft: Các máy chủ SharePoint cũng bị tấn công trong các cuộc tấn công ransomware

![Windows logo](https://www.bleepstatic.com/content/hl-images/2024/05/24/windows-logo-locked.jpg)

Một nhóm hacker Trung Quốc đang triển khai ransomware Warlock trên các máy chủ Microsoft SharePoint dễ bị tấn công trong các cuộc tấn công rộng rãi nhắm mục tiêu đến chuỗi khai thác zero-day ToolShell đã [được vá gần đây](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-emergency-patches-for-sharepoint-rce-flaws-exploited-in-attacks/).

Được theo dõi như Storm-2603, các diễn viên đe dọa có trụ sở tại Trung Quốc này trước đó cũng đã được các nhà nghiên cứu của Microsoft liên kết với các cuộc tấn công ransomware Lockbit.

"Microsoft theo dõi diễn viên đe dọa này liên quan đến các nỗ lực ăn cắp MachineKeys bằng cách sử dụng các lỗ hổng trên SharePoint tại chỗ," công ty [cho biết](https://www.microsoft.com/en-us/security/blog/2025/07/22/disrupting-active-exploitation-of-on-premises-sharepoint-vulnerabilities/#storm-2603) trong một báo cáo vào thứ Tư. "Bắt đầu từ ngày 18 tháng 7 năm 2025, Microsoft đã quan sát thấy Storm-2603 triển khai ransomware bằng cách sử dụng các lỗ hổng này."

Sau khi xâm nhập vào mạng của nạn nhân, các nhà điều hành Storm-2603 sử dụng công cụ hacking Mimikatz để trích xuất thông tin xác thực ở dạng văn bản từ bộ nhớ LSASS.

Họ sau đó di chuyển ngang qua PsExec và bộ công cụ Impacket, thực thi lệnh thông qua Windows Management Instrumentation (WMI), và chỉnh sửa Group Policy Objects (GPOs) để phát tán ransomware Warlock trên các hệ thống bị xâm nhập.

"Nhóm mà Microsoft theo dõi là Storm-2603 được đánh giá với độ tin cậy vừa phải là một diễn viên đe dọa có trụ sở tại Trung Quốc. Microsoft chưa xác định được mối liên hệ giữa Storm-2603 và các diễn viên đe dọa Trung Quốc khác đã biết," công ty còn cho biết.

"Khách hàng nên áp dụng các bản cập nhật bảo mật dành cho SharePoint Server tại chỗ ngay lập tức và làm theo hướng dẫn giảm thiểu chi tiết trong blog của chúng tôi," Microsoft [cảnh báo](https://x.com/msftsecresponse/status/1948193912595816768).

![Storm-2603 ransomware attack flow](https://www.bleepstatic.com/images/news/u/1109292/2025/Storm-2603-ransomware-attack.jpg)

_Dòng tấn công ransomware Storm-2603 (Microsoft)_

Các nhà nghiên cứu Intelligence của Microsoft [cũng đã liên kết](https://www.bleepingcomputer.com/news/security/microsoft-sharepoint-toolshell-attacks-linked-to-chinese-hackers/) các nhóm hacker được nhà nước Trung Quốc tài trợ là Linen Typhoon và Violet Typhoon với các cuộc tấn công này vào thứ Ba, chỉ vài ngày sau khi công ty an ninh mạng Hà Lan Eye Security [phát hiện lần đầu tiên các cuộc tấn công zero-day](https://www.bleepingcomputer.com/news/microsoft/microsoft-sharepoint-zero-day-exploited-in-rce-attacks-no-patch-available/) khai thác các lỗ hổng CVE-2025-49706 và CVE-2025-49704.

Kể từ đó, Giám đốc Công nghệ của Eye Security là Piet Kerkhofs đã cho BleepingComputer biết rằng số lượng thực thể bị xâm phạm lớn hơn nhiều, với "hầu hết trong số họ đã bị xâm nhập từ một thời gian dài." Theo thống kê của công ty an ninh mạng, những kẻ tấn công đã lây nhiễm ít nhất 400 máy chủ bằng phần mềm độc hại và xâm nhập vào 148 tổ chức trên toàn thế giới.

CISA cũng [đã thêm lỗ hổng thực thi mã từ xa CVE-2025-53770](https://www.cisa.gov/news-events/alerts/2025/07/20/microsoft-releases-guidance-exploitation-sharepoint-vulnerability-cve-2025-53770), một phần của cùng một chuỗi khai thác ToolShell, vào danh mục các lỗ hổng đã bị khai thác trong thực tế, yêu cầu các cơ quan liên bang Hoa Kỳ bảo vệ hệ thống của họ trong vòng một ngày.

Tuy nhiên, vào đầu tuần này, [Bộ Năng lượng xác nhận](https://www.bleepingcomputer.com/news/security/us-nuclear-weapons-agency-hacked-in-microsoft-sharepoint-attacks/) rằng mạng của Cơ quan An ninh Hạt nhân Quốc gia đã bị xâm phạm trong các cuộc tấn công Microsoft SharePoint đang diễn ra, mặc dù cơ quan này vẫn chưa tìm thấy bằng chứng nào cho thấy thông tin nhạy cảm hay được phân loại bị xâm phạm trong vụ việc.

Theo một [báo cáo của Bloomberg](https://www.bloomberg.com/news/articles/2025-07-22/microsoft-says-chinese-hackers-exploiting-sharepoint-flaws), những kẻ tấn công cũng đã xâm nhập vào các hệ thống của Bộ Giáo dục Hoa Kỳ, Cơ quan Lập pháp Bang Rhode Island, và Bộ Doanh thu Bang Florida, cũng như các mạng của các chính phủ quốc gia ở châu Âu và Trung Đông.