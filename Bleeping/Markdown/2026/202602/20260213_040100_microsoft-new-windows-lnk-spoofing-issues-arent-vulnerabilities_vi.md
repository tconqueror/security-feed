# Microsoft: Các vấn đề giả mạo LNK Windows mới không phải là lỗ hổng bảo mật

![Windows](https://www.bleepstatic.com/content/hl-images/2024/12/16/Windows.jpg)

Hôm nay tại Wild West Hackin' Fest, nhà nghiên cứu bảo mật Wietze Beukema đã tiết lộ nhiều lỗ hổng trong file shortcut LNK của Windows cho phép kẻ tấn công triển khai các payload độc hại.

Beukema [công bố bốn kỹ thuật chưa từng được biết đến trước đây](https://wietzebeukema.nl/blog/trust-me-im-a-shortcut) để thao túng file shortcut LNK của Windows nhằm che giấu mục tiêu độc hại khỏi người dùng khi kiểm tra thuộc tính file.

Các shortcut LNK được giới thiệu từ Windows 95 và sử dụng định dạng nhị phân phức tạp, cho phép kẻ tấn công tạo các file đánh lừa trông hợp lệ trong hộp thoại thuộc tính của Windows Explorer nhưng thực thi các chương trình hoàn toàn khác khi được mở.

[![Wiz](https://www.bleepstatic.com/c/w/MCP-Best-Practices-970x250.png)](https://www.wiz.io/lp/model-context-protocol-mcp-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FMCP-BestPractices-Cheat-Sheet&sfcid=701Py00000TCZuBIAX&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=MCP-Best-Practices) 

Các [vấn đề được phát hiện](https://web.cvent.com/event/1dbf78f6-bde8-4ad2-90f9-3212c148205d/websitePage:64e10132-4cb6-404c-b3b7-7cb06d280643?session=33b06565-b86b-4fe0-964f-8bf12c8c05d6&shareLink=true) khai thác sự không nhất quán trong cách Windows Explorer ưu tiên các đường dẫn mục tiêu xung đột được chỉ định qua nhiều cấu trúc dữ liệu tùy chọn trong file shortcut.

Các biến thể hiệu quả nhất sử dụng các ký tự đường dẫn bị cấm của Windows, như dấu ngoặc kép, để tạo ra các đường dẫn có vẻ hợp lệ nhưng về kỹ thuật là không hợp lệ, khiến Explorer hiển thị một mục tiêu trong khi thực thi một mục tiêu khác. Một biến thể khác sử dụng các giá trị LinkTargetIDList không tuân thủ để thực thi đường dẫn khác với đường dẫn hiển thị trong trường LinkInfo.

"Điều này dẫn đến tình huống kỳ lạ khi người dùng nhìn thấy một đường dẫn trong trường Mục tiêu, nhưng khi thực thi, một đường dẫn hoàn toàn khác được thực thi. Do trường bị vô hiệu hóa, cũng có thể 'ẩn' bất kỳ đối số dòng lệnh nào được cung cấp," Beukema cho biết.

Kỹ thuật mạnh mẽ nhất được xác định liên quan đến việc thao túng cấu trúc EnvironmentVariableDataBlock trong file LNK. Bằng cách chỉ thiết lập trường mục tiêu ANSI và để trống trường Unicode, kẻ tấn công có thể hiển thị mục tiêu giả như "invoice.pdf" trong cửa sổ thuộc tính nhưng thực tế lại thực thi các lệnh PowerShell hoặc các lệnh độc hại khác.

"Mở file LNK sẽ thực thi ngay 'mục tiêu thực sự' mà không cần mở hai lần. Ngoài ra, do trong trường hợp này mục tiêu giả mạo nằm trong TargetIdList và mục tiêu thực nằm trong EnvironmentVariableDataBlock, mục tiêu thực có thể sử dụng các biến môi trường," Beukema giải thích.

"Chương trình/file/thư mục mục tiêu hoàn toàn bị giả mạo," và "mọi đối số dòng lệnh đều bị ẩn đi," nhà nghiên cứu cũng lưu ý, khiến việc phát hiện trở nên cực kỳ khó khăn đối với người dùng.

Điều này có thể xảy ra vì, như Beukema nói, Windows Explorer sẽ xử lý tất cả các shortcut LNK bị biến đổi này một cách khoan dung, hiển thị thông tin giả mạo thay vì từ chối các file không hợp lệ.

Nhà nghiên cứu cũng đã phát hành "[lnk-it-up](https://www.github.com/wietze/lnk-it-up)", một bộ công cụ mã nguồn mở tạo shortcut LNK Windows bằng các kỹ thuật này để kiểm tra và có thể xác định các file LNK độc hại bằng cách dự đoán những gì Explorer hiển thị so với những gì thực sự được thực thi.

![lnk-it-up generating and testing a LNK file](https://www.bleepstatic.com/images/news/u/1109292/2026/2026-02-12-lnk-it-up.png)

_lnk-it-up generating and testing a LNK file (W.J.B. Beukema)_

## MSRC: Không phải lỗ hổng bảo mật

Khi Beukema gửi vấn đề EnvironmentVariableDataBlock cho Microsoft Security Response Center vào tháng 9 (VULN-162145), Microsoft từ chối phân loại nó là lỗ hổng bảo mật, lập luận rằng việc khai thác đòi hỏi tương tác của người dùng và không vi phạm ranh giới bảo mật.

"Những kỹ thuật này không đáp ứng tiêu chuẩn để được xử lý ngay lập tức theo hướng dẫn phân loại mức độ nghiêm trọng của chúng tôi vì chúng yêu cầu kẻ tấn công lừa người dùng chạy file độc hại," phát ngôn viên của Microsoft nói với BleepingComputer khi được hỏi liệu công ty có kế hoạch giải quyết bất kỳ lỗ hổng nào hay không.

"Microsoft Defender có các biện pháp phát hiện để xác định và chặn hoạt động đe dọa này, và Smart App Control cung cấp thêm một lớp bảo vệ bằng cách chặn các file độc hại từ Internet. Như một phương pháp thực hành bảo mật tốt nhất, chúng tôi rất khuyến khích khách hàng lưu ý các cảnh báo bảo mật và tránh mở các file từ nguồn không xác định."

Microsoft cũng lưu ý rằng Windows xác định file shortcut (.lnk) là tiềm ẩn nguy hiểm và khi cố gắng mở file .lnk được tải xuống từ Internet, tự động kích hoạt cảnh báo bảo mật khuyên người dùng không mở file từ các nguồn không xác định. Microsoft khuyến nghị mạnh mẽ nên tuân thủ cảnh báo này.

Tuy nhiên, Beukema bổ sung rằng "có lý do khiến kẻ tấn công vẫn thích file LNK - người dùng nhanh chóng bỏ qua các loại cảnh báo này. Nếu không, CVE-2025-9491 đã không 'thành công' như vậy."

[CVE-2025-9491,](https://nvd.nist.gov/vuln/detail/CVE-2025-9491) lỗ hổng bảo mật được nhắc đến bởi các nhà nghiên cứu bảo mật, tương tự các vấn đề Beukema phát hiện và có thể bị khai thác để ẩn đối số dòng lệnh bằng cách sử dụng phần đệm khoảng trắng quá mức. Các nhóm tội phạm mạng và nhóm hacker được nhà nước hậu thuẫn từ Triều Tiên, Iran, Nga và Trung Quốc đã lạm dụng lỗ hổng bảo mật này trong nhiều năm qua trong các cuộc tấn công zero-day.

Trong khi ban đầu Microsoft cho biết CVE-2025-9491 không vi phạm ranh giới bảo mật và từ chối sửa lỗi này, họ [đã thầm lặng thay đổi file LNK vào tháng 6 năm 2025](https://www.bleepingcomputer.com/news/microsoft/microsoft-mitigates-windows-lnk-flaw-exploited-as-zero-day/) trong nỗ lực giảm thiểu lỗ hổng bị khai thác tích cực này.

Như các nhà phân tích mối đe dọa của Trend Micro tiết lộ vào tháng 3 năm 2025, CVE-2025-9491 đã bị ít nhất [11 nhóm do nhà nước tài trợ và băng đảng tội phạm mạng](http://documents.trendmicro.com/assets/txt/Figure-1-Data---ZDI-CAN-25373-blogcU9ZZ2p.txt) khai thác rộng rãi, bao gồm Evil Corp, Bitter, APT37, APT43 (còn gọi là Kimsuky), Mustang Panda, SideWinder, RedHotel, Konni và những nhóm khác.

Công ty an ninh mạng Arctic Wolf cũng báo cáo vào tháng 10 rằng nhóm hacker Mustang Panda được nhà nước Trung Quốc hậu thuẫn đang [khai thác lỗ hổng Windows này](https://www.bleepingcomputer.com/news/security/chinese-hackers-exploit-windows-zero-day-to-spy-on-european-diplomats/) trong các cuộc tấn công zero-day nhắm vào các nhà ngoại giao châu Âu ở Hungary, Bỉ và các quốc gia châu Âu khác để triển khai phần mềm độc hại RAT PlugX.