# NVIDIA chia sẻ hướng dẫn để bảo vệ GPU GDDR6 chống lại các cuộc tấn công Rowhammer

![NVIDIA chia sẻ hướng dẫn để bảo vệ GPU GDDR6 chống lại các cuộc tấn công Rowhammer](https://www.bleepstatic.com/content/hl-images/2022/03/01/NVIDIA___headpic.jpg)

NVIDIA cảnh báo người dùng kích hoạt System Level Error-Correcting Code để bảo vệ chống lại các cuộc tấn công Rowhammer trên các bộ xử lý đồ họa sử dụng bộ nhớ GDDR6.

Công ty củng cố khuyến nghị này khi nghiên cứu mới cho thấy cuộc tấn công Rowhammer chống lại GPU NVIDIA A6000 (bộ xử lý đồ họa).

Rowhammer là một lỗi phần cứng có thể được kích hoạt thông qua các quy trình phần mềm và xuất phát từ việc các ô nhớ quá gần nhau. Cuộc tấn công đã được minh chứng trên các ô DRAM nhưng nó cũng có thể ảnh hưởng tới bộ nhớ GPU.

Nó hoạt động bằng cách truy cập một hàng nhớ với đủ các thao tác đọc-ghi, điều này khiến giá trị của các bit dữ liệu bên cạnh đảo ngược từ một thành không và ngược lại, dẫn đến thông tin trong bộ nhớ thay đổi.

Tác động có thể là một tình trạng từ chối dịch vụ, hỏng dữ liệu hoặc thậm chí là nâng cao quyền hạn.

Hệ thống Mã Sửa Lỗi Mức Hệ Thống (ECC) có thể bảo vệ tính toàn vẹn của dữ liệu bằng cách thêm các bit dư thừa và sửa lỗi đơn-bit để duy trì độ tin cậy và độ chính xác của dữ liệu.

Trong các GPU máy trạm và trung tâm dữ liệu mà VRAM xử lý các tập dữ liệu lớn và các phép toán chính xác liên quan đến khối lượng công việc AI, ECC phải được kích hoạt để ngăn chặn các lỗi quan trọng trong hoạt động của chúng.

Thông báo bảo mật của NVIDIA lưu ý rằng các nhà nghiên cứu tại Đại học Toronto đã chỉ ra "một cuộc tấn công Rowhammer tiềm năng chống lại GPU NVIDIA A6000 với Bộ nhớ GDDR6" mà ở đó System-Level ECC không được kích hoạt.

Các nhà nghiên cứu học thuật đã phát triển GPUHammer, một phương pháp tấn công để đảo bit trên bộ nhớ GPU.

Mặc dù việc tấn công Rowhammer trên GDDR6 khó hơn do độ trễ cao hơn và tốc độ làm mới nhanh hơn so với DDR4 dựa trên CPU, các nhà nghiên cứu đã chứng minh rằng [các cuộc tấn công Rowhammer trên GPU](https://gururaj-s.github.io/assets/pdf/SEC25%5FGPUHammer.pdf) là có thể.

Ngoài RTX A6000, nhà sản xuất GPU cũng [khuyến nghị](https://nvidia.custhelp.com/app/answers/detail/a%5Fid/5671) kích hoạt System-Level ECC cho các sản phẩm sau:

**GPU Trung tâm Dữ liệu:**

* Ampere: A100, A40, A30, A16, A10, A2, A800
* Ada: L40S, L40, L4
* Hopper: H100, H200, GH200, H20, H800
* Blackwell: GB200, B200, B100
* Turing: T1000, T600, T400, T4
* Volta: Tesla V100, Tesla V100S

**GPU Máy trạm:**

* Ampere RTX: A6000, A5000, A4500, A4000, A2000, A1000, A400
* Ada RTX: 6000, 5000, 4500, 4000, 4000 SFF, 2000
* Blackwell RTX PRO (dòng máy trạm mới nhất)
* Turing RTX: 8000, 6000, 5000, 4000
* Volta: Quadro GV100

**Nhúng / Công nghiệp:**

* Jetson AGX Orin Industrial
* IGX Orin

Nhà sản xuất GPU lưu ý rằng các GPU mới hơn như Dòng Blackwell RTX 50 (GeForce), Trung tâm Dữ liệu Blackwell GB200, B200, B100 và Trung tâm Dữ liệu Hopper H100, H200, H20 và GH200, đi kèm với bảo vệ ECC tích hợp trên chip, không cần sự can thiệp từ người dùng.

Một cách để kiểm tra xem System Level ECC có được kích hoạt hay không là sử dụng một phương pháp ngoài băng tần sử dụng BMC (Baseboard Management Controller) của hệ thống và phần mềm giao diện phần cứng, như [Redfish API](https://www.dmtf.org/standards/redfish), để kiểm tra trạng thái "ECCModeEnabled".

Các công cụ như NSM Type 3 và NVIDIA SMBPBI cũng có thể được sử dụng để cấu hình, mặc dù chúng yêu cầu truy cập vào NVIDIA Partner Portal.

Một phương pháp In-Band thứ hai cũng tồn tại, sử dụng tiện ích dòng lệnh nvidia-smi từ CPU của hệ thống để kiểm tra và kích hoạt ECC khi được hỗ trợ.

Rowhammer đại diện cho một mối đe dọa bảo mật thực sự có thể gây ra hỏng dữ liệu hoặc cho phép các cuộc tấn công trong các môi trường đa người dùng như máy chủ đám mây, nơi các GPU dễ bị tấn công có thể được triển khai.

Tuy nhiên, rủi ro thực sự phụ thuộc vào bối cảnh, và khai thác Rowhammer một cách đáng tin cậy là phức tạp, yêu cầu các điều kiện cụ thể, tỷ lệ truy cập cao và kiểm soát chính xác, làm cho nó trở thành một cuộc tấn công khó thực hiện.