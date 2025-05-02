# Mỹ buộc tội quản trị viên ransomware Black Kingdom vì các cuộc tấn công vào Microsoft Exchange

![Black Kingdom](https://www.bleepstatic.com/content/hl-images/2025/05/02/BlackKing.jpg)

Một công dân Yemen 36 tuổi, được cho là nhà phát triển và là điều hành chính của ransomware 'Black Kingdom', đã bị Mỹ buộc tội vì đã thực hiện 1.500 cuộc tấn công vào các máy chủ Microsoft Exchange.

Người nghi vấn, Rami Khaled Ahmed, bị cáo buộc đã triển khai phần mềm độc hại Black Kingdom trên khoảng 1.500 máy tính ở Hoa Kỳ và các quốc gia khác, yêu cầu khoản thanh toán tiền chuộc lên tới 10.000 đô la bằng Bitcoin.

"Theo cáo trạng, từ tháng 3 năm 2021 đến tháng 6 năm 2023, Ahmed và những người khác đã làm nhiễm độc mạng máy tính của một số nạn nhân có trụ sở tại Hoa Kỳ, bao gồm một công ty dịch vụ thanh toán y tế ở Encino, một khu nghỉ dưỡng trượt tuyết ở Oregon, một quận học ở Pennsylvania và một phòng khám y tế tại Wisconsin," [giải thích một thông báo của Bộ Tư pháp Hoa Kỳ](https://www.justice.gov/usao-cdca/pr/yemeni-man-charged-federal-indictment-alleging-he-sent-black-kingdom-malware-extort).

"Khi phần mềm độc hại hoạt động thành công, ransomware sẽ tạo ra một ghi chú yêu cầu tiền chuộc trên hệ thống của nạn nhân, hướng dẫn nạn nhân gửi 10.000 đô la Bitcoin tới một địa chỉ tiền điện tử do một đồng phạm kiểm soát và gửi chứng minh thanh toán này tới một địa chỉ email của Black Kingdom," đọc một phần khác của thông báo.

Bộ Tư pháp Hoa Kỳ nhấn mạnh rằng Ahmed đã thiết kế ransomware Black Kingdom để khai thác một lỗ hổng trong Microsoft Exchange nhằm truy cập ban đầu vào các máy tính mục tiêu.

Điều này lần đầu tiên được báo cáo vào tháng 3 năm 2021 bởi nhà nghiên cứu [Marcus Hutchins](https://www.bleepingcomputer.com/news/security/microsoft-exchange-servers-now-targeted-by-black-kingdom-ransomware/), người đã phát hiện ra các web shell được các quản trị viên ransomware Black Kingdom triển khai trên các máy chủ Exchange dễ bị tấn công bởi các cuộc tấn công ProxyLogon.

Lỗi [ProxyLogon](https://www.bleepingcomputer.com/news/security/microsoft-fixes-actively-exploited-exchange-zero-day-bugs-patch-now/) đề cập đến một bộ lỗ hổng nghiêm trọng trong Microsoft Exchange Server lần đầu tiên được công bố và khai thác vào đầu năm 2021.

Các lỗ hổng đó bao gồm CVE-2021-26855 (Server-Side Request Forgery được sử dụng để truy cập ban đầu), CVE-2021-26857 (phân tích không an toàn được sử dụng để tăng quyền truy cập lên SYSTEM), và CVE-2021-26858 cùng CVE-2021-27065 (ghi tệp tùy ý được sử dụng để ghi các web shell vào máy chủ).

Soon, Microsoft confirmed that Black Kingdom had [compromised 1,500 Exchange servers](https://www.bleepingcomputer.com/news/security/microsoft-black-kingdom-ransomware-group-hacked-15k-exchange-servers/) by leveraging ProxyLogon flaws.

Vào tháng 6 năm 2020, đã được tiết lộ rằng Black Kingdom [đã nhắm tới CVE-2019-11510](https://www.bleepingcomputer.com/news/security/black-kingdom-ransomware-hacks-networks-with-pulse-vpn-flaws/), một lỗ hổng nghiêm trọng ảnh hưởng đến Pulse Secure VPN, để xâm nhập vào mạng lưới doanh nghiệp và triển khai các tệp khóa của họ.

Đối với các cuộc tấn công Black Kingdom của mình, Ahmed hiện phải đối mặt với các cáo buộc âm mưu, cố ý gây hư hại cho máy tính được bảo vệ và đe dọa gây hư hại cho máy tính được bảo vệ.

Nếu bị kết án, Ahmed có thể phải đối mặt với bản án tối đa 5 năm tù liên bang cho mỗi tội danh, tổng cộng lên tới 15 năm.

Bộ Tư pháp Hoa Kỳ cho biết Ahmed được cho là đang sinh sống tại Yemen.