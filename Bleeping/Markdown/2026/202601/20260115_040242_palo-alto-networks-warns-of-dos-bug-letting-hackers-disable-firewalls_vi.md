# Palo Alto Networks cảnh báo lỗ hổng DoS cho phép tin tặc vô hiệu hóa tường lửa

![Palo Alto Networks](https://www.bleepstatic.com/content/hl-images/2024/11/08/Palo-Alto-Networks.jpg)

Palo Alto Networks đã vá một lỗ hổng nghiêm trọng có thể cho phép kẻ tấn công chưa xác thực vô hiệu hóa biện pháp bảo vệ tường lửa trong các cuộc tấn công từ chối dịch vụ (DoS).

Được theo dõi với mã CVE-2026-0227, lỗ hổng này ảnh hưởng đến các tường lửa thế hệ tiếp theo (chạy PAN-OS 10.1 trở lên) và cấu hình Prisma Access của Palo Alto Networks khi GlobalProtect gateway hoặc portal được kích hoạt.

Công ty an ninh mạng cho biết hầu hết các instance Prisma Access dựa trên đám mây đã được vá, những instance còn lại đã được lên lịch nâng cấp.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

"Một lỗ hổng trong phần mềm PAN-OS của Palo Alto Networks cho phép một kẻ tấn công chưa xác thực gây ra từ chối dịch vụ (DoS) đối với tường lửa. Các lần cố gắng lặp lại để kích hoạt vấn đề này dẫn đến tường lửa chuyển sang chế độ bảo trì," Palo Alto Networks [giải thích](https://security.paloaltonetworks.com/CVE-2026-0227).

"Chúng tôi đã hoàn tất nâng cấp Prisma Access cho hầu hết khách hàng, ngoại trừ một vài trường hợp đang tiến hành do lịch nâng cấp xung đột. Các khách hàng còn lại đang được lên lịch nâng cấp kịp thời thông qua quy trình nâng cấp tiêu chuẩn của chúng tôi."

Cơ quan giám sát an ninh mạng Shadowserver hiện đang [theo dõi gần 6.000 tường lửa Palo Alto Networks](https://dashboard.shadowserver.org/statistics/iot-devices/time-series/?date%5Frange=7&vendor=palo+alto+networks&type=firewall&dataset=count&limit=100&group%5Fby=geo&stacking=stacked) được mở ra trực tuyến, mặc dù không có thông tin về bao nhiêu trong số đó có cấu hình dễ bị tấn công hoặc đã được vá.

![Palo Alto Networks firewalls exposed online](https://www.bleepstatic.com/images/news/u/1109292/2026/PAN%20firewalls%20exposed%20online.jpg)

_Palo Alto Networks firewalls exposed online (Shadowserver)_

Khi thông báo bảo mật được công bố vào thứ Tư, công ty cho biết họ chưa tìm thấy bằng chứng lỗ hổng này đang bị lợi dụng trong các cuộc tấn công.

Palo Alto Networks đã phát hành các bản cập nhật bảo mật cho tất cả các phiên bản bị ảnh hưởng, và quản trị viên được khuyến cáo nâng cấp lên bản phát hành mới nhất để bảo vệ hệ thống khỏi các cuộc tấn công tiềm tàng.

| Version                    | Minor Version                                  | Suggested Solution                    |
| -------------------------- | ---------------------------------------------- | ------------------------------------- |
| Cloud NGFW All             |                                                | Không cần hành động.                  |
| PAN-OS 12.1                | 12.1.0 through 12.1.3                          | Nâng cấp lên 12.1.4 hoặc mới hơn.     |
| PAN-OS 11.2                | 11.2.8 through 11.2.10                         | Nâng cấp lên 11.2.10-h2 hoặc mới hơn. |
| |  11.2.5 through 11.2.7   | Nâng cấp lên 11.2.7-h8 hoặc 11.2.10-h2 hoặc mới hơn.   |                                       |
| |  11.2.0 through 11.2.4   | Nâng cấp lên 11.2.4-h15 hoặc 11.2.10-h2 hoặc mới hơn.  |                                       |
| PAN-OS 11.1                | 11.1.11 through 11.1.12                        | Nâng cấp lên 11.1.13 hoặc mới hơn.    |
| |  11.1.7 through 11.1.10  | Nâng cấp lên 11.1.10-h9 hoặc 11.1.13 hoặc mới hơn.     |                                       |
| |  11.1.5 through 11.1.6   | Nâng cấp lên 11.1.6-h23 hoặc 11.1.13 hoặc mới hơn.     |                                       |
| |  11.1.0 through 11.1.4   | Nâng cấp lên 11.1.4-h27 hoặc 11.1.13 hoặc mới hơn.     |                                       |
| PAN-OS 10.2                | 10.2.17 through 10.2.18                        | Nâng cấp lên 10.2.18-h1 hoặc mới hơn. |
| |  10.2.14 through 10.2.16 | Nâng cấp lên 10.2.16-h6 hoặc 10.2.18-h1 hoặc mới hơn.  |                                       |
| |  10.2.11 through 10.2.13 | Nâng cấp lên 10.2.13-h18 hoặc 10.2.18-h1 hoặc mới hơn. |                                       |
| |  10.2.8 through 10.2.10  | Nâng cấp lên 10.2.10-h30 hoặc 10.2.18-h1 hoặc mới hơn. |                                       |
| |  10.2.0 through 10.2.7   | Nâng cấp lên 10.2.7-h32 hoặc 10.2.18-h1 hoặc mới hơn.  |                                       |
| Unsupported PAN-OS         |                                                | Nâng cấp lên phiên bản được hỗ trợ đã được sửa lỗi. |
| Prisma Access 11.2         | 11.2 through                                   | Nâng cấp lên 11.2.7-h8 hoặc mới hơn.  |
| Prisma Access 10.2         | 10.2 through                                   | Nâng cấp lên 10.2.10-h29 hoặc mới hơn.      |

Tường lửa của Palo Alto Networks thường bị nhắm mục tiêu trong các cuộc tấn công, thường sử dụng các lỗ hổng zero-day chưa được tiết lộ hoặc vá.

Vào tháng 11 năm 2024, Palo Alto Networks [đã vá hai lỗ hổng PAN-OS zero-day đang bị khai thác tích cực](https://www.bleepingcomputer.com/news/security/palo-alto-networks-patches-two-firewall-zero-days-used-in-attacks/) cho phép kẻ tấn công chiếm quyền root. Shadowserver tiết lộ vài ngày sau đó rằng [hàng nghìn tường lửa đã bị xâm phạm](https://www.bleepingcomputer.com/news/security/over-2-000-palo-alto-firewalls-hacked-using-recently-patched-bugs/) trong chiến dịch (mặc dù công ty nói các cuộc tấn công chỉ ảnh hưởng đến "một số rất nhỏ"), trong khi CISA yêu cầu các cơ quan liên bang bảo đảm thiết bị của họ trong vòng 3 tuần.

Một tháng sau đó, vào tháng 12 năm 2024, công ty an ninh mạng đã cảnh báo khách hàng rằng [tin tặc đang khai thác một lỗ hổng DoS PAN-OS khác](https://www.bleepingcomputer.com/news/security/hackers-exploit-dos-flaw-to-disable-palo-alto-networks-firewalls/) (CVE-2024-3393) để nhắm mục tiêu các tường lửa PA-Series, VM-Series, và CN-Series với tính năng ghi nhật ký DNS Security được bật, buộc chúng khởi động lại và vô hiệu hóa các biện pháp bảo vệ tường lửa.

Ngay sau đó, vào tháng Hai, công ty nói ba lỗ hổng khác (CVE-2025-0111, CVE-2025-0108, và CVE-2024-9474) [đã bị xâu chuỗi trong các cuộc tấn công](https://www.bleepingcomputer.com/news/security/palo-alto-networks-tags-new-firewall-bug-as-exploited-in-attacks/) để xâm phạm các tường lửa PAN-OS.

Gần đây hơn, công ty tình báo mối đe dọa GreyNoise [cảnh báo về một chiến dịch tự động](https://www.bleepingcomputer.com/news/security/new-wave-of-vpn-login-attempts-targets-palo-alto-globalprotect-portals/) nhắm vào các portal Palo Alto GlobalProtect với các lần thử brute-force và đăng nhập từ hơn 7.000 địa chỉ IP. GlobalProtect là thành phần VPN và truy cập từ xa của PAN-OS firewalls, được sử dụng bởi nhiều cơ quan chính phủ, nhà cung cấp dịch vụ, và các doanh nghiệp lớn.

Sản phẩm và dịch vụ của Palo Alto Networks được sử dụng bởi hơn 70.000 khách hàng trên toàn thế giới, bao gồm hầu hết các ngân hàng lớn nhất của U.S. và 90% các công ty trong Fortune 10.