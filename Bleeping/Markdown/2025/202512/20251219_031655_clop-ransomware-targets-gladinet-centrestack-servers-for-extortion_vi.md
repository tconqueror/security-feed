# Mã độc tống tiền Clop nhắm vào máy chủ Gladinet CentreStack để tống tiền

![Tin tặc](https://www.bleepstatic.com/content/hl-images/2024/08/28/hacker.jpg)

Nhóm tội phạm mạng Clop đang nhắm mục tiêu các máy chủ tệp Gladinet CentreStack được mở ra trên Internet trong một chiến dịch tống tiền đánh cắp dữ liệu mới.

[Gladinet CentreStack](https://www.bleepingcomputer.com/tag/gladinet-centrestack/) cho phép doanh nghiệp chia sẻ an toàn các tệp được lưu trên máy chủ tệp tại chỗ thông qua trình duyệt web, ứng dụng di động và ổ đĩa ánh xạ mà không cần VPN. Theo Gladinet, CentreStack "được sử dụng bởi hàng nghìn doanh nghiệp từ hơn 49 quốc gia."

Kể từ tháng Tư, Gladinet đã phát hành bản cập nhật bảo mật để khắc phục một số lỗ hổng bảo mật khác đã bị lợi dụng [trong các cuộc tấn công](https://www.bleepingcomputer.com/news/security/hackers-exploit-gladinet-centrestack-cryptographic-flaw-in-rce-attacks/), một số [trong đó](https://www.bleepingcomputer.com/news/security/hackers-exploiting-zero-day-in-gladinet-file-sharing-software/) là [zero-days](https://www.bleepingcomputer.com/news/security/centrestack-rce-exploited-as-zero-day-to-breach-file-sharing-servers/).

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Nhóm tội phạm mạng Clop hiện đang quét và xâm nhập các máy chủ CentreStack để lộ ra Internet, với Curated Intel cho biết với BleepingComputer rằng các ghi chú tống tiền đã được để lại trên các máy chủ bị xâm phạm.

Tuy nhiên, hiện chưa có thông tin về lỗ hổng mà Clop đang khai thác để tấn công vào các máy chủ CentreStack. Chưa rõ đây có phải là lỗ hổng zero-day hay là một lỗi đã được khắc phục trước đó nhưng chủ sở hữu các hệ thống bị tấn công chưa cập nhật bản vá.

"Incident Responders from the Curated Intelligence community have encountered a new CLOP extortion campaign targeting Internet-facing CentreStack file servers," [cảnh báo](http://www.linkedin.com/posts/curatedintelligence%5Fpsa-incident-responders-from-the-curated-activity-7407480091133231104-C6hv/) nhóm tình báo mối đe dọa Curated Intelligence vào thứ Năm.

"Từ dữ liệu quét cổng gần đây, dường như có ít nhất hơn 200 IP duy nhất chạy tiêu đề HTTP 'CentreStack - Login', khiến chúng trở thành các mục tiêu tiềm năng của CLOP, kẻ đang khai thác một CVE không rõ (n-day hoặc zero-day) trong các hệ thống này."

## Các cuộc tấn công đánh cắp dữ liệu của Clop

Clop có lịch sử dài nhắm vào các sản phẩm truyền tệp an toàn. Trong quá khứ, nhóm tống tiền này đã đứng sau các chiến dịch đánh cắp dữ liệu nhắm vào [Accellion FTA](https://www.bleepingcomputer.com/tag/accellion/), [GoAnywhere MFT](https://www.bleepingcomputer.com/news/security/fortra-shares-findings-on-goanywhere-mft-zero-day-attacks/), [Cleo](https://www.bleepingcomputer.com/news/security/new-cleo-zero-day-rce-flaw-exploited-in-data-theft-attacks/), và [MOVEit Transfer](https://www.bleepingcomputer.com/news/security/new-moveit-transfer-zero-day-mass-exploited-in-data-theft-attacks/) các máy chủ chia sẻ tệp, vụ sau cùng đã ảnh hưởng tới [hơn 2.770 tổ chức trên toàn thế giới](https://www.emsisoft.com/en/blog/44123/unpacking-the-moveit-breach-statistics-and-analysis/).

Gần đây nhất, họ [khai thác một lỗ hổng zero-day Oracle EBS](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/) (CVE-2025-61882) để đánh cắp các tệp nhạy cảm từ nhiều tổ chức kể từ [đầu tháng 8 năm 2025](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/).

Danh sách khách hàng Oracle bị ảnh hưởng bao gồm [Harvard University](https://www.bleepingcomputer.com/news/security/harvard-investigating-breach-linked-to-oracle-zero-day-exploit/), [The Washington Post](https://www.bleepingcomputer.com/news/security/washington-post-data-breach-impacts-nearly-10k-employees-contractors/), [GlobalLogic](https://www.bleepingcomputer.com/news/security/globallogic-warns-10-000-employees-of-data-theft-after-oracle-breach/), [the University of Pennsylvania](https://www.bleepingcomputer.com/news/security/university-of-pennsylvania-confirms-data-theft-after-oracle-ebs-hack/), [Logitech](https://www.bleepingcomputer.com/news/security/logitech-confirms-data-breach-after-clop-extortion-attack/), và [the American Airlines subsidiary Envoy Air](https://www.bleepingcomputer.com/news/security/american-airlines-subsidiary-envoy-confirms-oracle-data-theft-attack/).

Sau khi xâm nhập hệ thống và trích xuất các tài liệu nhạy cảm, Clop đã công bố dữ liệu bị đánh cắp trên trang rò rỉ dark web của họ và cho phép tải xuống thông qua Torrent.

U.S. Department of State đang [cung cấp phần thưởng 10 triệu USD](https://www.bleepingcomputer.com/news/security/us-govt-offers-10-million-bounty-for-info-on-clop-ransomware/) cho bất kỳ thông tin nào có thể liên kết các cuộc tấn công của nhóm tội phạm mạng này với một chính phủ nước ngoài.

Người phát ngôn của Gladinet chưa thể cung cấp bình luận ngay lập tức khi được BleepingComputer liên hệ vào đầu ngày hôm nay.