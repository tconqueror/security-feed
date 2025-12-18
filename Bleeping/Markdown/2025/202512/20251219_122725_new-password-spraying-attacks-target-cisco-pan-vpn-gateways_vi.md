# Các cuộc tấn công password spraying mới nhắm vào cổng VPN của Cisco và PAN

![Các cuộc tấn công password spraying mới nhắm vào Cisco, PAN VPN gateways](https://www.bleepstatic.com/content/hl-images/2025/11/05/Credit-card-hacker.jpg)

Một chiến dịch tự động đang nhắm vào nhiều nền tảng VPN, với các tấn công dựa trên thông tin đăng nhập được quan sát trên Palo Alto Networks GlobalProtect và Cisco SSL VPN.

Vào ngày 11 tháng 12, nền tảng giám sát mối đe dọa GreyNoise quan sát thấy số lần cố gắng đăng nhập nhắm vào các cổng GlobalProtect đạt đỉnh ở 1,7 triệu trong khoảng thời gian 16 giờ.

Dữ liệu thu thập cho thấy các cuộc tấn công có nguồn gốc từ hơn 10.000 địa chỉ IP duy nhất và nhắm vào hạ tầng đặt tại United States, Mexico, and Pakistan.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Lưu lượng độc hại gần như hoàn toàn phát sinh từ không gian địa chỉ IP của 3xK GmbH (Germany), cho thấy một hạ tầng đám mây tập trung.

Dựa trên quan sát của các nhà nghiên cứu, tác nhân đe dọa đã tái sử dụng các kết hợp tên đăng nhập và mật khẩu phổ biến, và hầu hết các yêu cầu đến từ user agent Firefox mà không thường thấy đối với hoạt động đăng nhập tự động qua nhà cung cấp này.

"Sự nhất quán của user agent, cấu trúc yêu cầu, và thời điểm cho thấy hành vi dò tìm thông tin đăng nhập được kịch bản hóa nhằm xác định các cổng GlobalProtect bị lộ hoặc được bảo vệ yếu, thay vì các nỗ lực truy cập tương tác hay khai thác lỗ hổng," [GreyNoise giải thích](https://www.greynoise.io/blog/credential-based-campaign-cisco-palo-alto-networks-vpn-gateways).

“Hoạt động này phản ánh áp lực liên tục nhằm vào các điểm xác thực VPN doanh nghiệp, một mô thức mà GreyNoise đã quan sát lặp lại trong các giai đoạn tăng cường hoạt động của kẻ tấn công.”

![Hoạt động nhắm vào các cổng GlobalProtect](https://www.bleepstatic.com/images/news/u/1220909/2025/December/globalprotect.jpg)

**Hoạt động nhắm vào các cổng GlobalProtect**  
_Nguồn: GreyNoise_

Vào ngày 12 tháng 12, hoạt động xuất phát từ cùng nhà cung cấp hosting sử dụng cùng dấu vân tay TCP bắt đầu dò quét các endpoint Cisco SSL VPN.

Các bộ giám sát của GreyNoise ghi nhận số địa chỉ IP tấn công duy nhất tăng lên 1.273, từ mức cơ sở bình thường dưới 200.

Hoạt động này cấu thành việc sử dụng quy mô lớn đầu tiên của các IP do 3xK lưu trữ nhằm vào Cisco SSL VPN trong 12 tuần qua.

Trong trường hợp này cũng vậy, payload đăng nhập tuân theo luồng xác thực SSL VPN bình thường, bao gồm xử lý CSRF, cho thấy các tấn công dựa trên thông tin đăng nhập tự động hơn là khai thác lỗ hổng.

**Số lượng IP dò quét các endpoint Cisco SSL VPN**  
_Nguồn: GreyNoise_

Hôm qua, Cisco cảnh báo khách hàng về một lỗ hổng zero-day mức độ nghiêm trọng tối đa (CVE-2025-20393) trong Cisco AsyncOS đang [bị lợi dụng tích cực trong các cuộc tấn công](https://www.bleepingcomputer.com/news/security/cisco-warns-of-unpatched-asyncos-zero-day-exploited-in-attacks/) nhắm vào các thiết bị Secure Email Gateway (SEG) và Secure Email and Web Manager (SEWM).

Tuy nhiên, GreyNoise nhấn mạnh rằng họ không tìm thấy bằng chứng liên kết hoạt động quan sát được với CVE-2025-20393.

Một phát ngôn viên của Palo Alto Networks xác nhận với BleepingComputer rằng họ biết về hoạt động này. Công ty khuyến nghị người dùng sử dụng mật khẩu mạnh và bảo vệ bằng xác thực đa yếu tố.

“Chúng tôi biết về hoạt động dựa trên thông tin đăng nhập do GreyNoise báo cáo nhắm vào các cổng VPN, bao gồm các cổng GlobalProtect. Hoạt động này phản ánh việc dò tìm thông tin đăng nhập được kịch bản hóa và không cấu thành việc xâm phạm môi trường của chúng tôi hay khai thác bất kỳ lỗ hổng nào của Palo Alto Networks,” người phát ngôn của Palo Alto Networks cho biết.

"Cuộc điều tra của chúng tôi xác nhận rằng đây là các nỗ lực được kịch bản hóa nhằm xác định thông tin đăng nhập yếu," họ bổ sung.

Ngoài các hành động được Palo Alto Networks khuyến nghị, GreyNoise cũng khuyên các quản trị viên nên kiểm toán các thiết bị mạng, tìm các nỗ lực đăng nhập bất thường, và chặn các địa chỉ IP độc hại đã biết đang thực hiện những cuộc dò quét này.