# CISA cảnh báo về Akira ransomware Linux encryptor nhắm vào Nutanix VMs

![Tin tặc](https://www.bleepstatic.com/content/hl-images/2024/12/10/hacker-box.jpg)

Các cơ quan chính phủ Hoa Kỳ đang cảnh báo rằng chiến dịch Akira ransomware đã được phát hiện mã hóa các máy ảo Nutanix AHV trong các cuộc tấn công.

Một thông báo chung cập nhật từ CISA, FBI, Department of Defense Cyber Crime Center (DC3), Department of Health and Human Services (HHS), và một số đối tác quốc tế cảnh báo rằng Akira ransomware đã mở rộng khả năng mã hóa sang các tệp đĩa VM của Nutanix AHV.

Thông báo bao gồm các chỉ số xâm phạm mới và các chiến thuật quan sát được thông qua các cuộc điều tra của FBI và báo cáo từ bên thứ ba, mới nhất là vào tháng 11 năm 2025.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

## Mã hóa Nutanix VMs trong các cuộc tấn công

Thông báo cảnh báo rằng vào tháng 6 năm 2025, các tác nhân Akira bắt đầu mã hóa các tệp đĩa cho các máy ảo Nutanix AHV.

"Trong một sự cố vào tháng 6 năm 2025, các tác nhân nguy cơ Akira đã mã hóa các tệp đĩa VM Nutanix AHV lần đầu tiên, mở rộng khả năng của họ vượt ra ngoài VMware ESXi và Hyper-V bằng cách lợi dụng lỗ hổng Common Vulnerabilities and Exposures (CVE)-2024-40766 [Common Weakness Enumeration (CWE)-284: Improper Access Control], một lỗ hổng của SonicWall," trích từ [thông báo cập nhật](https://www.cisa.gov/news-events/cybersecurity-advisories/aa24-109a).

Nền tảng AHV của Nutanix là một giải pháp ảo hóa dựa trên Linux chạy và quản lý các máy ảo trên hạ tầng của Nutanix.

Vì nó được triển khai rộng rãi, không có gì ngạc nhiên khi các nhóm ransomware bắt đầu nhắm mục tiêu các máy ảo trên nền tảng này, tương tự như với VMware ESXi và Hyper-V.

Mặc dù CISA chưa chia sẻ cách Akira đang nhắm vào các môi trường Nutanix AHV, các Linux encryptor của Akira được BleepingComputer phân tích cố gắng mã hóa các tệp có phần mở rộng **.qcow2**, là định dạng đĩa ảo được Nutanix AHV sử dụng.

Tuy nhiên, phần mở rộng tệp .qcow2 đã bị các Linux encryptor của Akira nhắm mục tiêu ít nhất kể từ cuối năm 2024.

Hơn nữa, sự tập trung của Akira vào Nutanix VMs cũng chưa phát triển mạnh như việc nhắm mục tiêu VMware ESXi của chúng.

Trình mã hóa Linux sử dụng _esxcli_ và _vim-cmd_ để tắt khéo léo các máy ảo ESXi trước khi mã hóa đĩa của chúng, nhưng đối với Nutanix AHV, nó đơn giản mã hóa trực tiếp các tệp .qcow2 và không sử dụng các lệnh _acli_ hoặc _ncli_ của nền tảng để tắt nguồn các VM trên AHV.

## Các cập nhật khác

Thông báo cập nhật cũng bao gồm thông tin mới về phương thức xâm nhập và chiến thuật sau thỏa hiệp của Akira.

Để xâm nhập vào mạng doanh nghiệp, các cộng tác viên Akira thường sử dụng thông tin đăng nhập VPN và SSH bị đánh cắp hoặc bị brute-force trên các router lộ diện và [khai thác lỗ hổng SonicWall](https://www.bleepingcomputer.com/news/security/akira-ransomware-breaching-mfa-protected-sonicwall-vpn-accounts/) (CVE-2024-40766) trên các firewall lộ diện.

Sau khi chiếm được quyền truy cập, họ khai thác các lỗ hổng CVE-2023-27532 hoặc CVE-2024-40711 trên các server Veeam Backup & Replication chưa được vá để truy cập và xóa các bản sao lưu.

Trong mạng, các thành viên Akira đã được quan sát sử dụng các tiện ích như nltest, AnyDesk, LogMeIn, Impacket's wmiexec.py, và các script VB để thực hiện thu thập thông tin tình báo, di chuyển ngang sang các hệ thống khác và thiết lập persistence. Các tác nhân đe dọa cũng thường xóa các công cụ phát hiện điểm cuối và tạo các tài khoản quản trị mới để giữ chân quyền truy cập.

Trong một sự cố, kẻ tấn công đã tắt một VM domain controller, sao chép các tệp VMDK của nó, gắn chúng vào một VM mới và trích xuất tệp NTDS.dit và hive SYSTEM để lấy được một tài khoản domain administrator.

Thông báo lưu ý rằng công cụ "Megazord" trước đây được liên kết với hoạt động Akira dường như đã bị bỏ rơi kể từ năm 2024.

Akira đã exfiltrate dữ liệu chỉ trong vòng hai giờ trong một số cuộc tấn công, và để điều khiển và chỉ huy (command-and-control) đã dựa vào các công cụ tunneling như Ngrok để thiết lập các kênh mã hóa vượt qua việc giám sát biên mạng.

Thông báo kêu gọi các tổ chức xem xét hướng dẫn cập nhật và triển khai các biện pháp giảm thiểu được khuyến nghị.

CISA và FBI cũng tiếp tục khuyến nghị sao lưu ngoại tuyến định kỳ, thực thi xác thực đa yếu tố, và vá nhanh các lỗ hổng đã biết bị khai thác.