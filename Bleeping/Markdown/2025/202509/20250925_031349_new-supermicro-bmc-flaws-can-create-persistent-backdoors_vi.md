# Lỗ hổng BMC mới của Supermicro có thể tạo backdoor tồn tại lâu dài

![Lỗ hổng BMC mới của Supermicro có thể tạo backdoor tồn tại lâu dài](https://www.bleepstatic.com/content/hl-images/2023/12/18/warning.jpg)

Hai lỗ hổng ảnh hưởng tới firmware của phần cứng Supermicro, bao gồm Baseboard Management Controller (BMC), cho phép kẻ tấn công cập nhật hệ thống bằng các image được chế tạo độc hại.

Supermicro là nhà sản xuất server, motherboard và phần cứng cho trung tâm dữ liệu. BMC là một vi điều khiển trên các bo mạch chủ server Supermicro cho phép giám sát và quản lý hệ thống từ xa ngay cả khi hệ thống đã tắt nguồn.

Các chuyên gia tại công ty bảo mật firmware Binarly đã phát hiện một phương thức vượt qua cho một lỗi ([CVE-2024-10237](https://nvd.nist.gov/vuln/detail/CVE-2024-10237)) mà Supermicro đã vá vào tháng Giêng năm nay cùng với một lỗ hổng khác được xác định là CVE-2025-6198.

"Vấn đề an ninh này có thể cho phép kẻ tấn công tiềm năng giành quyền kiểm soát hoàn toàn và tồn tại lâu dài cả hệ thống BMC lẫn OS chính của server," các nhà nghiên cứu của Binarly cho biết.

Cả hai vấn đề an ninh đều có thể được dùng để cập nhật hệ thống BMC bằng firmware không chính thức, nhưng các nhà nghiên cứu cho biết CVE-2025-6198 còn có thể bị khai thác để vượt qua BMC RoT (Root of Trust) — một tính năng bảo mật xác thực rằng hệ thống đang khởi động bằng firmware hợp lệ.

Cấy ghép firmware độc hại cho phép duy trì tồn tại sau khi khởi động lại và cài đặt lại OS, kiểm soát mức cao đối với server, và bỏ qua đáng tin cậy các kiểm tra bảo mật.

Để sửa CVE-2024-10237, Supermicro [đã thêm các kiểm tra](https://www.supermicro.com/en/support/security%5FBMC%5FIPMI%5FJan%5F2025) nhằm hạn chế các mục _fwmap_ tùy chỉnh, đây là một bảng hướng dẫn bên trong image firmware có thể bị lợi dụng để thao túng image firmware.

![The signature validation process](https://www.bleepstatic.com/images/news/u/1220909/2025/September/validation%20process.jpg)

**Quy trình xác thực chữ ký**  
_Nguồn: Binarly_

Tuy nhiên, các nhà nghiên cứu của Binarly [phát hiện](https://www.binarly.io/blog/broken-trust-fixed-supermicro-bmc-bug-gains-a-new-life-in-two-new-vulnerabilities) rằng vẫn có thể tiêm một _fwmap_ độc hại trước khi mục gốc của nhà cung cấp được hệ thống tải, khai báo các vùng đã được ký theo cách cho phép kẻ tấn công dịch chuyển hoặc thay thế nội dung thực tế trong khi vẫn giữ được digest nhất quán.

Điều này có nghĩa là băm được tính bằng cách khác nhưng bằng giá trị đã ký và việc xác minh chữ ký thành công, ngay cả khi các phần trong image firmware đã bị tráo đổi hoặc thay thế.

![Bypassing the check](https://www.bleepstatic.com/images/news/u/1220909/2025/September/signed-regions.jpg)

**Vượt qua kiểm tra**  
_Nguồn: Binarly_

Kết quả là BMC chấp nhận và flash image, đưa vào một bootloader hoặc kernel có thể độc hại, trong khi mọi thứ vẫn trông có vẻ đã được ký và hợp lệ.

Các nhà nghiên cứu đã báo cáo vấn đề này cho Supermicro. Công ty xác nhận lỗ hổng, hiện được xác định là [CVE-2025-7937](https://nvd.nist.gov/vuln/detail/CVE-2025-7937).

Lỗi thứ hai mà Binarly phát hiện, CVE-2025-6198, phát sinh từ logic xác thực sai trong hàm _auth_bmc_sig_, được thực thi trong môi trường OP-TEE của firmware bo mạch X13SEM-F.

Vì các vùng đã ký được xác định trong chính image được tải lên, kẻ tấn công có thể sửa kernel hoặc các vùng khác và dịch chuyển dữ liệu gốc đến không gian firmware chưa dùng, giữ cho digest vẫn hợp lệ.

Các nhà nghiên cứu đã trình diễn việc flash và thực thi một kernel tùy chỉnh, chứng minh rằng xác thực kernel không được thực hiện trong quá trình khởi động, đồng nghĩa với việc tính năng Root of Trust chỉ bảo vệ một phần của quy trình.

**Tiêm firmware BMC tùy chỉnh**  
_Nguồn: Binarly_

Khai thác lỗ hổng đạt được cùng kết quả như việc vượt qua, cho phép tiêm firmware độc hại hoặc hạ cấp image hiện có xuống phiên bản kém an toàn hơn.

Supermicro đã phát hành các [bản sửa firmware](http://www.supermicro.com/en/support/security%5FBMC%5FIPMI%5FSept%5F2025) cho các mẫu bị ảnh hưởng. Binarly đã phát hành proof-of-concept [exploits cho cả hai vấn đề](https://github.com/binarly-io/Research-Data/blob/main/Blogs/The%20Broken%20Trust%3A%20Fixed%20Supermicro%20BMC%20Bug%20Gains%20a%20New%20Life%20in%20Two%20New%20Vulnerabilities/Images/X13SEM-F%5FCVE-2025-6198%5FPOC.bin), vì vậy cần hành động nhanh để bảo vệ các hệ thống có khả năng bị ảnh hưởng.

Lỗ hổng firmware BMC có tính dai dẳng và có thể đặc biệt nguy hiểm, trong một số trường hợp gây [mass-bricking of servers](https://www.bleepingcomputer.com/news/security/critical-ami-megarac-bugs-can-let-hackers-brick-vulnerable-servers/). Những vấn đề này cũng không phải lý thuyết khi CISA trước đây đã [cảnh báo về việc khai thác](https://www.bleepingcomputer.com/news/security/cisa-ami-megarac-bug-that-lets-hackers-brick-servers-now-actively-exploited/) các lỗi như vậy ngoài thực tế.