# Cách một băng nhóm mã độc tống tiền đã mã hóa các hệ thống chính phủ Nevada

![Cách một băng nhóm mã độc tống tiền đã mã hóa các hệ thống chính phủ Nevada](https://www.bleepstatic.com/content/hl-images/2025/08/26/nevada-sign.jpg)

State of Nevada đã công bố một báo cáo sau sự kiện mô tả chi tiết cách các hacker xâm nhập hệ thống của họ để triển khai ransomware vào tháng 8, và các hành động được thực hiện để khôi phục sau cuộc tấn công.

Tài liệu này là một trong số ít báo cáo kỹ thuật hoàn toàn minh bạch từ một cơ quan chính phủ liên bang ở Hoa Kỳ về một sự cố an ninh mạng, mô tả tất cả các bước của kẻ tấn công và làm gương về cách các sự cố an ninh mạng nên được xử lý.

Sự cố ảnh hưởng đến hơn 60 cơ quan chính phủ bang và [gây gián đoạn các dịch vụ thiết yếu](https://www.bleepingcomputer.com/news/security/nevada-closes-state-offices-as-cyberattack-disrupts-it-systems/), từ các trang web và hệ thống điện thoại đến các nền tảng trực tuyến. Sau 28 ngày, mà không trả tiền chuộc, bang đã phục hồi 90% dữ liệu bị ảnh hưởng cần thiết để khôi phục các dịch vụ bị gián đoạn.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP)

Trong một báo cáo hôm nay, State of Nevada trình bày với sự minh bạch đầy đủ cách xâm phạm ban đầu diễn ra, hoạt động của tác nhân đe dọa trên mạng của họ, và các bước thực hiện sau khi phát hiện hoạt động độc hại.

## Diễn biến tấn công ransomware

Mặc dù vụ vi phạm được phát hiện vào ngày 24 tháng 8, hacker đã có quyền truy cập ban đầu từ ngày 14 tháng 5, khi một nhân viên bang sử dụng phiên bản trojanized của một công cụ quản trị hệ thống.

Theo [báo cáo](https://www.documentcloud.org/documents/26218568-gto-statewide-cyber-event-aar-final/), một nhân viên bang đã tìm kiếm Google cho một công cụ quản trị hệ thống để tải về và thay vào đó được hiển thị một quảng cáo độc hại dẫn đến một trang web lừa đảo mạo danh dự án hợp pháp.

Trang web giả này cung cấp phiên bản công cụ quản trị chứa mã độc, vốn đã triển khai một backdoor trên thiết bị của nhân viên.

Các tác nhân đe dọa ngày càng bắt đầu [sử dụng quảng cáo tìm kiếm để đẩy mã độc](https://www.bleepingcomputer.com/news/security/new-nitrogen-malware-pushed-via-google-ads-for-ransomware-attacks/) ngụy trang thành các công cụ quản trị hệ thống phổ biến, như WinSCP, Putty, RVTools, KeePass, LogMeIn, và AnyDesk. Tuy nhiên, mã độc được cài đặt thay vì chương trình mong muốn, cho phép kẻ tấn công có quyền truy cập ban đầu vào mạng doanh nghiệp.

Vì các công cụ này được thiết kế cho quản trị viên hệ thống, các tác nhân đe dọa hy vọng đạt được quyền truy cập nâng cao trên mạng bằng cách nhắm mục tiêu vào các nhân viên IT này.

Khi được thực thi, mã độc cấu hình một backdoor ẩn tự động kết nối với cơ sở hạ tầng của kẻ tấn công khi người dùng đăng nhập, cung cấp cho họ quyền truy cập từ xa liên tục vào mạng nội bộ của bang.

Vào ngày 26 tháng 6, Symantec Endpoint Protection (SEP) xác định và cách ly công cụ độc hại, rồi sau đó xóa nó khỏi máy trạm bị nhiễm, nhưng cơ chế duy trì tồn tại vẫn còn, và hacker vẫn có thể tiếp cận môi trường.

Vào ngày 5 tháng 8, kẻ tấn công đã cài đặt một phần mềm commercial remote-monitoring trên một hệ thống, cho phép họ ghi màn hình và ghi phím. Một lần nhiễm thứ hai với công cụ đó xảy ra mười ngày sau.

Giữa ngày 14 và 16 tháng 8, kẻ tấn công đã triển khai một công cụ đường hầm mạng tùy chỉnh được mã hóa để vượt qua các biện pháp kiểm soát an ninh và thiết lập các phiên Remote Desktop Protocol (RDP) trên nhiều hệ thống.

Loại truy cập từ xa này cho phép họ di chuyển ngang giữa các máy chủ quan trọng, bao gồm cả máy chủ kho mật khẩu, từ đó họ lấy thông tin xác thực của 26 tài khoản, rồi xóa nhật ký sự kiện để che giấu hành động của mình.

Đội phản ứng sự cố của Mandiant xác nhận rằng kẻ tấn công đã truy cập 26,408 tệp trên nhiều hệ thống và chuẩn bị một kho lưu trữ .ZIP gồm sáu phần chứa thông tin nhạy cảm.

Cuộc điều tra không tìm thấy bằng chứng rằng kẻ tấn công đã exfiltrate hoặc công bố dữ liệu.

Vào ngày 24 tháng 8, kẻ tấn công xác thực vào server backup và xóa tất cả các backup volumes để vô hiệu hóa khả năng khôi phục, rồi đăng nhập vào virtualization management server với quyền root để sửa đổi cài đặt bảo mật nhằm cho phép thực thi mã không được ký.

Lúc 08:30:18 UTC, kẻ tấn công đã triển khai một chủng ransomware trên tất cả các server lưu trữ các máy ảo (VMs) của bang.

Governor’s Technology Office (GTO) phát hiện sự cố mất dịch vụ khoảng 20 phút sau đó (01:50 AM), đánh dấu bắt đầu nỗ lực phục hồi trên toàn bang kéo dài 28 ngày.

## Trả tiền làm thêm giờ, không trả tiền chuộc

State of Nevada giữ vững quan điểm không trả tiền chuộc và dựa vào nhân viên IT nội bộ cùng các khoản trả làm thêm giờ để khôi phục hệ thống và dịch vụ bị ảnh hưởng.

Phân tích chi phí cho thấy 50 nhân viên bang đã làm tổng cộng 4,212 giờ làm thêm, phát sinh chi phí tiền lương là $259,000 cho bang.

Phản ứng này cho phép xử lý bảng lương kịp thời, giữ liên lạc an toàn công cộng hoạt động trực tuyến, và tái thiết nhanh các hệ thống hướng tới công dân, và tiết kiệm cho bang ước tính $478,000 khi so sánh với mức giá nhà thầu tiêu chuẩn ($175/hour).

Chi phí cho hỗ trợ nhà cung cấp bên ngoài trong thời gian phản ứng sự cố là hơn $1.3 triệu, được phân chia trong bảng dưới đây.

| Nhà cung cấp           | Dịch vụ cung cấp                         | Chi phí đã cam kết |
| ---------------------- | ---------------------------------------- | ------------------ |
| Microsoft DART         | Unified Support & Infrastructure Rebuild | $354,481           |
| Mandiant               | Forensics & Incident Response            | $248,750           |
| Aeris                  | Recovery & Engineering Support           | $240,000           |
| BakerHostetler         | Legal & Privacy Counsel                  | $95,000            |
| SHI (Palo Alto)        | Network Security Services                | $69,400            |
| Dell                   | Data Recovery & Project Management       | $66,500            |
| Other IR Vendors       | Various Support Services                 | \~$240,069         |

Cần lưu ý rằng tác nhân ransomware chưa được đặt tên. BleepingComputer không thấy bất kỳ băng nhóm lớn nào tuyên bố vụ xâm nhập trên các trang extortion.

Sự cố cho thấy khả năng chống chịu mạng của Nevada, bao gồm hành động “playbook” quyết đoán và nhanh chóng, và cũng đưa ra mức độ minh bạch đáng khen ngợi.

Mặc dù chi phí và nỗ lực khôi phục, State of Nevada cũng đã cải thiện khả năng phòng thủ an ninh mạng theo khuyến nghị của các nhà cung cấp đáng tin cậy.

"The GTO focused on securing the most sensitive systems first, ensuring that access was limited to essential personnel," báo cáo ghi nhận.

Một số hành động kỹ thuật và chiến lược bao gồm xóa các tài khoản cũ hoặc không cần thiết, đặt lại mật khẩu, và loại bỏ các chứng chỉ bảo mật đã lỗi thời. Thêm vào đó, các quy tắc và quyền hệ thống đã được xem xét để đảm bảo chỉ người dùng được ủy quyền mới có quyền truy cập vào các cài đặt nhạy cảm.

Tuy nhiên, bang thừa nhận rằng vẫn còn nhiều chỗ để cải thiện và nhận ra tầm quan trọng của việc đầu tư vào an ninh mạng, đặc biệt là để nâng cao năng lực giám sát và phản ứng, vì các tác nhân đe dọa cũng liên tục phát triển thủ đoạn, kỹ thuật và quy trình của họ.