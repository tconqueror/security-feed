# Gã khổng lồ giáo dục Pearson bị tấn công mạng, thông tin khách hàng bị lộ

![Pearson](https://www.bleepstatic.com/content/hl-images/2025/05/08/pearson-header.jpg)

Gã khổng lồ giáo dục Pearson đã chịu một cuộc tấn công mạng, cho phép các tác nhân gây hại đánh cắp dữ liệu doanh nghiệp và thông tin khách hàng, theo thông tin từ BleepingComputer.

Pearson là một công ty giáo dục có trụ sở tại Vương quốc Anh và là một trong những nhà cung cấp lớn nhất thế giới về xuất bản học thuật, công cụ học tập số và đánh giá chuẩn hóa. Công ty làm việc với các trường học, đại học và cá nhân ở hơn 70 quốc gia thông qua các dịch vụ in ấn và trực tuyến của mình.

Trong một tuyên bố với BleepingComputer, Pearson xác nhận họ đã bị tấn công mạng và dữ liệu đã bị đánh cắp, nhưng cho biết phần lớn là "dữ liệu cũ".

"Chúng tôi vừa phát hiện ra rằng một tác nhân không được phép đã truy cập vào một phần hệ thống của chúng tôi," một đại diện của Pearson xác nhận với BleepingComputer.

"Khi chúng tôi xác định được hoạt động này, chúng tôi đã thực hiện các bước để ngăn chặn nó và điều tra những gì đã xảy ra và dữ liệu nào bị ảnh hưởng cùng với các chuyên gia pháp y. Chúng tôi cũng đã hỗ trợ cuộc điều tra của cơ quan thực thi pháp luật. Chúng tôi đã thực hiện các bước để triển khai các biện pháp bảo vệ bổ sung cho hệ thống của mình, bao gồm tăng cường giám sát bảo mật và xác thực."

"Chúng tôi vẫn đang điều tra, nhưng vào thời điểm này chúng tôi tin rằng tác nhân đã tải xuống chủ yếu là dữ liệu cũ. Chúng tôi sẽ chia sẻ thêm thông tin trực tiếp với khách hàng và đối tác khi phù hợp."

Pearson cũng xác nhận rằng dữ liệu bị đánh cắp không bao gồm thông tin nhân viên.

Bạn có thông tin về cuộc tấn công mạng này hoặc một cuộc tấn công khác không? Nếu bạn muốn chia sẻ thông tin, bạn có thể liên hệ với chúng tôi một cách an toàn và bảo mật qua Signal tại LawrenceA.11, qua email tại lawrence.abrams@bleepingcomputer.com, hoặc bằng cách sử dụng [mẫu tips](https://www.bleepingcomputer.com/news-tip/).

## Một token GitLab bị lộ

Tuyên bố này được đưa ra sau khi các nguồn tin cho biết BleepingComputer rằng các tác nhân gây hại đã xâm phạm môi trường phát triển của Pearson vào tháng 1 năm 2025 thông qua một GitLab Personal Access Token (PAT) bị lộ tìm thấy trong một tệp .git/config công khai.

Tệp .git/config là một tệp cấu hình cục bộ được sử dụng bởi các dự án Git để lưu trữ các thiết lập cấu hình, chẳng hạn như tên dự án, địa chỉ email và thông tin khác. Nếu tệp này bị tiết lộ một cách nhầm lẫn và chứa các token truy cập được nhúng trong các URL từ xa, nó có thể cho phép kẻ tấn công truy cập trái phép vào các kho nội bộ.

Trong cuộc tấn công vào Pearson, token bị lộ đã cho phép các tác nhân gây hại truy cập vào mã nguồn của công ty, trong đó chứa thêm các thông tin xác thực được mã hóa cứng và các token xác thực cho các nền tảng đám mây.

Trong những tháng tiếp theo, kẻ tấn công được cho là đã sử dụng các thông tin xác thực này để đánh cắp terabyte dữ liệu từ mạng nội bộ và cơ sở hạ tầng đám mây của công ty, bao gồm AWS, Google Cloud và các dịch vụ cơ sở dữ liệu đám mây khác như Snowflake và Salesforce CRM.

Dữ liệu bị đánh cắp này được cho là chứa thông tin khách hàng, tài chính, các vé hỗ trợ và mã nguồn, với hàng triệu người bị ảnh hưởng.

Tuy nhiên, khi BleepingComputer hỏi Pearson về việc họ có trả tiền chuộc hay không, ý nghĩa của "dữ liệu cũ", số lượng khách hàng bị ảnh hưởng và liệu khách hàng có được thông báo hay không, công ty cho biết họ sẽ không bình luận về những câu hỏi này.

Pearson [đã tiết lộ trước đó](https://plc.pearson.com/en-GB/news-and-insights/news/cyber-security-incident-involving-pdri) vào tháng 1 rằng họ đang điều tra một vụ vi phạm của một trong các công ty con của họ, PDRI, mà được tin là liên quan đến cuộc tấn công này.

Quét các tệp cấu hình Git và các thông tin xác thực bị lộ đã trở thành một phương pháp phổ biến để các tác nhân gây hại xâm nhập các dịch vụ đám mây.

Năm ngoái, [Internet Archive đã bị xâm phạm](https://www.bleepingcomputer.com/news/security/internet-archive-hacked-data-breach-impacts-31-million-users/) sau khi các tác nhân gây hại phát hiện một [tệp cấu hình Git bị lộ](https://www.bleepingcomputer.com/news/security/internet-archive-breached-again-through-stolen-access-tokens/) chứa một token xác thực cho các kho GitLab của công ty.

Vì lý do này, việc bảo mật các tệp ".git/config" bằng cách ngăn chặn truy cập công khai và tránh nhúng thông tin xác thực trong các URL từ xa là rất quan trọng.