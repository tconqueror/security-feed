# NVIDIA đưa ra hướng dẫn bảo vệ GPU GDDR6 khỏi các cuộc tấn công Rowhammer

![NVIDIA đưa ra hướng dẫn bảo vệ GPU GDDR6 khỏi các cuộc tấn công Rowhammer](https://www.bleepstatic.com/content/hl-images/2022/03/01/NVIDIA___headpic.jpg)

NVIDIA đang cảnh báo người dùng kích hoạt cơ chế mã sửa lỗi hệ thống (System Level Error-Correcting Code) để bảo vệ chống lại các cuộc tấn công Rowhammer trên các bộ xử lý đồ họa sử dụng bộ nhớ GDDR6.

Công ty đang củng cố khuyến nghị khi các nghiên cứu mới cho thấy một cuộc tấn công Rowhammer chống lại GPU NVIDIA A6000.

Rowhammer là một lỗi phần cứng có thể được kích hoạt thông qua các quy trình phần mềm và xuất phát từ việc các ô nhớ quá gần nhau. Nếu một vị trí bị tấn công bằng đủ các thao tác đọc-ghi, giá trị của các bit dữ liệu kề bên có thể bị đảo ngược từ một thành không và ngược lại, và do đó thay đổi thông tin trong bộ nhớ.

Hệ quả có thể là tình trạng từ chối dịch vụ, hư hại dữ liệu hoặc thậm chí tăng cường đặc quyền.

Các mã sửa lỗi hệ thống (ECC) có thể giữ nguyên tính toàn vẹn của dữ liệu bằng cách thêm các bit dư và sửa chữa lỗi từng bit để duy trì độ tin cậy và chính xác của dữ liệu.

Trong các GPU workstation và trung tâm dữ liệu, nơi VRAM xử lý các tập dữ liệu lớn và các phép tính chính xác liên quan đến khối lượng công việc AI, ECC phải được bật để ngăn chặn các lỗi quan trọng trong hoạt động của chúng.

Thông báo bảo mật của NVIDIA lưu ý rằng các nhà nghiên cứu tại Đại học Toronto đã chỉ ra "một cuộc tấn công Rowhammer tiềm năng chống lại GPU NVIDIA A6000 với bộ nhớ GDDR6" mà không có System-Level ECC được bật.

Ngoài RTX A6000, nhà sản xuất GPU cũng [khuyến nghị](https://nvidia.custhelp.com/app/answers/detail/a%5Fid/5671) bật System-Level ECC cho các sản phẩm sau:

**GPU Trung tâm Dữ liệu:**

* Ampere: A100, A40, A30, A16, A10, A2, A800
* Ada: L40S, L40, L4
* Hopper: H100, H200, GH200, H20, H800
* Blackwell: GB200, B200, B100
* Turing: T1000, T600, T400, T4
* Volta: Tesla V100, Tesla V100S

**GPU Workstation:**

* Ampere RTX: A6000, A5000, A4500, A4000, A2000, A1000, A400
* Ada RTX: 6000, 5000, 4500, 4000, 4000 SFF, 2000
* Blackwell RTX PRO (dòng workstation mới nhất)
* Turing RTX: 8000, 6000, 5000, 4000
* Volta: Quadro GV100

**Nhúng / Công nghiệp:**

* Jetson AGX Orin Industrial
* IGX Orin

Nhà sản xuất GPU lưu ý rằng các GPU mới hơn như Blackwell RTX 50 Series (GeForce), Blackwell Data Center GB200, B200, B100, và Hopper Data Center H100, H200, H20, và GH200, có tích hợp bảo vệ ECC trên die, không yêu cầu can thiệp từ người dùng.

Một cách để kiểm tra xem System Level ECC có được bật hay không là sử dụng phương pháp ngoài băng (out-of-band) sử dụng BMC (Baseboard Management Controller) của hệ thống và phần mềm giao diện phần cứng, như [Redfish API](https://www.dmtf.org/standards/redfish), để kiểm tra trạng thái "ECCModeEnabled".

Các công cụ như NSM Type 3 và NVIDIA SMBPBI cũng có thể được sử dụng để cấu hình, mặc dù chúng yêu cầu quyền truy cập vào Cổng thông tin Đối tác NVIDIA.

Một phương pháp In-Band thứ hai cũng tồn tại, sử dụng tiện ích dòng lệnh nvidia-smi từ CPU của hệ thống để kiểm tra và bật ECC ở những nơi có hỗ trợ.

Rowhammer đại diện cho một mối quan tâm an ninh thực sự có thể gây ra hư hại dữ liệu hoặc cho phép các cuộc tấn công trong các môi trường đa người dùng như máy chủ đám mây nơi các GPU dễ bị tổn thương có thể được triển khai.

Tuy nhiên, rủi ro thực sự phụ thuộc vào ngữ cảnh, và việc khai thác Rowhammer một cách đáng tin cậy là phức tạp, đòi hỏi các điều kiện cụ thể, tỷ lệ truy cập cao và kiểm soát chính xác, làm cho nó trở thành một cuộc tấn công khó thực hiện.