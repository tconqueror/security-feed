# UAC-0050 nhắm mục tiêu vào Tổ chức Tài chính Châu Âu bằng miền giả mạo và Malware RMS

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiMR8uMyTA6j9P1KBgNFXf7uKvuD9CpolHGiMuaTIMOc87IKSqoGXWxea4Hs3unk1kLewzUd0hyOxpk6AsnEy1WmKwQwW8QV2zFBJiCi6PLOMi5zxAD%5FC2%5FDZytczAcPCSA%5FJGN9Se8arByQlLzoTiDaX1qJiA0Q6IT2Sfeg7BgkeQZ2ptQcjo%5FRX8jMgs1/s1700-e365/bank-cyberattack.jpg)

Một nhóm đe dọa liên kết với Nga đã được quan sát nhắm mục tiêu vào một tổ chức tài chính Châu Âu như một phần của cuộc tấn công kỹ thuật xã hội nhằm có thể tạo điều kiện thu thập thông tin tình báo hoặc đánh cắp tài chính, cho thấy khả năng mở rộng mục tiêu của nhóm đe dọa này vượt ra khỏi Ukraine và vào các thực thể hỗ trợ [quốc gia đổ nát vì chiến tranh](https://ukraine.un.org/en/310531-immense-devastation-amid-severe-and-worsening-disruption-basic-services-four-years-full).

Hoạt động này, nhắm vào một thực thể không được nêu tên liên quan đến các sáng kiến phát triển và tái thiết khu vực, đã được gán cho nhóm tội phạm mạng được theo dõi là **[UAC-0050](https://thehackernews.com/2025/09/comicform-and-sectorj149-hackers-deploy.html)** (còn gọi là [Nhóm DaVinci](https://blog.bushidotoken.net/2024/03/tracking-adversaries-uac-0050-cracking.html)). BlueVoyant đã chỉ định tên Mercenary Akula cho cụm đe dọa này. Cuộc tấn công được quan sát vào đầu tháng này.

"Các cuộc tấn công giả mạo một miền tư pháp Ukraine để gửi email chứa liên kết đến một tải trọng truy cập từ xa," các nhà nghiên cứu Patrick McHale và Joshua Green [cho biết](https://www.bluevoyant.com/blog/mercenary-akula-hits-financial-institution) trong một báo cáo được chia sẻ với The Hacker News. "Mục tiêu là một cố vấn pháp lý và chính sách cấp cao tham gia vào việc mua sắm, một vai trò có cái nhìn đặc quyền vào hoạt động của tổ chức và cơ chế tài chính."

[](https://thehackernews.uk/sse-customer-awards-d)

Điểm khởi đầu là một email lừa đảo có chủ đích sử dụng các chủ đề pháp lý để hướng người nhận tải xuống một tệp lưu trữ được lưu trữ trên PixelDrain, một dịch vụ chia sẻ tệp được nhóm đe dọa sử dụng để vượt qua các biện pháp kiểm soát bảo mật dựa trên danh tiếng.

ZIP chịu trách nhiệm khởi động một chuỗi lây nhiễm nhiều lớp. Có trong tệp ZIP là một lưu trữ RAR chứa một tệp 7-Zip được bảo vệ bằng mật khẩu, bao gồm một tệp thực thi giả mạo tài liệu PDF bằng cách sử dụng thủ thuật phần mở rộng kép bị lạm dụng rộng rãi (\*.pdf.exe).

Việc thực thi dẫn đến việc triển khai trình cài đặt MSI cho Remote Manipulator System (RMS), một [phần mềm điều khiển từ xa của Nga](https://thehackernews.com/2024/12/horns-campaign-delivers-rats-via-fake.html) cho phép điều khiển từ xa, chia sẻ màn hình và chuyển tệp.

"Các công cụ 'sống trong hệ thống' này cung cấp cho kẻ tấn công quyền truy cập liên tục, kín đáo trong khi thường tránh được sự phát hiện của phần mềm chống virus truyền thống," các nhà nghiên cứu lưu ý.

Việc sử dụng RMS [phù hợp](https://thehackernews.com/2024/01/uac-0050-group-using-new-phishing.html) với [modus operandi trước đây của UAC-0050](https://thehackernews.com/2024/11/russian-hackers-exploit-new-ntlm-flaw.html), với nhóm đe dọa được biết đến là thả phần mềm truy cập từ xa hợp pháp như LiteManager và trojan truy cập từ xa như RemcosRAT trong các cuộc tấn công nhắm vào Ukraine.

Đội ứng phó khẩn cấp máy tính của Ukraine (CERT-UA) đã [đặc trưng](https://cert.gov.ua/article/6277822) UAC-0050 là một nhóm lính đánh thuê liên kết với các cơ quan thực thi pháp luật của Nga, nhóm này [tiến hành](https://thehackernews.com/2024/10/russian-romcom-attacks-target-ukrainian.html) thu thập dữ liệu, đánh cắp tài chính, và các hoạt động thông tin và tâm lý dưới thương hiệu Fire Cells.

"Cuộc tấn công này phản ánh hồ sơ tấn công được thiết lập tốt và lặp lại của Mercenary Akula, đồng thời cũng mang lại một phát triển đáng chú ý," BlueVoyant cho biết. "Đầu tiên, mục tiêu của họ chủ yếu tập trung vào các thực thể có trụ sở tại Ukraine, đặc biệt là kế toán và sĩ quan tài chính. Tuy nhiên, sự cố này cho thấy khả năng thăm dò các tổ chức hỗ trợ Ukraine ở Tây Âu."

Thông báo được đưa ra khi Ukraine tiết lộ rằng các cuộc tấn công mạng của Nga nhắm vào cơ sở hạ tầng năng lượng của nước này ngày càng tập trung vào việc thu thập thông tin tình báo để hướng dẫn các cuộc tấn công tên lửa hơn là ngay lập tức làm gián đoạn hoạt động, The Record [đưa tin](https://therecord.media/ukraine-cyberattacks-guiding-russian-missile-strikes).

[](https://thehackernews.uk/ztw-hands-on-d)

Công ty an ninh mạng CrowdStrike, trong báo cáo thường niên [Báo cáo Mối đe dọa Toàn cầu](https://www.crowdstrike.com/en-us/blog/crowdstrike-2026-global-threat-report-findings/) của mình, cho biết họ kỳ vọng các đối thủ liên kết với Nga sẽ tiếp tục tiến hành các hoạt động tấn công với mục tiêu thu thập thông tin tình báo từ các mục tiêu Ukraine và các quốc gia thành viên NATO.

Điều này bao gồm các nỗ lực được thực hiện bởi [APT29](https://thehackernews.com/2024/03/microsoft-confirms-russian-hackers.html) (còn gọi là Cozy Bear và Midnight Blizzard) để "hệ thống" khai thác lòng tin, uy tín tổ chức, và tính hợp pháp của nền tảng như một phần của các chiến dịch lừa đảo có chủ đích nhắm vào các tổ chức phi chính phủ (NGOs) có trụ sở tại Mỹ và một thực thể pháp lý có trụ sở tại Mỹ để giành quyền truy cập trái phép vào tài khoản Microsoft của nạn nhân.

"Cozy Bear đã thành công trong việc xâm phạm hoặc giả mạo các cá nhân mà người dùng mục tiêu duy trì mối quan hệ chuyên nghiệp tin cậy," CrowdStrike cho biết. "Các cá nhân bị giả mạo bao gồm nhân viên từ các chi nhánh NGO quốc tế và các tổ chức ủng hộ Ukraine."

"Đối thủ đã đầu tư mạnh vào việc chứng thực các vụ giả mạo này, sử dụng các tài khoản email hợp pháp của các cá nhân bị xâm phạm cùng với các kênh liên lạc tạm thời để củng cố tính xác thực."