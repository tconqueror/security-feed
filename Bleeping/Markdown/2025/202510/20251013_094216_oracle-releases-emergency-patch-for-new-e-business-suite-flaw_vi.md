# Oracle phát hành bản vá khẩn cấp cho lỗ hổng mới của E-Business Suite

![Oracle](https://www.bleepstatic.com/content/hl-images/2025/10/13/Oracle.jpg)

Oracle đã phát hành một bản cập nhật bảo mật khẩn cấp trong cuối tuần để vá một lỗ hổng khác trong E-Business Suite (EBS) có thể bị khai thác từ xa bởi các kẻ tấn công không xác thực.

Được theo dõi là [CVE-2025-61884](https://nvd.nist.gov/vuln/detail/CVE-2025-61884), lỗ hổng rò rỉ thông tin này trong thành phần Runtime UI ảnh hưởng đến các phiên bản EBS 12.2.3 đến 12.2.14 và có thể cho phép các tác nhân đe dọa không xác thực đánh cắp dữ liệu nhạy cảm từ xa nếu khai thác thành công.

"Vulnerabilty này có thể bị khai thác từ xa mà không cần xác thực, tức là có thể bị khai thác qua mạng mà không cần tên người dùng và mật khẩu. Oracle khuyến nghị mạnh mẽ rằng khách hàng nên áp dụng các bản cập nhật hoặc biện pháp giảm thiểu do Security Alert này cung cấp càng sớm càng tốt," [Oracle cho biết](http://www.oracle.com/security-alerts/alert-cve-2025-61884.html).

"Lỗ hổng này nhận được điểm CVSS Base Score là 7.5. Nếu khai thác thành công, lỗ hổng này có thể cho phép truy cập vào các tài nguyên nhạy cảm," [thêm](https://blogs.oracle.com/security/post/alert-cve-2025-61884) Rob Duhart, Chief Security Officer của Oracle.

Oracle phát hành bản vá CVE-2025-61884 gần hai tuần sau một chiến dịch tống tiền của Clop nhắm vào [executives at multiple companies](https://www.bleepingcomputer.com/news/security/clop-extortion-emails-claim-theft-of-oracle-e-business-suite-data/), mà công ty sau đó đã liên kết với [EBS vulnerabilities patched in July 2025](https://www.bleepingcomputer.com/news/security/oracle-links-clop-extortion-attacks-to-july-security-flaws/) và sau đó [to another Oracle EBS vulnerability](https://www.bleepingcomputer.com/news/security/oracle-patches-ebs-zero-day-exploited-in-clop-data-theft-attacks/) hiện được theo dõi là CVE-2025-61882.

Kể từ đó, công ty an ninh mạng CrowdStrike cho biết họ lần đầu tiên phát hiện Clop khai thác CVE-2025-61882 như một zero-day [since early August in data theft attacks](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/) và cảnh báo rằng các nhóm tấn công khác có thể cũng đã tham gia các cuộc tấn công này.

Các nhà nghiên cứu bảo mật của watchTowr Labs cũng đã [found that CVE-2025-61882 is ](http://labs.watchtowr.com/well-well-well-its-another-day-oracle-e-business-suite-pre-auth-rce-chain-cve-2025-61882well-well-well-its-another-day-oracle-e-business-suite-pre-auth-rce-chain-cve-2025-61882/)[a vulnerability chain](http://labs.watchtowr.com/well-well-well-its-another-day-oracle-e-business-suite-pre-auth-rce-chain-cve-2025-61882well-well-well-its-another-day-oracle-e-business-suite-pre-auth-rce-chain-cve-2025-61882/) có thể cho phép kẻ tấn công không xác thực thực thi mã từ xa, như được chứng minh bởi một khai thác proof-of-concept (PoC) (với dấu thời gian tháng 5 năm 2025) đã bị [leaked online](https://www.bleepingcomputer.com/news/security/oracle-patches-ebs-zero-day-exploited-in-clop-data-theft-attacks/#:~:text=Exploit%C2%A0leaked%20by%C2%A0Scattered%20Lapsus%24%20Hunters) bởi nhóm tội phạm mạng Scattered Lapsus$ Hunters.

Nhóm tống tiền Clop đứng sau các [major data theft campaigns](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-moveit-extortion-attacks/) khác nhắm vào các zero-day trong Accellion FTA, GoAnywhere MFT, Cleo và MOVEit Transfer, trong đó vụ việc liên quan đến MOVEit đã ảnh hưởng tới [over 2,770 organizations](https://www.emsisoft.com/en/blog/44123/unpacking-the-moveit-breach-statistics-and-analysis/).

Oracle chưa gắn nhãn CVE-2025-61884 được vá trong cuối tuần là đã bị khai thác trong tự nhiên, và chưa liên kết nó với các cuộc tấn công CVE-2025-61882.

Tuy nhiên, vì các instance EBS có mặt trên Internet đang bị nhắm mục tiêu tích cực, các nhà phòng thủ được khuyến cáo mạnh mẽ nên áp dụng bản vá ngoài lịch (out-of-band) CVE-2025-61884 càng sớm càng tốt.