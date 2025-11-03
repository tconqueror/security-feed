# Tin tặc sử dụng công cụ RMM để xâm nhập các phương tiện chở hàng và đánh cắp lô hàng

![Tin tặc sử dụng công cụ RMM để xâm nhập tàu chở hàng và đánh cắp lô hàng](https://www.bleepstatic.com/content/hl-images/2025/11/03/truck.jpg)

Những tác nhân đe doạ đang nhắm tới các nhà môi giới hàng hóa và các doanh nghiệp vận tải bằng các liên kết và email độc hại để triển khai công cụ giám sát và quản trị từ xa (RMMs) cho phép họ chiếm đoạt hàng hóa và đánh cắp tài sản vật lý.

Các nhà nghiên cứu theo dõi hoạt động này đến tháng Sáu, nhưng họ tìm thấy bằng chứng cho thấy các chiến dịch kiểu này đã phân phối NetSupport và ScreenConnect từ tháng Một.

Theo công ty an ninh email Proofpoint, những cuộc tấn công này đang trở nên phổ biến hơn, với gần hai tá chiến dịch được ghi nhận kể từ tháng Tám, mỗi chiến dịch gửi tới một nghìn tin nhắn.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Các mục tiêu chủ yếu là các tổ chức Bắc Mỹ; tuy nhiên, Proofpoint cũng đã quan sát hoạt động tương tự ở Brazil, Mexico, India, Germany, Chile, và South Africa.

## Trộm cắp hàng hóa được số hóa

Trộm cắp hàng hóa bao gồm việc đánh cắp lô hàng thương mại bằng cách chiếm đoạt xe tải hoặc rơ-moóc đang vận chuyển, chuyển hướng chúng, hoặc mạo danh các nhà vận chuyển hợp pháp. Hàng hóa sau đó bị chuyển đến các điểm nhận giả mạo.

National Insurance Crime Bureau (NICB) ước tính thiệt hại do trộm cắp hàng hóa tại Hoa Kỳ lên tới $35 billion mỗi năm.

Ngày nay, tội phạm mạng tập trung khai thác các lỗ hổng trong phân đoạn số của chuỗi cung ứng giúp các công ty vận chuyển hàng hóa hiệu quả hơn.

Mục tiêu chính của kẻ tấn công là cài đặt các RMM như ScreenConnect, SimpleHelp, PDQ Connect, Fleetdeck, N-able, và LogMeIn Resolve trên hệ thống của các công ty mục tiêu, cho phép chúng kiểm soát từ xa đầy đủ, tiến hành trinh sát và thu thập thông tin đăng nhập.

Để đạt được mục tiêu này, chúng sử dụng các tài khoản bị xâm phạm trên các bảng chào hàng (load boards) để đăng các danh sách vận chuyển gian lận, hoặc xâm nhập tài khoản email của nhà môi giới và điều phối viên, rồi chiếm các chuỗi email để dụ nạn nhân tới một URL độc hại.

![Phản hồi email gửi cho các nạn nhân bị mắc bẫy](https://www.bleepstatic.com/images/news/u/1220909/2025/October/email(3).jpg)

**Phản hồi email gửi cho các nhà vận chuyển bị mắc bẫy do mồi trên bảng chào hàng**  
_Nguồn: Proofpoint_

Theo các nhà nghiên cứu, tác nhân đe doạ đạt được mục tiêu bằng cách gửi email trực tiếp tới các nhà vận chuyển có tài sản (asset-based carriers), các công ty môi giới hàng hóa và các nhà cung cấp chuỗi cung ứng tích hợp, nhưng điều này chủ yếu xảy ra với các tổ chức lớn hơn.

**Email gửi trực tiếp tới các công ty lớn hơn**  
_Nguồn: Proofpoint_

Ở giai đoạn này, kỹ thuật xã hội đóng vai trò chủ đạo, nơi kẻ tấn công điều chỉnh thông điệp cho các cuộc đàm phán tải gấp và lợi dụng sự tin tưởng vào các gói thông tin hàng, thể hiện hiểu biết về cách hoạt động của ngành vận tải hàng hóa.

Các trang ngoài được thiết kế tinh vi và có vẻ hợp pháp bằng cách đặt thương hiệu nhà vận chuyển thuyết phục, và dẫn tới việc tải về các tệp thực thi hoặc tệp cài đặt MSI cài đặt công cụ RMM.

Thông qua các công cụ này, vốn là phần mềm hợp lệ, kẻ tấn công có thể điều khiển máy bị xâm phạm và có thể sửa đổi đặt chỗ, chặn thông báo cho điều phối viên, thêm thiết bị của mình vào các máy nhánh điện thoại của điều phối viên, và đặt tải dưới danh tính của nhà vận chuyển bị xâm phạm.

“Các RMM này thường được sử dụng đồng thời; ví dụ, PDQ Connect đã được quan sát tải xuống và cài đặt cả ScreenConnect và SimpleHelp,” Proofpoint giải thích.

“Khi đã có quyền truy cập ban đầu, tác nhân đe doạ tiến hành trinh sát hệ thống và mạng và triển khai các công cụ thu thập thông tin đăng nhập như WebBrowserPassView,” các nhà nghiên cứu nói.

Hoạt động trinh sát và thu thập thông tin đăng nhập cho thấy mục đích tấn công rộng hơn bao gồm di chuyển sang các phần sâu hơn trong môi trường bị xâm phạm.

**Tổng quan về cuộc tấn công**  
_Nguồn: Proofpoint_

Proofpoint lưu ý rằng các cuộc tấn công gợi ý về việc có kiến thức nội bộ về lộ trình, thời gian và loại hàng hóa có giá trị cao, cho phép tội phạm mạng chọn các lô hàng có lợi nhất để đánh cắp.

Các nhà nghiên cứu tin rằng các hacker "đang làm việc với các nhóm tội phạm có tổ chức để xâm phạm các thực thể trong ngành vận tải bề mặt" và chiếm đoạt hàng hóa.

Một công ty vận chuyển từng là mục tiêu trong các cuộc tấn công như vậy cho biết kẻ tấn công đã lừa điều phối viên của họ cài đặt một công cụ RMM và chiếm quyền kiểm soát tài khoản của họ.

Kẻ tấn công "đã xóa mọi email đặt chỗ và chặn thông báo" và thêm thiết bị của chúng vào máy nhánh điện thoại của điều phối viên. Điều này cho phép chúng mạo danh công ty nạn nhân và nói chuyện trực tiếp với các nhà môi giới.

"Khi đặt tải, hắn dùng email MC chính thức + điện thoại của chúng tôi (listed on FMCSA)," một đại diện của nhà vận chuyển cho biết, thêm rằng "Brokers, Highway, MyCarrierPackets sẽ gọi số của chúng tôi và gửi email — hacker trả lời, xác minh mọi thứ, và lấy được các tải."

Hàng hóa bị đánh cắp, bao gồm các mặt hàng như thực phẩm, đồ uống và điện tử, bị chặn vật lý hoặc chuyển hướng và sau đó được bán trực tuyến hoặc gửi ra nước ngoài.

Trong khi Proofpoint đã quan sát thấy các công cụ RMM được sử dụng trong các cuộc tấn công, công ty lưu ý rằng các trình đánh cắp thông tin như NetSupport, DanaBot, Lumma Stealer, và StealC cũng đã được triển khai trong các hoạt động liên quan, mặc dù không thể xác định được qui cụ cụ thể cho từng nhóm.

Các biện pháp phòng thủ được khuyến nghị bao gồm hạn chế cài đặt các công cụ RMM không được phê duyệt, giám sát hoạt động mạng, và chặn các tệp đính kèm .EXE và .MSI ở mức cổng email.