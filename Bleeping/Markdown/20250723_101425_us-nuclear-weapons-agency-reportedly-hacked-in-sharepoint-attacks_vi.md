# Cơ quan vũ khí hạt nhân Mỹ được cho là đã bị hack trong các cuộc tấn công SharePoint

![Cơ quan Quản lý An ninh Hạt nhân Quốc gia NNSA](https://www.bleepstatic.com/content/hl-images/2025/07/23/NNSA.jpg)

Những tác nhân đe dọa không xác định được cho là đã xâm nhập vào mạng lưới của Cơ quan Quản lý An ninh Hạt nhân Quốc gia (NNSA) trong các cuộc tấn công khai thác chuỗi lỗ hổng zero-day trên Microsoft SharePoint vừa được vá gần đây.

NNSA là một cơ quan chính phủ tự trị bán phần của Hoa Kỳ thuộc Bộ Năng lượng, có nhiệm vụ duy trì kho vũ khí hạt nhân của quốc gia và cũng được giao nhiệm vụ đối phó với các tình huống khẩn cấp hạt nhân và phóng xạ trong nước và quốc tế.

Một người phát ngôn của Bộ Năng lượng đã xác nhận trong một tuyên bố rằng các hacker đã xâm nhập vào các mạng của NNSA vào tuần trước.

"Vào thứ Sáu, ngày 18 tháng 7, việc khai thác lỗ hổng zero-day trên Microsoft SharePoint đã bắt đầu ảnh hưởng đến Bộ Năng lượng," người phát ngôn [nói với Bleeomberg](https://www.bloomberg.com/news/articles/2025-07-23/us-nuclear-weapons-agency-breached-in-microsoft-sharepoint-hack). "Bộ này đã bị ảnh hưởng tối thiểu nhờ việc sử dụng rộng rãi đám mây Microsoft M365 và các hệ thống an ninh mạng rất mạnh."

Cơ quan này cũng cho biết chỉ "một số rất nhỏ các hệ thống bị ảnh hưởng" và rằng "tất cả các hệ thống bị ảnh hưởng đang được khôi phục."

Một nguồn tin ẩn danh từ cơ quan cũng lưu ý rằng không có thông tin nhạy cảm hay mật được cho là đã bị xâm phạm trong lỗ hổng này.

Nhóm đe dọa APT29, được nhà nước tài trợ của Nga, bộ phận hack của Cơ quan Tình báo Đối ngoại Nga (SVR), cũng [đã xâm nhập vào cơ quan vũ khí hạt nhân của Mỹ](https://www.bleepingcomputer.com/news/security/solarwinds-hackers-breach-us-nuclear-weapons-agency/) vào năm 2019 bằng cách sử dụng một bản cập nhật SolarWinds Orion bị trojan hóa.

Một người phát ngôn của Bộ Năng lượng chưa thể trả lời ngay lập tức khi được BleepingComputer liên hệ vào hôm nay.

## Các cuộc tấn công liên quan đến hacker nhà nước Trung Quốc, hơn 400 máy chủ bị xâm phạm

Vào thứ Ba, Microsoft và Google đã liên kết các cuộc tấn công rộng rãi nhằm vào chuỗi lỗ hổng zero-day trên Microsoft SharePoint (được gọi là [ToolShell](https://www.bleepingcomputer.com/tag/toolshell/)) với các nhóm hacker tài trợ từ nhà nước Trung Quốc.

"Microsoft đã quan sát thấy hai tác nhân nhà nước Trung Quốc có tên, Linen Typhoon và Violet Typhoon, đang khai thác các lỗ hổng này nhằm vào các máy chủ SharePoint truy cập qua Internet," [Microsoft cho biết](https://www.bleepingcomputer.com/news/security/microsoft-sharepoint-toolshell-attacks-linked-to-chinese-hackers/).

"Thêm vào đó, chúng tôi đã quan sát thấy một tác nhân đe dọa khác có nguồn gốc từ Trung Quốc, theo dõi với tên Storm-2603, đang khai thác những lỗ hổng này. Các cuộc điều tra về các tác nhân khác cũng sử dụng những lỗ hổng này vẫn đang được tiến hành."

Công ty an ninh mạng Hà Lan Eye Security [đã phát hiện các cuộc tấn công zero-day đầu tiên](https://www.bleepingcomputer.com/news/microsoft/microsoft-sharepoint-zero-day-exploited-in-rce-attacks-no-patch-available/) vào thứ Sáu, cho biết rằng ít nhất 54 tổ chức đã bị xâm phạm, bao gồm các thực thể chính phủ quốc gia và các công ty đa quốc gia.

Công ty an ninh mạng Check Point sau đó đã tiết lộ rằng họ [đã phát hiện dấu hiệu khai thác từ ngày 7 tháng 7](https://blog.checkpoint.com/research/sharepoint-zero-day-cve-2025-53770-actively-exploited-what-security-teams-need-to-know/) nhằm vào hàng chục tổ chức chính phủ, viễn thông và công nghệ tại Bắc Mỹ và Tây Âu.

Kể từ đó, CTO của Eye Security, Piet Kerkhofs, đã nói với BleepingComputer rằng số lượng các thực thể bị xâm phạm, "hầu hết trong số họ đã bị xâm phạm trong một thời gian," lớn hơn nhiều. Theo thống kê của công ty an ninh mạng, các tác nhân đe dọa đứng sau những cuộc tấn công này đã lây nhiễm ít nhất 400 máy chủ bằng malware và xâm nhập 148 tổ chức trên toàn thế giới.

CISA cũng [đã thêm lỗ hổng thực thi mã từ xa CVE-2025-53770](https://www.cisa.gov/news-events/alerts/2025/07/20/microsoft-releases-guidance-exploitation-sharepoint-vulnerability-cve-2025-53770), một phần của chuỗi khai thác ToolShell, vào danh mục các lỗ hổng đã bị khai thác, yêu cầu các cơ quan liên bang của Mỹ phải bảo mật hệ thống của họ trong vòng một ngày.