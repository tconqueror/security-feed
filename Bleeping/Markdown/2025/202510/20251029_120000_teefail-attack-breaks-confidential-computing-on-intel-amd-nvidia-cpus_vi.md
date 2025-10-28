# TEE.Fail attack breaks confidential computing on Intel, AMD, NVIDIA CPUs

![TEE.Fail attack breaks confidential computing on Intel, AMD, NVIDIA CPUs](https://www.bleepstatic.com/content/hl-images/2023/11/14/CPU_attack.jpg)

Các nhà nghiên cứu học thuật đã phát triển một cuộc tấn công kênh bên gọi là TEE.Fail, cho phép trích xuất bí mật từ môi trường thực thi tin cậy trong CPU — vùng rất an toàn của hệ thống, như Intel's SGX và TDX, và AMD's SEV-SNP.

Phương pháp này là một cuộc tấn công chèn vào bus bộ nhớ trên hệ thống DDR5 mà những người yêu thích máy tính có thể thực hiện thành công với chi phí dưới $1,000.

Trusted Execution Environments (TEEs) là phần cứng “confidential computing” bên trong bộ xử lý chính đảm bảo tính bảo mật và toàn vẹn của dữ liệu nhạy cảm, như khóa mã hóa dùng cho xác thực và ủy quyền.

Môi trường này được cách ly khỏi hệ điều hành và tạo ra các vùng nhớ được bảo vệ nơi mã và dữ liệu có thể chạy an toàn.

Những nhà nghiên cứu từ Georgia Tech và Purdue University ghi nhận rằng các triển khai hiện đại của Intel SGX, Intel TDX và AMD SEV-SNP không còn an toàn như quảng cáo, do các đánh đổi kiến trúc trong các thế hệ gần đây.

Cụ thể, TEEs đã chuyển từ CPU dành cho khách hàng sang phần cứng chuẩn máy chủ sử dụng bộ nhớ DDR5, vốn áp dụng mã hóa bộ nhớ AES-XTS có tính xác định và loại bỏ các biện pháp bảo toàn toàn vẹn bộ nhớ và chống phát lại để đổi lấy hiệu năng và khả năng mở rộng.

Thí nghiệm của họ xác nhận rằng có thể lợi dụng những điểm yếu này để trích xuất khóa và giả mạo attestation. TEE.Fail là cuộc tấn công ciphertext dựa trên DDR5 đầu tiên, mở rộng các công trình DDR4 trước đó như [WireTap](https://wiretap.fail/) và [BatteringRAM](https://batteringram.eu/).

## Cuộc tấn công và hậu quả

Cuộc tấn công đòi hỏi truy cập vật lý vào mục tiêu cũng như quyền root để sửa đổi driver Kernel, nhưng không cần chuyên môn cấp chip.

Trong bài báo kỹ thuật, các nhà nghiên cứu giải thích rằng họ có thể thu tín hiệu một cách đáng tin cậy bằng cách giảm xung nhịp bộ nhớ của hệ thống xuống 3200 MT/s (1.6 GHz). Để làm điều này, họ gắn một RDIMM riser và một mạng cô lập probe tùy chỉnh giữa một DDR5 DIMM và bo mạch chủ.

![The snooping rig (right) and the target (left)](https://www.bleepstatic.com/images/news/u/1220909/2025/October/rig.jpg)

**Dàn dò nghe lén (bên phải) và mục tiêu (bên trái)**  
_Source: tee.fail_

Với interposer được kết nối vào logic analyzer, kẻ tấn công ghi lại các lệnh/địa chỉ và các chuỗi dữ liệu DDR5, nên họ có thể thấy các ciphertext được ghi vào và đọc từ các vị trí DRAM vật lý.

![DDR5 memory bus traffic during a TEE.fail attack](https://www.bleepstatic.com/images/news/u/1220909/2025/October/analuze.jpg)

**Lưu lượng bus bộ nhớ DDR5 trong một cuộc tấn công TEE.fail**  
_Source: tee.fail_

Để đạt được mục tiêu với Intel's SGX, các nhà nghiên cứu buộc dữ liệu trong các địa chỉ ảo về một kênh bộ nhớ đơn mà họ có thể quan sát qua interposer.

Thông qua một giao diện cho địa chỉ vật lý mà Intel phơi bày tới thành phần Memory Address Translation, các nhà nghiên cứu có thể "tiếp tục phơi bày giao diện giải mã này cho không gian người dùng thông qua _sysfs._"

Điều này cho phép họ tìm thông tin để xác định vị trí DIMM cho địa chỉ vật lý.

Tuy nhiên, SGX sử dụng kernel của OS để phân bổ bộ nhớ vật lý và các nhà nghiên cứu đã "sửa đổi driver SGX của kernel để chấp nhận một cặp địa chỉ ảo và vật lý như một tham số được lưu trong bộ nhớ kernel toàn cục."

Các nhà nghiên cứu cho biết họ đã tạo một SGX enclave mà liên tục truy vấn một địa chỉ ảo cụ thể bằng các thao tác đọc và ghi. Điều này cho phép họ xác minh rằng ciphertext được mã hóa quan sát trên interposer bộ nhớ là một hàm xác định của địa chỉ bộ nhớ vật lý và nội dung của nó.

"Để kiểm tra rằng mã hóa là có tính xác định, chúng tôi hướng dẫn enclave của mình thực hiện một chuỗi các thao tác ghi và đọc tới một địa chỉ ảo cố định trong bộ nhớ enclave, thu lại dữ liệu ciphertext đọc được sau mỗi bước bằng logic analyzer của chúng tôi," họ giải thích.

Do việc sử dụng mã hóa AES-XTS, nơi một mảnh thông tin được mã hóa ra cùng một đầu ra mỗi lần, nhóm đã ghi các giá trị đã biết vào các địa chỉ vật lý có thể quan sát để xây dựng ánh xạ ciphertext–giá trị.

**Ciphertext from three reads of enclave data**  
_Source: tee.fail_

Sau đó, bằng cách kích hoạt và ghi lại các hoạt động mã hóa mục tiêu, họ quan sát các truy cập được mã hóa tới các mục bảng trung gian và phục hồi các chữ số nonce từng chữ ký.

Từ nonce phục hồi và chữ ký công khai, họ tái tạo khóa bí mật ký, cho phép họ giả mạo các quotes hợp lệ của SGX/TDX và mạo danh TEEs chân chính.

Cùng một phương pháp được sử dụng để trích xuất khóa ký từ OpenSSL chạy trong một máy ảo được bảo vệ bởi AMD's SEV-SNP.

Cần lưu ý rằng các cuộc tấn công chống lại AMD SEV-SNP vẫn hoạt động ngay cả khi tùy chọn bảo mật “Ciphertext Hiding” được bật.

Các nhà nghiên cứu trình diễn các cuộc tấn công cho phép họ:

* Giả mạo attestation TDX trên Ethereum BuilderNet để truy cập dữ liệu giao dịch và khóa bí mật, cho phép frontrunning không bị phát hiện.
* Giả mạo attestation của Intel và NVIDIA để chạy workload ngoài TEE trong khi vẫn có vẻ hợp lệ.
* Trích xuất khóa riêng ECDH trực tiếp từ enclave, phục hồi khóa chính của mạng và hoàn toàn phá vỡ tính bảo mật.

Thông qua TEE.Fail, các nhà nghiên cứu có thể chứng minh rằng có thể chiếm quyền thực thi TEE và quan sát các địa chỉ ảo cụ thể. Các nhà nghiên cứu cũng nhắm vào một server Xeon và thu được Provisioning Certificate Key (PCK) — được dùng để xác minh danh tính của thiết bị.

TEE.Fail là một cuộc tấn công phức tạp đòi hỏi truy cập vật lý. Điều này khiến nó kém thực tế hơn trong kịch bản thế giới thực và độ phức tạp của nó không phải là mối đe dọa đối với người dùng trung bình.

Các nhà nghiên cứu đã báo cáo phát hiện của họ cho Intel vào tháng Tư, cho AMD vào tháng Tám, và cho NVIDIA vào tháng Sáu. Cả ba nhà cung cấp đều thừa nhận các vấn đề và cho biết họ đang làm việc trên các biện pháp giảm nhẹ và điều chỉnh cho mô hình mối đe dọa confidential computing, với kế hoạch công bố các tuyên bố chính thức khi bài báo TEE.Fail được công bố.

BleepingComputer đã yêu cầu Intel, AMD và NVIDIA chia sẻ các tuyên bố của họ để đưa vào báo cáo này, nhưng chúng tôi chưa nhận được phản hồi khi bài viết được xuất bản.