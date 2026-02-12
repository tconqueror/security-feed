# Microsoft: Các vấn đề giả mạo LNK Windows mới không phải là lỗ hổng bảo mật

![Windows](https://www.bleepstatic.com/content/hl-images/2024/12/16/Windows.jpg)

Hôm nay, tại Wild West Hackin' Fest, nhà nghiên cứu bảo mật Wietze Beukema đã tiết lộ nhiều lỗ hổng trong các tệp rút gọn Windows LNK cho phép kẻ tấn công triển khai các tải trọng độc hại.

Beukema [đã ghi lại bốn kỹ thuật trước đây chưa được biết đến](https://wietzebeukema.nl/blog/trust-me-im-a-shortcut) để thao túng các tệp rút gọn Windows LNK nhằm ẩn các mục tiêu độc hại khỏi người dùng kiểm tra thuộc tính tệp.

Các phím tắt LNK được giới thiệu cùng với Windows 95 và sử dụng một định dạng nhị phân phức tạp cho phép kẻ tấn công tạo ra các tệp đánh lừa trông hợp pháp trong hộp thoại thuộc tính của Windows Explorer nhưng thực thi các chương trình hoàn toàn khác khi được mở.

[![Wiz](https://www.bleepstatic.com/c/w/GitLab-970x250.png)](https://www.wiz.io/lp/gitlab-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FGitLab-Security-Best-Practices-Cheat-Sheet&sfcid=701Vh00000Wn1rmIAB&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=GitLab-Best-Practices) 

[Các vấn đề được phát hiện](https://web.cvent.com/event/1dbf78f6-bde8-4ad2-90f9-3212c148205d/websitePage:64e10132-4cb6-404c-b3b7-7cb06d280643?session=33b06565-b86b-4fe0-964f-8bf12c8c05d6&shareLink=true) khai thác sự không nhất quán trong cách Windows Explorer ưu tiên các đường dẫn mục tiêu xung đột được chỉ định trên nhiều cấu trúc dữ liệu tùy chọn trong tệp rút gọn.

Các biến thể hiệu quả nhất sử dụng các ký tự đường dẫn Windows bị cấm, chẳng hạn như dấu ngoặc kép, để tạo ra các đường dẫn có vẻ hợp lệ nhưng về mặt kỹ thuật là không hợp lệ, khiến Explorer hiển thị một mục tiêu trong khi thực thi mục tiêu khác, trong khi một biến thể khác sử dụng các giá trị LinkTargetIDList không tuân thủ để thực thi một đường dẫn khác với đường dẫn được hiển thị trong trường LinkInfo.

"Kết quả là tình huống kỳ lạ khi người dùng thấy một đường dẫn trong trường Target, nhưng khi thực thi, một đường dẫn hoàn toàn khác được thực thi. Do trường bị vô hiệu hóa, cũng có thể 'ẩn' bất kỳ đối số dòng lệnh nào được cung cấp," Beukema cho biết.

Kỹ thuật mạnh mẽ nhất được xác định liên quan đến việc thao túng cấu trúc EnvironmentVariableDataBlock trong các tệp LNK. Bằng cách chỉ đặt trường mục tiêu ANSI và để trống trường Unicode, kẻ tấn công có thể hiển thị một mục tiêu giả như "invoice.pdf" trong cửa sổ thuộc tính trong khi thực tế thực thi PowerShell hoặc các lệnh độc hại khác.

"Mở phím tắt LNK sẽ thực thi mục tiêu 'thực' ngay lập tức, không cần mở nó hai lần. Ngoài ra, vì trong trường hợp này mục tiêu giả nằm trong TargetIdList và mục tiêu thực nằm trong EnvironmentVariableDataBlock, mục tiêu thực có thể sử dụng các biến môi trường," Beukema giải thích.

"Mục tiêu chương trình/tệp/thư mục được giả mạo hoàn toàn," và "bất kỳ đối số dòng lệnh nào cũng bị ẩn," nhà nghiên cứu cũng lưu ý, điều này khiến việc phát hiện trở nên cực kỳ khó khăn đối với người dùng.

Điều này là có thể vì, như Beukema đã nói, Windows Explorer sẽ xử lý tất cả các phím tắt LNK bị hỏng này một cách khoan dung, hiển thị thông tin giả mạo thay vì từ chối các tệp không hợp lệ.

Nhà nghiên cứu cũng đã phát hành "[lnk-it-up](https://www.github.com/wietze/lnk-it-up)," một bộ công cụ mã nguồn mở tạo các phím tắt Windows LNK bằng các kỹ thuật này để kiểm tra và có thể xác định các tệp LNK độc hại bằng cách dự đoán những gì Explorer hiển thị so với những gì thực tế thực thi.

![lnk-it-up generating and testing a LNK file](https://www.bleepstatic.com/images/news/u/1109292/2026/2026-02-12-lnk-it-up.png)

_lnk-it-up generating and testing a LNK file (W.J.B. Beukema)_

## MSRC: Không phải là lỗ hổng bảo mật

Khi Beukema gửi vấn đề EnvironmentVariableDataBlock cho Microsoft Security Response Center vào tháng 9 (VULN-162145), Microsoft đã từ chối phân loại nó là lỗ hổng bảo mật, lập luận rằng việc khai thác yêu cầu tương tác của người dùng và không vi phạm ranh giới bảo mật.

"Các kỹ thuật này không đáp ứng tiêu chuẩn để phục vụ ngay lập tức theo hướng dẫn phân loại mức độ nghiêm trọng của chúng vì chúng yêu cầu kẻ tấn công lừa người dùng chạy một tệp độc hại," một người phát ngôn của Microsoft cho biết khi được hỏi liệu công ty có kế hoạch giải quyết bất kỳ lỗ hổng nào hay không.

"Microsoft Defender có các tính năng phát hiện để xác định và chặn hoạt động đe dọa này, và Smart App Control cung cấp một lớp bảo vệ bổ sung bằng cách chặn các tệp độc hại từ Internet. Là một thực hành bảo mật tốt nhất, chúng tôi khuyến khích mạnh mẽ khách hàng tuân thủ cảnh báo bảo mật và tránh mở các tệp từ các nguồn không xác định."

Microsoft cũng lưu ý rằng Windows xác định các tệp rút gọn (.lnk) là có khả năng nguy hiểm và, khi cố gắng mở một tệp .lnk được tải xuống từ Internet, sẽ tự động kích hoạt cảnh báo bảo mật khuyên người dùng không nên mở các tệp từ các nguồn không xác định. Microsoft khuyến nghị mạnh mẽ tuân thủ cảnh báo này.

Tuy nhiên, Beukema cho biết thêm rằng "có một lý do khiến kẻ tấn công vẫn thích các tệp LNK - người dùng nhanh chóng bỏ qua các cảnh báo này. Nếu không, CVE-2025-9491 sẽ không 'thành công' như vậy."

[CVE-2025-9491,](https://nvd.nist.gov/vuln/detail/CVE-2025-9491) lỗ hổng bảo mật được nhà nghiên cứu bảo mật đề cập, tương tự như các vấn đề Beukema đã phát hiện và có thể được khai thác để ẩn các đối số dòng lệnh bằng cách sử dụng khoảng trắng đệm quá mức. Các nhóm tội phạm mạng và nhóm hack được nhà nước hậu thuẫn từ Triều Tiên, Iran, Nga và Trung Quốc đã lạm dụng lỗ hổng bảo mật này trong nhiều năm trong các cuộc tấn công zero-day.

Mặc dù ban đầu Microsoft cho rằng CVE-2025-9491 không phá vỡ ranh giới bảo mật và từ chối khắc phục sự cố, nhưng vào tháng 6 năm 2025, họ đã [thay đổi thầm lặng các tệp LNK](https://www.bleepingcomputer.com/news/microsoft/microsoft-mitigates-windows-lnk-flaw-exploited-as-zero-day/) trong một nỗ lực rõ ràng nhằm giảm thiểu lỗ hổng này đang bị khai thác tích cực.

Như các nhà phân tích đe dọa của Trend Micro tiết lộ vào tháng 3 năm 2025, CVE-2025-9491 đã được ít nhất [11 nhóm được nhà nước hậu thuẫn và băng nhóm tội phạm mạng](http://documents.trendmicro.com/assets/txt/Figure-1-Data---ZDI-CAN-25373-blogcU9ZZ2p.txt) khai thác rộng rãi, bao gồm Evil Corp, Bitter, APT37, APT43 (còn được gọi là Kimsuky), Mustang Panda, SideWinder, RedHotel, Konni và những nhóm khác.

Công ty an ninh mạng Arctic Wolf cũng báo cáo vào tháng 10 rằng nhóm hack được nhà nước Trung Quốc hậu thuẫn Mustang Panda đã [khai thác lỗ hổng Windows này](https://www.bleepingcomputer.com/news/security/chinese-hackers-exploit-windows-zero-day-to-spy-on-european-diplomats/) trong các cuộc tấn công zero-day nhắm vào các nhà ngoại giao châu Âu ở Hungary, Bỉ và các quốc gia châu Âu khác để triển khai phần mềm độc hại trojan truy cập từ xa (RAT) PlugX.