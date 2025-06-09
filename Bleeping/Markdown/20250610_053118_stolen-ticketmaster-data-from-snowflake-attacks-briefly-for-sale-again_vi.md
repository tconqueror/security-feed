+-+-+-+-+-
# Dữ liệu Ticketmaster bị đánh cắp từ các cuộc tấn công Snowflake lại được rao bán một cách ngắn hạn

![Ticketmaster](https://www.bleepstatic.com/content/hl-images/2024/07/08/ticketmaster-concert.jpg)

Băng nhóm extortion Arkana Security đã rao bán gì đó có vẻ như là dữ liệu Ticketmaster mới bị đánh cắp vào cuối tuần qua, nhưng thực tế đây là dữ liệu bị đánh cắp trong các cuộc tấn công ăn cắp dữ liệu Snowflake năm 2024.

Nhóm extortion [đã đăng tải ảnh chụp màn hình](https://x.com/DarkWebInformer/status/1931114003314684381) của dữ liệu bị đánh cắp, quảng cáo hơn 569 GB dữ liệu Ticketmaster đang được rao bán, gây ra suy đoán rằng đây là một cuộc tấn công mới.

![Danh sách dữ liệu Ticketmaster đang được Arkana bán](https://www.bleepstatic.com/images/news/security/data-for-sale/ticketmaster-arkana/ticketmaster-arkana.jpg)

**Danh sách dữ liệu Ticketmaster đang được Arkana bán**  
_Nguồn: BleepingComputer_

Tuy nhiên, BleepingComputer đã xác định rằng các tệp được hiển thị trong bài đăng của Arkana khớp với các mẫu dữ liệu Ticketmaster mà chúng tôi đã thấy trước đó trong các cuộc [tấn công ăn cắp dữ liệu Snowflake năm 2024](https://www.bleepingcomputer.com/news/security/snowflake-account-hacks-linked-to-santander-ticketmaster-breaches/).

Hơn nữa, một trong những bức ảnh có dòng chú thích "rapeflaked copy 4 quick sale 1 buyer," mà là một tham chiếu đến một công cụ có tên là "RapeFlake."

RapeFlake là một công cụ tùy chỉnh được tạo ra bởi các tác nhân đe dọa để thực hiện trinh sát và trích xuất dữ liệu từ các cơ sở dữ liệu của Snowflake.

Như đã được báo cáo trước đó, các [cuộc tấn công Snowflake](https://www.bleepingcomputer.com/tag/snowflake/) đã nhắm mục tiêu nhiều tổ chức, bao gồm Santander, Ticketmaster, [AT&T](https://www.bleepingcomputer.com/news/security/massive-atandt-data-breach-exposes-call-logs-of-109-million-customers/), [Advance Auto Parts](https://www.bleepingcomputer.com/news/security/advance-auto-parts-data-breach-impacts-23-million-people/), [Neiman Marcus](https://www.bleepingcomputer.com/news/security/neiman-marcus-data-breach-31-million-email-addresses-found-exposed/), [Los Angeles Unified](https://www.bleepingcomputer.com/news/security/los-angeles-unified-confirms-student-data-stolen-in-snowflake-account-hack/), [Pure Storage](https://www.bleepingcomputer.com/news/security/pure-storage-confirms-data-breach-after-snowflake-account-hack/), và [Cylance](https://www.bleepingcomputer.com/news/security/cylance-confirms-data-breach-linked-to-third-party-platform/). Những cuộc tấn công này đã được một nhóm extortion được biết đến với tên gọi ShinyHunters tuyên bố.

Các cuộc tấn công này được thực hiện bằng cách sử dụng thông tin đăng nhập Snowflake bị xâm phạm đã được đánh cắp bởi các infostealers, và sau đó được dùng để tải dữ liệu công ty nhằm mục đích thực hiện các kế hoạch extortion.

Ticketmaster là một trong những nạn nhân bị extortion nhiều nhất trong cuộc tấn công Snowflake, dẫn đến việc đánh cắp thông tin cá nhân và thông tin vé. Sau khi dữ liệu được rao bán trực tuyến, công ty này đã [xác nhận vụ xâm phạm](https://www.bleepingcomputer.com/news/security/ticketmaster-confirms-massive-breach-after-stolen-data-for-sale-online/) vào cuối tháng 5 và đã bắt đầu thông báo cho các khách hàng bị ảnh hưởng.

Sau khi việc rò rỉ ban đầu xảy ra, các tác nhân đe dọa đã gia tăng các nỗ lực extortion của họ bằng cách phát hành những gì họ [khẳng định là vé in tại nhà](https://www.bleepingcomputer.com/news/security/hackers-leak-39-000-print-at-home-ticketmaster-tickets-for-154-events/) và thậm chí là [các vé Taylor Swift](https://www.bleepingcomputer.com/news/security/hackers-leak-alleged-taylor-swift-tickets-amp-up-ticketmaster-extortion/) trong một loạt bài đăng trên một diễn đàn hack.

Mặc dù Arkana không xác định nguồn gốc của dữ liệu, việc sử dụng các tham chiếu đến Snowflake và các tên tệp khớp với các tệp đã bị rò rỉ trước đó cho thấy rằng nhóm này đang cố gắng bán lại dữ liệu cũ đã bị đánh cắp.

Việc Arkana có mua dữ liệu này trước đó hay không, nhóm này có được hình thành từ các tác nhân đe dọa đã có dữ liệu trước đó, hay họ đang làm việc với ShinyHunters để bán nó vẫn chưa rõ.

Vào ngày 9 tháng 6, mục cho dữ liệu Ticketmaster đã bị gỡ bỏ khỏi trang web rò rỉ dữ liệu của Arkana Security.

Tên "ShinyHunters" đã được liên kết với một số lượng lớn các vụ xâm phạm trong suốt những năm qua, bao gồm việc [rò rỉ dữ liệu PowerSchool](https://www.bleepingcomputer.com/news/security/powerschool-hacker-now-extorting-individual-school-districts/) nơi dữ liệu đã bị đánh cắp cho 62.4 triệu sinh viên và 9.5 triệu giáo viên cho 6,505 quận học ở Mỹ, Canada và các quốc gia khác.

Gần đây hơn, Mandiant đã liên kết ShinyHunters với một chiến dịch gần đây [nhắm vào tài khoản Salesforce](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/), nơi các tác nhân đe dọa đã xâm phạm các tài khoản để đánh cắp dữ liệu khách hàng và extortion các công ty.

Khi nhiều tác nhân đe dọa liên quan đến ShinyHunters đã bị bắt giữ trong ba năm qua \[[1](https://www.bleepingcomputer.com/news/security/shinyhunters-member-gets-3-years-in-prison-for-breaching-60-firms/), [2](https://www.bleepingcomputer.com/news/security/us-indicts-snowflake-hackers-who-extorted-25-million-from-3-victims/), [3](https://krebsonsecurity.com/2025/02/u-s-soldier-charged-in-att-hack-searched-can-hacking-be-treason/)\], không rõ liệu đây có phải là nhóm gốc hay các tác nhân đe dọa khác đang tuyên bố là họ để đánh lừa cơ quan thực thi pháp luật.

BleepingComputer đã liên hệ với Arkana và Ticketmaster về danh sách này nhưng không nhận được phản hồi.