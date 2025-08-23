# ASUS phát hành bản sửa lỗi cho lỗi AMI cho phép tin tặc làm hỏng máy chủ

![ASUS](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

ASUS đã phát hành các bản cập nhật bảo mật để khắc phục CVE-2024-54085, một lỗi cực kỳ nghiêm trọng có thể cho phép các kẻ tấn công chiếm quyền điều khiển và có thể làm hỏng các máy chủ.

Lỗi này ảnh hưởng đến phần mềm MegaRAC Baseboard Management Controller (BMC) của American Megatrends International, được sử dụng bởi hơn một tá nhà cung cấp phần cứng máy chủ, trong đó có HPE, ASUS và ASRock.

Lỗi [CVE-2024-54085](https://nvd.nist.gov/vuln/detail/CVE-2024-54085) có thể bị khai thác từ xa, có khả năng dẫn đến nhiễm mã độc, sửa đổi firmware và thiệt hại vật lý không thể khôi phục do quá điện.

"Một kẻ tấn công nội bộ hoặc từ xa có thể khai thác lỗ hổng bằng cách truy cập vào các giao diện quản lý từ xa (Redfish) hoặc máy chủ nội bộ đến giao diện BMC (Redfish)," [giải thích Eclypsium trong một báo cáo liên quan](https://www.bleepingcomputer.com/news/security/critical-ami-megarac-bug-can-let-attackers-hijack-brick-servers/).

"Khai thác lỗ hổng này cho phép kẻ tấn công điều khiển từ xa máy chủ bị xâm phạm, triển khai mã độc, ransomware, làm hỏng firmware, làm hỏng các linh kiện trên bo mạch chủ (BMC hoặc có thể là BIOS/UEFI), gây hại vật lý cho máy chủ (quá điện / làm hỏng), và các vòng lặp khởi động không hồi kết mà nạn nhân không thể dừng lại."

Mặc dù AMI đã [phát hành một thông cáo](https://go.ami.com/hubfs/Security%20Advisories/2025/AMI-SA-2025003.pdf) cùng với các bản sửa lỗi vào ngày 11 tháng 3 năm 2025, thời gian cần thiết cho các OEM bị ảnh hưởng để thực hiện các bản sửa lỗi trên sản phẩm của họ.

Hôm nay, ASUS đã thông báo rằng họ đã phát hành các bản sửa lỗi cho CVE-2024-54085 cho bốn mẫu bo mạch chủ bị ảnh hưởng bởi lỗi này.

Các bản cập nhật và phiên bản firmware BMC được khuyến nghị mà người dùng nên nâng cấp là:

* **PRO WS W790E-SAGE SE** – phiên bản 1.1.57 ([tải xuống từ đây](https://www.asus.com/motherboards-components/motherboards/workstation/pro-ws-w790e-sage-se/helpdesk%5Fbios?model2Name=Pro-WS-W790E-SAGE-SE))
* **PRO WS W680M-ACE SE** – phiên bản 1.1.21([tải xuống từ đây](https://www.asus.com/motherboards-components/motherboards/workstation/pro-ws-w680m-ace-se/helpdesk%5Fbios?model2Name=Pro-WS-W680M-ACE-SE))
* **PRO WS WRX90E-SAGE SE** – phiên bản 2.1.28 ([tải xuống từ đây](https://www.asus.com/motherboards-components/motherboards/workstation/pro-ws-wrx90e-sage-se/helpdesk%5Fbios?model2Name=Pro-WS-WRX90E-SAGE-SE))
* **Pro WS WRX80E-SAGE SE WIFI** – phiên bản 1.34.0 ([tải xuống từ đây](https://www.asus.com/motherboards-components/motherboards/workstation/pro-ws-wrx80e-sage-se-wifi/helpdesk%5Fbios?model2Name=Pro-WS-WRX80E-SAGE-SE-WIFI))

Với mức độ nghiêm trọng của lỗ hổng và khả năng khai thác từ xa, việc thực hiện cập nhật firmware là rất quan trọng và nên thực hiện ngay lập tức.

Sau khi tải xuống bản cập nhật firmware BMC mới nhất (.ima file), bạn có thể áp dụng nó thông qua giao diện web > Bảo trì > Cập nhật Firmware, chọn tệp và nhấn 'Bắt đầu Cập nhật Firmware.' Cũng khuyến nghị bạn nên kiểm tra tùy chọn 'Full Flash'.

Để có hướng dẫn chi tiết về cách thực hiện cập nhật firmware MBC một cách an toàn và khắc phục sự cố, [kiểm tra FAQ của ASUS tại đây](https://www.asus.com/support/faq/1047906/).