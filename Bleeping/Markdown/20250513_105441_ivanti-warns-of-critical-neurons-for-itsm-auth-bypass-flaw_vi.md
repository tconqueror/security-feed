# Ivanti cảnh báo về lỗ hổng vượt qua xác thực nghiêm trọng tại Neurons for ITSM

![Ivanti](https://www.bleepstatic.com/content/hl-images/2023/12/20/Ivanti.jpg)

Ivanti đã phát hành các bản cập nhật bảo mật cho giải pháp quản lý dịch vụ CNTT Neurons for ITSM của họ nhằm giảm thiểu một lỗ hổng vượt qua xác thực nghiêm trọng.

Được theo dõi với mã CVE-2025-22462, lỗ hổng bảo mật này có thể cho phép các kẻ tấn công không xác thực có được quyền truy cập quản trị vào các hệ thống chưa được vá trong các cuộc tấn công có độ phức tạp thấp, tùy thuộc vào cấu hình hệ thống.

Như công ty đã nhấn mạnh trong một thông báo bảo mật được phát hành hôm nay, các tổ chức đã tuân theo hướng dẫn của họ ít bị đe dọa hơn bởi các cuộc tấn công.

"Các khách hàng đã tuân theo [hướng dẫn của Ivanti](https://help.ivanti.com/ht/help/en%5FUS/ISM/2024/ITSM-On-Prem-Help/Content/ConfigDB%5FGuide/Securing-IIS-Website.htm) về việc bảo mật trang web IIS và hạn chế quyền truy cập đến một số địa chỉ IP và tên miền hạn chế có nguy cơ thấp hơn cho môi trường của họ," [Ivanti cho biết](https://forums.ivanti.com/s/article/Security-Advisory-Ivanti-Neurons-for-ITSM-on-premises-only-CVE-2025-22462?language=en%5FUS).

"Các khách hàng có người dùng đăng nhập vào giải pháp từ bên ngoài mạng công ty của họ cũng có nguy cơ thấp hơn cho môi trường của họ nếu họ đảm bảo rằng giải pháp [được cấu hình với DMZ.](https://help.ivanti.com/ht/help/en%5FUS/ISM/2024/ITSM-On-Prem-Help/Content/Install%5FDeploy%5Fguide/Deployment%5FEnter%5FProd%5FSecure.htm)"

Ivanti đã thêm rằng CVE-2025-22462 chỉ ảnh hưởng đến các phiên bản tại chỗ đang chạy các phiên bản 2023.4, 2024.2, 2024.3 và các phiên bản trước đó, và nói rằng họ không tìm thấy bằng chứng cho thấy lỗ hổng này đang được khai thác để nhắm mục tiêu vào khách hàng.

| **Tên sản phẩm**                       | **Phiên bản bị ảnh hưởng**    | **Phiên bản đã được khắc phục**                                                                      |
| -------------------------------------- | -------------------------- | -------------------------------------------------------------------------------------------- |
| Ivanti Neurons for ITSM (chỉ tại chỗ) | 2023.4, 2024.2 và 2024.3 | Bản vá bảo mật tháng 5 năm 2025 cho 2023.4, Bản vá bảo mật tháng 5 năm 2025 cho 2024.2, Bản vá bảo mật tháng 5 năm 2025 cho 2024.3 |

Công ty cũng đã khuyến cáo khách hàng ngày hôm nay vá một lỗ hổng bảo mật nhắm đến thông tin đăng nhập mặc định (CVE-2025-22460) trong Cloud Services Appliance (CSA) của họ, có thể cho phép các kẻ tấn công xác thực tại chỗ nâng cao quyền hạn trên các hệ thống dễ bị tổn thương.

Trong khi lỗ hổng này cũng không bị khai thác trực tiếp, Ivanti đã cảnh báo rằng bản vá sẽ không được áp dụng đúng cách sau khi cài đặt các bản cập nhật bảo mật hôm nay và yêu cầu các quản trị viên cài đặt lại từ đầu hoặc sử dụng [các bước giảm thiểu này](https://forums.ivanti.com/s/article/Securing-the-Ivanti-Cloud-Services-Application-CSA-Against-CVE-2025-22460?ui-force-components-controllers-recordGlobalValueProvider.RecordGvp.getRecord=1) để đảm bảo mạng của họ được bảo vệ khỏi các cuộc tấn công tiềm ẩn.

"Đã xác định rằng nếu một cài đặt Cloud Services Application được nâng cấp lên phiên bản 5.0.5, bản sửa lỗi này sẽ không được áp dụng tự động như dự kiến. Điều này sẽ được giải quyết trong một bản phát hành tương lai," Ivanti cho biết.

Tháng trước, công ty cũng đã [vá một lỗ hổng zero-day Connect Secure nghiêm trọng](https://www.bleepingcomputer.com/news/security/ivanti-patches-connect-secure-zero-day-exploited-since-mid-march/) bị nhóm gián điệp UNC5221 liên kết với Trung Quốc khai thác trong các cuộc tấn công thực thi mã từ xa để triển khai malware từ ít nhất giữa tháng Ba năm 2025.

Như CISA và FBI đã cảnh báo vào tháng Giêng, các đối tượng tấn công vẫn tiếp tục khai thác [các lỗ hổng bảo mật của Ivanti Cloud Service Appliances (CSA)](https://www.bleepingcomputer.com/news/security/cisa-hackers-still-exploiting-older-ivanti-bugs-to-breach-networks/) đã được vá từ tháng Chín để xâm nhập vào các mạng dễ bị tổn thương.

Trong năm qua, nhiều lỗ hổng bảo mật khác của Ivanti đã bị [khai thác](https://www.bleepingcomputer.com/news/security/ivanti-connect-secure-zero-days-now-under-mass-exploitation/) trong các cuộc tấn công zero-day [nhắm đến](https://www.bleepingcomputer.com/news/security/newest-ivanti-ssrf-zero-day-now-under-mass-exploitation/) các [thiết bị VPN](https://www.bleepingcomputer.com/news/security/ivanti-warns-of-connect-secure-zero-days-exploited-in-attacks/) của công ty và các [cổng ICS, IPS và ZTA](https://www.bleepingcomputer.com/news/security/ivanti-warns-of-new-connect-secure-zero-day-exploited-in-attacks/).