# Thị trường đám mây Pax8 vô tình tiết lộ dữ liệu của 1.800 đối tác MSP

![Pax8](https://www.bleepstatic.com/content/hl-images/2026/01/14/pax8-background.jpg)

Thị trường đám mây và nhà phân phối Pax8 xác nhận rằng họ đã vô tình gửi một email tới dưới 40 đối tác có trụ sở tại UK chứa một bảng tính với thông tin kinh doanh nội bộ, bao gồm dữ liệu khách hàng MSP và dữ liệu cấp phép Microsoft.

Pax8 là một thị trường thương mại đám mây phát triển nhanh với hơn 1.700 nhân viên, hơn 47.000 đối tác trên toàn thế giới và hoạt động tại 18 quốc gia. Công ty gần đây đã vượt qua mốc 2 tỷ đô la doanh thu hàng năm, với mức tăng trưởng đặc biệt mạnh ở châu Âu.

## CSV tiết lộ dữ liệu khách hàng và dữ liệu cấp phép

Email, có tiêu đề "Chiến thuật nâng cấp Business Premium tiềm năng để tiết kiệm tiền", được gửi vào ngày 13 tháng 1 bởi một quản lý tài khoản chiến lược có trụ sở EMEA và kèm theo một tệp đính kèm CSV.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Theo Pax8, tệp chứa thông tin định giá nội bộ và thông tin chương trình Microsoft ảnh hưởng đến **khoảng 1.800 đối tác**, chủ yếu ở UK, với một trường hợp ở Canada — và đã bị phân phối nhầm cho dưới 40 người nhận có trụ sở tại UK.

Các MSP nhận được thông điệp nói với BleepingComputer rằng tệp CSV liệt kê tên tổ chức khách hàng, Microsoft SKUs, số lượng giấy phép và ngày gia hạn [New Commerce Experience (NCE)](https://www.pax8.com/blog/microsoft-csp-new-commerce-experience/).

![Pax8 email sent to MSPs containing the spreadsheet](https://www.bleepstatic.com/images/news/u/1164866/2026/Jan/pax8-data-leak/pax8-original-email-with-csv-redacted.jpg)

**Email của Pax8 gửi cho MSPs chứa bảng tính với dữ liệu khách hàng** (BleepingComputer)

Các hiện vật được chia sẻ trực tiếp với BleepingComputer bởi nhiều người nhận cho thấy bảng tính rò rỉ chứa hơn 56.000 mục với các trường như:

* Tên và ID đối tác
* Tên và ID khách hàng
* Tên nhà cung cấp và tên sản phẩm
* Gross & Net Bookings
* Tổng số lượng theo tiền tệ
* Territory
* Account Owner
* Provision Date
* Cancelled Book Date
* Postal Code
* Transaction Type
* Commitment Term End Date

Ngay sau khi email được gửi, người gửi đã cố gắng thu hồi tin nhắn và sau đó tiếp tục gửi một email theo dõi yêu cầu người nhận xóa tin nhắn và tệp đính kèm ban đầu, thừa nhận rằng nó đã được gửi nhầm:

**Pax8 recalling the accidental email** (BleepingComputer)

Trong thông báo theo dõi, Pax8 nói với các đối tác rằng tệp không chứa thông tin nhận dạng cá nhân nhưng là thông tin kinh doanh hạn chế có thể [tiết lộ](http://status.pax8.com/incidents/ndmn6zrpnxjp) định giá của MSP và dữ liệu quản lý chương trình Microsoft. Những thông tin như danh mục khách hàng và dấu chân cấp phép sẽ thường chỉ hiển thị với MSP quản lý các tenant đó và Pax8.

Nhiều người nhận đã chia sẻ nguyên văn thông điệp theo dõi của Pax8 với BleepingComputer:

"Dear Partner,  
  
Earlier today, 13 January 2026, a Pax8 employee mistakenly sent an email with an attached spreadsheet to fewer than 40 UK-based partners. The attachment did not contain personally identifiable information. However, the file included limited internal business information reflective of your Pax8 pricing and some Microsoft program management.  
  
Importantly, there is no impact to Marketplace availability or security controls as a result of this incident.  
  
**What we did immediately**  
  
\* Contacted each recipient directly and requested deletion of the email and attachment  
\* Required confirmation of deletion and non-forwarding  
\* Are conducting 1:1 follow-up calls with recipients to reinforce deletion and confirm completion  
\* Launched an internal review to determine how this occurred and to prevent recurrence  
  
**What you need to do**  
  
No action is required from you.  
If you have questions, please reach out to us at trust@pax8.com.  
  
We recognize the responsibility we have to protect partner-confidential information.  
  
Sincerely,  
Pax8 Alerts"

## Các nhóm tấn công được cho là đang tìm cách mua bộ dữ liệu

BleepingComputer cũng biết từ các nguồn trong ngành rằng các tác nhân đe dọa hiện đang tiếp cận một số MSP bị ảnh hưởng, đề nghị mua các bản sao của bộ dữ liệu bị lộ.

Những thông tin như vậy có thể có giá trị đối với cả đối thủ cạnh tranh và tội phạm mạng. Đối với các MSP đối thủ, danh sách có thể tiết lộ những tổ chức sử dụng Pax8 làm nhà phân phối, quy mô môi trường Microsoft của từng khách hàng, thời hạn gia hạn hợp đồng và có thể là các mức định giá đang được trả — dữ liệu có thể được sử dụng để nhắm mục tiêu cạnh tranh hoặc dụ dỗ nhân sự.

Đối với các tác nhân đe dọa, bộ dữ liệu có thể hoạt động như một danh sách nhắm mục tiêu chất lượng cao, xác định các tổ chức đang chạy sản phẩm Microsoft cụ thể, quy mô triển khai của họ và MSP nào quản lý môi trường của họ. Điều này có thể cho phép chiến dịch phishing thuyết phục hơn, các nỗ lực Business Email Compromise hoặc những vụ tống tiền được căn thời điểm xung quanh các lần gia hạn giấy phép và đàm phán hợp đồng.

BleepingComputer đã tiếp cận đội truyền thông của Pax8 để yêu cầu bình luận trước khi xuất bản, nhưng các tin nhắn gửi tới địa chỉ báo chí liệt kê nhiều lần bị trả lại. Chúng tôi cũng đã liên hệ với các thành viên của đội truyền thông, bàn hỗ trợ, hộp thư trust@pax8.com và nhân sự quen thuộc với sự cố để xin thêm bình luận.