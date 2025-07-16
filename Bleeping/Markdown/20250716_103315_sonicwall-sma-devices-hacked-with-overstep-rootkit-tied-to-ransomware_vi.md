# Thiết bị SonicWall SMA bị tấn công bằng rootkit OVERSTEP liên quan đến ransomware

![](https://www.bleepstatic.com/content/hl-images/2022/01/24/Sonicwall.jpg)

Một tác nhân đe dọa đã triển khai một loại malware chưa từng thấy gọi là OVERSTEP, loại malware này sửa đổi quy trình khởi động của các thiết bị SonicWall Secure Mobile Access đã được vá hoàn toàn nhưng không còn được hỗ trợ.

Backdoor này là một rootkit ở chế độ người dùng cho phép tin tặc ẩn các thành phần độc hại, duy trì quyền truy cập liên tục trên thiết bị và đánh cắp thông tin xác thực nhạy cảm.

Các nhà nghiên cứu tại Google Threat Intelligence Group (GTIG) đã quan sát rootkit này trong các cuộc tấn công có thể dựa trên "một lỗ hổng thực thi mã từ xa zero-day chưa biết".

Tác nhân đe dọa được theo dõi với tên UNC6148 và đã hoạt động từ ít nhất tháng Mười năm ngoái, với một tổ chức bị nhắm mục tiêu gần đây vào tháng Năm.

Vì các tập tin bị đánh cắp từ nạn nhân sau đó đã được công bố trên trang web rò rỉ dữ liệu World Leaks ([thương hiệu Hunters International](https://www.bleepingcomputer.com/news/security/hunters-international-ransomware-shuts-down-after-world-leaks-rebrand/)), các nhà nghiên cứu GTIG tin rằng UNC6148 tham gia vào các cuộc tấn công đánh cắp dữ liệu và tống tiền, và cũng có thể triển khai ransomware Abyss (được theo dõi với tên VSOCIETY bởi GTIG).

### Tin tặc đã chuẩn bị kỹ lưỡng

Tin tặc đang nhắm vào các thiết bị SonicWall SMA 100 Series đã hết hạn (EoL) cung cấp quyền truy cập từ xa an toàn đến các tài nguyên doanh nghiệp trên mạng cục bộ, trong đám mây hoặc trung tâm dữ liệu kết hợp.

Không rõ tin tặc đã có được quyền truy cập ban đầu như thế nào, nhưng các nhà nghiên cứu điều tra các cuộc tấn công của UNC6148 đã nhận thấy rằng tác nhân đe dọa đã có sẵn thông tin xác thực quản trị viên cục bộ trên thiết bị bị nhắm mục tiêu.

“GTIG đánh giá với độ tự tin cao rằng UNC6148 đã khai thác một lỗ hổng đã biết để đánh cắp thông tin xác thực quản trị viên trước khi thiết bị SMA bị nhắm mục tiêu được cập nhật lên phiên bản firmware mới nhất (10.2.1.15-81sv)” - Nhóm Tình báo Đe dọa Google

Xem xét thông tin metadata của lưu lượng mạng, các điều tra viên đã phát hiện ra bằng chứng cho thấy UNC6148 đã đánh cắp thông tin xác thực cho thiết bị bị nhắm mục tiêu vào tháng Giêng.

Nhiều lỗ hổng n-day ([CVE-2021-20038](https://nvd.nist.gov/vuln/detail/CVE-2021-20038), [CVE-2024-38475](https://nvd.nist.gov/vuln/detail/CVE-2024-38475), [CVE-2021-20035](https://nvd.nist.gov/vuln/detail/CVE-2021-20035), [CVE-2021-20039](https://nvd.nist.gov/vuln/detail/CVE-2021-20039), [CVE-2025-32819](https://nvd.nist.gov/vuln/detail/CVE-2025-32819)) có thể đã bị khai thác nhằm mục đích này, cái cũ nhất được công bố vào năm 2021 và cái mới nhất từ tháng Năm năm 2025.

Trong số đó, tin tặc có thể đã khai thác CVE-2024-38475 vì nó cung cấp “thông tin xác thực quản trị viên cục bộ và các token phiên hợp lệ mà UNC6148 có thể sử dụng lại”.

Tuy nhiên, các nhân viên ứng cứu sự cố tại Mandiant (một công ty của Google) không thể xác nhận rằng kẻ tấn công đã khai thác lỗ hổng này.

### Bí ẩn reverse-shell

Trong một cuộc tấn công vào tháng Sáu, UNC6148 đã sử dụng thông tin xác thực quản trị viên cục bộ để kết nối với thiết bị SMA 100 Series bị nhắm mục tiêu qua một phiên SSL-VPN.

Tin tặc đã bắt đầu một reverse shell, mặc dù quyền truy cập shell lẽ ra không thể xảy ra theo thiết kế trên các thiết bị này.

Nhóm Phản ứng Sự cố An toàn Sản phẩm của SonicWall (PSIRT) đã cố gắng xác định cách mà điều này có thể xảy ra nhưng không đưa ra được lời giải thích, và một câu trả lời có thể là việc khai thác một vấn đề an ninh chưa biết.

Với quyền truy cập shell trên thiết bị, tác nhân đe dọa đã thực hiện các hoạt động thu thập thông tin và thao tác tệp, và nhập các thiết lập bao gồm các quy tắc chính sách kiểm soát truy cập mạng mới để cho phép các địa chỉ IP của hacker.

### Rootkit OVERSTEP không để lại dấu vết

Sau đó, UNC6148 đã triển khai rootkit OVERSTEP thông qua một loạt các lệnh đã giải mã nhị phân từ base64 và cài đặt nó dưới dạng tệp .ELF.

“Sau khi cài đặt, kẻ tấn công đã xóa thủ công các nhật ký hệ thống trước khi khởi động lại thiết bị, kích hoạt backdoor OVERSTEP” - Nhóm Tình báo Đe dọa Google

OVERSTEP hoạt động như một backdoor thiết lập một reverse shell và đánh cắp mật khẩu từ máy chủ. Nó cũng thực hiện các khả năng của rootkit ở chế độ người dùng để giữ cho các thành phần của nó ẩn đi trên máy chủ.

Thành phần rootkit mang đến cho tác nhân đe dọa sự hiện diện lâu dài bằng cách tải và thực thi mã độc mỗi khi một chương trình thực thi động khởi động.

Tính năng chống hình sự của OVERSTEP cho phép kẻ tấn công chọn lọc xóa các mục nhật ký, từ đó che giấu dấu vết của chúng. Tính năng này và việc thiếu lịch sử lệnh trên đĩa đã làm hạn chế tầm nhìn của các nhà nghiên cứu về các hoạt động sau khi xâm nhập của tác nhân đe dọa.

Tuy nhiên, GTIG cảnh báo rằng OVERSTEP có thể đánh cắp các tệp nhạy cảm như cơ sở dữ liệu _persist.db_ và các tệp chứng chỉ, mang lại cho tin tặc quyền truy cập vào thông tin xác thực, hạt giống OTP và chứng chỉ cho phép duy trì hiện diện.

Mặc dù các nhà nghiên cứu không thể xác định mục đích thực sự của các cuộc tấn công của UNC6148, họ nhấn mạnh “các điểm tương đồng đáng chú ý” trong hoạt động của tác nhân đe dọa này và phân tích các sự cố mà ransomware liên quan đến Abyss đã được triển khai.

Vào cuối năm 2023, các nhà nghiên cứu Truesec đã [điều tra](https://www.truesec.com/hub/blog/web-shell-on-a-sonicwall-sma) một sự cố ransomware Abyss xảy ra sau khi tin tặc triển khai một web shell trên một thiết bị SMA, cơ chế ẩn và thiết lập sự hiện diện qua các bản cập nhật firmware.

Vài tháng sau vào tháng Ba năm 2024, người phản ứng sự cố của InfoGuard AG, Stephan Berger, đã [công bố một bài viết](https://dfir.ch/posts/microsocks%5Fsonicwall/) mô tả một sự thỏa hiệp tương tự của một thiết bị SMA kết thúc với việc triển khai cùng một malware Abyss.

Các tổ chức có thiết bị SMA được khuyến nghị kiểm tra các thiết bị để phát hiện tiềm năng bị xâm phạm bằng cách thu thập hình ảnh đĩa, điều này nên ngăn chặn sự can thiệp từ rootkit.

GTIG cung cấp một tập hợp các chỉ số của sự thỏa hiệp cùng với các dấu hiệu mà các nhà phân tích nên tìm kiếm để xác định xem thiết bị có bị tấn công hay không.