# Chiêu trả lời-bình luận có sức thuyết phục trên LinkedIn được sử dụng trong chiến dịch phishing mới

![LinkedIn](https://www.bleepstatic.com/content/hl-images/2022/10/26/linkedin-header.jpg)

Kẻ lừa đảo đang tràn ngập các bài đăng trên LinkedIn tuần này bằng các bình luận "reply" giả mạo có vẻ như đến từ chính nền tảng, cảnh báo người dùng về các vi phạm chính sách giả và thúc giục họ truy cập một liên kết bên ngoài.

Các tin nhắn này mạo danh thương hiệu LinkedIn một cách thuyết phục và trong một số trường hợp thậm chí sử dụng bộ rút gọn URL chính thức của công ty, lnkd.in, khiến các liên kết phishing khó phân biệt với liên kết hợp pháp hơn.

## 'Truy cập vào tài khoản của bạn tạm thời bị hạn chế'

Trong vài ngày qua, người dùng LinkedIn đã trở thành mục tiêu của các hoạt động giống bot từ một số hồ sơ mang chủ đề LinkedIn bình luận trên bài đăng của họ.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Những bài đăng này tuyên bố sai rằng người dùng đã "tham gia vào các hoạt động không tuân thủ" nền tảng và rằng tài khoản của họ đã bị "tạm thời hạn chế" cho đến khi họ truy cập liên kết được chỉ định trong bình luận.

Phản hồi giả mạo mang logo LinkedIn, được trình bày bên dưới và [lưu trữ tại đây](http://archive.md/xFDiL), trông khá thuyết phục tùy thuộc vào cách người xem tương tác với khu vực bình luận và thiết bị họ đang sử dụng.

![Fake LinkedIn reply-comment urging users to visit a phishing page](https://www.bleepstatic.com/images/news/u/1164866/2026/Jan/linkedin-fake-comment-replies/LinkedIn-fake-suspension-comment.jpg)

Bình luận-phản hồi giả mạo LinkedIn khuyến khích người dùng truy cập một trang phishing

"Chúng tôi thực hiện các bước để bảo vệ tài khoản của bạn khi phát hiện dấu hiệu truy cập trái phép tiềm tàng. Điều này có thể bao gồm việc đăng nhập từ các vị trí không quen thuộc hoặc..." cũng là nội dung xem trước liên kết được tạo trong phản hồi được dựng sẵn.

Ví dụ chia sẻ ở trên cho thấy một tên miền ".app" gồm ký tự chữ-số không liên quan đến LinkedIn và có thể khiến một số người dùng nghi ngờ. Tuy nhiên, các bài đăng khác đưa mồi nhử này lên một bước nữa bằng cách che giấu các liên kết đích qua bộ rút gọn URL chính thức của LinkedIn, lnkd.in, khiến các tên miền phishing khó bị phát hiện mà không nhấp vào chúng. Điều này có thể đặc biệt đáng lo ngại nếu xem trước liên kết không hiển thị đầy đủ trên một số thiết bị.

Các ví dụ về những phản hồi và bình luận như vậy đã được chia sẻ bởi một số thành viên LinkedIn, bao gồm Ratko Ivekovic, Jocelyn M., Candyce Edelen, và Adama Coulibaly.

Phản hồi lạm dụng bộ rút gọn URL lnkd.in (Jocelyn M on LinkedIn)

Trang phishing _very1929412.netlify[.]app_ cụ thể, được BleepingComputer ghi nhận, đầu tiên mở rộng về "hạn chế tạm thời" giả và khuyên người xem rằng họ cần "xác minh" danh tính của mình để gỡ hạn chế:

First LinkedIn phishing domain (BleepingComputer)

Khi nhấp, nút "Verify your identity" chuyển hướng người dùng đến một tên miền phishing khác, _https://very128918[.]site_ nơi thực sự diễn ra việc thu thập thông tin đăng nhập:

Second LinkedIn-themed phishing domain harvesting credentials  
(BleepingComputer)

## Các trang Company trên LinkedIn bị lạm dụng

Những bình luận này được đăng từ các trang công ty giả mạo sử dụng logo chính thức của LinkedIn và một biến thể của tên nền tảng, ví dụ Linked Very.

Edelen đã chia sẻ [một vài tài khoản "Linked Very"](https://archive.md/wip/h7hVS) đã xuất hiện trên nền tảng mạng chuyên nghiệp trong tuần qua.

Tại thời điểm viết bài, [trang được hiển thị bên dưới](http://archive.md/igUgw) đã bị LinkedIn gỡ xuống:

Một trang Company trên LinkedIn mạo danh LinkedIn (BleepingComputer)

## LinkedIn biết về và đang xử lý chiến dịch

BleepingComputer đã liên hệ với LinkedIn để hỏi liệu nền tảng có biết về chiến dịch đang diễn ra này hay không.

"Tôi có thể xác nhận rằng chúng tôi biết về hoạt động này và các nhóm của chúng tôi đang làm việc để có hành động," một người phát ngôn của LinkedIn tuyên bố với BleepingComputer.

"Điều quan trọng cần lưu ý là LinkedIn không và sẽ không thông báo vi phạm chính sách tới thành viên thông qua các bình luận công khai, và chúng tôi khuyến khích thành viên [gửi báo cáo](http://www.linkedin.com/help/linkedin/answer/a1338436?hcppcid=search) nếu họ gặp phải hành vi đáng ngờ này. Bằng cách đó chúng tôi có thể xem xét và thực hiện hành động phù hợp."

Trong năm 2023, BleepingComputer [lần đầu báo cáo](https://www.bleepingcomputer.com/news/security/convincing-twitter-quote-tweet-phone-scam-targets-bank-customers/) một trò lừa đảo trên X (khi đó là Twitter) thuyết phục trong đó các tài khoản mạo danh các ngân hàng lớn trả lời các khiếu nại của khách hàng gửi đến các tổ chức thực, thúc giục họ liên hệ với một số điện thoại do kẻ lừa đảo kiểm soát.

Người dùng cần luôn cảnh giác và tránh tương tác với các bình luận, phản hồi hoặc tin nhắn riêng tư có vẻ mạo danh LinkedIn và thúc giục người nhận nhấp vào các liên kết bên ngoài.