# DragonForce mở rộng mô hình ransomware với kế hoạch thương hiệu trắng

![DragonForce hình thành băng nhóm ransomware với nhiều đối tác RaaS](https://www.bleepstatic.com/content/hl-images/2023/06/07/blacksuit-ransomware.jpg)

Cảnh ransomware đang được tổ chức lại, với một băng nhóm được biết đến là DragonForce làm việc để tập hợp các hoạt động khác dưới một cấu trúc giống như băng nhóm.

DragonForce hiện đang khuyến khích các tác nhân ransomware với mô hình thương hiệu phân phối, cung cấp cho các hoạt động ransomware-as-a-service (RaaS) khác một phương tiện để thực hiện kinh doanh của họ mà không phải lo lắng về chi phí và nỗ lực bảo trì hạ tầng.

Một đại diện của nhóm cho biết với BleepingComputer rằng họ hoàn toàn có động cơ tài chính nhưng cũng tuân theo một "đạo đức" nhất định và phản đối tấn công các tổ chức chăm sóc sức khỏe nhất định.

Thông thường, một hoạt động RaaS có các đối tác hoặc liên kết riêng của mình, và nhà phát triển ransomware cung cấp phần mềm mã hóa tập tin và cơ sở hạ tầng.

Các đối tác sẽ tạo ra một biến thể của gói mã hóa, vi phạm mạng của nạn nhân, và triển khai ransomware. Họ cũng sẽ quản lý các khóa giải mã và thường thương lượng với nạn nhân để nhận tiền chuộc.

Nhà phát triển cũng duy trì một trang web rò rỉ dữ liệu (DLS) nơi họ công bố thông tin bị đánh cắp từ những nạn nhân không thanh toán cho kẻ tấn công.

Để đổi lấy việc sử dụng phần mềm độc hại và cơ sở hạ tầng của họ, nhà phát triển sẽ tính phí các đối tác một khoản phí từ tiền chuộc nhận được, thường là lên đến 30%.

### Kinh doanh ransomware của DragonForce

DragonForce giờ đây tự gọi mình là một “băng nhóm ransomware” và lấy 20% số tiền chuộc đã trả.

Dưới mô hình của họ, các đối tác có quyền truy cập vào cơ sở hạ tầng (công cụ thương lượng, lưu trữ dữ liệu bị đánh cắp, quản lý phần mềm độc hại), và sử dụng bộ mã hóa DragonForce dưới thương hiệu của riêng mình.

Nhóm đã công bố “hướng đi mới” vào tháng Ba, nói rằng các đối tác có thể tạo ra “thương hiệu riêng của mình dưới sự bảo trợ của một đối tác đã được chứng minh”.

Như bài đăng bên dưới đã nói, DragonForce đặt mục tiêu quản lý “vô số thương hiệu” có thể nhắm mục tiêu đến các hệ thống ESXi, NAS, BSD và Windows.

![DragonForce công bố mô hình RaaS mới](https://www.bleepstatic.com/images/news/u/1100723/DragonForce_new-model.png)

**DragonForce công bố mô hình RaaS giống như SaaS**  
_source: [Secureworks](https://www.secureworks.com/blog/ransomware-groups-evolve-affiliate-models)_

DragonForce cho biết với BleepingComputer rằng cấu trúc của họ là một thị trường, nơi các đối tác có thể chọn triển khai các cuộc tấn công dưới thương hiệu DragonForce hoặc một thương hiệu khác.

Về cơ bản, các nhóm tác nhân đe dọa có thể sử dụng dịch vụ và gán nhãn trắng dưới tên của riêng họ để nó trông như thể họ là một thương hiệu của riêng mình.

Đổi lại, họ không phải đối phó với cơn đau đầu khi điều hành các trang web rò rỉ dữ liệu và thương lượng, phát triển phần mềm độc hại hoặc xử lý các cuộc đàm phán.

Tuy nhiên, có quy tắc cần tuân theo, và các đối tác sẽ bị loại ra ngay khi có sai lầm đầu tiên. “Chúng tôi là những đối tác trung thực tôn trọng quy tắc,” đại diện DragonForce cho biết với chúng tôi.

“Họ phải tuân theo quy tắc, và chúng tôi có thể kiểm soát điều đó vì mọi thứ chúng tôi điều hành đều trên máy chủ của chúng tôi, nếu không sẽ không có ý nghĩa,” DragonForce nói.

Tuy nhiên, những quy tắc đó chỉ có sẵn cho những tác nhân đe dọa chấp nhận mô hình kinh doanh ransomware mới được đề xuất.

Khi được hỏi liệu các bệnh viện hoặc tổ chức chăm sóc sức khỏe có bị cấm hay không, DragonForce nói rằng điều đó hoàn toàn phụ thuộc vào loại bệnh viện, và thể hiện một cái gì đó có thể được mô tả là tính đồng cảm.

“Chúng tôi không tấn công bệnh nhân ung thư hoặc bất cứ điều gì liên quan đến tim, chúng tôi muốn gửi tiền cho họ và giúp đỡ họ. Chúng tôi ở đây vì kinh doanh và tiền bạc, tôi không đến đây để giết người, và các đối tác của tôi cũng vậy,” tác nhân đe dọa nói với BleepingComputer.

Các nhà nghiên cứu tại công ty an ninh mạng Secureworks cho biết mô hình của DragonForce có thể thu hút một loạt các đối tác rộng hơn và thu hút các tác nhân đe dọa kém kỹ thuật hơn.

“Ngay cả những tác nhân đe dọa tinh vi cũng có thể đánh giá cao tính linh hoạt cho phép họ triển khai phần mềm độc hại của riêng mà không cần tạo ra và duy trì cơ sở hạ tầng của riêng họ” - [Secureworks](https://www.secureworks.com/blog/ransomware-groups-evolve-affiliate-models)

Bằng cách mở rộng cơ sở đối tác, DragonForce có thể nhìn thấy lợi nhuận lớn hơn nhờ vào tính linh hoạt của mô hình đã đề xuất của mình.

Không rõ có bao nhiêu đối tác ransomware đã liên hệ với băng nhóm DragonForce về mô hình dịch vụ mới này, nhưng tác nhân đe dọa cho biết rằng danh sách thành viên bao gồm các băng nhóm nổi tiếng.

"Tôi không thể cho bạn biết số lượng chính xác, nhưng chúng tôi có những người chơi đến với chúng tôi mà bạn thường viết về và muốn hợp tác với chúng tôi," DragonForce nói với BleepingComputer.

Một băng nhóm ransomware mới gọi là RansomBay đã đăng ký theo mô hình của DragonForce.