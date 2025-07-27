+ 
# Scattered Spider đang triển khai cuộc tấn công VMware ESXi

![Scattered Spider đang triển khai cuộc tấn công VMware ESXi](https://www.bleepstatic.com/content/hl-images/2024/11/25/ghost-spider-center.jpg)

Các hacker Scattered Spider đã tấn công mạnh mẽ các môi trường ảo hóa bằng cách tấn công các hypervisor VMware ESXi tại các công ty ở Mỹ trong các lĩnh vực bán lẻ, hàng không, vận tải và bảo hiểm.

Theo Nhóm Tình báo Đe dọa của Google (GITG), những kẻ tấn công tiếp tục sử dụng các chiến thuật thông thường của họ mà không bao gồm việc khai thác lỗ hổng mà dựa vào kỹ thuật social engineering được thực hiện hoàn hảo "để vượt qua ngay cả những chương trình bảo mật trưởng thành."

### Một cuộc tấn công của Scattered Spider

Các nhà nghiên cứu cho biết rằng băng nhóm bắt đầu một cuộc tấn công bằng cách giả mạo một nhân viên trong một cuộc gọi tới bàn trợ giúp IT. Mục đích của kẻ đe dọa là thuyết phục đại lý thay đổi mật khẩu Active Directory của nhân viên và do đó取得 quyền truy cập ban đầu.

Điều này cho phép Scattered Spider quét các thiết bị mạng để tìm kiếm tài liệu CNTT có thể cung cấp các mục tiêu có giá trị cao, như tên của các quản trị viên miền hoặc VMware vSphere, và các nhóm bảo mật có thể cung cấp quyền quản trị đối với môi trường ảo.

Đồng thời, họ quét các giải pháp quản lý quyền truy cập đặc quyền (PAM) có thể giữ dữ liệu nhạy cảm hữu ích cho việc di chuyển đến các tài sản mạng có giá trị.

"Vũ trang với tên một quản trị viên cụ thể, có giá trị cao, họ thực hiện thêm các cuộc gọi tới bàn trợ giúp. Lần này, họ giả mạo người dùng đặc quyền và yêu cầu thiết lập lại mật khẩu, cho phép họ kiểm soát một tài khoản đặc quyền" - [Nhóm Tình báo Đe dọa của Google](https://cloud.google.com/blog/topics/threat-intelligence/defending-vsphere-from-unc3944)

Sau đó, các hacker làm việc theo cách của họ để đạt được quyền truy cập vào Bộ phận Máy chủ vCenter VMware (vCSA) của công ty - một máy ảo cho phép quản lý các môi trường VMware vSphere, bao gồm hypervisor ESXi để quản lý tất cả các máy ảo trên một máy chủ vật lý.

Cấp độ truy cập này cho phép họ bật các kết nối SSH trên các máy chủ ESXi và đặt lại mật khẩu root. Hơn nữa, họ thực hiện một cuộc tấn công gọi là “disk-swap” để trích xuất cơ sở dữ liệu quan trọng NTDS.dit cho Active Directory.

Một cuộc tấn công disk-swap xảy ra khi các kẻ tấn công tắt một máy chủ miền ảo (VM) và tách đĩa ảo của nó chỉ để gắn nó vào một VM khác không được giám sát mà họ kiểm soát. Sau khi sao chép dữ liệu nhạy cảm (ví dụ: tệp NTDS.dit), họ hoàn tác quy trình và bật máy chủ miền.

Điều quan trọng cần lưu ý là cấp độ kiểm soát mà Scattered Spider đạt được trên cơ sở hạ tầng ảo cho phép họ quản lý mọi tài sản có sẵn, bao gồm cả các máy sao lưu, mà bị xóa toàn bộ các công việc sao lưu, snapshots và repository.

Trong giai đoạn cuối của cuộc tấn công, Scattered Spider tận dụng quyền truy cập SSH của họ để phân phối và triển khai các nhị phân ransomware để mã hóa tất cả các tệp VM được phát hiện trong các kho dữ liệu.

Dựa trên quan sát của họ, các nhà nghiên cứu GTIG cho biết cuộc tấn công của Scattered Spider có năm giai đoạn rõ ràng cho phép hacker di chuyển từ quyền truy cập cấp thấp đến việc hoàn toàn kiểm soát hypervisor.

![Chuỗi tấn công Scattered Spider](https://www.bleepstatic.com/images/news/u/1220909/2025/July/attack-chain.jpg)

**Chuỗi tấn công Scattered Spider**  
_Nguồn: Google_

Một chuỗi tấn công của Scattered Spider, hoàn chỉnh từ quyền truy cập ban đầu đến việc xóa dữ liệu và triển khai ransomware, có thể xảy ra chỉ trong vài giờ.

Ngay cả khi không khai thác bất kỳ lỗ hổng phần mềm nào, kẻ đe dọa vẫn quản lý để đạt được “một cấp độ kiểm soát chưa từng có đối với toàn bộ môi trường ảo hóa, cho phép họ vượt qua nhiều biện pháp bảo mật truyền thống,” một đại diện của Google đã nói với BleepingComputer.

Trong khi việc nhắm mục tiêu các hypervisor ESXi không phải là mới (được thấy trong các vụ vi phạm nổi tiếng của Scattered Spider như vụ [tấn công MGM Resorts năm 2023](https://www.bleepingcomputer.com/news/security/mgm-casinos-esxi-servers-allegedly-encrypted-in-ransomware-attack/)) GITG lưu ý rằng họ đang thấy nhiều nhóm ransomware hơn áp dụng chiến thuật này và mong rằng vấn đề sẽ gia tăng.

Một lý do phía sau điều này có thể là những kẻ kẻ thù đã nhận ra rằng hạ tầng VMware thường bị tổ chức hiểu lầm và do đó, không được phòng thủ mạnh mẽ.

Để giúp các tổ chức bảo vệ chống lại những cuộc tấn công này, Google đã [công bố một bài viết kỹ thuật](https://cloud.google.com/blog/topics/threat-intelligence/defending-vsphere-from-unc3944) mô tả các giai đoạn của một cuộc tấn công Scattered Spider, giải thích lý do tại sao nó hiệu quả và cung cấp các hành động mà một công ty có thể thực hiện để phát hiện sự xâm nhập ở giai đoạn sớm hơn.

Các biện pháp đề xuất có thể được tóm tắt thành ba trụ cột chính:

* Khóa vSphere với execInstalledOnly, mã hóa VM và tắt SSH. Tránh các liên kết AD trực tiếp trên ESXi, xóa các VM không còn sử dụng, và thực thi các chính sách MFA và truy cập nghiêm ngặt. Giám sát liên tục để theo dõi các thay đổi cấu hình.
* Sử dụng MFA chống phishing qua VPN, AD và vCenter. Tách biệt các tài sản Tier 0 (DCs, backups, PAM) và tránh lưu trữ chúng trên cùng một hạ tầng mà chúng bảo vệ. Cân nhắc các IdP đám mây riêng để phá bỏ sự phụ thuộc vào AD.
* Tập trung hóa nhật ký trong một SIEM và cảnh báo về các hành vi quan trọng, chẳng hạn như thay đổi nhóm admin, đăng nhập vCenter và bật SSH. Sử dụng sao lưu không thể thay đổi và được bảo vệ không khí và kiểm tra phục hồi chống lại các cuộc tấn công ở tầng hypervisor.

Scattered Spider (còn được gọi là UNC3944, Octo Tempest, 0ktapus) là một nhóm đe dọa có động cơ tài chính chuyên biệt về social engineering đến mức nó có thể giả mạo nhân viên công ty sử dụng từ ngữ và giọng điệu phù hợp.

Gần đây, nó đã tăng cường hoạt động với các cuộc tấn công vào [các công ty bán lẻ lớn của Vương quốc Anh](https://www.bleepingcomputer.com/news/security/uk-ncsc-cyberattacks-impacting-uk-retailers-are-a-wake-up-call/), [các hãng hàng không và vận tải](https://www.bleepingcomputer.com/news/security/scattered-spider-hackers-shift-focus-to-aviation-transportation-firms/) và [các công ty bảo hiểm](https://www.bleepingcomputer.com/news/security/google-warns-scattered-spider-hackers-now-target-us-insurance-companies/).

Mặc dù Cơ quan Tội phạm Quốc gia Vương quốc Anh [đã bắt giữ bốn thành viên nghi ngờ](https://www.bleepingcomputer.com/news/security/four-arrested-in-uk-over-mands-co-op-harrods-cyberattacks/) của nhóm, nhưng hoạt động độc hại, xuất phát từ các cụm khác, vẫn không giảm bớt.