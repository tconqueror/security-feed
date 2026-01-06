# Mạng botnet Kimwolf trên Android lạm dụng proxy dân cư để lây nhiễm thiết bị nội bộ

![Kimwolf Android botnet abuses residential proxies to infect internal devices](https://www.bleepstatic.com/content/hl-images/2024/09/12/android-tv-malware.jpg)

Mạng botnet Kimwolf, một biến thể trên Android của Aisuru, đã phát triển lên hơn hai triệu máy chủ, phần lớn bị nhiễm thông qua việc khai thác lỗ hổng trong các mạng proxy dân cư để nhắm mục tiêu các thiết bị trên mạng nội bộ.

Các nhà nghiên cứu quan sát thấy hoạt động gia tăng của phần mềm độc hại kể từ tháng Tám năm ngoái. Trong tháng vừa qua, Kimwolf đã tăng cường quét các mạng proxy, tìm kiếm các thiết bị có dịch vụ Android Debug Bridge (ADB) bị mở ra.

Các mục tiêu phổ biến là các hộp TV và thiết bị phát trực tuyến dựa trên Android cho phép truy cập không xác thực qua ADB. Các thiết bị bị xâm nhập chủ yếu được sử dụng trong các cuộc tấn công từ chối dịch vụ phân tán (DDoS), bán lại proxy và kiếm tiền từ cài đặt ứng dụng thông qua SDK của bên thứ ba như Plainproxies Byteconnect.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Mạng botnet Aisuru hiện chịu trách nhiệm cho cuộc tấn công DDoS lớn nhất được công bố công khai, đạt đỉnh [29.7 terabits per second](https://www.bleepingcomputer.com/news/security/aisuru-botnet-behind-new-record-breaking-297-tbps-ddos-attack/) theo đo lường của Cloudflare.

Một báo cáo từ [XLab notes](https://blog.xlab.qianxin.com/kimwolf-botnet-en/) cho biết rằng mạng botnet Kimwolf trên Android có hơn 1.8 triệu thiết bị bị xâm nhập vào ngày 4 tháng 12.

Các nhà nghiên cứu tại công ty tình báo mối đe dọa và an ninh chống gian lận Synthient đã theo dõi hoạt động Kimwolf. Họ cho biết số lượng thiết bị bị xâm nhập đã tăng lên gần hai triệu, và tạo ra khoảng 12 triệu địa chỉ IP duy nhất mỗi tuần.

Hầu hết các thiết bị Android bị nhiễm nằm ở Vietnam, Brazil, India và Saudi Arabia. Trong nhiều trường hợp, hệ thống đã bị xâm nhập bởi SDK proxy trước khi mua, điều này đã được [báo cáo trong quá khứ](https://www.bleepingcomputer.com/news/security/android-tv-box-on-amazon-came-pre-installed-with-malware/).

![Kimwolf infection heatmap](https://www.bleepstatic.com/images/news/u/1220909/2026/January/map.jpg)

**Bản đồ nhiệt nhiễm Kimwolf**  
_Source: Synthient_

### Lạm dụng proxy dân cư

Theo Synthient, sự phát triển nhanh chóng của Kimwolf phần lớn là do việc lạm dụng các mạng proxy dân cư để tiếp cận các thiết bị Android dễ bị tổn thương. Cụ thể, phần mềm độc hại lợi dụng các nhà cung cấp proxy cho phép truy cập vào địa chỉ và cổng mạng nội bộ, cho phép tương tác trực tiếp với các thiết bị chạy trên cùng mạng nội bộ với client proxy.

Bắt đầu từ ngày 12 tháng 11 năm 2025, Synthient quan sát thấy hoạt động cao hơn trong việc quét các dịch vụ ADB không xác thực được phơi bày qua các điểm cuối proxy, nhắm tới các cổng 5555, 5858, 12108 và 3222.

Android Debug Bridge (ADB) là một giao diện phát triển và gỡ lỗi cho phép cài đặt và gỡ bỏ ứng dụng, chạy lệnh shell, chuyển tệp và gỡ lỗi các thiết bị Android. Khi được mở trên mạng, ADB có thể cho phép kết nối từ xa trái phép để sửa đổi hoặc kiểm soát các thiết bị Android.

Khi có thể truy cập được, các payload của botnet được truyền qua netcat hoặc telnet, dẫn các shell script trực tiếp vào thiết bị bị phơi bày để thực thi cục bộ, được ghi vào /data/local/tmp.

Synthient đã thu được nhiều biến thể payload trong suốt tháng Mười Hai, nhưng các phương pháp phân phối vẫn không thay đổi.

**Tổng quan về lây nhiễm**  
_Source: Synthient_

Các nhà nghiên cứu phát hiện tỉ lệ phơi bày cao trong một mẫu pool proxy dân cư, nhấn mạnh rằng các thiết bị như vậy có thể bị khai thác trong vài phút sau khi tham gia các mạng này.

"Upon analyzing exposed devices part of IPIDEAs proxy pool, we found that 67% of all Android devices are unauthenticated, leaving them vulnerable to remote code execution," [Synthient explains](https://synthient.com/blog/a-broken-system-fueling-botnets).

"From our scans, we found approximately 6 million vulnerable IPs \[…\] These devices are often shipped pre-infected with SDKs from proxy providers," the researchers say.

IPIDEA, một trong những nhà cung cấp proxy bị ảnh hưởng và là mục tiêu hàng đầu của Kimwolf vì nó cho phép truy cập tới tất cả các cổng, đã phản hồi cảnh báo của Synthient vào ngày 28 tháng 12 bằng cách chặn truy cập vào mạng nội bộ và một loạt cổng rộng.

Tổng cộng, các nhà nghiên cứu đã gửi gần một tá báo cáo lỗ hổng "tới các nhà cung cấp proxy hàng đầu" được quan sát trong hoạt động Kimwolf. Tuy nhiên, các nhà nghiên cứu không thể xác định một cách tự tin tất cả các nhà cung cấp proxy bị phần mềm độc hại nhắm tới.

### Bảo vệ chống lại Kimwolf

Synthient đã phát hành một [công cụ quét trực tuyến](https://synthient.com/check) để giúp người dùng xác định liệu bất kỳ thiết bị mạng nào của họ có phải là một phần của mạng botnet Kimwolf hay không.

Trong trường hợp kết quả dương tính, các nhà nghiên cứu đề nghị rằng các hộp TV bị nhiễm nên được "xóa sạch hoặc phá hủy", nếu không mạng botnet sẽ tồn tại.

Khuyến nghị chung là tránh các Android TV boxes giá rẻ, kém chất lượng và ưu tiên các thiết bị được 'Google Play Protect certified' từ các OEM có uy tín, chẳng hạn như Chromecast của Google, NVIDIA Shield TV và Xiaomi Mi TV Box.