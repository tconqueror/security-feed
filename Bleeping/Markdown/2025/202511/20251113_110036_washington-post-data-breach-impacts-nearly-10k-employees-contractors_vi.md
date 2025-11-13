# Sự cố rò rỉ dữ liệu của Washington Post ảnh hưởng gần 10.000 nhân viên, nhà thầu

![Sự cố rò rỉ dữ liệu của Washington Post ảnh hưởng gần 10.000 nhân viên, nhà thầu](https://www.bleepstatic.com/content/hl-images/2025/06/16/newspaper.jpg)

Washington Post đang thông báo tới gần 10.000 nhân viên và nhà thầu rằng một số dữ liệu cá nhân và tài chính của họ đã bị lộ trong vụ đánh cắp dữ liệu của Oracle.

Tổ chức tin tức này là một trong những nhật báo lớn nhất ở U.S. với khoảng 2,5 triệu người đăng ký kỹ thuật số.

Từ ngày 10 tháng 7 đến 22 tháng 8, các tác nhân đe doạ đã truy cập một phần mạng lưới của tổ chức. Họ lợi dụng một lỗ hổng trong phần mềm Oracle E-Business Suite mà lúc đó là một zero-day để đánh cắp dữ liệu nhạy cảm.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Vào cuối tháng 9, những kẻ tấn công đã cố gắng tống tiền Washington Post, cùng với các công ty lớn khác mà họ đã xâm nhập theo cùng phương thức.

Những kẻ tấn công đã lợi dụng một lỗ hổng zero-day trong Oracle E-Business Suite mà Washington Post sử dụng nội bộ, đánh cắp dữ liệu, và sau đó cố gắng tống tiền tổ chức vào cuối tháng 9.

Oracle E-Business Suite là một nền tảng hoạch định nguồn lực doanh nghiệp (ERP) được sử dụng rộng rãi, có các chức năng HR, tài chính và chuỗi cung ứng mà các tổ chức lớn dùng nội bộ.

Theo thông báo của Washington Post gửi tới các cá nhân bị ảnh hưởng, Oracle đã tiết lộ lỗ hổng bảo mật trong khi tổ chức tin tức này đang điều tra sự cố vi phạm.

“Vào ngày 29 tháng 9 năm 2025, Post đã được một tác nhân xấu liên hệ, người này tuyên bố đã truy cập vào các ứng dụng Oracle E-Business Suite của tổ chức,” [mô tả lá thư](https://www.maine.gov/agviewer/content/ag/985235c7-cb95-4be2-8792-a1252b4f8318/12a31419-4ed0-41ba-a045-2593908ba368.html).  
  
“Để đáp lại, Post đã triển khai một cuộc điều tra toàn diện về môi trường ứng dụng Oracle của mình với sự hỗ trợ của các chuyên gia để xác định xem môi trường có bị truy cập trái phép hay không.”

“Trong quá trình điều tra, Oracle thông báo rằng họ đã xác định một lỗ hổng trước đây chưa biết và có quy mô lớn trong phần mềm E-Business Suite cho phép các tác nhân trái phép truy cập vào nhiều ứng dụng E-Business Suite của khách hàng Oracle.”

Mặc dù những kẻ tấn công không được nêu tên trong lá thư, nhóm ransomware Clop đã bị [liên kết với các cuộc tấn công này](https://www.bleepingcomputer.com/news/security/oracle-links-clop-extortion-attacks-to-july-security-flaws/), khai thác một lỗ hổng zero-day hiện được theo dõi là CVE-2025-61884.

Trong số các tổ chức bị xâm nhập sử dụng cùng lỗ hổng trong Oracle E-Business Suite có [Harvard University](https://www.bleepingcomputer.com/news/security/harvard-investigating-breach-linked-to-oracle-zero-day-exploit/), công ty con của American Airlines là [Envoy Air](https://www.bleepingcomputer.com/news/security/american-airlines-subsidiary-envoy-confirms-oracle-data-theft-attack/), và [GlobalLogic](https://www.bleepingcomputer.com/news/security/globallogic-warns-10-000-employees-of-data-theft-after-oracle-breach/) thuộc Hitachi.

Đây là một số nạn nhân đã xác nhận bị vi phạm hoặc đang điều tra hoạt động đáng ngờ trong môi trường của họ. Tuy nhiên, trang rò rỉ dữ liệu của Clop liệt kê một số lượng lớn các tổ chức bị xâm phạm hơn.

Cuộc điều tra của Post về sự cố kết thúc vào ngày 27 tháng 10 và tiết lộ rằng các loại dữ liệu sau thuộc về 9.720 nhân viên và nhà thầu đã bị lộ:

* Họ và tên đầy đủ
* Số tài khoản ngân hàng và số routing
* Số An Sinh Xã Hội (SSNs)
* Số thuế và số giấy tờ tùy thân

Các cá nhân bị ảnh hưởng đã nhận được dịch vụ bảo vệ danh tính miễn phí trong 12 tháng thông qua IDX và được khuyến nghị xem xét việc đặt đóng băng tín dụng trên hồ sơ tín dụng của mình và thiết lập cảnh báo gian lận trên báo cáo tín dụng.

Vào tháng 6, Washington Post thông báo rằng các tài khoản email của một số nhà báo của họ [đã bị xâm phạm](https://www.bleepingcomputer.com/news/security/washington-posts-email-system-hacked-journalists-accounts-compromised/) trong một cuộc tấn công mạng do các tác nhân nhà nước nước ngoài tiến hành.

Mặc dù hai sự cố xảy ra gần nhau, có bằng chứng cho thấy có sự liên quan giữa chúng.

BleepingComputer đã liên hệ với The Washington Post để đặt thêm câu hỏi, và chúng tôi sẽ cập nhật bài viết này khi nhận được phản hồi.