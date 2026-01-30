# Tin tấn công mạng vào lưới điện Ba Lan ảnh hưởng khoảng 30 cơ sở

![Cyberattack on Polish energy grid impacted around 30 facilities](https://www.bleepstatic.com/content/hl-images/2026/01/28/turbines.jpg)

Cuộc tấn công có tổ chức vào lưới điện Ba Lan cuối tháng 12 nhắm vào nhiều địa điểm tài nguyên năng lượng phân tán (DER) trên cả nước, bao gồm các cơ sở kết hợp nhiệt điện (CHP) và hệ thống điều phối gió và mặt trời.

Mặc dù kẻ tấn công xâm nhập vào hệ thống công nghệ vận hành (OT) làm hư hỏng "thiết bị chính không thể sửa chữa được", nhưng chúng không thành công trong việc làm gián đoạn nguồn điện, tổng công suất 1.2 GW tương đương 5% nguồn cung năng lượng của Ba Lan.

Dựa trên các báo cáo công khai, có ít nhất 12 địa điểm bị ảnh hưởng được xác nhận. Tuy nhiên, nhà nghiên cứu tại Dragos, một công ty bảo mật hệ thống điều khiển công nghiệp (OT) và cơ sở hạ tầng quan trọng (ICS), cho biết con số này xấp xỉ 30.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

### Lỗ hổng và cấu hình sai

Các nhà nghiên cứu tại Dragos đã công bố thêm chi tiết về cuộc tấn công và cho biết việc không xảy ra mất điện không phải là dấu hiệu của sự cố ít nghiêm trọng hơn, mà nên được xem như cảnh báo về tính dễ bị tổn thương của hệ thống năng lượng phi tập trung.

"Một cuộc tấn công vào lưới điện vào bất kỳ thời điểm nào đều là vô trách nhiệm, nhưng thực hiện nó vào giữa mùa đông có khả năng gây chết người đối với dân thường phụ thuộc vào nó," theo [báo cáo Dragos](http://hub.dragos.com/report/electrum-targeting-polands-electric-sector).

"Thật đáng tiếc khi những kẻ tấn công các hệ thống này dường như cố tình chọn thời điểm để tối đa hóa tác động lên dân thường."

Dragos cho rằng với mức độ tin cậy vừa phải rằng cuộc tấn công thuộc về một tác nhân đe dọa Nga được theo dõi dưới tên Electrum. Dù chồng lấn với Sandworm (APT44), các nhà nghiên cứu nhấn mạnh đây là một cụm hoạt động riêng biệt.

ESET trước đó vài ngày đã công bố báo cáo về APT44, liên hệ nó với các cuộc tấn công phá hoại không thành công vào lưới điện Ba Lan bằng phần mềm độc hại tên [DynoWiper](https://www.bleepingcomputer.com/news/security/sandworm-hackers-linked-to-failed-wiper-attack-on-polands-energy-systems/).

Dragos liên kết Electrum với các phần mềm xóa dữ liệu khác nhắm vào mạng lưới Ukraine, bao gồm các đơn vị cung cấp điện như [Caddywiper](https://www.bleepingcomputer.com/news/security/new-caddywiper-data-wiping-malware-hits-ukrainian-networks/) và [Industroyer2](https://www.bleepingcomputer.com/news/security/sandworm-hackers-fail-to-take-down-ukrainian-energy-provider/), ghi nhận rằng hoạt động của nhóm đe dọa này gần đây đã mở rộng sang nhiều quốc gia hơn.

Electrum nhắm mục tiêu vào các hệ thống bị lộ và dễ bị tổn thương liên quan đến điều phối và giao tiếp với lưới điện, thiết bị đầu cuối từ xa (RTUs), thiết bị biên mạng, hệ thống giám sát và điều khiển, cùng máy tính Windows tại các địa điểm DER.

### Kẻ tấn công am hiểu

Dựa trên bằng chứng từ ứng phó sự cố tại một trong các cơ sở bị ảnh hưởng, Dragos lưu ý rằng kẻ tấn công đã thể hiện sự hiểu biết sâu sắc về cách các thiết bị này được triển khai và vận hành, liên tục xâm nhập vào các cấu hình RTU và thiết bị biên tương tự trên nhiều địa điểm.

Electrum đã thành công trong việc vô hiệu hóa thiết bị truyền thông tại nhiều địa điểm, dẫn đến mất khả năng giám sát và điều khiển từ xa, nhưng việc phát điện trên các đơn vị vẫn tiếp tục mà không bị gián đoạn.

Một số thiết bị OT/ICS đã bị vô hiệu hóa, cấu hình của chúng bị hỏng không thể khôi phục được, trong khi hệ thống Windows tại các địa điểm bị xóa dữ liệu.

Ngay cả khi các cuộc tấn công thành công trong việc cắt điện, phạm vi mục tiêu tương đối hẹp sẽ không đủ để gây ra mất điện trên toàn quốc ở Ba Lan.

Tuy nhiên, chúng có thể gây ra sự bất ổn đáng kể về tần số hệ thống. "Những sai lệch tần số như vậy đã gây ra sự cố lan truyền trong các hệ thống điện khác, bao gồm cả sự sụp đổ lưới điện Iberian năm 2025," các nhà nghiên cứu cho biết.