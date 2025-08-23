# SmartAttack sử dụng đồng hồ thông minh để đánh cắp dữ liệu từ các hệ thống không kết nối mạng

![Air-gapped](https://www.bleepstatic.com/content/hl-images/2024/09/05/Airgapped.jpg)

Một cuộc tấn công mới có tên 'SmartAttack' sử dụng đồng hồ thông minh như một thiết bị nhận tín hiệu siêu âm bí mật để khai thác dữ liệu từ các hệ thống vật lý cách ly (air-gapped).

Các hệ thống air-gapped, thường được triển khai trong các môi trường quan trọng như cơ sở chính phủ, nền tảng vũ khí và nhà máy điện hạt nhân, được cách ly hoàn toàn khỏi các mạng bên ngoài để ngăn chặn các cuộc tấn công mã độc và đánh cắp dữ liệu.

Mặc dù bị cách ly, các hệ thống này vẫn dễ bị tổn thương trước các mối đe dọa nội bộ như nhân viên bất chính sử dụng USB hoặc các cuộc tấn công từ chuỗi cung ứng tài trợ bởi nhà nước.

Một khi bị xâm nhập, mã độc có thể hoạt động bí mật, sử dụng các kỹ thuật stealthy để điều chỉnh các đặc điểm vật lý của các thành phần phần cứng nhằm truyền tải dữ liệu nhạy cảm đến một thiết bị nhận gần đó mà không làm xáo trộn hoạt động bình thường của hệ thống.

SmartAttack được phát triển bởi các nhà nghiên cứu tại các trường đại học Israel do [Mordechai Guri](https://arxiv.org/html/2506.08866v1) dẫn đầu, một chuyên gia trong lĩnh vực kênh tấn công bí mật, người đã công bố các phương pháp rò rỉ dữ liệu bằng cách sử dụng [tiếng ồn từ màn hình LCD](https://www.bleepingcomputer.com/news/security/new-pixhell-acoustic-attack-leaks-secrets-from-lcd-screen-noise/), [modulation RAM](https://www.bleepingcomputer.com/news/security/new-rambo-attack-steals-data-using-ram-in-air-gapped-computers/), [LED của card mạng](https://www.bleepingcomputer.com/news/security/etherled-air-gapped-systems-leak-data-via-network-card-leds/), [tín hiệu RF từ USB](https://www.bleepingcomputer.com/news/security/new-software-bridges-an-air-gap-using-an-unmodified-usb/), [cáp SATA](https://www.bleepingcomputer.com/news/security/air-gapped-systems-leak-data-via-sata-cable-wifi-antennas/), và [nguồn điện](https://www.bleepingcomputer.com/news/security/air-gapped-pcs-vulnerable-to-data-theft-via-power-supply-radiation/).

Mặc dù các cuộc tấn công vào môi trường air-gapped thường chỉ là lý thuyết và cực kỳ khó thực hiện, chúng vẫn đưa ra những cách tiếp cận thú vị và mới mẻ để khai thác dữ liệu.

## Cách SmartAttack hoạt động

SmartAttack yêu cầu mã độc phải xâm nhập vào một máy tính air-gapped để thu thập thông tin nhạy cảm như các cú gõ phím, khóa mã hóa và thông tin đăng nhập. Sau đó, nó có thể sử dụng loa tích hợp của máy tính để phát tín hiệu siêu âm ra môi trường.

Bằng cách sử dụng kỹ thuật nhảy tần số nhị phân (B-FSK), các tần số tín hiệu âm thanh có thể được điều chỉnh để đại diện cho dữ liệu nhị phân, tức là các giá trị 0 và 1. Một tần số 18.5 kHz đại diện cho "0," trong khi 19.5 kHz thể hiện "1."

![Kênh bí mật và can thiệp từ cú gõ bàn phím](https://www.bleepstatic.com/images/news/u/1220909/2025/June/inter.jpg)

**Kênh bí mật và can thiệp từ cú gõ bàn phím**  
_Nguồn: arxiv.org_

Các tần số trong khoảng này là không thể nghe thấy đối với con người, nhưng chúng vẫn có thể được thu nhận bởi microphone của đồng hồ thông minh được đeo bởi một người gần đó.

Ứng dụng giám sát âm thanh trong đồng hồ thông minh áp dụng các kỹ thuật xử lý tín hiệu để phát hiện các sự thay đổi tần số và giải điều chế tín hiệu được mã hóa, trong khi các bài kiểm tra tính toàn vẹn cũng có thể được áp dụng.

Cuối cùng, dữ liệu có thể được khai thác qua kết nối Wi-Fi, Bluetooth, hoặc mạng di động.

Đồng hồ thông minh có thể được trang bị công cụ này bởi một nhân viên bất chính, hoặc có thể bị nhiễm từ bên ngoài mà không cần đến sự nhận thức của người đeo.

## Hiệu suất và giới hạn

Các nhà nghiên cứu ghi nhận rằng đồng hồ thông minh sử dụng microphone nhỏ có tỷ lệ tín hiệu-nhiễu (SNR) thấp hơn so với smartphone, do đó, việc giải điều chế tín hiệu khá khó khăn, đặc biệt là ở các tần số cao hơn và cường độ tín hiệu thấp hơn.

Ngay cả hướng đeo đồng hồ cũng được phát hiện có vai trò quan trọng trong tính khả thi của cuộc tấn công, hoạt động tốt nhất khi đồng hồ có "tầm nhìn thẳng" với loa máy tính.

Tùy thuộc vào loại transmitter (loại loa), khoảng cách truyền tối đa dao động từ 6 đến 9 mét (20 – 30 feet).

![Hiệu suất loại phát tín hiệu](https://www.bleepstatic.com/images/news/u/1220909/2025/June/transmitter.jpg)

**Hiệu suất loại phát tín hiệu**  
_Nguồn: arxiv.org_

Tốc độ truyền dữ liệu dao động từ 5 bit trên giây (bps) đến 50 bps, làm giảm độ tin cậy khi tốc độ và khoảng cách tăng lên.

**Đo lường hiệu suất (Tỷ lệ tín hiệu trên nhiễu, Tỷ lệ lỗi bit)**  
_Nguồn: arxiv.org_

Các nhà nghiên cứu cho biết cách tốt nhất để đối phó với SmartAttack là cấm sử dụng đồng hồ thông minh trong môi trường an toàn.

Một biện pháp khác là loại bỏ loa tích hợp khỏi các máy tính air-gapped. Điều này sẽ loại bỏ mặt tấn công cho tất cả các kênh bí mật âm học, không chỉ riêng SmartAttack.

Nếu không có giải pháp nào khả thi, việc làm nhiễu siêu âm thông qua việc phát tán tiếng ồn băng thông rộng, tường lửa dựa trên phần mềm và âm thanh gapping cũng có thể chứng tỏ hiệu quả.