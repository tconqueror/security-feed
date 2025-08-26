# Silk Typhoon attackers chiếm đoạt thẻ cổng nằm trong mạng trong các cuộc tấn công đối với ngoại giao

![Silk Typhoon hackers hijack network captive portals in diplomat attacks](https://www.bleepstatic.com/content/hl-images/2022/10/27/hand-grasping-cables.jpg)

Những hacker tài trợ bởi nhà nước liên quan tới cụm hoạt động Silk Typhoon đã nhắm vào các nhân vật ngoại giao bằng cách chiếm đoạt lưu lượng web để chuyển hướng tới một trang web phục vụ phần mềm độc hại.

Chính các hacker đã sử dụng kỹ thuật adversary-in-the-middle (AitM) tiên tiến để chiếm quyền thẻ cổng nắm giữ mạng và gửi mục tiêu tới phần mềm độc hại giai đoạn đầu.

Google Threat Intelligence Group (GTIG) theo dõi tác nhân mối đe dọa này với tên gọi UNC6384 và, dựa trên công cụ, mục tiêu, và hạ tầng, tin rằng tác nhân này liên kết với thực thể mối đe dọa Trung Quốc TEMP.Hex, còn được biết đến là Mustang Panda và Silk Typhoon.

## Chiếm đoạt các yêu cầu của Chrome

Các nhà nghiên cứu GTIG tin rằng AitM có thể thực hiện sau khi đã xâm nhập vào một thiết bị cạnh (edge device) trong mạng mục tiêu; tuy nhiên, họ không tìm thấy bằng chứng để hỗ trợ giả thuyết này.

Khi phát hiện rằng trình duyệt Chrome đang đứng sau một thẻ cổng nằm (captive portal), một trang web nơi người dùng mạng phải xác thực trước khi kết nối tới Internet, cuộc tấn công bắt đầu.

Với vị trí chiếm đoạt lưu lượng web, hacker chuyển hướng mục tiêu tới một trang đích giả mạo trang cập nhật plugin Adobe.

Bị bào lừa tải về file **AdobePlugins.exe** được ký điện tử, được trình bày như một bản cập nhật plugin bắt buộc, và họ hướng dẫn điều hướng từng bước trên trang để bỏ qua các lời nhắc bảo mật Windows trong quá trình cài đặt.

![Fake site prompting Adobe plugin installation](https://www.bleepstatic.com/images/news/u/1220909/2025/August/adobe.jpg)

**Fake site prompting Adobe plugin installation**  
_Giáo nguồn: [Google](https://cloud.google.com/blog/topics/threat-intelligence/prc-nexus-espionage-targets-diplomats)_

Mở file này hiển thị trình cài đặt Microsoft Visual C++ nhưng ngay sau đó, nó tải về một gói MSI bị che giấu (20250509.bmp) chứa công cụ in ấn Canon hợp lệ, một DLL (**CANONSTAGER**) và phụ lục **SOGU.SEC** đã được mã hóa RC‑4.

**CANONSTAGER** giải mã và nạp payload cuối cùng vào bộ nhớ hệ thống bằng kỹ thuật side‑loading của DLL.

**SOGU.SEC**, như Google cho biết là biến thể của phần mềm độc hại **PlugX**, được sử dụng rộng rãi bởi nhiều nhóm mối đe dọa Trung Quốc, có thể thu thập thông tin hệ thống, tải lên hoặc tải xuống file, và cung cấp một shell lệnh từ xa cho các đặc vụ.

![Overview of the attack chain](https://www.bleepstatic.com/images/news/u/1220909/2025/August/overview(1).jpg)

**Overview of the attack chain**  
_Giáo nguồn: Google_

Các nhà nghiên cứu **GTIG** đã lưu ý rằng không rõ liệu thực thể ký các file trong chiến dịch này, Chengdu Nuoxin Times Technology Co., Ltd, có tham gia tích cực trong các hoạt động này hay đã bị xâm phạm hay không.

Tuy nhiên, GTIG đã theo dõi ít nhất 25 mẫu phần mềm độc hại đã được ký bởi thực thể này kể từ đầu năm 2023, liên quan đến nhiều cụm hoạt động Trung Quốc.

Việc coi tất cả các chứng chỉ từ Chengdu Nuoxin Times Technology Co., Ltd là không đáng tin cậy là một biện pháp phòng thủ hợp lý cho tới khi tình hình được làm rõ.

**Certificate used in the latest Mustang Panda campaign**  
_Giáo nguồn: Google_

Google đã chặn các domain và hash file độc hại qua Safe Browsing và phát hành cảnh báo bảo mật cho người dùng Gmail và Workspace bị ảnh hưởng.

Công ty công nghệ cũng đã chia sẻ quy tắc YARA để phát hiện **STATICPLUGIN** và **CANONSTAGER**, cùng với các chỉ số Nguy cơ (IoCs) cho tất cả các file lấy mẫu từ những cuộc tấn công này.

Chiến dịch mới nhất này cho thấy mức độ tinh vi ngày càng tăng của các tác nhân ngụy trang liên quan đến Trung Quốc, có khả năng chuyển sang hạ tầng và bản dựng cấp phát nhanh chóng và liên tục.