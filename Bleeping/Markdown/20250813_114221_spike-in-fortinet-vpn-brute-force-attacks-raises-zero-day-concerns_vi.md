# Tăng đột biến trong các cuộc tấn công brute-force VPN Fortinet gây lo ngại về zero-day

![Globe](https://www.bleepstatic.com/content/hl-images/2025/06/12/DDoS-outage-map-globe.jpg)

Một đợt tăng đột biến lớn trong các cuộc tấn công brute-force nhằm vào Fortinet SSL VPN đã diễn ra vào tháng trước, tiếp theo là một sự chuyển đổi sang FortiManager, đánh dấu một sự chuyển hướng có chủ đích trong việc nhắm đến mà theo truyền thống đã trước các thông báo về lỗ hổng bảo mật mới.

Chiến dịch này, được nền tảng giám sát mối đe dọa GreyNoise phát hiện, đã xuất hiện trong hai làn sóng, vào ngày 3 và 5 tháng 8, với làn sóng thứ hai chuyển sang việc nhắm đến FortiManager với một chữ ký TCP khác.

Như GreyNoise [đã báo cáo trước đó](https://www.bleepingcomputer.com/news/security/spikes-in-malicious-activity-precede-new-cves-in-80-percent-of-cases/), những đợt tăng như vậy trong việc quét có mục đích và brute-forcing xuất hiện trước sự công bố của các lỗ hổng bảo mật mới 80% thời gian.

Thường thì, những cuộc quét như vậy nhắm vào việc liệt kê các điểm cuối lộ ra, đánh giá tầm quan trọng của chúng và ước lượng tiềm năng khai thác của chúng, với các làn sóng tấn công thực tế diễn ra ngay sau đó.

"Nghiên cứu mới cho thấy các đợt tăng như thế này thường trước sự công bố của các lỗ hổng bảo mật mới ảnh hưởng đến cùng một nhà cung cấp - hầu hết trong vòng sáu tuần," GreyNoise cảnh báo.

"Trên thực tế, GreyNoise phát hiện ra rằng các đợt tăng hoạt động kích hoạt thẻ chính xác này có sự tương quan đáng kể với các lỗ hổng bảo mật được công bố trong các sản phẩm của Fortinet."

Vì lý do này, những người bảo vệ không nên coi thường những đợt tăng hoạt động này như là các nỗ lực thất bại nhằm khai thác các lỗ hổng cũ đã được vá, mà thay vào đó nên xem chúng như là những dấu hiệu tiềm năng của sự công bố zero-day và tăng cường các biện pháp bảo mật để chặn chúng.

## Các cuộc tấn công brute-force Fortinet

Vào ngày 3 tháng 8 năm 2025, GreyNoise đã ghi nhận một đợt tăng trong các nỗ lực brute-forcing nhắm vào Fortinet SSL VPN như một phần của một hoạt động ổn định mà họ đã theo dõi kể từ trước đó.

Phân tích dấu vân tay JA4+, một phương pháp dấu vân tay mạng để nhận diện và phân loại lưu lượng mã hóa, đã liên kết đợt tăng này với hoạt động vào tháng Sáu xuất phát từ một thiết bị FortiGate trên một địa chỉ IP dân cư có liên quan đến Pilot Fiber Inc.

"Sự chồng chéo này không xác nhận việc quy trách nhiệm, nhưng nó gợi ý về việc có thể tái sử dụng công cụ hoặc môi trường mạng," [GreyNoise đã bình luận](https://www.greynoise.io/blog/vulnerability-fortinet-vpn-bruteforce-spike) trong tài liệu của họ.

![Đợt tăng hoạt động vào ngày 3 tháng 8](https://www.bleepstatic.com/images/news/u/1220909/2025/August/spike.jpg)

**Đợt tăng hoạt động vào ngày 3 tháng 8 năm 2025**  
_Nguồn: GreyNoise_

Hai ngày sau, vào ngày 5 tháng 8, một chiến dịch brute-force mới từ cùng một kẻ tấn công xuất hiện, mà đã chuyển đổi nhắm đến từ các điểm cuối FortiOS SSL VPN sang dịch vụ FGFM của FortiManager.

"Trong khi lưu lượng từ ngày 3 tháng 8 đã nhằm vào hồ sơ _FortiOS_, thì lưu lượng được phân tích dấu vân tay với các chữ ký TCP và client - một chữ ký meta - từ ngày 5 tháng 8 trở đi không còn nhắm vào _FortiOS_," GreyNoise giải thích.

"Thay vào đó, nó đã liên tục nhắm mục tiêu vào hồ sơ _FortiManager - FGFM_ của chúng tôi mặc dù vẫn kích hoạt thẻ Fortinet SSL VPN Bruteforcer của chúng tôi."

Sự chuyển đổi này gợi ý rằng hoặc là cùng một kẻ tấn công hoặc cùng một công cụ/tiến trình hạ tầng đã chuyển từ cố gắng brute-force đăng nhập VPN sang cố gắng brute-force quyền truy cập FortiManager.

Các địa chỉ IP liên quan đến hoạt động này, và được khuyến nghị đặt vào danh sách chặn, bao gồm:

* 31.206.51.194
* 23.120.100.230
* 96.67.212.83
* 104.129.137.162
* 118.97.151.34
* 180.254.147.16
* 20.207.197.237
* 180.254.155.227
* 185.77.225.174
* 45.227.254.113

GreyNoise lưu ý rằng hoạt động độc hại theo dõi đang phát triển theo thời gian và liên quan đến một cụm nguồn cụ thể, rất có khả năng thực hiện các thử nghiệm thích ứng.

Nói chung, hoạt động này khó mà là các cuộc quét nghiên cứu, thường rộng hơn về phạm vi và giới hạn về tỷ lệ, và sẽ không liên quan đến việc brute-forcing thông tin xác thực, điều này được xem như một nỗ lực xâm nhập rõ ràng.

Do đó, các nhà bảo vệ nên chặn các IP được liệt kê, tăng cường bảo vệ đăng nhập trên các thiết bị Fortinet, và củng cố truy cập bên ngoài khi có thể, hạn chế truy cập chỉ đến các dải IP và VPN đáng tin cậy.