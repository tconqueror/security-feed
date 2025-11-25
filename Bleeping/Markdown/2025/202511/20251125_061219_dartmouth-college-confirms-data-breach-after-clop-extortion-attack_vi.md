# Dartmouth College xác nhận vi phạm dữ liệu sau cuộc tấn công tống tiền của Clop

![Darthmouth College](https://www.bleepstatic.com/content/hl-images/2025/11/25/Darthmouth_College.jpg)

Dartmouth College đã công bố một vụ vi phạm dữ liệu sau khi băng tống tiền Clop rò rỉ dữ liệu bị cáo buộc bị đánh cắp từ các máy chủ Oracle E-Business Suite của trường trên trang rò rỉ dark web của nhóm này.

Trường đại học tư thuộc Ivy League chuyên nghiên cứu, thành lập năm 1769, có quỹ tài trợ (endowment) 9 tỷ USD tính đến ngày 30 tháng 6, 2025, hơn 40 khoa và chương trình học thuật, và hơn 4.000 sinh viên đại học, với tỷ lệ sinh viên trên giảng viên là 7:1.

Trong một thư thông báo vi phạm [filed with the office of Maine's Attorney General](https://www.maine.gov/agviewer/content/ag/985235c7-cb95-4be2-8792-a1252b4f8318/a69e0001-a0f8-46d9-a49d-cb01159afec2.html), Dartmouth cho biết các kẻ tấn công đã lợi dụng một lỗ hổng zero-day trong Oracle E-Business Suite (EBS) để đánh cắp thông tin cá nhân thuộc về 1.494 cá nhân.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Tuy nhiên, tổng số người có khả năng bị ảnh hưởng bởi vụ vi phạm này có thể lớn hơn nhiều, do trường đặt trụ sở tại Hanover, New Hampshire, và trường [hasn't yet filed a breach notice](https://www.doj.nh.gov/citizens/consumer-protection-antitrust-bureau/security-breach-notifications) với Văn phòng Tổng Trưởng Bang (Attorney General) của tiểu bang.

"Thông qua điều tra, chúng tôi xác định rằng một tác nhân không được ủy quyền đã lấy một số tệp trong khoảng thời gian từ ngày 9 tháng 8, 2025 đến ngày 12 tháng 8, 2025. Chúng tôi đã rà soát các tệp và vào ngày 30 tháng 10, 2025, xác định một hoặc nhiều tệp có chứa tên của bạn và Social Security number," trường cho biết trong các thư gửi bằng thư cho những người bị ảnh hưởng bởi rò rỉ dữ liệu.

Trong một phụ lục riêng nộp cho Maine's AG, Dartmouth bổ sung rằng các tác nhân đe dọa cũng đã đánh cắp các tài liệu chứa thông tin tài khoản tài chính của các cá nhân bị ảnh hưởng.

Một phát ngôn viên của Dartmouth College không có sẵn ngay lập tức để bình luận khi được BleepingComputer liên hệ hôm nay về khoản tiền chuộc mà băng Clop yêu cầu và tổng số người bị ảnh hưởng bởi vi phạm.

![Darthmouth-College-Clop-entry](https://www.bleepstatic.com/images/news/u/1109292/2025/Darthmouth-College-Clop-entry.png)

_Mục nhập Dartmouth College trên trang rò rỉ của Clop (BleepingComputer)_

Sự cố này là một phần của một chiến dịch tống tiền lớn hơn, trong đó băng mã độc Clop [has exploited a zero-day flaw (CVE-2025-61882)](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/) từ [early August 2025] để đánh cắp các tệp nhạy cảm từ nhiều nền tảng Oracle EBS của nạn nhân.

Mặc dù Clop vẫn chưa tiết lộ tổng số tổ chức bị ảnh hưởng, nhà phân tích chính của Google Threat Intelligence Group, John Hultquist, đã nói với BleepingComputer rằng có khả năng hàng chục tổ chức đã bị xâm phạm.

Băng tống tiền này cũng đã [targeted Harvard University](https://www.bleepingcomputer.com/news/security/harvard-investigating-breach-linked-to-oracle-zero-day-exploit/), [The Washington Post](https://www.reuters.com/business/media-telecom/washington-post-says-it-is-among-victims-cyber-breach-tied-oracle-software-2025-11-06/), [Logitech](https://www.bleepingcomputer.com/news/security/logitech-confirms-data-breach-after-clop-extortion-attack/), [GlobalLogic](https://www.bleepingcomputer.com/news/security/globallogic-warns-10-000-employees-of-data-theft-after-oracle-breach/), và [American Airlines subsidiary Envoy Air](https://www.bleepingcomputer.com/news/security/american-airlines-subsidiary-envoy-confirms-oracle-data-theft-attack/) trong chiến dịch này, với dữ liệu của họ cũng bị rò rỉ trực tuyến và hiện có thể tải xuống qua Torrent.

Trong quá khứ, Clop cũng đã đứng sau các cuộc tấn công đánh cắp dữ liệu nhằm vào [Accellion FTA](https://www.bleepingcomputer.com/tag/accellion/), [GoAnywhere MFT](https://www.bleepingcomputer.com/news/security/fortra-shares-findings-on-goanywhere-mft-zero-day-attacks/), [Cleo](https://www.bleepingcomputer.com/news/security/new-cleo-zero-day-rce-flaw-exploited-in-data-theft-attacks/), và [MOVEit Transfer](https://www.bleepingcomputer.com/news/security/new-moveit-transfer-zero-day-mass-exploited-in-data-theft-attacks/), vụ sau cùng đã ảnh hưởng tới hơn 2.770 tổ chức. U.S. Department of State hiện [offers a $10 million reward](https://www.bleepingcomputer.com/news/security/us-govt-offers-10-million-bounty-for-info-on-clop-ransomware/) cho thông tin liên kết các cuộc tấn công của băng với một chính phủ nước ngoài.

Trong vài tuần gần đây, các trường thuộc Ivy League cũng bị [targeted by voice phishing attacks](https://www.bleepingcomputer.com/tag/ivy-league/), với [Harvard University](https://www.bleepingcomputer.com/news/security/harvard-university-discloses-data-breach-affecting-alumni-donors/), [Princeton University](https://www.bleepingcomputer.com/news/security/princeton-university-discloses-data-breach-affecting-donors-alumni/), và [University of Pennsylvania](https://www.bleepingcomputer.com/news/security/university-of-pennsylvania-confirms-data-stolen-in-cyberattack/) tiết lộ rằng một hacker đã xâm nhập các hệ thống nội bộ dùng cho phát triển và hoạt động cựu sinh viên để đánh cắp thông tin cá nhân của sinh viên, cựu sinh viên, nhà tài trợ, nhân viên và giảng viên.