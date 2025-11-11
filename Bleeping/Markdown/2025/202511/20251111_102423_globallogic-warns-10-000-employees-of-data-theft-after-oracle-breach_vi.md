# GlobalLogic cảnh báo 10.000 nhân viên về việc đánh cắp dữ liệu sau vụ vi phạm Oracle

![GlobalLogic](https://www.bleepstatic.com/content/hl-images/2025/11/11/GlobalLogic.jpg)

GlobalLogic, một nhà cung cấp dịch vụ kỹ thuật số thuộc nhóm Hitachi, đang thông báo cho hơn 10.000 nhân viên hiện tại và trước đây rằng dữ liệu của họ đã bị đánh cắp trong một vụ vi phạm dữ liệu Oracle E-Business Suite (EBS).

Based in Santa Clara, California, this software and product development services company was founded in 2000. Since then, it has expanded to 59 product engineering centers and several offices worldwide.

Trong một thư thông báo vụ vi phạm [đệ trình với văn phòng Maine's Attorney General](https://www.maine.gov/agviewer/content/ag/985235c7-cb95-4be2-8792-a1252b4f8318/a69e0001-a0f8-46d9-a49d-cb01159afec2.html), công ty cho biết kẻ tấn công đã lợi dụng một lỗ hổng zero-day trong Oracle EBS để đánh cắp thông tin cá nhân thuộc về 10.471 nhân viên.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

"GlobalLogic's investigation identified access to Oracle and exfiltration on October 9, 2025. We then began drafting and sending out notifications. The investigation has identified the earliest date of threat actor activity as July 10, 2025, with the most recent activity occurring on August 20, 2025," công ty cho biết.

"Sự cố này không nhắm mục tiêu hoặc ảnh hưởng đến hệ thống của GlobalLogic bên ngoài nền tảng Oracle của chúng tôi, và, dựa trên các báo cáo trong ngành, chúng tôi là một trong nhiều khách hàng Oracle được cho là đã bị ảnh hưởng. Thông tin cá nhân liên quan trong sự cố này đến từ nền tảng Oracle của chúng tôi, bao gồm thông tin nhân sự cho nhân viên hiện tại và trước đây."

Dữ liệu bị đánh cắp trong vụ vi phạm bao gồm thông tin cá nhân do nhân sự của GlobalLogic thu thập và, tùy theo từng cá nhân bị ảnh hưởng, bao gồm tên, địa chỉ, số điện thoại và liên hệ khẩn cấp (tên và số điện thoại).

Kẻ tấn công cũng đã lấy cắp địa chỉ email, ngày sinh, quốc tịch, quốc gia nơi sinh, thông tin hộ chiếu, mã định danh quốc gia hoặc mã định thuế (ví dụ: Social Security Numbers), thông tin lương và chi tiết tài khoản ngân hàng của các nhân viên bị ảnh hưởng.

## Các cuộc tấn công đánh cắp dữ liệu Oracle EBS của Clop

Mặc dù GlobalLogic chưa quy trách nhiệm vụ vi phạm cho một nhóm mối đe dọa cụ thể, các chi tiết của sự cố phù hợp với một chiến dịch tống tiền trong đó băng nhóm ransomware Clop [đã lợi dụng một lỗi zero-day (CVE-2025-61882)](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/) từ [đầu tháng Tám](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/) để đánh cắp dữ liệu nhạy cảm từ hệ thống Oracle EBS của nhiều công ty.

Mặc dù Clop chưa tiết lộ tổng số công ty bị ảnh hưởng bởi các vụ đánh cắp dữ liệu này, Giám đốc phân tích nhóm Google Threat Intelligence Group John Hultquist đã nói với BleepingComputer rằng họ tin rằng hàng chục tổ chức đã bị ảnh hưởng.

Băng nhóm tống tiền này hiện cũng đang nhắm tới Harvard University, Envoy Air, và The Washington Post, những bên đã được thêm vào trang rò rỉ của nhóm tội phạm mạng trên Tor. Dữ liệu của họ cũng đã bị rò rỉ trực tuyến và hiện có thể tải về qua Torrent.

Clop vẫn chưa thêm GlobalLogic vào trang rò rỉ của chúng, điều này gợi ý rằng công ty có thể đang đàm phán với nhóm mối đe dọa hoặc đã trả tiền chuộc.

Một phát ngôn viên của GlobalLogic không có sẵn ngay lập tức để bình luận khi được BleepingComputer liên hệ trước đó trong ngày.

Clop trước đây đã được liên kết với các chiến dịch đánh cắp dữ liệu khác nhắm vào Accellion FTA, GoAnywhere MFT, Cleo, và MOVEit Transfer, trong đó vụ sau cùng đã ảnh hưởng tới hơn 2.770 tổ chức trên toàn thế giới.

U.S. State Department hiện đang đưa ra một khoản tiền thưởng trị giá $10 million cho thông tin liên kết các cuộc tấn công của băng nhóm ransomware này với một chính phủ nước ngoài.