# University of Pennsylvania xác nhận dữ liệu bị đánh cắp trong cuộc tấn công mạng

![University of Pennsylvania](https://www.bleepstatic.com/content/hl-images/2025/10/31/university-of-pennsylvania.jpg)

University of Pennsylvania đã xác nhận rằng một hacker đã xâm nhập nhiều hệ thống nội bộ liên quan đến hoạt động phát triển và cựu sinh viên của trường và đánh cắp dữ liệu trong một cuộc tấn công mạng.

Trong một tuyên bố mới, Penn xác nhận [báo cáo của BleepingComputer](https://www.bleepingcomputer.com/news/security/university-of-pennsylvania-hacker-claims-1.2-million-donor-data-breach/) rằng các hacker đã xâm nhập hệ thống của họ bằng các thông tin đăng nhập bị xâm phạm, cho biết những thông tin này bị đánh cắp trong một cuộc tấn công lừa đảo xã hội.

"Vào ngày 31 tháng 10, Penn phát hiện rằng một nhóm hệ thống thông tin được chọn liên quan đến hoạt động phát triển và cựu sinh viên của Penn đã bị xâm phạm," theo một tuyên bố mới của Penn.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Penn áp dụng một chương trình an ninh thông tin vững mạnh; tuy nhiên, việc truy cập vào các hệ thống này xảy ra do một thủ đoạn giả mạo danh tính tinh vi, thường được gọi là lừa đảo xã hội."

"Nhân viên của Penn đã nhanh chóng khóa các hệ thống và ngăn chặn các truy cập trái phép tiếp theo; tuy nhiên, trước đó kẻ tấn công đã gửi một email mang tính xúc phạm và gian lận tới cộng đồng của chúng tôi và thông tin đã bị kẻ tấn công lấy đi. Penn vẫn đang điều tra bản chất của thông tin đã bị thu thập trong thời gian này."

University of Pennsylvania cho biết đã thông báo cho FBI về vụ xâm nhập và đang làm việc với CrowdStrike để điều tra sự cố an ninh.

Như BleepingComputer đưa tin đầu tiên, tác nhân đe dọa đã xâm nhập hệ thống của Penn vào ngày 30 tháng 10 bằng một tài khoản PennKey SSO của nhân viên, tài khoản này cho phép truy cập vào instance Salesforce của trường, nền tảng phân tích Qlik, hệ thống business intelligence của SAP và các file trên SharePoint.

Sử dụng quyền truy cập này, các tác nhân đã đánh cắp 1,71 GB tài liệu nội bộ từ các nền tảng lưu trữ SharePoint và Box của trường, bao gồm bảng tính, tài liệu, thông tin tài chính và tài liệu tiếp thị cho cựu sinh viên.

Các hacker cũng nói với BleepingComputer rằng họ đã đánh cắp cơ sở dữ liệu tiếp thị nhà tài trợ Salesforce của Penn, chứa 1,2 triệu bản ghi với nhiều loại thông tin của nhà tài trợ.

Một mẫu dữ liệu này bao gồm 158 trường khác nhau, chứa các thông tin nhạy cảm sau:

* Thông tin nhận dạng cá nhân (Personally Identifiable Information - PII): họ và tên đầy đủ, ngày sinh, giới tính, địa chỉ nhà và địa chỉ gửi thư, số điện thoại và địa chỉ email.
* Dữ liệu tài chính và thông tin về nhà tài trợ: lịch sử quyên góp, xếp hạng tài sản, và tổng cam kết suốt đời.
* Thông tin việc làm và liên kết: nơi làm việc, chức danh công việc, và liên kết học thuật.

Sau khi phát hiện quyền truy cập của họ bị thu hồi, hacker cho biết họ vẫn có quyền truy cập vào tài khoản Salesforce Marketing Cloud của Penn và đã sử dụng nó để [gửi một email hàng loạt mang tính xúc phạm](https://www.bleepingcomputer.com/news/security/offensive-we-got-hacked-emails-sent-in-penn-security-incident/) tới 700.000 người nhận.

Trong một bài đăng trên một diễn đàn hacker, các kẻ tấn công nói rằng hiện họ chưa rò rỉ các bản ghi dữ liệu nhưng có thể sẽ làm vậy trong một hoặc hai tháng tới.

Mặc dù các hacker khẳng định vụ tấn công không mang động cơ chính trị và cho biết mục tiêu của họ là "cơ sở dữ liệu nhà tài trợ rộng lớn, vô cùng giàu có" của Penn, cả email của họ và một bài đăng trên diễn đàn hacker đều chứa những lời chỉ trích gay gắt về các thực hành DEI được cho là của trường, chính sách tuyển sinh, và "tình yêu đối với nepobabies."

University of Pennsylvania cho biết đang thực hiện các biện pháp để tăng cường an ninh cho hệ thống của mình, bao gồm đào tạo nhân viên về các cuộc tấn công lừa đảo xã hội và tăng cường giám sát cùng biện pháp an ninh.

Sau khi cuộc điều tra kết thúc, Penn cho biết sẽ thông báo cho những người bị ảnh hưởng bởi vụ rò rỉ dữ liệu.

Trường cũng cảnh báo sinh viên và cựu sinh viên Penn cảnh giác với các cuộc gọi hoặc email đáng ngờ có thể là các nỗ lực lừa đảo hoặc tấn công lừa đảo xã hội.