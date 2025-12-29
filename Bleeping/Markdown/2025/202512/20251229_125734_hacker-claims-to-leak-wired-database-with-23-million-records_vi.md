# Hacker claims to leak WIRED database with 2.3 million records

![Bàn tay sàng lọc dữ liệu bị rò rỉ](https://www.bleepstatic.com/content/hl-images/2022/10/28/hand-sifting-data.jpg)

Một hacker tuyên bố đã xâm phạm Condé Nast và rò rỉ một cơ sở dữ liệu được cho là của WIRED chứa hơn 2,3 triệu bản ghi thuê bao, đồng thời cảnh báo rằng họ dự định phát hành thêm tới 40 triệu bản ghi cho các ấn phẩm khác của Condé Nast.

Vào ngày 20 tháng 12, một tác nhân đe dọa sử dụng tên "Lovely" đã rò rỉ cơ sở dữ liệu trên một diễn đàn hack, chào bán truy cập với giá khoảng $2.30 trong hệ thống tín dụng của trang. Trong bài đăng, Lovely cáo buộc Condé Nast phớt lờ các báo cáo lỗ hổng và cho rằng công ty không coi trọng an ninh.

"Condé Nast does not care about the security of their users' data. It took us an entire month to convince them to fix the vulnerabilities on their websites," reads a post on a hacking forum.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

"We will leak more of their users' data (40+ million) over the next few weeks. Enjoy!"

![Bài đăng trên diễn đàn rò rỉ dữ liệu của WIRED trên một diễn đàn hack](https://www.bleepstatic.com/images/news/security/d/data-breaches/w/wired/lovely-post.jpg)

**Bài đăng trên diễn đàn rò rỉ dữ liệu của WIRED**  
_Nguồn: BleepingComputer_

Người này sau đó cũng rò rỉ dữ liệu trên các diễn đàn hack khác, nơi người dùng cũng phải tiêu tín dụng diễn đàn để lấy mật khẩu giải nén kho lưu trữ chứa dữ liệu.

Lovely cũng chia sẻ số lượng bản ghi cho các ấn phẩm Condé Nast khác mà họ tuyên bố đã đánh cắp dữ liệu, bao gồm, dựa trên các chữ viết tắt được sử dụng, The New Yorker, Epicurious, SELF, Vogue, Allure, Vanity Fair, Glamour, Men's Journal, Architectural Digest, Golf Digest, Teen Vogue, Style.com, và Condé Nast Traveler.

Mặc dù Condé Nast chưa xác nhận rằng họ bị xâm phạm, BleepingComputer đã phân tích cơ sở dữ liệu rò rỉ và có thể xác thực hai mươi bản ghi là thuê bao WIRED hợp lệ.

Bộ dữ liệu chứa 2,366,576 bản ghi tổng cộng và 2,366,574 địa chỉ email duy nhất, với dấu thời gian từ ngày 26 tháng 4 năm 1996 đến ngày 9 tháng 9 năm 2025.

Mỗi bản ghi bao gồm ID nội bộ duy nhất của thuê bao, một địa chỉ email, và dữ liệu tùy chọn, như tên và họ, số điện thoại, địa chỉ vật lý, giới tính và ngày sinh. Nhiều trường trong số này để trống.

Các bản ghi cũng bao gồm dấu thời gian tạo và cập nhật tài khoản, thông tin phiên truy cập cuối cùng, và các trường đặc thù của WIRED như tên hiển thị và ngày tạo và cập nhật tài khoản WIRED. 

**Ví dụ bản ghi từ dữ liệu bị rò rỉ**  
_Nguồn: BleepingComputer_

Mặc dù nhiều trường bản ghi để trống, một số bản ghi bao gồm thêm chi tiết cá nhân.

Khoảng 284,196 bản ghi (12.01%) bao gồm cả tên và họ, 194,361 bản ghi (8.21%) bao gồm địa chỉ vật lý, 67,223 bản ghi (2.84%) bao gồm ngày sinh, và 32,438 bản ghi (1.37%) bao gồm số điện thoại.

Một tập hợp nhỏ hơn nhiều bao gồm hồ sơ đầy đủ hơn, với 1,529 bản ghi (0.06%) chứa tên đầy đủ, ngày sinh, số điện thoại, địa chỉ và giới tính.

Alon Gal, đồng sáng lập kiêm CTO của Hudson Rock, cũng đã xác minh các bản ghi bằng cách sử dụng nhật ký infostealer chứa thông tin đăng nhập đã bị xâm phạm trước đó.

"Our researchers identified legitimate subscriber credentials for wired.com within global infostealer infection logs," reads an article on Infostealers.com.

"By matching these compromised credentials against the records in the leaked database, we have definitively confirmed the authenticity of the dataset without any interaction with the victim organization."

Cơ sở dữ liệu bị rò rỉ kể từ đó đã được thêm vào Have I Been Pwned, cho phép người dùng kiểm tra xem địa chỉ email của họ có bị lộ do vụ rò rỉ dữ liệu hay không.

## Tự nhận là nhà nghiên cứu bảo mật

Trước khi rò rỉ, Lovely được cho là tự nhận là một nhà nghiên cứu bảo mật đã liên hệ với Dissent Doe của DataBreaches.net để nhờ giúp tiết lộ lỗ hổng một cách có trách nhiệm tới Condé Nast.

Theo DataBreaches.net, cá nhân này đã liên hệ với họ vào cuối tháng 11 để tìm cách tiếp cận đội ngũ bảo mật của Condé Nast về các lỗ hổng mà theo lời họ cho phép kẻ tấn công xem và sửa thông tin tài khoản người dùng.

Người này ban đầu nói rằng họ chỉ tải xuống một số ít bản ghi để làm bằng chứng cho Condé Nast, bao gồm các bản ghi được xác minh thuộc về DataBreaches.net và một nhân viên của WIRED.

Tuy nhiên, sau khi không nhận được phản hồi từ Condé Nast, người này sau đó nói với Dissent Doe rằng họ đã tải xuống toàn bộ cơ sở dữ liệu và đe dọa sẽ rò rỉ nó.

Dissent Doe kết luận rằng cô đã bị lừa và mô tả sự việc như một trường hợp họ bị một tác nhân đe dọa lợi dụng để tải xuống và rò rỉ dữ liệu đã bị đánh cắp thay vì theo đuổi việc tiết lộ có trách nhiệm.

"As for 'Lovely,' they played me. Condé Nast should never pay them a dime, and no one else should ever, as their word clearly cannot be trusted," admitted DataBreaches.net.

BleepingComputer đã liên hệ Condé Nast với các câu hỏi về vụ việc, nhưng chưa nhận được phản hồi vào thời điểm này.