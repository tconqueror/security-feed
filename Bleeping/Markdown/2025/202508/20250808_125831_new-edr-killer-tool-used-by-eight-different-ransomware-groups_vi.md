# Công cụ EDR killer mới được sử dụng bởi tám nhóm ransomware khác nhau

![Hacker](https://www.bleepstatic.com/content/hl-images/2025/03/12/hacker.jpg)

Một công cụ Endpoint Detection and Response (EDR) killer mới, được coi là sự tiến hóa của 'EDRKillShifter', được phát triển bởi RansomHub, đã được quan sát trong các cuộc tấn công của tám băng nhóm ransomware khác nhau.

Các công cụ như vậy giúp các nhà điều hành ransomware tắt sản phẩm bảo mật trên các hệ thống bị xâm phạm để họ có thể triển khai payloads, nâng cao đặc quyền, thực hiện chuyển động bên, và cuối cùng mã hóa các thiết bị trên mạng mà không bị phát hiện.

Theo các nhà nghiên cứu bảo mật của Sophos, công cụ mới này, không được đặt tên cụ thể, được sử dụng bởi RansomHub, Blacksuit, Medusa, Qilin, Dragonforce, Crytox, Lynx và INC.

Công cụ EDR killer mới sử dụng một nhị phân bị che giấu nhiều mà tự giải mã tại thời gian chạy và được tiêm vào các ứng dụng hợp pháp.

Công cụ này tìm kiếm một driver có chữ ký số (chứng chỉ đánh cắp hoặc hết hạn) với tên ngẫu nhiên gồm năm ký tự, được lập trình sẵn trong file thực thi.

![Chứng chỉ đánh cắp và hết hạn](https://www.bleepstatic.com/images/news/u/1220909/2025/August/certificate.jpg)

**Chứng chỉ đánh cắp và hết hạn được sử dụng bởi driver độc hại**  
_Nguồn: Sophos_

Nếu được tìm thấy, driver độc hại sẽ được nạp vào kernel, như yêu cầu để thực hiện một cuộc tấn công theo kiểu 'bring your own vulnerable driver' (BYOVD) và đạt được đặc quyền kernel cần thiết để tắt các sản phẩm bảo mật.

Driver này giả mạo như một file hợp pháp như CrowdStrike Falcon Sensor Driver, nhưng khi hoạt động, nó sẽ tiêu diệt các quá trình liên quan đến AV/EDR và dừng các dịch vụ liên quan đến các công cụ bảo mật.

Các nhà cung cấp mục tiêu bao gồm Sophos, Microsoft Defender, Kaspersky, Symantec, Trend Micro, SentinelOne, Cylance, McAfee, F-Secure, HitmanPro và Webroot.

Mặc dù các biến thể của công cụ EDR killer mới khác nhau về tên driver, AVs mục tiêu và đặc điểm xây dựng, chúng đều sử dụng HeartCrypt để đóng gói, và bằng chứng cho thấy có sự chia sẻ kiến thức và công cụ giữa cả những nhóm đe dọa cạnh tranh.

Sophos đặc biệt lưu ý rằng không có khả năng công cụ này bị rò rỉ và sau đó được tái sử dụng bởi các tác nhân đe dọa khác, mà thay vào đó được phát triển thông qua một khung chia sẻ và hợp tác.

"Để rõ ràng, không phải là một nhị phân đơn lẻ của EDR killer bị rò rỉ và được chia sẻ giữa các tác nhân đe dọa. Thay vào đó, mỗi cuộc tấn công đã sử dụng một bản xây dựng khác nhau của công cụ độc quyền," [Sophos giải thích](https://news.sophos.com/en-us/2025/08/06/shared-secret-edr-killer-in-the-kill-chain/).

Chiến thuật chia sẻ công cụ này, đặc biệt là trong vấn đề EDR killers, là phổ biến trong không gian ransomware.

Ngoài [EDRKillShifter](https://www.bleepingcomputer.com/news/security/ransomware-gang-deploys-new-malware-to-kill-security-software/), Sophos cũng phát hiện ra một công cụ khác gọi là [AuKill](https://www.bleepingcomputer.com/news/security/ransomware-gangs-abuse-process-explorer-driver-to-kill-security-software/), mà Medusa Locker và LockBit đã sử dụng trong các cuộc tấn công.

SentinelOne cũng đã báo cáo vào năm ngoái về những kẻ hack FIN7 đang bán công cụ tùy chỉnh "[AvNeutralizer](https://www.bleepingcomputer.com/news/security/notorious-fin7-hackers-sell-edr-killer-to-other-threat-actors/)" của họ cho nhiều băng nhóm ransomware khác nhau, bao gồm BlackBasta, AvosLocker, MedusaLocker, BlackCat, Trigona và LockBit.

Các chỉ số hoàn chỉnh về sự thỏa hiệp liên quan đến công cụ EDR killer mới này có thể được [tìm thấy trên kho GitHub này](https://github.com/sophoslabs/IoCs/blob/master/06082025-edrkiller-iocs.csv).