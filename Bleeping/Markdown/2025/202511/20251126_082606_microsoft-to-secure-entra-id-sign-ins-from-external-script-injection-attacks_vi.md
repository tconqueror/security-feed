# Microsoft tăng cường bảo vệ đăng nhập Entra ID khỏi các cuộc tấn công chèn mã script

![Microsoft](https://www.bleepstatic.com/content/hl-images/2025/04/24/Microsoft.jpg)

Microsoft dự định tăng cường bảo mật cho hệ thống xác thực Entra ID chống lại các cuộc tấn công chèn script bên ngoài, bắt đầu từ giữa đến cuối tháng 10 năm 2026.

Bản cập nhật này sẽ triển khai một Content Security Policy được tăng cường cho phép chỉ tải xuống script từ các miền mạng phân phối nội dung được Microsoft tin cậy và chỉ cho phép thực thi script nội tuyến từ các nguồn được Microsoft tin cậy trong quá trình đăng nhập.

Sau khi triển khai, nó sẽ bảo vệ người dùng khỏi nhiều rủi ro bảo mật khác nhau, bao gồm các cuộc tấn công cross-site scripting trong đó kẻ tấn công chèn mã độc vào các trang web để đánh cắp thông tin đăng nhập hoặc xâm phạm hệ thống.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Chính sách cập nhật sẽ chỉ áp dụng cho trải nghiệm đăng nhập trên trình duyệt tại các URL bắt đầu bằng login.microsoftonline.com, và Microsoft Entra External ID sẽ không bị ảnh hưởng.

" Bản cập nhật này củng cố bảo mật và thêm một lớp bảo vệ bằng cách chỉ cho phép các script từ các miền Microsoft đáng tin cậy chạy trong quá trình xác thực, ngăn chặn mã không được phép hoặc mã chèn được thực thi trong trải nghiệm đăng nhập," [nói](https://techcommunity.microsoft.com/blog/microsoft-entra-blog/enhance-protection-of-microsoft-entra-id-authentication-by-blocking-external-scr/4435200) Megna Kokkalera, quản lý sản phẩm cho Microsoft Identity and Authentication Experiences.

Microsoft kêu gọi các tổ chức thử nghiệm các kịch bản đăng nhập trước hạn chót tháng 10 năm 2026 để xác định và xử lý bất kỳ phụ thuộc nào vào các công cụ chèn mã.

Quản trị viên IT có thể xác định tác động tiềm ẩn bằng cách kiểm tra luồng đăng nhập trong bảng điều khiển dành cho nhà phát triển của trình duyệt: các vi phạm sẽ xuất hiện bằng chữ màu đỏ kèm chi tiết về các script bị chặn.

![CSP policy violation](https://www.bleepstatic.com/images/news/u/1109292/2025/Entra-ID-script-CSP-violation.png)

_Vi phạm chính sách CSP (Microsoft)_

Microsoft cũng khuyên khách hàng doanh nghiệp ngừng sử dụng các tiện ích mở rộng trình duyệt và công cụ chèn mã hoặc script vào các trang đăng nhập trước khi thay đổi có hiệu lực. Những công cụ này sẽ không còn được hỗ trợ và sẽ ngừng hoạt động, mặc dù người dùng vẫn sẽ có thể đăng nhập.

"Bản cập nhật Content Security Policy này thêm một lớp bảo vệ bổ sung bằng cách chặn các script không được phép, giúp bảo vệ tổ chức của bạn trước các mối đe dọa bảo mật đang phát triển," Kokkalera bổ sung.

Động thái này là một phần của Secure Future Initiative (SFI) của Microsoft, một nỗ lực toàn công ty được khởi động hai năm trước, vào tháng 11 năm 2023, sau một báo cáo từ Cyber Safety Review Board của U.S. Department of Homeland Security, trong đó [phát hiện](https://www.cisa.gov/sites/default/files/2025-03/CSRBReviewOfTheSummer2023MEOIntrusion508.pdf) rằng văn hóa bảo mật của công ty là "inadequate and requires an overhaul."

Trong khuôn khổ cùng sáng kiến, Microsoft cũng [đã cập nhật các cài đặt bảo mật mặc định của Microsoft 365](https://www.bleepingcomputer.com/news/microsoft/microsoft-365-to-block-file-access-via-legacy-auth-protocols-by-default/) để chặn truy cập vào các tệp SharePoint, OneDrive và Office thông qua các giao thức xác thực cũ, và [đã vô hiệu hóa tất cả các điều khiển ActiveX](https://www.bleepingcomputer.com/news/microsoft/microsoft-blocks-activex-by-default-in-microsoft-365-office-2024/) trong các phiên bản Windows của Microsoft 365 và ứng dụng Office 2024.

Đầu tháng này, hãng cũng bắt đầu triển khai một tính năng mới của Teams [được công bố vào tháng 5](https://www.bleepingcomputer.com/news/microsoft/microsoft-teams-will-soon-block-screen-capture-during-meetings/) và được thiết kế để [chặn các nỗ lực chụp màn hình](https://www.bleepingcomputer.com/news/microsoft/microsoft-rolls-out-screen-capture-prevention-for-teams-users/) trong các cuộc họp.