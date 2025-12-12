# Shadow spreadsheets: The security gap your tools can’t see

![Grist hình tiêu đề](https://www.bleepstatic.com/content/posts/2025/12/11/grist-security-header.png)

Đội IT của bạn vừa hoàn thành một bài kiểm tra bảo mật toàn diện. Mạng đã được khóa chặt. Ngăn xếp công nghệ của tổ chức bạn đã bật MFA trên toàn bộ. Nhân viên vừa hoàn thành đào tạo chống lừa đảo qua email.

Và hôm qua, Bob từ Finance đã chia sẻ dự báo doanh thu Q3 với một liên kết Google Sheets được đặt ở chế độ "anyone with the link can edit." Bob chỉ đang làm công việc của mình theo cách thuận tiện cho anh ấy. Tuy nhiên, điều đó không ngăn được liên kết Google Sheets của Bob trở thành mắt xích yếu nhất của toàn bộ hệ thống của bạn.

Mối đe dọa nội bộ thường được hiểu là nhân viên bất mãn đánh cắp dữ liệu. Nhưng những người có thiện ý như Bob sử dụng bảng tính vì các công cụ được phê duyệt không thể làm mọi thứ họ cần lại phổ biến hơn nhiều.

Có thể phần mềm ERP mạnh mẽ đó làm được 90% công việc mọi người cần, nhưng 10% còn lại — dù là chỉnh sửa biểu đồ hay xuất báo cáo PDF — lại không đủ để hoàn thành dự án.

Vậy nên mọi người xuất dữ liệu. Họ kéo dữ liệu vào bảng tính, làm 10% cuối cùng, và rồi có thể — có thể — cập nhật hoặc đối chiếu hệ thống chính thức sau. Bảng tính đó vẫn ở đó, trôi nổi cho bất kỳ ai có liên kết. Hãy gọi đây là ‘shadow spreadsheet’.

Tại Grist Labs chúng tôi thấy các đội IT phải xử lý shadow spreadsheets hàng ngày. Chúng tôi đã xây một spreadsheet-database mã nguồn mở để xoá những cái bóng này, nhưng sẽ nói về điều đó sau. Trước hết, hãy xem lý do tại sao shadow spreadsheets là vấn đề thực sự.

## Cách một shadow spreadsheet trở thành rủi ro bảo mật

Khi các đội chuyển dữ liệu quan trọng sang bảng tính, chúng tôi thường thấy một trong hai kịch bản, cả hai đều không lý tưởng:

### Chia sẻ quá mức theo mặc định

Ai đó tạo một bảng tính chính để cộng tác. Họ đặt chia sẻ là “anyone in the organization with this link” và gửi nó cho mọi người trong một kênh Slack.

Giờ thì toàn công ty bạn có thể truy cập dữ liệu lương, điều khoản thanh toán của khách hàng, kế hoạch mở rộng chiến lược, hoặc bất cứ thứ gì bảng tính đó chứa. Phần lớn sẽ không truy cập, nhưng bạn đã mất kiểm soát ai có thể, có lẽ mà không hề có khả năng được thông báo.

Bỏ qua an ninh, có thể bảng tính này bắt đầu vượt quá giới hạn của Sheets hoặc Excel? Nhân viên xây dựng ứng dụng trong bảng tính suốt, họ chỉ không luôn gọi chúng là ứng dụng. Các công thức mong manh trong những bảng tính biến thành ứng dụng này có thể biến một lỗi gõ thành ba giờ khắc phục.

Rồi, trong nỗ lực ngăn điều này tái diễn, IT thêm một hàng màu đỏ nổi bật bên trên mỗi phần quan trọng ghi “WARNING: DO NOT TOUCH THIS FORMULA, EVER.” Bob từ Finance ngay lập tức động vào công thức.

### Sự bùng nổ bảng tính

Để tránh chia sẻ quá mức, mọi người lo lắng và thay vào đó tạo các bản sao "an toàn". Phiên bản này cho Finance, phiên bản kia cho ban điều hành, một bản khác cho tư vấn họ thuê. Sáu phiên bản của cùng một bảng tính lưu hành qua email, Slack DM, và thư mục SharePoint. Có vẻ như ai đó còn có một bản trên Google Drive cá nhân nữa.

Phiên bản nào là chính thức, hoặc thậm chí là hiện hành? Ai có quyền truy cập gì? Khi ai đó phát hiện lỗi, phiên bản nào được sửa? Và quan trọng nhất, việc này gây ra loại mối đe dọa lộ thông tin nào?

Bằng cách ưu tiên khả năng hiển thị, nhân viên cũng làm tổn hại tính toàn vẹn và giờ theo dõi kiểm toán của bạn đã biến mất.

![Grist dashboard](https://www.bleepstatic.com/images/news/Microsoft/Windows-10/esu/grist-dashboard-1.png)

## Những gì khiến các CISO trăn trở

Bob chuyển tiếp một bảng phân tích khách hàng cho một tư vấn viên đang làm dự án cho họ. Bảng tính có nhiều tab. Tư vấn viên chỉ cần tab ba. Tab bảy, mà Bob quên mất, chứa điều khoản hợp đồng khách hàng, ngày gia hạn và giá cho các tài khoản lớn.

Tư vấn viên không cố gắng thực hiện hành vi ăn cắp danh tính. Tuy nhiên, họ cũng có thể không bị ràng buộc bởi chính sách DLP của tổ chức bạn. Những thông tin nhạy cảm đó giờ đã ra ngoài phạm vi bảo vệ của bạn, và bạn không biết chúng có thể đi đâu tiếp theo.

Shadow spreadsheets tạo ra một bề mặt tấn công mà không thể vẽ bản đồ. Nếu bạn không biết có bao nhiêu bản sao khác nhau tồn tại, nơi chúng nằm, hoặc ai đã truy cập và tải xuống chúng, tất cả những gì bạn biết là bạn đang gặp rắc rối.

Khi thực sự có một tác nhân xấu liên quan, dữ liệu phân mảnh tạo ra sự chối bỏ hợp lý. Nếu không có nguồn dữ liệu chính thức với nhật ký kiểm toán, không có cách nào để chứng minh họ đã truy cập, thay đổi hay xuất gì trong một sheet.

Nếu hệ thống chính thức quá cứng nhắc để hỗ trợ công việc thực tế, mọi người sẽ luôn tìm cách làm việc xung quanh nó. Bạn giải quyết điều này thế nào?

## [Các ứng dụng dữ liệu có cấu trúc mà cảm giác như bảng tính. An toàn, có thể mở rộng, tự-host.](https://www.getgrist.com/solve-spreadsheet-problems/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=placement&utm%5Fcampaign=bleeping-computer&utm%5Fcontent=shadow-spreadsheets)

Grist mang lại cho các đội sự linh hoạt của bảng tính mà IT cần các quyền truy cập bắt buộc.

Quyền ở mức chi tiết, nhật ký kiểm toán đầy đủ, mã nguồn mở, và các tùy chọn triển khai self-hosted. Không bị ràng buộc nhà cung cấp.

[Bắt đầu miễn phí](https://www.getgrist.com/solve-spreadsheet-problems/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=placement&utm%5Fcampaign=bleeping-computer&utm%5Fcontent=shadow-spreadsheets)

## Tại sao những giải pháp hiển nhiên thất bại

Đào tạo sẽ không sửa được một công cụ không làm được những gì mọi người cần. Bạn cũng không thể lập chính sách để vượt qua cuộc đụng độ không thể tránh giữa kiểm soát bảo mật và “chỉ để hoàn thành công việc”.

Nếu bạn thắt chặt? Khóa chia sẻ tệp và triển khai DLP để đánh dấu hoặc chặn tệp đính kèm bảng tính chứa dữ liệu nhạy cảm? Mọi người thường sẽ tìm các cách giải quyết ít an toàn hơn nữa – ổ USB, tài khoản Dropbox cá nhân – vì họ có công việc phải làm. Điều này chỉ làm vấn đề trở nên khó theo dõi hơn.

Còn việc xây một ứng dụng nội bộ được thiết kế riêng theo cách nhóm bạn làm việc? Giờ bạn đang nhìn vào sáu tháng phát triển và chi phí 200k$+.

Khi bạn đã xác định yêu cầu, thuê bên nhận thầu, và điều phối mua sắm, đội cần giải pháp từ chín tháng trước đã lưu hành hàng chục shadow spreadsheets. Và khi nhu cầu kinh doanh thay đổi, đó là một trò chơi đuổi bắt không hồi kết. Các dự án tùy chỉnh giải quyết vấn đề linh hoạt và bảo mật bằng cách tạo ra gánh nặng bảo trì không bao giờ hết.

Chúng tôi thấy mọi người dùng bảng tính vì một bảng tính thực sự tốt cho hầu hết mọi thứ. Đó là một giao diện phổ quát mà hầu hết mọi người hiểu. Nhiều nền tảng SaaS về cơ bản là một bảng tính với giao diện người dùng đẹp. Chống lại bảng tính thường có nghĩa là chống lại phần lớn tổ chức của bạn.

Vậy nếu bạn không thể chống lại bảng tính, tại sao không bảo mật nó?

![Grist kết hợp những phần tốt nhất của bảng tính, cơ sở dữ liệu và trình tạo ứng dụng để có cấu trúc và an toàn.](https://www.bleepstatic.com/images/news/security/g/grist/insider-risk/grist-circle.jpg)

**Grist kết hợp những phần tốt nhất của bảng tính, cơ sở dữ liệu và trình tạo ứng dụng để có cấu trúc và an toàn.**

## Grist: nơi bảng tính bước ra khỏi bóng tối

Tại Grist Labs, chúng tôi đã đặt mục tiêu tạo phần mềm giữ những điều tốt nhất của bảng tính và tránh những điều tồi tệ nhất. Chúng tôi được sáng lập bởi một ex-Google Sheets engineer quá hiểu rõ điểm mạnh và điểm yếu của lưới bảng truyền thống. Grist được làm để nhìn và cảm nhận như một bảng tính, nhưng được xây dựng trên một cơ sở dữ liệu quan hệ cho phép kiểm soát truy cập theo vai trò chi tiết.

Bạn có thể self-host Grist trên hạ tầng của riêng bạn, có nghĩa là dữ liệu nhạy cảm không bao giờ rời khỏi môi trường của bạn. RBAC của chúng tôi có thể được thiết lập ở cấp cột và hàng, có nghĩa người dùng có thể cộng tác theo thời gian thực, trong khi mọi người, từ nhà thầu bên ngoài đến điều hành, chỉ thấy những gì họ nên thấy mà không cần tạo bản sao. Đó là một nguồn sự thật duy nhất thực sự.

Thêm nữa, bạn có thể hạn chế khả năng Bob làm hỏng các công thức quan trọng một lần nữa.

Bạn có thể kết nối Grist với SSO, và chạy nó phía sau một VPN hoặc thậm chí air-gapped. Phiên bản Enterprise của chúng tôi bao gồm các quyền quản trị bổ sung. Trong số những thứ khác, điều này cho phép bạn xem danh sách tất cả các tài liệu được chia sẻ bằng liên kết trên toàn bộ cài đặt của bạn, hoặc xác nhận chính xác Bob có thể truy cập gì. Bạn cũng có thể bật ghi nhật ký kiểm toán kết nối với hệ thống SIEM bên ngoài của bạn.

Khi bạn có các công cụ mang cảm giác quen thuộc và phù hợp với người dùng, việc áp dụng là khả thi. Thay vì chống lại trải nghiệm bảng tính, hãy sử dụng nó như một giao diện nền tảng chung phù hợp với mọi người ngoại trừ những tác nhân xấu tiềm năng.

**[Hãy tự mình xem sự tiến hoá của bảng tính ngay hôm nay.](https://www.getgrist.com/solve-spreadsheet-problems/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=placement&utm%5Fcampaign=bleeping-computer&utm%5Fcontent=shadow-spreadsheets)**

_Được tài trợ và viết bởi [Grist](https://www.getgrist.com/solve-spreadsheet-problems/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=placement&utm%5Fcampaign=bleeping-computer&utm%5Fcontent=shadow-spreadsheets)._