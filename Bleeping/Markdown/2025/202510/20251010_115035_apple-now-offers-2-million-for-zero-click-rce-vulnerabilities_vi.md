# Apple hiện cung cấp $2 million cho lỗ hổng RCE không cần tương tác (zero-click)

![Apple hiện cung cấp $2 million cho lỗ hổng RCE không cần tương tác (zero-click)](https://www.bleepstatic.com/content/hl-images/2025/08/20/Apple_logo.jpg)

Apple đang công bố một sự mở rộng và thiết kế lại lớn cho chương trình tiền thưởng lỗi của mình, tăng gấp đôi mức thưởng tối đa, thêm các hạng mục nghiên cứu mới và giới thiệu một cấu trúc phần thưởng minh bạch hơn.

Kể từ khi chương trình ra mắt vào năm 2020, Apple đã trao $35 million cho 800 nhà nghiên cứu bảo mật, công ty đã chi trả $500,000 cho một số báo cáo được gửi đến.

Mức thưởng cao nhất đã được tăng gấp đôi lên $2 million, dành cho việc báo cáo các lỗ hổng có thể dẫn đến việc bị chiếm quyền từ xa không cần tương tác (zero-click), tương tự như [các cuộc tấn công phần mềm gián điệp "mercenary"](https://www.bleepingcomputer.com/news/security/apple-warns-customers-targeted-in-recent-spyware-attacks/). Tuy nhiên, các khoản thanh toán có thể lên tới $5 million thông qua hệ thống tiền thưởng bổ sung.

“Đây là một mức chưa từng có trong ngành và là khoản thanh toán lớn nhất mà bất kỳ chương trình tiền thưởng nào mà chúng tôi biết đến từng cung cấp — và hệ thống tiền thưởng của chúng tôi, cung cấp phần thưởng bổ sung cho việc vượt qua Lockdown Mode và các lỗ hổng được phát hiện trong beta software, có thể hơn gấp đôi khoản thưởng này, với mức thanh toán tối đa vượt quá $5 million,” [theo Apple](https://security.apple.com/blog/apple-security-bounty-evolved/).

Các khoản thanh toán khác được tăng hoặc được giới thiệu theo sơ đồ chương trình mới bao gồm:

* One-click (cần tương tác người dùng) remote attack - $1,000,000
* Wireless proximity attack - $1,000,000
* Broad unauthorized iCloud access - $1,000,000
* WebKit exploit chain dẫn đến unsigned arbitrary code execution - $1,000,000
* Tấn công lên thiết bị bị khóa có quyền truy cập vật lý - $500,000
* Thoát khỏi sandbox ứng dụng (App sandbox escape) - $500,000
* One-click WebKit sandbox escape - $300,000
* Bypass hoàn toàn macOS Gatekeeper mà không cần tương tác người dùng - $100,000
* $1,000 “encouragement award” cho các báo cáo có ảnh hưởng thấp nhưng hợp lệ

Apple cho biết rằng họ chưa bao giờ nhận được một báo cáo chứng minh bypass hoàn toàn Gatekeeper mà không cần tương tác người dùng hay truy cập iCloud trái phép ở quy mô lớn, vì vậy hai mục này là những thách thức lớn đối với các thợ săn tiền thưởng.

Ngoài ra, Apple nói rằng họ “chưa bao giờ quan sát thấy một cuộc tấn công zero-click thực tế được thực hiện hoàn toàn qua wireless proximity,” ám chỉ tới khoản thưởng $1M ‘Wireless Proximity’, được nâng từ $250,000 trước đó.

Hạng mục này cũng đang được mở rộng, hiện bao gồm các chip do Apple phát triển như C1 và C1X modem và chip không dây N1.

Cho năm 2026, Apple dự định phân phát một nghìn thiết bị iPhone 17 được bảo mật cho các thành viên của các tổ chức xã hội dân sự có nguy cơ cao bị nhắm mục tiêu bởi phần mềm gián điệp vụ thuê.

Cùng những thiết bị này sẽ phục vụ cho chương trình Security Research Device Program của Apple vào năm tới, mà các nhà nghiên cứu bảo mật có thể nộp đơn xin đến ngày October 31.

Gã khổng lồ công nghệ mong rằng các khoản thưởng tăng lên sẽ có ảnh hưởng bổ sung tới việc phát triển các chuỗi tấn công tinh vi từ các nhà cung cấp phần mềm gián điệp, vì các nhà nghiên cứu sẽ có động lực hơn để tìm và báo cáo các vấn đề bảo mật.

Để bảo vệ người dùng khỏi các cuộc tấn công phần mềm gián điệp tinh vi, Apple đã triển khai trong iOS các biện pháp bảo vệ nâng cao như Lockdown Mode và Memory Integrity Enforcement, giúp làm cho việc phát triển và thực hiện các cuộc tấn công phần mềm gián điệp tinh vi trở nên tốn kém hơn.