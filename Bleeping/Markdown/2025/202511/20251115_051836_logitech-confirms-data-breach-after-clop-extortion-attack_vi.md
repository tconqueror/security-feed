# Logitech xác nhận vi phạm dữ liệu sau cuộc tấn công tống tiền của Clop

![Logitech](https://www.bleepstatic.com/content/hl-images/2025/11/14/logitech.jpg)

Gã khổng lồ phụ kiện phần cứng Logitech đã xác nhận họ chịu một vụ vi phạm dữ liệu trong một cuộc tấn công mạng do băng nhóm tống tiền Clop nhận trách nhiệm, nhóm này đã tiến hành các cuộc tấn công đánh cắp dữ liệu Oracle E-Business Suite vào tháng Bảy.

Logitech International S.A. là một công ty điện tử đa quốc gia Thụy Sĩ bán các giải pháp phần cứng và phần mềm, bao gồm thiết bị ngoại vi máy tính, thiết bị chơi game, cộng tác video, âm nhạc và sản phẩm nhà thông minh.

Hôm nay, Logitech đã nộp một [Form 8-K ](https://www.sec.gov/Archives/edgar/data/1032975/000103297525000085/logi-20251114.htm) lên U.S. Securities and Exchange Commission, xác nhận rằng dữ liệu đã bị đánh cắp trong một vụ vi phạm.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Logitech International S.A. (\"Logitech\") gần đây đã gặp phải một sự cố an ninh mạng liên quan đến việc rút trộm dữ liệu. Sự cố an ninh mạng này không ảnh hưởng đến sản phẩm, hoạt động kinh doanh hoặc sản xuất của Logitech," Logitech tiết lộ.

"Ngay khi phát hiện sự cố, Logitech đã nhanh chóng thực hiện các bước để điều tra và ứng phó với sự cố với sự hỗ trợ của các công ty an ninh mạng hàng đầu bên ngoài."

Logitech cho biết dữ liệu có khả năng bao gồm một số thông tin giới hạn về nhân viên và người tiêu dùng, cũng như dữ liệu liên quan đến khách hàng và nhà cung cấp, nhưng công ty cho rằng tin tặc không truy cập được các thông tin nhạy cảm như số chứng minh nhân dân hoặc thông tin thẻ tín dụng, vì những dữ liệu đó không được lưu trữ trong các hệ thống bị xâm phạm.

Logitech cho biết vụ vi phạm xảy ra thông qua một lỗ hổng zero-day bên thứ ba đã được vá ngay khi có bản sửa.

Tuyên bố này đưa ra sau khi băng tống tiền Clop thêm Logitech vào trang tống tiền rò rỉ dữ liệu của chúng vào tuần trước, rò rỉ gần 1.8 TB dữ liệu được cho là bị đánh cắp từ công ty.

Mặc dù công ty không nêu tên nhà cung cấp phần mềm, vụ vi phạm có khả năng do một lỗ hổng zero-day của Oracle bị băng tống tiền Clop khai thác trong các cuộc tấn công đánh cắp dữ liệu vào tháng Bảy.

Tháng trước, Mandiant và Google bắt đầu theo dõi một [chiến dịch tống tiền mới](https://www.bleepingcomputer.com/news/security/clop-extortion-emails-claim-theft-of-oracle-e-business-suite-data/) trong đó nhiều công ty nhận được email từ nhóm ransomware Clop tuyên bố rằng dữ liệu nhạy cảm đã bị đánh cắp từ các hệ thống Oracle E-Business Suite của họ. 

Những email này cảnh báo rằng dữ liệu bị đánh cắp sẽ bị rò rỉ nếu yêu cầu tiền chuộc không được trả.

![Clop extortion email sent to Oracle customers](https://www.bleepstatic.com/images/news/security/c/clop/oracle-e-business-suite-extortion/clop-oracle-extortion-email.jpg)

**Email tống tiền của Clop gửi đến khách hàng Oracle**

Ngay sau đó, [Oracle đã xác nhận một lỗ hổng zero-day mới trong E-Business Suite](https://www.bleepingcomputer.com/news/security/oracle-patches-ebs-zero-day-exploited-in-clop-data-theft-attacks/), được theo dõi là CVE-2025-61882, và phát hành bản cập nhật khẩn cấp để sửa lỗi.

Băng tống tiền Clop có một [lịch sử dài trong việc khai thác các lỗ hổng zero-day](https://www.bleepingcomputer.com/tag/clop/) trong các cuộc tấn công đánh cắp dữ liệu quy mô lớn, bao gồm:

* **2020:** Khai thác một [lỗ hổng zero-day trong nền tảng Accellion FTA](https://www.bleepingcomputer.com/tag/accellion/), ảnh hưởng tới gần 100 tổ chức.
* **2021:** Khai thác một [lỗ hổng zero-day trong phần mềm SolarWinds Serv-U FTP](https://www.bleepingcomputer.com/news/security/clop-gang-exploiting-solarwinds-serv-u-flaw-in-ransomware-attacks/).
* **2023:** Khai thác một [lỗ hổng zero-day trong nền tảng GoAnywhere MFT](https://www.bleepingcomputer.com/news/security/fortra-shares-findings-on-goanywhere-mft-zero-day-attacks/), xâm phạm hơn 100 công ty.
* **2023:** Khai thác một [lỗ hổng zero-day trong MOVEit Transfer](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-moveit-extortion-attacks/), đó là chiến dịch lớn nhất của Clop đến nay, nơi kẻ tấn công [đã đánh cắp dữ liệu từ 2,773 tổ chức trên toàn thế giới](https://www.emsisoft.com/en/blog/44123/unpacking-the-moveit-breach-statistics-and-analysis/).
* **2024:** Khai thác [hai lỗ hổng zero-day trong Cleo file transfer (CVE-2024-50623 và CVE-2024-55956)](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-cleo-data-theft-attacks/) để đánh cắp dữ liệu và tống tiền các công ty.

Các tổ chức khác bị ảnh hưởng bởi các cuộc tấn công đánh cắp dữ liệu Oracle E-Business Suite năm 2025 bao gồm [Harvard](https://www.bleepingcomputer.com/news/security/harvard-investigating-breach-linked-to-oracle-zero-day-exploit/), [Envoy Air](https://www.bleepingcomputer.com/news/security/american-airlines-subsidiary-envoy-confirms-oracle-data-theft-attack/), và [The Washington Post](https://www.bleepingcomputer.com/news/security/washington-post-data-breach-impacts-nearly-10k-employees-contractors/).

BleepingComputer đã liên hệ với Logitech đầu tháng này và một lần nữa hôm nay với các câu hỏi liên quan đến vụ vi phạm và sẽ cập nhật bài viết nếu nhận được phản hồi.