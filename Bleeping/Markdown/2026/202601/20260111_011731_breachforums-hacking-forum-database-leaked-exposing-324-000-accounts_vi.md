# Cơ sở dữ liệu diễn đàn hacker BreachForums bị rò rỉ, lộ 324,000 tài khoản

![Tin tặc giơ tay lên](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

Phiên bản mới nhất của diễn đàn hacker khét tiếng BreachForums đã chịu một vụ rò rỉ dữ liệu, với bảng cơ sở dữ liệu người dùng của nó bị rò rỉ trực tuyến.

BreachForums là tên của một chuỗi diễn đàn hacker được sử dụng để giao dịch, bán và rò rỉ dữ liệu bị đánh cắp, cũng như bán quyền truy cập vào mạng lưới doanh nghiệp và các dịch vụ tội phạm mạng bất hợp pháp khác.

Trang này được ra mắt sau khi diễn đàn đầu tiên trong số các diễn đàn này, RaidForums, [đã bị cơ quan thực thi pháp luật thu giữ](https://www.bleepingcomputer.com/news/security/raidforums-hacking-forum-seized-by-police-owner-arrested/), với chủ sở hữu, "Omnipotent", bị bắt.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Mặc dù BreachForums đã [chịu các vụ rò rỉ dữ liệu](https://www.bleepingcomputer.com/news/security/breachforums-v1-hacking-forum-data-leak-exposes-members-info/) và [các hành động của cảnh sát](https://www.bleepingcomputer.com/news/security/fbi-seizes-breachforums-after-arresting-its-owner-pompompurin-in-march/) trong [quá khứ](https://www.bleepingcomputer.com/news/security/fbi-seize-breachforums-hacking-forum-used-to-leak-stolen-data/), nó đã nhiều lần được khởi động lại dưới các tên miền mới, với một số người cáo buộc nó hiện là một honeypot cho cơ quan thực thi pháp luật.

Hôm qua, một website mang tên nhóm tống tiền ShinyHunters đã phát hành một tệp lưu trữ 7Zip có tên breachedforum.7z.

Kho lưu trữ này chứa ba tệp có tên:

* shinyhunte.rs-the-story-of-james.txt
* databoose.sql
* breachedforum-pgp-key.txt.asc

Một đại diện của nhóm tống tiền ShinyHunters đã nói với BleepingComputer rằng họ không liên kết với trang đã phân phối kho lưu trữ này.

Tệp 'breachedforum-pgp-key.txt.asc' trong kho là khóa riêng PGP được tạo vào ngày 25 tháng 7 năm 2023, và được BreachForums sử dụng để ký các thông điệp chính thức từ quản trị viên. Mặc dù khóa đã bị rò rỉ, nó được bảo vệ bằng passphrase, và nếu không có mật khẩu thì khóa không thể bị lạm dụng để ký thông điệp.

![Passphrase-protected BreachForums PGP private key](https://www.bleepstatic.com/images/news/security/d/data-breaches/b/breachforums-2025/pgp-passphrase.jpg)

**Khóa riêng PGP của BreachForums được bảo vệ bằng passphrase**  
_Nguồn: BleepingComputer_

Tệp "databoose.sql" là một bảng cơ sở dữ liệu người dùng MyBB (mybb\_users) chứa 323,988 hồ sơ thành viên bao gồm tên hiển thị thành viên, ngày đăng ký, địa chỉ IP và các thông tin nội bộ khác.

Phân tích của BleepingComputer về bảng cho thấy hầu hết các địa chỉ IP quy về địa chỉ IP vòng lặp cục bộ (0x7F000009/127.0.0.9), vì vậy chúng không hữu ích nhiều.

Tuy nhiên, 70,296 hồ sơ không chứa địa chỉ IP 127.0.0.9, và các hồ sơ chúng tôi kiểm tra quy về một địa chỉ IP công cộng. Những địa chỉ IP công cộng này có thể là mối quan ngại OPSEC đối với những người đó và có giá trị đối với cơ quan thực thi pháp luật và các nhà nghiên cứu an ninh mạng.

Ngày đăng ký cuối cùng trong cơ sở dữ liệu người dùng mới bị rò rỉ là ngày 11 tháng 8 năm 2025, trùng với ngày diễn đàn BreachForums trước đó tại breachforums[.]hn bị đóng cửa. Việc đóng cửa này diễn ra sau vụ bắt giữ một số [nghi phạm điều hành](https://www.bleepingcomputer.com/news/security/breachforums-hacking-forum-operators-reportedly-arrested-in-france/) của nó.

Cùng ngày đó, một thành viên của nhóm tống tiền ShinyHunters [đã đăng một thông điệp](https://web.archive.org/web/20250811213740/https://pastebin.com/raw/EDUtVYq2) trên kênh Telegram "Scattered Lapsus$ Hunters", tuyên bố diễn đàn là một honeypot của cơ quan thực thi pháp luật. Các quản trị viên BreachForums sau đó đã phủ nhận những cáo buộc này.

Tên miền breachforums[.]hn sau đó đã bị [cơ quan thực thi pháp luật thu giữ](https://www.bleepingcomputer.com/news/security/fbi-takes-down-breachforums-portal-used-for-salesforce-extortion/) vào tháng 10 năm 2025 sau khi nó [bị tái sử dụng để tống tiền các công ty](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/) bị ảnh hưởng bởi các vụ trộm dữ liệu Salesforce quy mô lớn do nhóm tống tiền ShinyHunters tiến hành.

Quản trị viên hiện tại của BreachForums, được biết đến với tên "N/A," đã thừa nhận vụ rò rỉ mới, cho biết một bản sao lưu của bảng cơ sở dữ liệu người dùng MyBB đã tạm thời bị phơi bày trong một thư mục không an toàn và chỉ được tải xuống một lần.

"Chúng tôi muốn giải quyết các cuộc thảo luận gần đây liên quan đến một vụ rò rỉ cơ sở dữ liệu được cho là và giải thích rõ ràng những gì đã xảy ra," N/A đã viết trên BreachForums.

"Trước hết, đây không phải là một sự cố gần đây. Dữ liệu được đề cập xuất phát từ một vụ rò rỉ bảng người dùng cũ có niên đại từ tháng 8 năm 2025, trong giai đoạn BreachForums đang được phục hồi/khôi phục từ tên miền .hn."

"Trong quá trình phục hồi, bảng người dùng và khóa PGP của diễn đàn đã tạm thời được lưu trong một thư mục không an toàn trong một khoảng thời gian rất ngắn. Cuộc điều tra của chúng tôi cho thấy thư mục đó chỉ được tải xuống một lần trong khoảng thời gian đó," quản trị viên tiếp tục.

Mặc dù quản trị viên khuyên các thành viên BreachForums nên sử dụng địa chỉ email dùng một lần để giảm rủi ro và rằng hầu hết địa chỉ IP quy về các IP cục bộ, cơ sở dữ liệu vẫn chứa thông tin có thể thu hút sự quan tâm của cơ quan thực thi pháp luật.