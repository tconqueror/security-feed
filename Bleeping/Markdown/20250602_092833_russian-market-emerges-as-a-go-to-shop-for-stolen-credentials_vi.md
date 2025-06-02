# ‘Thị Trường Nga’ nổi lên như một cửa hàng lý tưởng cho các thông tin xác thực bị đánh cắp

![Cửa hàng](https://www.bleepstatic.com/content/hl-images/2023/12/12/shop.jpg)

Thị trường cybercrime "Thị Trường Nga" đã nổi lên như một trong những nền tảng phổ biến nhất để mua và bán thông tin xác thực bị đánh cắp bởi malware lấy cắp thông tin.

Mặc dù thị trường này đã hoạt động được khoảng sáu năm và trở nên tương đối phổ biến vào năm 2022, [ReliaQuest báo cáo](https://reliaquest.com/resources/research-reports/stolen-credential-attacks-russian-marketplace/) rằng Thị Trường Nga gần đây đã đạt tới những đỉnh cao mới. Một phần của sự gia tăng này là do [việc triệt phá Genesis Market](https://www.bleepingcomputer.com/news/security/fbi-seizes-stolen-credentials-market-genesis-in-operation-cookie-monster/), điều này đã tạo ra một khoảng trống lớn trong lĩnh vực này.

Mặc dù phần lớn (85%) thông tin xác thực được bán trên Thị Trường Nga là "tái chế" từ các nguồn hiện có, nhưng nó vẫn thu hút được một lượng lớn khán giả cybercrime nhờ vào danh sách rộng rãi các mặt hàng bán và sự sẵn có của các file log với giá chỉ từ $2.

Một file log của infostealer thường là một tệp văn bản, hoặc nhiều tệp, được tạo ra bởi malware lấy cắp thông tin, chứa các mật khẩu tài khoản, cookie phiên, dữ liệu thẻ tín dụng, dữ liệu ví tiền điện tử và dữ liệu xác định hệ thống bị đánh cắp từ một thiết bị bị nhiễm.

Mỗi file log có thể chứa hàng chục hoặc thậm chí hàng nghìn thông tin xác thực, vì vậy tổng số thông tin xác thực bị đánh cắp có thể lên tới hàng trăm triệu hoặc hơn. Sau khi được thu thập, các file log sẽ được tải lên máy chủ của kẻ tấn công, nơi chúng được thu thập để sử dụng cho các hoạt động độc hại khác hoặc bán trên các thị trường như Thị Trường Nga.

![Các log trên thị trường](https://www.bleepstatic.com/images/news/u/1220909/2025/May/market-logs.jpg)

**Trang log trên thị trường**  
_Nguồn: ReliaQuest_

Infostealers đã trở thành công cụ vô cùng phổ biến cho các tác nhân mối đe dọa, với [nhiều chiến dịch](https://www.bleepingcomputer.com/news/security/north-korean-hackers-adopt-clickfix-attacks-to-target-crypto-firms/) hiện tại [nhắm vào doanh nghiệp](https://www.bleepingcomputer.com/news/security/fake-google-meet-conference-errors-push-infostealing-malware/) để đánh cắp cookie phiên và thông tin xác thực công ty.

ReliaQuest cho biết điều này được phản ánh trong Thị Trường Nga, với 61% các log bị đánh cắp chứa thông tin xác thực SaaS từ các nền tảng như Google Workspace, Zoom, và Salesforce. Ngoài ra, 77% các file log bao gồm thông tin xác thực SSO (Single Sign-On).

"Các tài khoản đám mây bị xâm phạm cho phép kẻ tấn công truy cập vào các hệ thống quan trọng và tạo cơ hội hoàn hảo để đánh cắp dữ liệu nhạy cảm," các nhà nghiên cứu giải thích.

## Lumma gặp khó khăn, Acreed nổi lên

ReliaQuest đã phân tích hơn 1,6 triệu bài đăng trên Thị Trường Nga để vẽ đồ thị sự gia tăng và giảm sút của sự phổ biến của các malware lấy cắp thông tin cụ thể.

Cho đến gần đây, hầu hết các log được đánh cắp bởi Lumma stealer, chiếm 92% tất cả các log thông tin xác thực được bán trên Thị Trường Nga.

![Tỷ lệ log infostealer trên Thị Trường Nga](https://www.bleepstatic.com/images/news/u/1220909/2025/May/percentage.jpg)

**Tỷ lệ log infostealer trên Thị Trường Nga**  
_Nguồn: ReliaQuest_

Lumma đã dẫn đầu thị trường sau sự sụp đổ của Raccoon Stealer, sau [hành động thực thi pháp luật](https://www.bleepingcomputer.com/news/security/raccoon-stealer-malware-operator-gets-5-years-in-prison-after-guilty-plea/). Tuy nhiên, số phận tương tự có thể đang diễn ra cho Lumma, khi các hoạt động của nó gần đây đã bị [gián đoạn bởi một chiến dịch thực thi pháp luật toàn cầu](https://www.bleepingcomputer.com/news/security/lumma-infostealer-malware-operation-disrupted-2-300-domains-seized/) mà trong đó 2,300 tên miền đã bị tịch thu.

Kết quả lâu dài của hoạt động này vẫn chưa rõ ràng, và [Check Point báo cáo](https://blog.checkpoint.com/security/lumma-infostealer-down-but-not-out/) rằng các nhà phát triển của Lumma hiện đang cố gắng hồi phục và khởi động lại các hoạt động cybercrime của họ.

Trong lúc đó, ReliaQuest báo cáo đã thấy sự gia tăng đột ngột của một infostealer mới có tên là Acreed, đang nhanh chóng gaining traction sau khi Lumma bị triệt phá.

Sự gia tăng nhanh chóng của Acreed trên Thị Trường Nga được phản ánh qua hơn 4,000 log được tải lên trong tuần đầu tiên hoạt động của nó, [theo Webz](https://webz.io/dwp/acreed-infostealer-everything-we-know-so-far/).

Acreed không khác gì so với một infostealer điển hình về thông tin mà nó nhắm đến, bao gồm dữ liệu được lưu trữ trong Chrome, Firefox và các biến thể khác của nó, bao gồm mật khẩu, cookie, ví tiền điện tử và thông tin thẻ tín dụng.

Các infostealer đang infecting người dùng thông qua email phishing, các cuộc tấn công "ClickFix", quảng cáo độc hại cho phần mềm premium, và video trên YouTube hoặc TikTok. Do đó, việc cẩn trọng và thực hành tải phần mềm tốt được khuyến nghị để tránh nguy cơ rộng rãi này.