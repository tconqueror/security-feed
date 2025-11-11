# Synology sửa các lỗ hổng zero-day của BeeStation được trình diễn tại Pwn2Own Ireland

![Synology sửa các lỗ hổng zero-day của BeeStation được trình diễn tại Pwn2Own Ireland](https://www.bleepstatic.com/content/hl-images/2024/11/01/Synology.jpg)

Synology đã khắc phục một lỗ hổng thực thi mã từ xa (RCE) có mức độ nghiêm trọng cao trong sản phẩm BeeStation, lỗ hổng này đã được trình diễn tại cuộc thi Pwn2Own gần đây.

Vấn đề bảo mật (CVE-2025-12686) được mô tả là 'sao chép bộ đệm mà không kiểm tra kích thước đầu vào', và có thể bị khai thác để thực thi mã tùy ý.

Nó ảnh hưởng đến nhiều phiên bản BeeStation OS, phần mềm vận hành các thiết bị lưu trữ gắn mạng (NAS) của Synology được tiếp thị như một “đám mây cá nhân”.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Không có biện pháp giảm nhẹ nào sẵn có, vì vậy nhà cung cấp [khuyến nghị](https://www.synology.com/en-us/security/advisory/Synology%5FSA%5F25%5F12) người dùng nâng cấp lên các phiên bản sau, đã khắc phục:

* BeeStation OS version 1.3.2-65648 or above
* BeeStation OS version 1.3.2-65648 or above
* BeeStation OS version 1.3.2-65648 or above
* BeeStation OS version 1.3.2-65648 or above

Các nhà nghiên cứu [Tek](https://x.com/tek%5F7987) và [anyfun](https://x.com/%5FAnyfun) tại công ty an ninh mạng Pháp Synacktiv đã khai thác lỗi này trong một màn trình diễn tại cuộc thi Pwn2Own Ireland 2025 vào ngày 21 tháng 10. Vì việc khai thác thành công, hai nhà nghiên cứu đã nhận phần thưởng $40,000.

[![tweet](https://www.bleepstatic.com/images/news/u/1220909/2025/November/tweet.png)](https://x.com/Synacktiv/status/1980658629369094563)

Pwn2Own là một cuộc thi tấn công kéo dài ba ngày do Trend Micro và Zero Day Initiative (ZDI) tổ chức, tạo cơ hội cho các nhà nghiên cứu bảo mật tấn công các thiết bị tiêu dùng phổ biến bằng các lỗ hổng zero-day.

Sự kiện gần đây nhất tổ chức ở Ireland có các nhà nghiên cứu trình diễn [73 lỗ hổng zero-day](https://www.bleepingcomputer.com/news/security/hackers-earn-1-024-750-for-73-zero-days-at-pwn2own-ireland/) trên nhiều sản phẩm khác nhau và giành được hơn $1 triệu.

Tuần trước, một nhà cung cấp NAS lớn khác, [QNAP](https://www.bleepingcomputer.com/news/security/qnap-fixes-seven-nas-zero-day-vulnerabilities-exploited-at-pwn2own/), đã sửa tổng cộng bảy lỗ hổng zero-day trong nhiều thiết bị của công ty, những lỗ hổng mà các hacker mũ trắng đã trình diễn tại Pwn2Own Ireland năm nay.

ZDI có thỏa thuận tiết lộ với các công ty tham gia Pwn2Own và trì hoãn việc công bố chi tiết kỹ thuật của các vấn đề bảo mật cho đến khi các bản vá có sẵn và người dùng có đủ thời gian để áp dụng cập nhật.

Chi tiết hơn về những lỗ hổng này sẽ được công bố trong những tháng tới trên bảng tin của ZDI và, trong một số trường hợp, trên các blog cá nhân của chính các nhà nghiên cứu.