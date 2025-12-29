# Rò rỉ lớn của Rainbow Six Siege khiến người chơi nhận được hàng tỷ credits

![Rainbow Six Siege](https://www.bleepstatic.com/content/hl-images/2025/12/28/rainbow-6-siege.jpg)

Rainbow Six Siege của Ubisoft (R6) đã gặp một sự cố xâm phạm cho phép kẻ tấn công lợi dụng hệ thống nội bộ để cấm và gỡ cấm người chơi, thao túng dòng thông báo kiểm duyệt trong trò chơi và cấp số lượng lớn tiền trong trò chơi cùng các vật phẩm trang trí cho các tài khoản trên toàn thế giới.

Theo nhiều [báo cáo của người chơi](https://x.com/kinggeorge/status/2004902566434668686) và các ảnh chụp màn hình trong trò chơi được chia sẻ trực tuyến, những kẻ tấn công đã có thể:

* Cấm/gỡ cấm người chơi Rainbow Six Siege
* Hiển thị các thông báo cấm giả trên dòng thông báo cấm
* Cấp cho tất cả người chơi khoảng 2 tỷ R6 Credits và Renown
* Mở khóa mọi vật phẩm trang trí trong trò chơi, bao gồm cả skin chỉ dành cho nhà phát triển

R6 Credits là một loại tiền trong trò chơi cao cấp được bán bằng tiền thật trên cửa hàng của Ubisoft. Dựa trên giá của Ubisoft, 15.000 R6 Credits có giá 99,99 USD, đặt giá trị của 2 tỷ credits vào khoảng 13,33 triệu USD tiền tệ trong trò chơi được phân phát miễn phí.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Lúc 9:10 sáng thứ Bảy, tài khoản chính thức Rainbow Six Siege trên X [xác nhận sự cố](https://x.com/Rainbow6Game/status/2004917731829948808), cho biết Ubisoft đang nhận biết một vấn đề ảnh hưởng đến trò chơi và các đội đang làm việc để khắc phục.

Ngay sau đó, Ubisoft đã chủ động tắt Rainbow Six Siege và Marketplace trong trò chơi, thông báo họ vẫn đang nỗ lực giải quyết sự cố.

"Siege and the Marketplace have been intentionally shut down while the team focuses on resolving the issue," [đọc một bài đăng trên X](http://x.com/rainbow6game/status/2004943312390926740).

Trong cập nhật cuối cùng, Ubisoft làm rõ rằng người chơi sẽ không bị trừng phạt vì đã chi tiêu số credits được cấp, nhưng tất cả các giao dịch kể từ 11:00 AM UTC sẽ bị hoàn tác.

Công ty cũng cho biết Ubisoft không tạo ra các thông điệp thấy được trên dòng thông báo cấm và rằng dòng thông báo đã bị vô hiệu hóa trước đó.

![Fake ban messages on the Rainbow Six Siege ban ticker](https://www.bleepstatic.com/images/news/security/attacks/r/rainbow-six/r6-ban-hack.jpg)

**Các thông báo cấm giả trên dòng thông báo cấm của Rainbow Six Siege**  
_Source: [@ViTo\_DEE91](https://x.com/ViTo%5FDEE91/status/2004910559884628290)_

Ubisoft cho biết họ vẫn đang tiếp tục nỗ lực khôi phục hoàn toàn trò chơi, nhưng các máy chủ hiện vẫn đang tắt.

Tại thời điểm này, Ubisoft chưa phát hành tuyên bố chính thức về sự việc và chưa trả lời các email từ BleepingComputer yêu cầu chi tiết về cách xảy ra vụ xâm phạm.

Nếu bạn có bất kỳ thông tin nào liên quan đến sự cố này hoặc bất kỳ cuộc tấn công chưa được tiết lộ nào khác, bạn có thể liên hệ với chúng tôi một cách bảo mật qua Signal tại 646-961-3731 hoặc qua email tips@bleepingcomputer.com.

## Tin đồn về một sự xâm phạm lớn hơn

Các tuyên bố chưa được kiểm chứng cho rằng một vụ xâm phạm lớn hơn đã xảy ra trong hạ tầng của Ubisoft.

Theo nhóm nghiên cứu an ninh [VX-Underground](https://x.com/vxunderground/status/2005008887234048091), các tác nhân đe dọa cho biết họ đã xâm nhập máy chủ của Ubisoft bằng cách lợi dụng một lỗ hổng MongoDB mới được tiết lộ có tên "MongoBleed."

Được theo dõi dưới mã CVE-2025-14847, lỗ hổng cho phép kẻ tấn công từ xa không xác thực rò rỉ bộ nhớ của các instance MongoDB bị phơi bày, làm lộ thông tin đăng nhập và khóa xác thực. Một PoC công khai đã được phát hành tìm kiếm bí mật trong các máy chủ MongoDB bị phơi bày.

VX-Underground báo cáo rằng nhiều nhóm đe dọa không liên quan có thể đã nhắm vào Ubisoft:

* Một nhóm tuyên bố đã khai thác một dịch vụ của Rainbow Six Siege để thao túng các lệnh cấm và kho vật phẩm trong trò chơi mà không truy cập dữ liệu người dùng.
* Nhóm thứ hai bị cáo buộc đã khai thác một instance MongoDB bằng MongoBleed để pivot vào các kho Git nội bộ của Ubisoft, tuyên bố đã đánh cắp một kho lưu trữ lớn mã nguồn nội bộ từ những năm 1990 đến hiện tại.
* Nhóm thứ ba tuyên bố đã đánh cắp dữ liệu người dùng Ubisoft thông qua MongoBleed và đang cố gắng tống tiền công ty để đòi tiền chuộc.
* Nhóm thứ tư tranh cãi một số tuyên bố này, nói rằng nhóm thứ hai đã có quyền truy cập vào mã nguồn của Ubisoft trong một thời gian.

BleepingComputer chưa thể xác minh độc lập bất kỳ tuyên bố nào trong số này, bao gồm việc MongoBleed có bị khai thác hay không, liệu mã nguồn nội bộ có bị truy cập hay không, hoặc liệu dữ liệu khách hàng có bị đánh cắp hay không.

Tại thời điểm này, chúng ta chỉ biết rằng Ubisoft đã xác nhận hành vi lạm dụng trong game của Rainbow Six Siege, và không có bằng chứng công khai về một sự xâm phạm lớn hơn.

BleepingComputer sẽ cập nhật câu chuyện này nếu Ubisoft cung cấp thêm chi tiết hoặc nếu chúng tôi biết thêm về các tuyên bố khác.