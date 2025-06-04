# Tấn công AS-REP Roasting trong Kerberos: Những điều bạn cần biết

![Tấn công mạng](https://www.bleepstatic.com/content/posts/2025/06/03/as-rep-roasting-attacks.jpg)

Mật khẩu mạnh vẫn là nền tảng của bảo mật trực tuyến, ngay cả khi các đối tượng xấu ngày càng tinh vi trong các cuộc tấn công của họ. Hãy xem xét mối đe dọa từ AS-REP roasting – và những biện pháp mà các tổ chức cần triển khai để bảo vệ Active Directory của họ.

AS-REP (Authentication Server Response) Roasting nhắm vào các đối tượng người dùng trong Active Directory không yêu cầu xác thực trước Kerberos. Kerberos – một giao thức xác thực – thường yêu cầu một người điều hành gửi một Yêu cầu của Máy Chủ Xác Thực (được gọi là AS-REQ) đến một bộ điều khiển miền (DC).

Tin nhắn này chứa một dấu thời gian được mã hóa bằng cách băm mật khẩu của người dùng. DC phải giải mã dấu thời gian đó bằng cách sử dụng phiên bản băm của chính nó: nếu thành công, DC sẽ gửi lại một thông điệp AS-REP với một Ticket Granting Ticket (TGT), mà sau đó có thể được sử dụng để thực hiện các yêu cầu truy cập.

Tuy nhiên, quy trình bảo mật này chỉ hoạt động an toàn khi xác thực trước Kerberos hoạt động. Trong một số trường hợp, nó có thể bị vô hiệu hóa – chẳng hạn, trong các hệ thống không hỗ trợ Kerberos hoặc sử dụng phiên bản sớm hơn của giao thức. Trong những trường hợp như vậy, DC có thể gửi AS-REP ngay cả khi người dùng chưa được xác thực.

Nói cách khác, các đối tượng xấu có thể tìm cách truy cập và khai thác bất kỳ đối tượng người dùng nào không yêu cầu xác thực trước.

## Một mối đe dọa ngày càng tăng

Có [nhiều công cụ có thể được sử dụng trong các cuộc tấn công này](https://n1chr0x.medium.com/kerberos-takedown-unleashing-rubeus-and-impacket-for-active-directory-domination-58eeb7b6b6e3), chẳng hạn như Rubeus hoặc Impacket. Mối đe dọa [diễn ra thông qua một quy trình ba bước](https://media.defense.gov/2024/Sep/25/2003553985/-1/-1/0/CTR-DETECTING-AND-MITIGATING-AD-COMPROMISES.PDF):

1. Kẻ tấn công gửi một AS-REQ đến DC, nhắm vào một đối tượng không được cấu hình cho xác thực trước Kerberos.
2. DC phản hồi yêu cầu này bằng một thông điệp AS-REP chứa một TGT.
3. Những kẻ tội phạm sau đó cố gắng truy cập mật khẩu trong TGT. Họ có thể đưa nó vào chế độ ngoại tuyến, sử dụng các kỹ thuật như tấn công brute force để cố gắng truy cập mật khẩu của người dùng.

Việc xâm phạm Active Directory đang trở thành mối quan ngại ngày càng gia tăng ở các cấp cao nhất. Ví dụ, các cơ quan an ninh mạng ở Australia, Canada, New Zealand, Vương quốc Anh và Hoa Kỳ đã nêu bật [17 kỹ thuật phổ biến](https://media.defense.gov/2024/Sep/25/2003553985/-1/-1/0/CTR-DETECTING-AND-MITIGATING-AD-COMPROMISES.PDF) được sử dụng thường xuyên để nhắm mục tiêu vào Active Directory. AS-Rep Roasting đứng ở vị trí cao trong danh sách. “Phản ứng và phục hồi từ hoạt động độc hại liên quan đến việc xâm phạm Active Directory thường tiêu tốn nhiều thời gian, chi phí và gây gián đoạn,” báo cáo cảnh báo.

## [**Bảo vệ mật khẩu Active Directory của bạn bằng Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Báo cáo Điều Tra Vi Phạm Dữ Liệu của Verizon cho thấy các thông tin đăng nhập bị đánh cắp chiếm 44,7% các vụ vi phạm.   
  
Bảo mật Active Directory một cách dễ dàng với các chính sách mật khẩu tuân thủ, chặn 4+ tỷ mật khẩu bị xâm phạm, nâng cao bảo mật và giảm thiểu sự hỗ trợ tốn kém!

[Hãy thử miễn phí](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Cách phát hiện và giảm thiểu AS-REP Roasting

AS-REP Roasting có thể rất khó phát hiện. Đầu tiên bạn cần xác định xem bạn có thể là nạn nhân – và sau đó bạn phải thực hiện các bước để bảo vệ Active Directory của mình.

Xác định các tài khoản dễ bị tổn thương: Để bắt đầu, bạn cần xác định các điểm yếu của mình. Qua việc sử dụng các script cụ thể, [có thể xác định các tài khoản người dùng không có xác thực trước Kerberos cần thiết](https://www.picussecurity.com/resource/blog/as-rep-roasting-attack-explained-mitre-attack-t1558.004).

Thiết lập xác thực trước Kerberos: AS-REP Roasting chỉ hoạt động khi một đối tượng không yêu cầu xác thực trước Kerberos; do đó, bạn có thể giảm thiểu nguy cơ nếu bạn đảm bảo xác thực trước này có hiệu lực. Tuy nhiên, trong một số trường hợp, có thể các đối tượng cần bỏ qua xác thực trước Kerberos: những đối tượng này nên được giữ ra khỏi các nhóm an toàn và chỉ được cấp quyền tối thiểu.

Kỹ thuật giám sát và ghi lại: Bạn nên có mục tiêu nghiên cứu mạng của mình để theo dõi các ID sự kiện cụ thể có thể [cho thấy ai đó đang yêu cầu TGT](https://trustmarque.com/resources/asreproasting/) hoặc hành vi khác cho thấy khả năng xảy ra một cuộc tấn công AS-REP Roasting.

[Có thể có các sự kiện khác nhau liên quan](https://media.defense.gov/2024/Sep/25/2003553985/-1/-1/0/CTR-DETECTING-AND-MITIGATING-AD-COMPROMISES.PDF), chẳng hạn như 4625, được tạo ra khi một tài khoản không thể đăng nhập; 4768, được tạo ra khi yêu cầu TGT; và 4738 và 5136, được tạo ra khi tài khoản người dùng bị thay đổi.

Triển khai các thực hành bảo mật tốt nhất: AS-REP Roasting và các kỹ thuật tương tự chỉ là một bước trong quy trình cần thiết để truy cập một mật khẩu. Bằng cách thực hiện các mật khẩu có độ dài tối thiểu và phức tạp, có thể khó khăn cho các hacker trong việc bẻ khóa mật khẩu, ngay cả khi họ thành công trong một cuộc tấn công AS-REP Roasting.

## Sức mạnh mật khẩu

Bằng cách thực hiện xác thực trước Kerberos, bạn nên có thể bảo vệ Active Directory của mình khỏi các cuộc tấn công AS-REP Roasting. Nhưng như chúng ta đã thấy, điều đó không phải lúc nào cũng khả thi. Điều này có nghĩa rằng mật khẩu mạnh vẫn quan trọng hơn bao giờ hết – có lẽ còn nhiều hơn thế.

Bạn có thể giảm thiểu nguy cơ từ các cuộc tấn công AS-REP Roasting bằng cách đảm bảo rằng các tài khoản người dùng được bảo vệ bằng mật khẩu mạnh và không bị xâm phạm. Điều này không chỉ bảo vệ Active Directory của bạn khỏi AS-REP Roasting mà còn nâng cao bảo mật tổng quát.

Tất nhiên, bạn có thể có nhiều mật khẩu để phân tích, đến mức có thể trở nên überwhelming. Nhưng với [Specops Password Policy](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), bạn có thể đơn giản hóa việc quản lý các chính sách mật khẩu tinh vi, và chặn người dùng tạo mật khẩu yếu và dễ đoán.

Công nghệ này cũng liên tục quét Active Directory của bạn để phát hiện các mật khẩu bị xâm phạm, hiện đang chặn hơn 4 tỷ mật khẩu. Điều này làm cho việc đảm bảo sự tuân thủ dễ dàng hơn rất nhiều, đồng thời tăng cường mật khẩu của bạn chống lại các cuộc tấn công ngay cả khi kẻ tấn công thành công trong một cuộc tấn công AS-REP Roasting. **[Hãy thử Specops Password Policy miễn phí hôm nay](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

Active Directory của tổ chức bạn luôn cần được bảo vệ khỏi các đối tượng xấu. Các kỹ thuật tấn công chắc chắn sẽ phát triển, cũng như công nghệ được sử dụng để bảo vệ hệ thống của bạn – nhưng miễn là con người còn sử dụng mật khẩu, bảo mật mật khẩu sẽ vẫn là nền tảng của xác thực trực tuyến an toàn và bảo mật.

**Cần hỗ trợ bảo mật Active Directory? [Liên hệ ngay](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Được tài trợ và viết bởi [Specops Software](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._