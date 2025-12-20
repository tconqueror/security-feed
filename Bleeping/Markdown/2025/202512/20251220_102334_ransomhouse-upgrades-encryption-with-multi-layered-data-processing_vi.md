# RansomHouse nâng cấp mã hóa với xử lý dữ liệu nhiều lớp

![Mã độc tống tiền](https://www.bleepstatic.com/content/hl-images/2023/09/28/Hacker_ransomware.jpg)

RansomHouse, một dịch vụ ransomware-as-a-service (RaaS), gần đây đã nâng cấp bộ mã hóa của mình, chuyển từ một kỹ thuật tuyến tính đơn giản một pha sang một phương pháp phức tạp hơn, nhiều lớp.

Trên thực tế, các nâng cấp này mang lại kết quả mã hóa mạnh hơn, tốc độ nhanh hơn và độ tin cậy tốt hơn trên các môi trường mục tiêu hiện đại, giúp các tác nhân đe dọa có lợi thế mạnh hơn trong các cuộc đàm phán sau khi mã hóa.

RansomHouse xuất hiện vào tháng 12 năm 2021 như một [hoạt động tội phạm tống tiền dữ liệu](https://www.bleepingcomputer.com/news/security/new-ransomhouse-group-sets-up-extortion-market-adds-first-victims/), sau đó áp dụng các bộ mã hóa trong các cuộc tấn công và phát triển một [công cụ tự động có tên MrAgent](https://www.bleepingcomputer.com/news/security/ransomhouse-gang-automates-vmware-esxi-attacks-with-new-mragent-tool/) để khóa nhiều hypervisor VMware ESXi cùng lúc.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Gần đây có báo cáo rằng các tác nhân đe dọa [sử dụng nhiều họ ransomware khác nhau](https://www.bleepingcomputer.com/news/security/askul-confirms-theft-of-740k-customer-records-in-ransomhouse-attack/) nhắm vào tập đoàn thương mại điện tử lớn của Nhật Bản, Askul Corporation.

Một báo cáo mới từ các nhà nghiên cứu tại Palo Alto Networks Unit 42 cho thấy thêm thông tin về bộ công cụ của RansomHouse, bao gồm biến thể bộ mã hóa mới nhất, có tên là ‘Mario’.

## Bộ mã hóa ‘Mario’ mới

Biến thể bộ mã hóa mới nhất của RansomHouse chuyển từ một phép biến đổi dữ liệu tệp một lần sang một phép biến đổi hai giai đoạn sử dụng hai khóa, một khóa chính 32-byte và một khóa phụ 8-byte.

Cách tiếp cận này tăng entropy của mã hóa và làm cho việc phục hồi dữ liệu từng phần trở nên khó khăn hơn.

![Mario generating the two keys](https://www.bleepstatic.com/images/news/u/1220909/2025/December/keys.jpg)

**'Mario' tạo hai khóa mã hóa**  
_Nguồn: Unit 42_

Nâng cấp lớn thứ hai là việc giới thiệu chiến lược xử lý tệp mới sử dụng kích thước khối động với ngưỡng 8GB, kèm theo mã hóa gián đoạn.

Unit 42 cho biết điều này làm phân tích tĩnh trở nên khó khăn hơn do tính không tuyến tính, sử dụng toán học phức tạp để xác định thứ tự xử lý và việc áp dụng các phương pháp khác nhau cho mỗi tệp dựa trên kích thước của nó.

Một cải tiến đáng chú ý khác trong ‘Mario’ là bố trí bộ nhớ và tổ chức bộ đệm tốt hơn, cùng độ phức tạp cao hơn, với nhiều bộ đệm chuyên dụng hiện được sử dụng cho mỗi giai đoạn hoặc vai trò mã hóa.

Cuối cùng, phiên bản bộ mã hóa được nâng cấp hiện in thông tin chi tiết hơn về việc xử lý tệp so với các biến thể cũ hơn, vốn chỉ thông báo hoàn thành nhiệm vụ.

Biến thể mới vẫn nhắm vào các tệp VM và đổi tên các tệp đã được mã hóa với phần mở rộng ‘.emario’, đồng thời thả một ghi chú tiền chuộc (How To Restore Your Files.txt) vào tất cả các thư mục bị ảnh hưởng.

**Ghi chú tiền chuộc được thả bởi biến thể RansomHouse mới nhất**  
_Nguồn: Unit 42_

Unit 42 kết luận rằng việc nâng cấp mã hóa của RansomHouse là điều đáng báo động, báo hiệu “một xu hướng đáng lo ngại trong phát triển ransomware,” làm tăng độ khó giải mã và khiến phân tích tĩnh cũng như đảo ngược kỹ thuật trở nên khó khăn hơn.

RansomHouse là một trong những hoạt động RaaS tồn tại lâu hơn, nhưng vẫn ở mức trung bình về khối lượng tấn công. Việc phát triển liên tục các công cụ tiên tiến của họ cho thấy một chiến lược có tính toán, tập trung vào hiệu quả và né tránh hơn là quy mô.