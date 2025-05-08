# Băng nhóm ransomware LockBit bị hack, các cuộc đàm phán nạn nhân bị lộ

![LockBit](https://www.bleepstatic.com/content/hl-images/2023/02/01/lockbit-flames.jpg)

Băng nhóm ransomware LockBit đã bị rò rỉ dữ liệu sau khi các bảng liên kết affiliate trên dark web của nó bị phá hoại và thay thế bằng một thông điệp liên kết tới một tệp dump MySQL.

Tất cả các bảng quản trị của băng nhóm ransomware này giờ đây đều có thông báo. "Đừng phạm tội **CRIME IS BAD** xoxo từ Prague," với một liên kết để tải xuống "paneldb\_dump.zip."

![Trang web dark web của LockBit bị phá hoại với liên kết tới cơ sở dữ liệu](https://www.bleepstatic.com/images/news/ransomware/l/lockbit/admin-panel-data-breach/lockbit-panel-breached.png)

**Trang web dark web của LockBit bị phá hoại với liên kết tới cơ sở dữ liệu**

Theo [phát hiện đầu tiên](https://x.com/ReyXBF/status/1920220381681418713) bởi tác nhân đe dọa, Rey, tệp lưu trữ này chứa một tệp SQL được dump từ cơ sở dữ liệu MySQL của bảng affiliate.

Từ phân tích của BleepingComputer, cơ sở dữ liệu này chứa hai mươi bảng, trong đó một số bảng thú vị hơn những bảng khác, bao gồm:

* Một bảng '**btc\_addresses**' chứa 59,975 địa chỉ bitcoin duy nhất.
* Một bảng '**builds**' chứa các bản build riêng lẻ được tạo bởi các affiliate cho các cuộc tấn công. Các hàng trong bảng chứa các khóa công khai, nhưng không có khóa riêng, thật không may. Tên của các công ty mục tiêu cũng được liệt kê cho một số bản build.
* Một bảng '**builds\_configurations**' chứa các cấu hình khác nhau được sử dụng cho từng build, chẳng hạn như các máy chủ ESXi nào cần bỏ qua hay các tệp nào cần mã hóa.
* Một bảng '**chats**' rất thú vị vì nó chứa 4,442 tin nhắn thương lượng giữa hoạt động ransomware và các nạn nhân từ ngày 19 tháng 12 đến ngày 29 tháng 4.  
![Bảng 'chats' của bảng affiliate](https://www.bleepstatic.com/images/news/ransomware/l/lockbit/admin-panel-data-breach/chats-table.png)  
**Bảng 'chats' của bảng affiliate**
* Một bảng '**users**' liệt kê 75 quản trị viên và affiliate đã có quyền truy cập vào bảng affiliate, với [Michael Gillespie](https://x.com/demonslay335) phát hiện rằng mật khẩu được lưu trữ ở dạng văn bản không mã hóa. Ví dụ về một số mật khẩu văn bản không mã hóa là 'Weekendlover69', 'MovingBricks69420', và 'Lockbitproud231'.

Dựa trên ngày ghi cuối cùng trong bảng chat thương lượng, cơ sở dữ liệu dường như đã được dump vào một thời điểm nào đó vào ngày 29 tháng 4 năm 2025.

Chưa rõ ai đã thực hiện vụ rò rỉ và cách thức thực hiện, nhưng thông điệp phá hoại giống với thông điệp đã được sử dụng trong một vụ [xâm nhập gần đây của trang web dark web Everest ransomware](https://www.bleepingcomputer.com/news/security/everest-ransomwares-dark-web-leak-site-defaced-now-offline/), gợi ý một liên kết có thể xảy ra.

Hơn nữa, tệp dump phpMyAdmin SQL cho thấy máy chủ đang chạy PHP 8.1.2, phiên bản này có lỗ hổng nghiêm trọng và đang bị khai thác mạnh mẽ được theo dõi dưới mã [CVE-2024-4577](https://www.bleepingcomputer.com/news/security/critical-php-rce-vulnerability-mass-exploited-in-new-attacks/) có thể được sử dụng để đạt được khả năng thực thi mã từ xa trên máy chủ. 

Vào năm 2024, một chiến dịch thực thi pháp luật mang tên Operation Cronos [đã xóa bỏ cơ sở hạ tầng của LockBit](https://www.bleepingcomputer.com/news/security/lockbit-ransomware-disrupted-by-global-police-operation/), bao gồm 34 máy chủ lưu trữ trang web rò rỉ dữ liệu và các gương của nó, dữ liệu bị đánh cắp từ các nạn nhân, địa chỉ tiền điện tử, 1,000 khóa giải mã, và bảng affiliate.

Mặc dù LockBit đã quản lý để tái thiết và tiếp tục hoạt động sau khi bị tấn công, rò rỉ mới nhất này lại tiếp tục gây thêm tổn hại đến danh tiếng vốn đã bị tổn thất của nó.

Vẫn còn quá sớm để biết liệu cú đánh danh tiếng bổ sung này có phải là chiếc đinh cuối cùng trong quan tài của băng nhóm ransomware hay không.

Các nhóm ransomware khác đã trải qua những vụ rò rỉ tương tự bao gồm [Conti](https://www.bleepingcomputer.com/news/security/conti-ransomwares-internal-chats-leaked-after-siding-with-russia/), [Black Basta](https://www.bleepingcomputer.com/news/security/black-basta-ransomware-gang-s-internal-chat-logs-leak-online/), và [Everest](https://www.bleepingcomputer.com/news/security/everest-ransomwares-dark-web-leak-site-defaced-now-offline/).