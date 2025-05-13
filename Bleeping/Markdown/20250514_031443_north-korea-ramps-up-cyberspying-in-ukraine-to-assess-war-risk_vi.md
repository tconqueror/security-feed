# Triều Tiên tăng cường hoạt động gián điệp mạng ở Ucraina để đánh giá nguy cơ chiến tranh

![Triều Tiên](https://www.bleepstatic.com/content/hl-images/2023/11/10/North_Korean_hackers_headpic.jpg)

Nhóm đe dọa được nhà nước ủng hộ của Triều Tiên là Konni (Opal Sleet, TA406) đã được ghi nhận nhắm mục tiêu vào các thực thể chính phủ Ucraina trong các hoạt động thu thập thông tin tình báo.

Những kẻ tấn công sử dụng email lừa đảo giả mạo các tổ chức tư tưởng, đề cập đến các sự kiện chính trị quan trọng hoặc các phát triển quân sự để dụ dỗ các mục tiêu của chúng.

Các nhà nghiên cứu của Proofpoint, những người phát hiện hoạt động này vào tháng 2 năm 2025, cho rằng đây có thể là một nỗ lực hỗ trợ sự tham gia quân sự của CHDCND Triều Tiên cùng với Nga ở Ucraina và đánh giá tình trạng chính trị nền tảng cuộc xung đột.

"Proofpoint đánh giá rằng TA406 đang nhắm mục tiêu vào các thực thể chính phủ Ucraina để hiểu rõ hơn mong muốn tiếp tục chiến đấu chống lại cuộc xâm lược của Nga và đánh giá triển vọng trung hạn của cuộc xung đột," [các nhà nghiên cứu giải thích](https://www.proofpoint.com/us/blog/threat-insight/ta406-pivots-front).

"Triều Tiên đã cam kết quân đội hỗ trợ Nga vào mùa thu năm 2024, và TA406 rất có thể đang thu thập thông tin tình báo để giúp lãnh đạo Triều Tiên xác định rủi ro hiện tại với lực lượng của họ đã có mặt ở khu vực, cũng như khả năng Nga sẽ yêu cầu thêm quân đội hoặc vũ khí."

## Chuỗi tấn công

Các email độc hại được gửi đến các mục tiêu giả mạo thành viên của các tổ chức tư tưởng chìm, giải quyết các vấn đề quan trọng như việc sa thải các lãnh đạo quân sự gần đây hoặc cuộc bầu cử tổng thống ở Ucraina.

Những kẻ tấn công sử dụng dịch vụ email miễn phí như Gmail, ProtonMail và Outlook để nhiều lần gửi tin nhắn đến các mục tiêu của chúng, khuyến khích họ nhấp vào liên kết.

![Email lừa đảo được sử dụng trong các cuộc tấn công của Konni](https://www.bleepstatic.com/images/news/u/1220909/2025/May/email.jpg)

**Email lừa đảo được sử dụng trong các cuộc tấn công của Konni**  
_Nguồn: Proofpoint_

Khi làm như vậy, nó đưa các nạn nhân đến một tải xuống được lưu trữ trên MEGA, tải một file nén .RAR (Analytical Report.rar) được bảo vệ bằng mật khẩu vào hệ thống của họ, chứa một file .CHM có cùng tên.

Mở file đó sẽ kích hoạt PowerShell nhúng để tải xuống PowerShell ở giai đoạn tiếp theo, thu thập thông tin trinh sát từ máy tính bị nhiễm, và thiết lập tính liên tục.

Proofpoint cũng đã thấy các biến thể sử dụng tệp đính kèm HTML để tải xuống các tệp ZIP chứa các PDF vô hại và các tệp LNK độc hại, dẫn đến việc thực thi PowerShell và VBScript.

![PowerShell mã hóa trong tệp LNK](https://www.bleepstatic.com/images/news/u/1220909/2025/May/lnk.jpg)

**PowerShell mã hóa trong tệp LNK**  
_Nguồn: Proofpoint_

Proofpoint không thể thu thập được payload cuối cùng trong các cuộc tấn công này, mà được cho là một loại malware/backdoor có khả năng tạo điều kiện thuận lợi cho các hoạt động gián điệp.

Các nhà nghiên cứu cũng lưu ý rằng Konni đã thực hiện các cuộc tấn công chuẩn bị trước đó, nhắm vào cùng một người và cố gắng thu hoạch thông tin đăng nhập tài khoản mà họ có thể sử dụng để chiếm đoạt tài khoản.

Các nỗ lực này liên quan đến việc gửi email giả mạo thông báo bảo mật của Microsoft, tuyên bố về "hoạt động đăng nhập không bình thường," và yêu cầu người nhận xác minh đăng nhập của họ trên một trang web lừa đảo tại "jetmf\[.\]com."

**Thông báo bảo mật giả mạo của Microsoft**  
_Nguồn: Proofpoint_

Việc Triều Tiên nhắm mục tiêu vào các thực thể chính phủ Ucraina đã thêm một chiều mới vào chiến trường an ninh mạng vốn đã phức tạp của đất nước, nơi đã bị chi phối bởi các cuộc tấn công liên tục do nhà nước Nga tài trợ kể từ khi bắt đầu cuộc xâm lược.