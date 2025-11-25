# OnSolve CodeRED bị tấn công mạng làm gián đoạn hệ thống cảnh báo khẩn cấp trên toàn quốc

![Biểu tượng cảnh báo chấm than](https://www.bleepstatic.com/content/hl-images/2025/11/25/alert-yellow.jpg)

Công ty quản lý rủi ro Crisis24 xác nhận nền tảng OnSolve CodeRED của họ đã bị tấn công mạng, làm gián đoạn hệ thống thông báo khẩn cấp được sử dụng bởi các chính quyền tiểu bang và địa phương, các sở cảnh sát và cơ quan cứu hỏa trên khắp Hoa Kỳ.

Nền tảng CodeRED cho phép các cơ quan này gửi cảnh báo tới cư dân trong các tình huống khẩn cấp.

Vụ tấn công mạng buộc Crisis24 phải ngưng hoạt động môi trường CodeRED cũ, gây gián đoạn rộng rãi cho các tổ chức sử dụng nền tảng này để gửi thông báo khẩn cấp, cảnh báo thời tiết và các cảnh báo nhạy cảm khác.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Trong các tuyên bố và mục Câu hỏi thường gặp (FAQ) chia sẻ với khách hàng bị ảnh hưởng, Crisis24 cho biết cuộc điều tra của họ xác định vụ tấn công chỉ giới hạn trong môi trường CodeRED và không ảnh hưởng đến bất kỳ hệ thống nào khác của họ.

Tuy nhiên, họ xác nhận rằng dữ liệu đã bị đánh cắp từ nền tảng trong vụ tấn công. Thông tin bị đánh cắp bao gồm tên, địa chỉ, địa chỉ email, số điện thoại và mật khẩu được sử dụng cho hồ sơ người dùng CodeRED.

Crisis24 thông báo với khách hàng rằng họ chưa thấy dấu hiệu nào cho thấy dữ liệu bị đánh cắp đã được công khai đăng tải.

"CodeRED đã thông báo với chúng tôi rằng mặc dù có các dấu hiệu cho thấy dữ liệu đã bị lấy khỏi hệ thống, ở thời điểm này không có bằng chứng nào cho thấy thông tin này đã được đăng trực tuyến," cảnh báo một [thông báo](https://www.uptexas.org/312/Emergency-Notifications) của City of University Park, Texas.

Vì vụ tấn công đã làm hỏng nền tảng, Crisis24 đang xây dựng lại dịch vụ bằng cách khôi phục sao lưu vào hệ thống mới ra mắt CodeRED by Crisis24. Tuy nhiên, dữ liệu có sẵn là từ bản sao lưu trước đó vào March 31, 2025, nên nhiều tài khoản có thể sẽ bị thiếu trong hệ thống.

Nhiều quận, thành phố và cơ quan an toàn công cộng trên toàn quốc đã báo cáo về vụ tấn công mạng và sự gián đoạn, cho biết họ đang làm việc để khôi phục hệ thống cảnh báo khẩn cấp cho cư dân.

## Băng nhóm INC Ransom nhận trách nhiệm

Trong khi Crisis24 chỉ quy kết vụ vi phạm cho một "nhóm tội phạm mạng có tổ chức," BleepingComputer đã phát hiện rằng băng nhóm INC Ransomware đã nhận trách nhiệm về vụ tấn công.

Nhóm này đã tạo một mục cho OnSolve trên trang rò rỉ dữ liệu Tor của họ và đăng các ảnh chụp màn hình dường như cho thấy dữ liệu khách hàng, bao gồm địa chỉ email và mật khẩu lưu dưới dạng văn bản rõ ràng.

![OnSolve entry on the INC Ransom data leak site](https://www.bleepstatic.com/images/news/ransomware/attacks/o/onsolve-codered/inc-onsolve.jpg)

**OnSolve entry on the INC Ransom data leak site**  
_Nguồn: BleepingComputer_

Băng nhóm ransomware tuyên bố đã xâm nhập hệ thống OnSolve vào November 1, 2025, và mã hóa các tập tin vào November 10. Sau khi cho là không nhận được khoản tiền chuộc, các tác nhân đe doạ nói rằng họ hiện đang rao bán dữ liệu bị đánh cắp trong vụ tấn công.

Vì các mật khẩu được chia sẻ trong ảnh chụp màn hình ở dạng văn bản rõ ràng, khách hàng được khuyến nghị đặt lại mọi mật khẩu CodeRED đã tái sử dụng trên các trang web khác.

INC Ransom là một hoạt động ransomware-as-a-service (RaaS) ra mắt vào July 2023 và kể từ đó đã nhắm mục tiêu các tổ chức trên toàn thế giới.

Danh sách nạn nhân của nhóm trải rộng trên nhiều lĩnh vực, từ giáo dục và chăm sóc y tế đến chính phủ và các thực thể như [Yamaha Motor Philippines](https://www.bleepingcomputer.com/news/security/yamaha-motor-confirms-ransomware-attack-on-philippines-subsidiary/), Scotland's [National Health Service](https://www.bleepingcomputer.com/news/security/inc-ransom-threatens-to-leak-3tb-of-nhs-scotland-stolen-data/) (NHS), tập đoàn bán lẻ thực phẩm [Ahold Delhaize](https://www.bleepingcomputer.com/news/security/ahold-delhaize-confirms-data-theft-after-inc-ransomware-claims-attack/), và chi nhánh tại Hoa Kỳ của [Xerox Business Solutions](https://www.bleepingcomputer.com/news/security/xerox-says-subsidiary-xbs-us-breached-after-ransomware-gang-leaks-data/) (XBS).