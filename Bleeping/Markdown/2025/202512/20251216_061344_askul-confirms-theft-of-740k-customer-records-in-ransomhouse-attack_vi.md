# Askul xác nhận mất cắp 740k hồ sơ khách hàng trong cuộc tấn công ransomware

![Askul xác nhận mất cắp 740k hồ sơ khách hàng trong cuộc tấn công ransomware](https://www.bleepstatic.com/content/hl-images/2024/08/27/ransomware-2.jpg)

Tập đoàn thương mại điện tử lớn của Nhật Bản Askul Corporation xác nhận rằng các tin tặc RansomHouse đã đánh cắp khoảng 740.000 hồ sơ khách hàng trong cuộc tấn công ransomware mà công ty chịu ảnh hưởng vào tháng 10.

Askul là một công ty thương mại điện tử lớn cung cấp văn phòng phẩm và logistics theo mô hình business-to-business và business-to-consumer, thuộc sở hữu của Yahoo! Japan Corporation.

Sự cố ransomware vào tháng 10 đã gây ra sự cố hệ thống CNTT, buộc công ty phải tạm ngưng việc giao hàng cho khách hàng, bao gồm cả [retail giant Muji](https://www.bleepingcomputer.com/news/security/retail-giant-muji-halts-online-sales-after-ransomware-attack-on-supplier/).

Cuộc điều tra về phạm vi và tác động của sự cố hiện đã được kết luận, và Askul cho biết các loại dữ liệu sau đã bị xâm phạm:

* Dữ liệu dịch vụ khách hàng doanh nghiệp: khoảng 590.000 hồ sơ
* Dữ liệu dịch vụ khách hàng cá nhân: khoảng 132.000 hồ sơ
* Đối tác kinh doanh (bên gia công, đại lý, nhà cung cấp): khoảng 15.000 hồ sơ
* Ban lãnh đạo và nhân viên (bao gồm công ty thành viên): khoảng 2.700 hồ sơ

Askul lưu ý rằng các chi tiết chính xác đã được giữ lại để ngăn chặn việc lợi dụng thông tin bị xâm phạm, và những khách hàng cùng đối tác bị ảnh hưởng sẽ được thông báo riêng lẻ.

Ngoài ra, công ty đã thông báo cho Personal Information Protection Commission của quốc gia về việc rò rỉ dữ liệu và thiết lập giám sát dài hạn để ngăn chặn việc lạm dụng thông tin bị đánh cắp.

Trong khi đó, [tính đến ngày 15 tháng 12](https://www.askul.co.jp/snw/newsDispView/?newsId=18364), việc giao hàng vẫn tiếp tục bị ảnh hưởng, và công ty vẫn đang [làm việc để phục hồi hoàn toàn hệ thống](http://www.askul.co.jp/shopnews/news%5F251027%5Femergency%5Ffaq.html).

### Chi tiết cuộc tấn công RansomHouse

Cuộc tấn công vào Askul đã được nhóm tống tiền RansomHouse nhận trách nhiệm. Nhóm ban đầu công bố vi phạm vào ngày 30 tháng 10 và tiếp tục với hai đợt rò rỉ dữ liệu vào ngày 10 tháng 11 và ngày 2 tháng 12.

![RansomHouse rò rỉ dữ liệu Askul mới nhất](https://www.bleepstatic.com/images/news/u/1220909/2025/December/ransomhouse.jpg)

**RansomHouse rò rỉ dữ liệu Askul mới nhất**  
_Source: BleepingComputer_

Askul đã chia sẻ một số chi tiết về cách các tác nhân đe dọa xâm nhập vào mạng lưới của họ, ước tính rằng họ lợi dụng thông tin xác thực bị xâm phạm cho tài khoản quản trị của một đối tác gia công, vốn không được bảo vệ bằng xác thực đa yếu tố (MFA).

"After successfully achieving the initial intrusion, the attacker began reconnaissance of the network and attempted to collect authentication information to access multiple servers," reads the automated translation of [Askul's report](https://pdf.irpocket.com/C0032/PDLX/O3bg/N4O3.pdf).

"The attacker then disables vulnerability countermeasure software such as EDR, moves between multiple servers, and acquires the necessary privileges," the company said.

Đáng chú ý, Askul cho biết rằng nhiều biến thể ransomware đã được sử dụng trong cuộc tấn công, một số trong đó né tránh các chữ ký EDR đã được cập nhật vào thời điểm đó.

![Sơ đồ tấn công](https://www.bleepstatic.com/images/news/u/1220909/2025/December/1.jpg)

**Sơ đồ tấn công**  
_Nguồn: Askul_

RansomHouse nổi tiếng cả về việc đánh cắp dữ liệu lẫn mã hóa hệ thống. Askul cho biết cuộc tấn công ransomware "đã dẫn đến việc mã hóa dữ liệu và sự cố hệ thống."

Askul báo cáo rằng payload ransomware đã được triển khai đồng thời trên nhiều máy chủ, trong khi các tệp sao lưu đã bị xóa để ngăn việc khôi phục dễ dàng.

Để ứng phó, công ty đã ngắt kết nối vật lý các mạng bị nhiễm và cắt đứt liên lạc giữa các trung tâm dữ liệu và trung tâm logistics, cô lập các thiết bị bị ảnh hưởng, và cập nhật chữ ký EDR.

Hơn nữa, MFA đã được áp dụng cho tất cả hệ thống then chốt, và tất cả tài khoản quản trị viên đã được đặt lại mật khẩu.

Tác động tài chính của cuộc tấn công chưa được ước tính, và Askul đã hoãn báo cáo thu nhập dự kiến để có thêm thời gian đánh giá tài chính chi tiết.