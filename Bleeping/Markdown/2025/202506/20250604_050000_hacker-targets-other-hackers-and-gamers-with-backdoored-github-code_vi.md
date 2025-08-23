# Hacker nhắm vào các hacker và game thủ bằng mã GitHub có backdoor

![Biểu tượng hacker vui vẻ](https://www.bleepstatic.com/content/hl-images/2022/09/15/cyber-smiley-lower.jpg)

Một hacker nhắm vào các hacker khác, game thủ và nhà nghiên cứu với các lỗ hổng, bot và cheat game trong mã nguồn được lưu trữ trên GitHub mà chứa các backdoor ẩn để cho phép kẻ tấn công truy cập từ xa vào các thiết bị bị nhiễm.

Chiến dịch này đã được các nhà nghiên cứu của Sophos phát hiện, những người mà một khách hàng đã liên hệ để đánh giá mức độ nguy hiểm của một trojan truy cập từ xa có tên là Sakura RAT, mà có sẵn miễn phí trên GitHub.

Các nhà nghiên cứu đã phát hiện rằng mã Sakura RAT về cơ bản là không hoạt động nhưng có một _PreBuildEvent_ trong dự án Visual Studio mà tải xuống và cài đặt phần mềm độc hại trên các thiết bị của những người cố gắng biên dịch nó.

Nhà phát hành, "ischhfd83," đã được phát hiện có liên quan trực tiếp hoặc gián tiếp đến 141 kho GitHub khác, 133 trong số đó đã phát tán các backdoor ẩn, đánh dấu đây là một chiến dịch phối hợp để phân phối phần mềm độc hại.

![Một trong những kho độc hại quảng bá một trình xây dựng lỗ hổng giả](https://www.bleepstatic.com/images/news/u/1220909/2025/June/repo.jpg)

**Một trong những kho độc hại quảng bá một trình xây dựng lỗ hổng giả**  
_Nguồn: Sophos_

Danh sách các backdoor bao gồm các script Python với payload đã bị làm mờ, tệp screensaver ( .scr) độc hại sử dụng các mẹo Unicode, tệp JavaScript với payload được mã hóa và các sự kiện PreBuild trong Visual Studio.

Một số kho có vẻ như đã bị bỏ hoang kể từ cuối năm 2023, nhưng nhiều kho vẫn hoạt động với các cam kết định kỳ, một số được gửi chỉ vài phút trước khi phân tích của Sophos diễn ra.

Những cam kết này hoàn toàn tự động, vì vậy mục đích duy nhất của chúng là tạo ra một hình ảnh giả mạo về hoạt động để làm cho các dự án độc hại có ảo tưởng về tính hợp pháp.

![Lịch sử cam kết](https://www.bleepstatic.com/images/news/security/g/github/backdoored-cheats-code/anydesk-github.jpg)

**Lịch sử cam kết**  
_Nguồn: Sophos_

"Bởi vì các quy trình làm việc tự động, nhiều dự án đã có một số lượng lớn cam kết (một dự án có gần 60.000 cam kết, mặc dù chỉ mới được tạo vào tháng 3 năm 2025)," Sophos giải thích.

"Trên tất cả các kho, số lượng cam kết trung bình là 4.446 tại thời điểm thu thập ban đầu của chúng tôi."

Số lượng người đóng góp được cố định cho ba người dùng cụ thể cho mỗi kho, và các tài khoản phát hành khác nhau được sử dụng cho mỗi kho, không bao giờ vượt quá chín kho được gán cho một tài khoản đơn.

Các kho này nhận được lưu lượng truy cập từ video YouTube, Discord, và các bài đăng trên diễn đàn tội phạm mạng. Sakura RAT tự nó nhận được một số sự chú ý từ truyền thông đã khơi dậy sự quan tâm trong những "script kiddies" tò mò muốn tìm kiếm nó trên GitHub.

Tuy nhiên, khi các nạn nhân tải xuống các tệp tin, việc chạy hoặc xây dựng mã sẽ kích hoạt một giai đoạn lây nhiễm nhiều bước.

**Backdoor ban đầu kích hoạt quy trình lây nhiễm**  
_Nguồn: Sophos_

Quá trình này liên quan đến việc thực hiện các script VBS trên đĩa, PowerShell tải xuống payload đã được mã hóa từ các URL cứng, lấy một tệp 7zip từ GitHub và chạy một ứng dụng Electron (SearchFilter.exe).

Ứng dụng này tải một tệp nén có chứa 'main.js' và các tệp liên quan đã bị làm méo rất nhiều, bao gồm cả mã cho việc phân tích hệ thống, thực thi lệnh, tắt Windows Defender và thu hồi payload.

**Trích xuất từ main.js**  
_Nguồn: Sophos_

Các payload bổ sung được tải xuống bởi backdoor bao gồm các công cụ đánh cắp thông tin và trojan truy cập từ xa như Lumma Stealer, AsyncRAT, và Remcos, tất cả đều có khả năng đánh cắp dữ liệu mạnh mẽ.

Mặc dù nhiều kho bị trojan hóa được tạo ra để nhắm vào các hacker khác, nhưng một loạt các mồi câu, như cheat game, công cụ mod và lỗ hổng giả, đã được sử dụng để nhắm vào game thủ, sinh viên và thậm chí các nhà nghiên cứu an ninh mạng.

Vì bất kỳ ai cũng có thể tải lên mã nguồn lên GitHub, việc xem xét mã nguồn và xác minh bất kỳ sự kiện trước và sau khi xây dựng của các dự án là rất quan trọng trước khi cố gắng biên dịch phần mềm tải xuống từ các kho mã nguồn mở.