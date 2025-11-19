# ‘PlushDaemon’ hacker chiếm quyền cập nhật phần mềm trong các cuộc tấn công chuỗi cung ứng

![China](https://www.bleepstatic.com/content/hl-images/2025/05/28/China.jpg)

Một nhóm tác nhân đe dọa liên kết với China được theo dõi dưới tên 'PlushDaemon' đang chiếm quyền lưu lượng cập nhật phần mềm bằng cách sử dụng một implant mới có tên EdgeStepper trong các hoạt động gián điệp mạng.

Kể từ 2018, các hacker PlushDaemon đã nhắm mục tiêu cá nhân và tổ chức ở the United States, China, Taiwan, Hong Kong, South Korea, và New Zealand với phần mềm độc hại tùy chỉnh, chẳng hạn như backdoor SlowStepper.

PlushDaemon đã xâm phạm các nhà sản xuất điện tử, các trường đại học, và một nhà máy sản xuất ô tô Japanese ở Cambodia. Dữ liệu telemetry từ công ty an ninh mạng ESET cho thấy kể từ 2019, nhóm tác nhân này đã dựa vào các bản cập nhật độc hại để xâm nhập mạng mục tiêu.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

![PlushDaemon victims since 2023](https://www.bleepstatic.com/images/news/u/1220909/2025/November/map(1).jpg)

**Nạn nhân của PlushDaemon từ năm 2023**  
_Nguồn: ESET_

### Chuỗi tấn công

Kẻ tấn công truy cập vào router bằng cách khai thác các lỗ hổng đã biết hoặc mật khẩu quản trị yếu, cài đặt implant EdgeStepper, rồi chuyển hướng lưu lượng cập nhật phần mềm đến hạ tầng của chúng.

EdgeStepper hoạt động bằng cách chặn các truy vấn DNS và chuyển hướng chúng đến một node DNS độc hại sau khi xác nhận rằng domain đó được sử dụng để phân phối các bản cập nhật phần mềm, các nhà nghiên cứu ESET giải thích trong một báo cáo chia sẻ với BleepingComputer.

Khi nạn nhân cố gắng cập nhật phần mềm, họ sẽ nhận được chương trình tải xuống phần mềm độc hại LittleDaemon cho Windows đóng giả dưới dạng một file DLL có tên ‘_popup\_4.2.0.2246.dll._’

**Tổng quan về cuộc tấn công**  
_Nguồn: ESET_

LittleDaemon tải xuống một dropper phần mềm độc hại khác tên DaemonicLogistics, được giải mã và thực thi trong bộ nhớ, rồi lấy về backdoor có chữ ký của PlushDaemon là SlowStepper.

Backdoor này đã được [previously documented](https://www.bleepingcomputer.com/news/security/ipany-vpn-breached-in-supply-chain-attack-to-push-custom-malware/) trong các cuộc tấn công chống lại người dùng sản phẩm VPN IPany của South Korea. Trong những cuộc tấn công đó, người dùng đã tải xuống một bộ cài bị trojan hóa từ trang web chính thức của nhà cung cấp.

Phần mềm độc hại SlowStepper cho phép hacker thu thập thông tin hệ thống chi tiết, thực hiện các thao tác tệp rộng rãi, chạy lệnh và vận hành nhiều công cụ spyware dựa trên Python có thể đánh cắp dữ liệu từ trình duyệt, chặn phím và thu thập thông tin đăng nhập.