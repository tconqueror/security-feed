# Các thư viện phát triển giả mạo WhatsApp ẩn chứa mã xóa dữ liệu hủy diệt

![WhatsApp](https://www.bleepstatic.com/content/hl-images/2022/05/31/whatsapp-red-noglow.jpg)

Hai gói NPM độc hại giả làm công cụ phát triển WhatsApp đã được phát hiện đang triển khai mã xóa dữ liệu hủy diệt, xóa đệ quy các tệp trên máy tính của các nhà phát triển.

Hai gói NPM độc hại hiện có sẵn trong kho dữ liệu nhắm vào các nhà phát triển WhatsApp với mã xóa dữ liệu hủy diệt.

Các gói này, [được phát hiện bởi các nhà nghiên cứu tại Socket](https://socket.dev/blog/malicious-npm-packages-target-whatsapp-developers-with-remote-kill-switch), giả dạng như các thư viện socket WhatsApp và đã được tải xuống hơn 1,100 lần kể từ khi công bố cách đây một tháng.

Mặc dù Socket đã gửi yêu cầu gỡ bỏ và đánh dấu nhà xuất bản, nayflore, cả hai vẫn còn khả dụng tại thời điểm viết.

Tên của hai gói độc hại là [naya-flore](https://www.npmjs.com/package/naya-flore) và [nvlore-hsc](https://www.npmjs.com/package/nvlore-hsc), mặc dù nhà xuất bản này cũng đã gửi thêm nhiều gói khác trên NPM, như nouku-search, very-nay, naya-clone, node-smsk và @veryflore/disc.

Mặc dù năm gói bổ sung này không phải là độc hại trong thời điểm hiện tại, nhưng vẫn nên cẩn thận, vì một bản cập nhật được đẩy lên bất kỳ lúc nào có thể chèn mã độc hại.

Tất cả các gói này đều mô phỏng các thư viện phát triển hợp pháp của WhatsApp được sử dụng để xây dựng bot và công cụ tự động xung quanh WhatsApp Business API.

Socket lưu ý rằng các thư viện này gần đây đã trải qua một sự gia tăng đáng kể trong nhu cầu, khi nhiều doanh nghiệp sử dụng Cloud API của WhatsApp cho giao tiếp với khách hàng.

## Mã xóa dữ liệu

Cả naya-flore và nvlore-hs đều chứa một hàm có tên 'requestPairingCode', được cho là xử lý việc ghép nối WhatsApp, nhưng nó lại lấy một tệp JSON base64 từ một địa chỉ GitHub.

Tệp JSON chứa một danh sách các số điện thoại Indonesia hoạt động như một công tắc hủy, loại trừ các chủ sở hữu của những số này khỏi chức năng độc hại.

Đối với những người còn lại (mục tiêu hợp lệ), mã sẽ thực thi lệnh 'rm -rf \*', xóa tất cả các tệp theo đệ quy trong thư mục hiện tại, hiệu quả là xóa mã từ hệ thống của nhà phát triển.

![Mã xóa dữ liệu](https://www.bleepstatic.com/images/news/u/1220909/2025/August/wiper.jpg)

**Mã xóa dữ liệu**  
_Nguồn: Socket_

Socket cũng phát hiện một chức năng rò rỉ dữ liệu tiềm tàng ('generateCreeds'), có thể rò rỉ số điện thoại của nạn nhân, ID thiết bị, trạng thái và khóa mã hóa sẵn. Chức năng này có mặt nhưng được chú thích trong cả hai gói, do đó, nó đang bị vô hiệu.

![Chức năng rò rỉ dữ liệu hiện đang bị vô hiệu](https://www.bleepstatic.com/images/news/u/1220909/2025/August/data-exfil.jpg)

**Chức năng rò rỉ dữ liệu hiện đang bị vô hiệu**  
_Nguồn: Socket_

## Hệ sinh thái Go cũng bị ảnh hưởng

Trong tin tức song song, Socket cũng [phát hiện 11 gói Go độc hại](https://socket.dev/blog/11-malicious-go-packages-distribute-obfuscated-remote-payloads) sử dụng phương pháp che giấu chuỗi mảng để thực thi lén lút mã tải về từ xa tại thời điểm chạy.

Các gói này tạo ra một shell, lấy một kịch bản hoặc tập tin thực thi giai đoạn thứ hai từ các miền .icu hoặc .tech, và chạy nó trong bộ nhớ, nhắm mục tiêu cả máy chủ CI Linux và máy trạm Windows.

Phần lớn các gói này là kiểu gõ nhầm, có nghĩa là chúng dựa vào sự gõ sai và nhầm lẫn của nhà phát triển để lừa họ tải xuống.

**Kết quả tìm kiếm chứa liên kết đến một gói độc hại**  
_Nguồn: Socket_

Các gói độc hại và vị trí của chúng được liệt kê dưới đây:

* github.com/stripedconsu/linker
* github.com/agitatedleopa/stm
* github.com/expertsandba/opt
* github.com/wetteepee/hcloud-ip-floater
* github.com/weightycine/replika
* github.com/ordinarymea/tnsr_ids
* github.com/ordinarymea/TNSR_IDS
* github.com/cavernouskina/mcp-go
* github.com/lastnymph/gouid
* github.com/sinfulsky/gouid
* github.com/briefinitia/gouid

Hầu hết chúng vẫn còn sống, vì vậy các nhà phát triển Go được khuyên nên cẩn thận và kiểm tra kỹ lưỡng các thành phần xây dựng của họ trước khi sử dụng chúng trong môi trường của mình.