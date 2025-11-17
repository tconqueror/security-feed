# Pennsylvania AG xác nhận vi phạm dữ liệu sau cuộc tấn công của INC Ransom

![Tổng Chưởng lý bang Pennsylvania Dave Sunday](https://www.bleepstatic.com/content/hl-images/2025/11/17/Pennsylvania_Attorney_General_Dave_Sunday.jpg)

Văn phòng Tổng Chưởng lý bang Pennsylvania đã xác nhận rằng nhóm ransomware đứng sau một cuộc tấn công mạng vào tháng 8 năm 2025 đã đánh cắp các tệp chứa thông tin cá nhân và y tế.

Điều này diễn ra sau khi Tổng Chưởng lý Dave Sunday [xác nhận vào đầu tháng Chín](https://www.bleepingcomputer.com/news/security/pennsylvania-ag-office-says-ransomware-attack-behind-recent-outage/) rằng sự cố là một cuộc tấn công bằng ransomware và văn phòng của ông đã từ chối trả khoản tiền chuộc mà các tội phạm mạng yêu cầu sau khi họ mã hóa các hệ thống bị xâm phạm.

"Văn phòng OAG sau đó biết rằng một số tệp có thể đã bị truy cập mà không được phép. OAG đã xem xét các dữ liệu có thể liên quan và biết rằng một số tệp chứa thông tin cá nhân," [nói](https://www.prnewswire.com/news-releases/media-notice-pennsylvania-office-of-attorney-general-provides-notice-of-data-incident-302615934.html) Văn phòng Tổng Chưởng lý bang Pennsylvania (OAG) trong một thông cáo báo chí vào thứ Sáu.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

"Dựa trên việc OAG xem xét các dữ liệu liên quan, đối với một số cá nhân thông tin có thể bao gồm tên, Social Security number, và/hoặc thông tin y tế."

Vào ngày 9 tháng 8, khi vụ xâm phạm được phát hiện, các tác nhân đe dọa [đã làm sập các hệ thống](https://www.bleepingcomputer.com/news/security/pennsylvania-attorney-generals-email-site-down-after-cyberattack/) và dịch vụ trên mạng của Pennsylvania OAG, bao gồm trang web của văn phòng, tài khoản email của nhân viên và đường dây điện thoại cố định, trong một cuộc tấn công có tác động rộng và tê liệt.

Mặc dù Pennsylvania OAG vẫn chưa chia sẻ thêm thông tin về cách mạng bị xâm phạm, [chuyên gia an ninh mạng Kevin Beaumont phát hiện](https://cyberplace.social/@GossiTheDog/114852498783201767) rằng mạng của Pennsylvania AG có một số thiết bị Citrix NetScaler công khai dễ bị tấn công đang diễn ra, khai thác một lỗ hổng nghiêm trọng (CVE-2025-5777) được biết đến với tên Citrix Bleed 2.

Theo Beaumont, một trong hai thiết bị [đã ngừng hoạt động kể từ ngày 29 tháng 7](https://beta.shodan.io/host/207.218.103.19), trong khi thiết bị còn lại [đã bị ngoại tuyến kể từ ngày 7 tháng 8](https://beta.shodan.io/host/207.218.103.174).

## Vụ vi phạm được INC Ransom nhận trách nhiệm

Mặc dù Pennsylvania OAG không công khai quy trách nhiệm vụ vi phạm cho một nhóm ransomware cụ thể, nhóm INC Ransom đã nhận trách nhiệm về cuộc tấn công vào ngày 20 tháng 9, khi họ thêm vụ việc này làm một mục mới trên trang rò rỉ dark web của họ.

Vào thời điểm đó, nhóm ransomware khẳng định rằng họ đã đánh cắp 5.7TB dữ liệu từ mạng của Pennsylvania OAG và nói rằng vụ vi phạm được cho là đã cung cấp cho họ quyền truy cập vào một mạng nội bộ của FBI.

![Mục Pennsylvania OAG trên trang INC Ransom](https://www.bleepstatic.com/images/news/u/1109292/2025/Pennsylvania%20OAG%20entry%20on%20INC%20Ransom%20website.png)

_Pennsylvania OAG được INC Ransom tuyên bố (BleepingComputer)_

INC Ransom xuất hiện như một hoạt động ransomware-as-a-service (RaaS) vào tháng 7 năm 2023 và kể từ đó đã nhắm mục tiêu các tổ chức ở cả khu vực tư và công trên toàn thế giới.

Danh sách nạn nhân của nhóm trải rộng trên nhiều ngành, từ giáo dục và chăm sóc sức khỏe đến chính phủ và các thực thể như Yamaha Motor Philippines, Scotland's National Health Service (NHS), tập đoàn bán lẻ thực phẩm Ahold Delhaize, và chi nhánh Hoa Kỳ của Xerox Business Solutions (XBS).

Đây là lần thứ ba các thực thể bang Pennsylvania bị xâm phạm trong một cuộc tấn công ransomware: Delaware County đã trả 500.000 USD tiền chuộc sau một cuộc tấn công của DoppelPaymer vào năm 2020 để khôi phục hệ thống bị mã hóa, và một cuộc tấn công ransomware đã làm tê liệt mạng của Pennsylvania Senate Democratic Caucus vào năm 2017.