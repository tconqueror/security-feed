# Sự ra mắt ransomware của CyberVolk vấp phải lỗ hổng mật mã

![Bàn tay cầm chìa khóa](https://www.bleepstatic.com/content/hl-images/2022/10/09/cyber-key.jpg)

Nhóm hacktivist thân Nga CyberVolk đã ra mắt một dịch vụ ransomware-as-a-service (RaaS) có tên VolkLocker, nhưng chương trình này mắc phải những sai sót nghiêm trọng trong triển khai, cho phép nạn nhân có thể giải mã tập tin miễn phí.

Theo các nhà nghiên cứu của SentinelOne, khi kiểm tra họ phát hiện bộ mã hóa sử dụng một khóa chính (master key) được hardcoded trong file thực thi, khóa này cũng được ghi ở dạng văn bản thuần trong một file ẩn trên các máy bị ảnh hưởng.

Điều này cho phép các công ty bị tấn công sử dụng khóa đó để giải mã tập tin miễn phí, làm suy yếu tiềm năng của VolkLocker trong không gian tội phạm mạng.

## Hacktivism và tội phạm mạng

CyberVolk được [báo cáo](http://www.sentinelone.com/labs/cybervolk-a-deep-dive-into-the-hacktivists-tools-and-ransomware-fueling-pro-russian-cyber-attacks/) là một tập thể hacktivist có trụ sở tại Ấn Độ và thân Nga, bắt đầu hoạt động vào năm ngoái, thực hiện các cuộc tấn công từ chối dịch vụ phân tán và ransomware nhắm tới các tổ chức công và chính phủ phản đối Nga hoặc ủng hộ Ukraine.

Trong khi nhóm này từng bị gián đoạn trên Telegram, họ quay trở lại vào tháng 8 năm 2025 với chương trình RaaS mới, VolkLocker (CyberVolk 2.x), nhắm mục tiêu cả hệ thống Linux/VMware ESXi và Windows.

Một tính năng đáng chú ý của VolkLocker là việc sử dụng một hàm hẹn giờ Golang trong mã của nó, khi hết thời gian hoặc khi một khóa sai được nhập trong ghi chú ransomware dạng HTML, sẽ kích hoạt việc xóa các thư mục người dùng (Documents, Downloads, Pictures và Desktop).

![The timer function](https://www.bleepstatic.com/images/news/u/1220909/2025/December/timer.jpg)

**Hàm hẹn giờ kích hoạt wiper**  
_Source: SentinelOne_

Truy cập vào RaaS có giá từ $800 đến $1,100 cho một kiến trúc hệ điều hành duy nhất, hoặc $1,600 đến $2,200 cho cả hai.

Người mua có thể truy cập một builder bot trên Telegram để tùy biến bộ mã hóa và nhận payload được sinh ra.

Vào tháng 11 năm 2025, cùng nhóm tấn công bắt đầu quảng cáo một remote access trojan và một keylogger, cả hai đều có giá $500 mỗi cái.

![VolkLocker's ransom note HTML](https://www.bleepstatic.com/images/news/u/1220909/2025/December/ransomhtml.jpg)

**Ghi chú tống tiền HTML của VolkLocker**  
_Source: SentinelOne_

## Lỗ hổng mật mã nghiêm trọng

VolkLocker sử dụng AES-256 trong GCM (Galois/Counter Mode) để mã hóa, với một master key 32-bit được suy ra từ một chuỗi hex 64 ký tự nhúng trong binary.

Một nonce ngẫu nhiên 12-byte được sử dụng làm vector khởi tạo (IV) cho mỗi file, xóa file gốc và thêm phần mở rộng .locked hoặc .cvolk vào bản sao đã mã hóa.

Vấn đề là VolkLocker sử dụng cùng một master key để mã hóa tất cả các tập tin trên hệ thống nạn nhân, và cùng khóa đó cũng được ghi vào một file văn bản thuần (system_backup.key) trong thư mục %TEMP%.

"Vì ransomware không bao giờ xóa file backup key này, nạn nhân có thể cố gắng phục hồi tập tin bằng cách trích xuất các giá trị cần thiết từ file," [giải thích SentinelOne](https://www.sentinelone.com/blog/cybervolk-returns-flawed-volklocker-brings-new-features-with-growing-pains/).

"File backup key ở dạng văn bản thuần có khả năng là một sản phẩm thử nghiệm vô tình được đưa vào các bản build production."

**Giải mã tập tin bằng cách sử dụng giá trị khóa hardcoded**  
_Source: SentinelOne_

Mặc dù lỗi này có thể giúp những nạn nhân hiện có, việc công bố lỗ hổng mật mã của VolkLocker có khả năng sẽ thúc đẩy các tác nhân đe dọa sửa lỗi và ngăn không cho lỗ hổng bị lợi dụng trong tương lai.

Người ta cho rằng thực hành tốt hơn là không công bố lỗi ransomware khi một tác nhân đe dọa đang hoạt động tích cực, thay vào đó chia sẻ chúng riêng tư với cơ quan thi hành pháp luật và các công ty thương lượng ransomware có thể [hỗ trợ nạn nhân một cách riêng tư.](https://www.bleepingcomputer.com/news/security/researchers-secretly-helped-decrypt-zeppelin-ransomware-for-2-years/)

BleepingComputer đã liên hệ với SentinelOne để hỏi về quyết định công khai lỗ hổng của VolkLocker, và một phát ngôn viên đã gửi lời giải thích dưới đây:

"Nguyên nhân chúng tôi không do dự là vì đây không phải lỗi mã hóa lõi mà là một artifact kiểm thử vô tình được đưa vào một số bản build production bởi các operator kém năng lực và không phải là cơ chế giải mã đáng tin cậy ngoài những trường hợp đó. Nó phản ánh nhiều hơn hệ sinh thái mà CyberVolk đang cố gắng tạo ra thông qua dịch vụ RaaS này." - phát ngôn viên SentinelOne