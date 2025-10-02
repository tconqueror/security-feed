# DrayTek cảnh báo lỗ hổng thực thi mã từ xa trong bộ định tuyến Vigor

![DrayTek cảnh báo lỗ hổng thực thi mã từ xa trong bộ định tuyến Vigor](https://www.bleepstatic.com/content/hl-images/2025/10/02/draytek.jpg)

Nhà sản xuất phần cứng mạng DrayTek đã phát hành một khuyến cáo cảnh báo về một lỗ hổng bảo mật trong một số mẫu bộ định tuyến Vigor có thể cho phép tác nhân từ xa chưa xác thực thực thi mã tùy ý.

Lỗ hổng, được theo dõi với mã CVE-2025-10547, đã được báo cho nhà cung cấp vào ngày 22 tháng 7 bởi nhà nghiên cứu bảo mật ChapsVision Pierre-Yves Maes.

"Vấn đề có thể bị kích hoạt khi các kẻ tấn công từ xa chưa xác thực gửi các yêu cầu HTTP hoặc HTTPS được chế tạo đặc biệt tới Giao diện Web Người dùng của thiết bị (WebUI)," [theo thông báo bảo mật của DrayTek](https://www.draytek.com/about/security-advisory/use-of-uninitialized-variable-vulnerabilities).

"Khai thác thành công có thể gây ra hỏng bộ nhớ và làm sập hệ thống, với khả năng trong một số trường hợp có thể cho phép thực thi mã từ xa."

DrayTek lưu ý rằng việc phơi bày trên WAN có thể giảm bằng cách vô hiệu hóa truy cập WebUI/SSL VPN từ xa hoặc giới hạn nó bằng ACLs/VLANs. Tuy nhiên, WebUI vẫn có thể truy cập được qua LAN, khiến thiết bị bị phơi bày trước các kẻ tấn công nội bộ.

Maes nói với BleepingComputer rằng nguyên nhân gốc rễ của CVE-2025-10547 là một giá trị ngăn xếp chưa được khởi tạo có thể lợi dụng để khiến hàm _free()_ hoạt động trên các vị trí bộ nhớ tùy ý, còn được gọi là _arbitrary free()_, nhằm đạt được thực thi mã từ xa (RCE).

Nhà nghiên cứu đã kiểm thử thành công phát hiện của mình bằng cách tạo một khai thác và chạy nó trên các thiết bị DrayTek.

Bản tin bảo mật của DrayTek không đề cập đến việc khai thác đang diễn ra, nhưng khuyến nghị nên giảm thiểu rủi ro.

Dưới đây là các mẫu bị ảnh hưởng bởi CVE-2025-10547, và phiên bản firmware được khuyến nghị nâng cấp để giảm thiểu lỗ hổng:

* Vigor1000B, Vigor2962, Vigor3910/3912 → 4.4.3.6 or later (some models 4.4.5.1)
* Vigor2135, Vigor2763/2765/2766, Vigor2865/2866 Series (incl. LTE & 5G), Vigor2927 Series (incl. LTE & 5G) → 4.5.1 or later
* Vigor2915 Series → 4.4.6.1 or later
* Vigor2862/2926 Series (incl. LTE) → 3.9.9.12 or later
* Vigor2952/2952P, Vigor3220 → 3.9.8.8 or later
* Vigor2860/2925 Series (incl. LTE) → 3.9.8.6 or later
* Vigor2133/2762/2832 Series → 3.9.9.4 or later
* Vigor2620 Series → 3.9.9.5 or later
* VigorLTE 200n → 3.9.9.3 or later

Các bộ định tuyến DrayTek, đặc biệt là các mẫu Vigor, rất phổ biến trong môi trường prosumer và doanh nghiệp nhỏ đến vừa (SMB). Danh sách các mẫu bị ảnh hưởng bao phủ một phạm vi rộng, từ các mẫu hàng đầu đến các bộ định tuyến cũ hơn được sử dụng trong môi trường DLS/viễn thông.

Các quản trị viên hệ thống được khuyến nghị áp dụng các bản cập nhật firmware bảo mật có sẵn càng sớm càng tốt. Maes cho biết ông sẽ tiết lộ toàn bộ chi tiết kỹ thuật cho CVE-2025-10547 vào ngày mai.