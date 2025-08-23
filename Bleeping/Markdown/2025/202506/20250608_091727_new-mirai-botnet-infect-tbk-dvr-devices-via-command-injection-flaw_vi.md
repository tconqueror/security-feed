# Botnet Mirai mới nhiễm các thiết bị TBK DVR qua lỗ hổng tiêm lệnh

![Botnet](https://www.bleepstatic.com/content/hl-images/2025/04/08/botnet-2.jpg)

Một biến thể mới của botnet phần mềm độc hại Mirai đang khai thác một lỗ hổng tiêm lệnh trong các thiết bị ghi video kỹ thuật số TBK DVR-4104 và DVR-4216 để chiếm đoạt chúng.

Lỗ hổng này, được theo dõi dưới mã [CVE-2024-3721](https://nvd.nist.gov/vuln/detail/CVE-2024-3721), là một lỗ hổng tiêm lệnh được tiết lộ bởi nhà nghiên cứu bảo mật "[netsecfish](https://github.com/netsecfish/tbk%5Fdvr%5Fcommand%5Finjection)" vào tháng 4 năm 2024.

Chứng minh khái niệm (PoC) mà nhà nghiên cứu công bố vào thời điểm đó có dạng một yêu cầu POST được tạo đặc biệt tới một điểm cuối dễ bị tấn công, đạt được thi hành lệnh shell thông qua việc thao tác một số tham số nhất định (mdb và mdc).

Kaspersky [hiện báo cáo](https://securelist.com/mirai-botnet-variant-targets-dvr-devices-with-cve-2024-3721/116742/) đã phát hiện việc khai thác CVE-2024-3721 đang diễn ra trong các honeypots Linux của họ từ một biến thể mới của botnet Mirai sử dụng PoC của netsecfish.

Các kẻ tấn công tận dụng lỗ hổng để tải xuống một nhị phân phần mềm độc hại ARM32, thiết lập liên lạc với máy chủ chỉ huy và điều khiển (C2) để đưa thiết bị vào bầy botnet. Từ đó, thiết bị này có khả năng được sử dụng để thực hiện các cuộc tấn công từ chối dịch vụ phân tán (DDoS), làm proxy cho lưu lượng độc hại, và các hành vi khác.

![Kiểm tra môi trường của Mirai](https://www.bleepstatic.com/images/news/u/1220909/2025/June/env-checks.png)

**Kiểm tra môi trường của Mirai**  
_Nguồn: Kaspersky_

## Tác động của cuộc tấn công và biện pháp khắc phục

Mặc dù netsecfish đã báo cáo năm ngoái rằng có khoảng 114.000 DVR kết nối Internet dễ bị tổn thương với CVE-2024-3721, các quét của Kaspersky cho thấy khoảng 50.000 thiết bị bị lộ, điều này vẫn là đáng kể.

Hầu hết các cuộc tấn công mà công ty an ninh mạng Nga thấy có liên quan đến biến thể Mirai mới nhất ảnh hưởng đến Trung Quốc, Ấn Độ, Ai Cập, Ukraine, Nga, Thổ Nhĩ Kỳ và Brazil. Tuy nhiên, điều này dựa trên dữ liệu telemetry của Kaspersky, và do các sản phẩm bảo mật tiêu dùng của họ đang bị [cấm ở nhiều quốc gia](https://www.bleepingcomputer.com/news/security/biden-bans-kaspersky-antivirus-software-in-us-over-security-concerns/), điều này có thể không phản ánh chính xác mục tiêu của botnet.

Hiện tại, vẫn chưa rõ liệu nhà cung cấp, TBK Vision, đã phát hành bản cập nhật bảo mật để khắc phục lỗ hổng CVE-2024-3721 hay vẫn chưa được vá. BleepingComputer đã liên hệ với TBK để hỏi về điều này, nhưng chúng tôi vẫn đang chờ phản hồi của họ.

Đáng chú ý là DVR-4104 và DVR-4216 đã được [tiếp thị lại rộng rãi](https://www.bleepingcomputer.com/news/security/hackers-exploit-5-year-old-unpatched-flaw-in-tbk-dvr-devices/) dưới các thương hiệu Novo, CeNova, QSee, Pulnix, XVR 5 trong 1, Securus, Night OWL, DVR Login, HVR Login và MDVR, vì vậy việc có sẵn các bản vá cho các thiết bị bị ảnh hưởng là một vấn đề phức tạp.

Nhà nghiên cứu tiết lộ lỗ hổng TBK Vision đã phát hiện ra các lỗ hổng khác đã làm tăng cường khai thác đối với các thiết bị hết vòng đời năm ngoái.

Cụ thể, netsecfish đã tiết lộ một [vấn đề tài khoản backdoor](https://www.bleepingcomputer.com/news/security/over-92-000-exposed-d-link-nas-devices-have-a-backdoor-account/) và một [lỗ hổng tiêm lệnh](https://www.bleepingcomputer.com/news/security/d-link-wont-fix-critical-flaw-affecting-60-000-older-nas-devices/) ảnh hưởng đến hàng chục nghìn thiết bị D-Link hết vòng đời vào năm 2024.

Việc khai thác tích cực [đã được phát hiện](https://www.bleepingcomputer.com/news/security/critical-rce-bug-in-92-000-d-link-nas-devices-now-exploited-in-attacks/) trong [cả hai trường hợp](https://www.bleepingcomputer.com/news/security/critical-bug-in-eol-d-link-nas-devices-now-exploited-in-attacks/) chỉ vài ngày sau khi công bố PoC. Điều này cho thấy malware authors nhanh chóng tích hợp các lỗ hổng công khai vào kho vũ khí của họ.