# Phần mềm theo dõi nhân viên Kickidler bị lạm dụng trong các cuộc tấn công ransomware

![Hacker](https://www.bleepstatic.com/content/hl-images/2022/10/09/hacker-looking-at-screens.jpg)

Các hoạt động ransomware đang sử dụng phần mềm theo dõi nhân viên hợp pháp Kickidler để thực hiện nghiên cứu, theo dõi hoạt động của nạn nhân, và thu thập thông tin đăng nhập sau khi xâm nhập vào mạng của họ.

Trong các cuộc tấn công được quan sát bởi các công ty an ninh mạng [Varonis](https://www.varonis.com/blog/seo-poisoning#initial-access-and-persistence) và [Synacktiv](https://www.synacktiv.com/en/publications/case-study-how-hunters-international-and-friends-target-your-hypervisors), các đối tác ransomware Qilin và Hunters International đã cài đặt Kickidler, một [công cụ theo dõi nhân viên](http://www.kickidler.com/for-it/docs/grabber/) có thể ghi lại thao tác bàn phím, chụp ảnh màn hình, và tạo video màn hình.

Nhà phát triển của Kickidler cho biết công cụ này đang được sử dụng bởi hơn 5,000 tổ chức từ 60 quốc gia và cung cấp các tính năng theo dõi hình ảnh và phòng ngừa mất dữ liệu.

Các cuộc tấn công bắt đầu khi các tác nhân đe dọa sử dụng quảng cáo Google hiển thị khi mọi người tìm kiếm RVTools, một tiện ích Windows miễn phí để quản lý các triển khai VMware vSphere. Nhấp vào quảng cáo dẫn đến một trang web RVTools giả mạo (rv-tool\[.\]net), quảng bá một phiên bản chương trình bị trojan hóa.

Chương trình này là một trình tải malware tải về và chạy backdoor SMOKEDHAM PowerShell .NET, đã được sử dụng để triển khai Kickidler trên thiết bị.

![Attack flow](https://www.bleepstatic.com/images/news/u/1109292/2025/Attack-flow(1).jpg)

_Dòng tấn công (Varonis)_

Khi các cuộc tấn công này nhắm vào các quản trị viên doanh nghiệp, mà tài khoản của họ thường cung cấp cho các tác nhân đe dọa quyền truy cập đặc quyền sau khi bị xâm nhập, Varonis tin rằng họ có thể đã duy trì quyền truy cập vào hệ thống của nạn nhân trong nhiều ngày và thậm chí nhiều tuần để thu thập thông tin đăng nhập cần thiết để truy cập các bản sao lưu đám mây ngoài site mà không bị phát hiện.

"Trước tình trạng gia tăng việc nhắm mục tiêu các giải pháp sao lưu của các kẻ tấn công trong những năm gần đây, những người bảo vệ đang tách biệt xác thực hệ thống sao lưu khỏi các miền Windows. Biện pháp này ngăn cản kẻ tấn công truy cập vào các bản sao lưu ngay cả khi họ có được thông tin đăng nhập Windows cấp cao," Varonis đã nói với BleepingComputer.

"Kickidler giải quyết vấn đề này bằng cách ghi lại các thao tác bàn phím và các trang web từ máy trạm của quản trị viên. Điều này cho phép kẻ tấn công xác định các bản sao lưu đám mây ngoài site và lấy được các mật khẩu cần thiết để truy cập chúng. Điều này được thực hiện mà không cần lấy bộ nhớ hay các chiến thuật rủi ro cao khác mà có khả năng bị phát hiện nhiều hơn."

Trong cả hai trường hợp, sau khi tiếp tục các hoạt động độc hại trên các mạng bị xâm nhập, các nhà điều hành ransomware đã triển khai các payload nhắm vào hạ tầng VMware ESXi của nạn nhân, mã hóa các ổ đĩa cứng ảo VMDK và gây ra sự gián đoạn rộng rãi.

Kịch bản triển khai do Hunters International sử dụng đã tận dụng VMware PowerCLI và tự động hóa WinSCP để kích hoạt dịch vụ SSH, triển khai ransomware và thực hiện nó trên các máy chủ ESXi, Synacktiv cho biết.

## **Phần mềm RMM hợp pháp bị lạm dụng trong các cuộc tấn công**

Mặc dù phần mềm theo dõi nhân viên không phải là công cụ ưa thích của các băng nhóm ransomware, họ đã lạm dụng phần mềm giám sát và quản lý từ xa (RMM) hợp pháp trong nhiều năm.

Như CISA, NSA và MS-ISAC đã cảnh báo trong một [thông báo chung vào tháng 1 năm 2023](https://www.bleepingcomputer.com/news/security/cisa-federal-agencies-hacked-using-legitimate-remote-desktop-tools/), các kẻ tấn công trong nhiều hoạt động ransomware đã lừa nạn nhân cài đặt các giải pháp máy tính để bàn từ xa di động để vượt qua các kiểm soát phần mềm và chiếm quyền kiểm soát hệ thống của họ mà không cần quyền truy cập quản trị.

Kể từ giữa tháng 10 năm 2022, CISA cũng đã phát hiện hoạt động độc hại trong các mạng của nhiều [cơ quan hành chính dân sự liên bang](https://www.cisa.gov/agencies) (FCEB) có liên quan đến loại tấn công này.

Gần đây, các kẻ tấn công đã được thấy [nhắm vào các khách hàng RMM SimpleHelp dễ bị tổn thương](https://www.bleepingcomputer.com/news/security/hackers-exploit-simplehelp-rmm-flaws-to-deploy-sliver-malware/) để tạo tài khoản quản trị, cài đặt backdoor và có khả năng tạo điều kiện cho các cuộc tấn công ransomware Akira.

Để phòng ngừa các vi phạm bảo mật tiềm ẩn, các nhân viên mạng được khuyên nên kiểm tra các công cụ truy cập từ xa đã cài đặt và xác định phần mềm RMM được ủy quyền.

Cũng nên sử dụng các biện pháp kiểm soát ứng dụng để ngăn chặn việc thực thi phần mềm RMM không được phép và thực thi việc chỉ sử dụng các công cụ máy tính từ xa được ủy quyền, cùng với các giải pháp truy cập từ xa được phê duyệt như VPN hoặc VDI.

Ngoài ra, các nhóm bảo mật nên chặn các kết nối vào và ra trên các cổng và giao thức RMM tiêu chuẩn nếu không sử dụng.