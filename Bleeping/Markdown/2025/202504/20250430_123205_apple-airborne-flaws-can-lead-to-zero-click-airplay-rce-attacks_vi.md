# Các lỗ hổng 'AirBorne' của Apple có thể dẫn đến các cuộc tấn công RCE AirPlay không cần nhấp chuột

![Apple](https://www.bleepstatic.com/content/hl-images/2022/12/19/Apple.jpg)

Một loạt lỗ hổng bảo mật trong Giao thức AirPlay của Apple và Bộ phát triển phần mềm AirPlay (SDK) đã làm lộ các thiết bị của bên thứ ba và Apple không được vá lỗi ra trước các cuộc tấn công khác nhau, bao gồm việc thực thi mã từ xa.

Theo các nhà nghiên cứu bảo mật của công ty Oligo Security, những người đã phát hiện và báo cáo các lỗ hổng này, chúng có thể bị khai thác trong các cuộc tấn công RCE không cần nhấp chuột và RCE một cú nhấp chuột, các cuộc tấn công man-in-the-middle (MITM), và các cuộc tấn công từ chối dịch vụ (DoS), cũng như để vượt qua danh sách kiểm soát truy cập (ACL) và tương tác của người dùng, nhằm truy cập thông tin nhạy cảm và đọc các tệp cục bộ tùy ý.

Tổng cộng, Oligo đã công bố 23 lỗ hổng bảo mật tới Apple, công ty này đã phát hành các bản cập nhật bảo mật để giải quyết các lỗ hổng này (tổng thể được gọi là "AirBorne") vào ngày 31 tháng 3 cho iPhones và iPads ([iOS 18.4 và iPadOS 18.4](https://support.apple.com/en-us/122371)), Macs ([macOS Ventura 13.7.5](https://support.apple.com/en-us/122375), [macOS Sonoma 14.7.5](https://support.apple.com/en-us/122374), và [macOS Sequoia 15.4](https://support.apple.com/en-us/122373)), và thiết bị Apple Vision Pro ([visionOS 2.4](https://support.apple.com/en-us/122378)).

Công ty cũng đã vá [AirPlay audio SDK](https://support.apple.com/en-us/122403), [AirPlay video SDK](https://support.apple.com/en-us/122403), và [CarPlay Communication Plug-in](https://support.apple.com/en-us/122403).

Trong khi các lỗ hổng AirBorne chỉ có thể bị khai thác bởi các kẻ tấn công trên cùng một mạng thông qua mạng không dây hoặc kết nối ngang hàng, chúng cho phép kiểm soát các thiết bị dễ bị tổn thương và sử dụng quyền truy cập này như một nền tảng để tấn công các thiết bị khác hỗ trợ AirPlay trên cùng một mạng.

Các nhà nghiên cứu bảo mật của Oligo cho biết họ đã có thể chứng minh rằng kẻ tấn công có thể sử dụng hai trong số các lỗ hổng bảo mật (CVE-2025-24252 và CVE-2025-24132) để tạo ra các cuộc tấn công RCE không cần nhấp chuột có khả năng phát tán như sâu.

Ngoài ra, lỗ hổng vượt qua tương tác người dùng CVE-2025-24206 cho phép một tác nhân mối đe dọa vượt qua yêu cầu "Nhấp đồng ý" trên các yêu cầu AirPlay và có thể được kết nối với các lỗ hổng khác để khởi động các cuộc tấn công không cần nhấp chuột.

"Điều này có nghĩa là một kẻ tấn công có thể kiểm soát một số thiết bị hỗ trợ AirPlay và thực hiện những việc như triển khai malware mà lan truyền đến các thiết bị trên bất kỳ mạng cục bộ nào mà thiết bị nhiễm kết nối. Điều này có thể dẫn đến việc giao hàng các cuộc tấn công tinh vi khác liên quan đến gián điệp, ransomware, tấn công chuỗi cung ứng, và nhiều hơn nữa," [Oligo cảnh báo](https://www.oligo.security/blog/airborne).

"Bởi vì AirPlay là một phần mềm cơ bản cho các thiết bị Apple (Mac, iPhone, iPad, AppleTV, v.v.) cũng như các thiết bị bên thứ ba tận dụng SDK AirPlay, loại lỗ hổng này có thể có tác động sâu rộng."

Công ty an ninh mạng khuyên các tổ chức nên ngay lập tức cập nhật bất kỳ thiết bị Apple và thiết bị hỗ trợ AirPlay nào của công ty lên phiên bản phần mềm mới nhất và yêu cầu nhân viên cũng cập nhật tất cả các thiết bị AirPlay cá nhân của họ.

Các biện pháp bổ sung mà người dùng có thể thực hiện để giảm bề mặt tấn công bao gồm cập nhật tất cả các thiết bị Apple lên phiên bản mới nhất, vô hiệu hóa bộ thu AirPlay nếu không sử dụng, hạn chế quyền truy cập AirPlay cho các thiết bị đáng tin cậy bằng cách sử dụng quy tắc tường lửa, và giảm bề mặt tấn công bằng cách chỉ cho phép AirPlay cho người dùng hiện tại.

Apple cho biết có [hơn 2.35 tỷ thiết bị Apple đang hoạt động](https://security.apple.com/) trên toàn cầu (bao gồm iPhones, iPads, Macs và các thiết bị khác), và Oligo ước tính rằng cũng có hàng triệu thiết bị âm thanh bên thứ ba như loa và TV có hỗ trợ AirPlay, chưa bao gồm các hệ thống thông tin giải trí trong ô tô với hỗ trợ CarPlay.