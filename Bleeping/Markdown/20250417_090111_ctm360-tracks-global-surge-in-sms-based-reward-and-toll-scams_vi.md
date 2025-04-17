# CTM360 Theo Dõi Sự Tăng Trưởng Toàn Cầu Về Các Cuộc Lừa Đảo Dựa Trên SMS Về Giải Thưởng và Thanh Toán Phí

![CTM360 report](https://www.bleepstatic.com/content/posts/2025/04/16/ctm360-header.jpg)

[CTM360](http://www.ctm360.com) đã quan sát thấy một sự gia tăng đáng chú ý trong hai chiến dịch lừa đảo qua SMS: PointyPhish (lừa đảo giải thưởng) và TollShark (lừa đảo thanh toán phí).

PointyPhish liên quan đến hơn 3,000 miền và trang web lừa đảo, lợi dụng tính khẩn cấp bằng cách tuyên bố rằng các điểm thưởng sắp hết hiệu lực để lừa khách hàng vào các trang gian lận lấy cắp thông tin thanh toán.

Tương tự, TollShark liên quan đến hơn 2,000 miền và trang web lừa đảo, khai thác nỗi sợ hãi về các khoản phí chưa thanh toán để thu thập thông tin nhạy cảm từ những người không nghi ngờ.  

CTM360 đã phát hiện hàng ngàn trang web lừa đảo này ở nhiều quốc gia, cho thấy rằng đây không chỉ là một vấn đề cục bộ - mà là một nỗ lực phối hợp toàn cầu. Tính chất lan rộng của các cuộc tấn công này cho thấy một ý định rõ ràng là nhắm tới các cá nhân trên quy mô lớn, với mục tiêu là đánh cắp thông tin tài chính nhạy cảm.

Tác động là rất lớn, ảnh hưởng không chỉ đến một khu vực mà còn hàng ngàn khách hàng của nhiều thương hiệu trên toàn thế giới.

Tại trung tâm của các chiến dịch này là Darcula Suite, một nền tảng Phishing-as-a-Service (PhaaS) mạnh mẽ. Được xây dựng trên React và Docker, Darcula cho phép tội phạm mạng khởi chạy các trang lừa đảo trong vòng chưa đầy 10 phút.

Nó hỗ trợ phân phối SMS đa kênh (bao gồm iMessage và RCS), làm cho các trang web khó bị phát hiện hơn và dễ dàng mở rộng trên toàn cầu.

## **Hai Chiến Dịch Khác Nhau, Một Chiến Thuật Chung**

1. **PointyPhish –** Gửi các cảnh báo SMS giả về việc các điểm thưởng sắp hết hạn cho khách hàng ngân hàng, hàng không và cửa hàng bán lẻ, dẫn đến các trang lừa đảo lấy cắp toàn bộ thông tin thẻ tín dụng/thẻ ghi nợ.
1. **TollShark –** Giả làm cơ quan thu phí đường bộ, cảnh báo về các hóa đơn và tiền phạt chưa thanh toán. Nạn nhân được hướng đến các trang thanh toán giả thu thập thông tin cá nhân và tài chính.

Cả hai cuộc tấn công đều có cấu trúc đơn giản: chúng bắt đầu bằng việc phân phối SMS, tạo sự khẩn cấp, mạo danh một thương hiệu đáng tin cậy và khiến khách hàng cung cấp thông tin thanh toán.

![Toll Shark phishing texts](https://www.bleepstatic.com/images/news/security/c/ctm360/ctm360-report/ctm360-phishing.jpg)

## [Đọc báo cáo PlayPraetor mới của chúng tôi để khám phá các hành vi, thông tin phát hiện](https://www.ctm360.com/reports/play-masquerading-party-report?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sidebar&utm%5Fcampaign=ctm360%5Fbleepingcomputer)

CTM360 hiện đã xác định được quy mô lớn hơn nhiều của chiến dịch PlayPraetor đang diễn ra.

Bắt đầu với hơn 6,000 URL liên quan đến một cuộc tấn công ngân hàng cụ thể, số lượng này đã tăng lên hơn 16,000 trang web mạo danh trên nhiều biến thể malware. Nghiên cứu này vẫn đang tiếp tục, với những phát hiện mới dự kiến sẽ xuất hiện trong những ngày tới.

[Đọc báo cáo](https://www.ctm360.com/reports/play-masquerading-party-report?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sidebar&utm%5Fcampaign=ctm360%5Fbleepingcomputer)

## Cách Thức Hoạt Động – Từng Bước

![Scam stages](https://www.bleepstatic.com/images/news/security/c/ctm360/ctm360-report/scam-stages.png)

Các nhà phân tích mối đe dọa của CTM360 đã lập bản đồ toàn bộ vòng đời tấn công bằng cách sử dụng CTM360 Scam Navigator và phân tích từng bước một cách chi tiết.

1. **Phân phối SMS:**  
 Các tin nhắn tạo ra sự khẩn cấp, hoặc một khoản phí chưa thanh toán, hoặc các điểm sắp hết hạn.
2. **Trang đích giả mạo:**  
 Nạn nhân được chuyển hướng đến các trang web lừa đảo giả mạo thương hiệu thực.
3. **Tương tác & mồi nhử:**  
 Nạn nhân được yêu cầu đổi điểm hoặc thanh toán phí để tránh bị phạt.
4. **Thu thập dữ liệu:**  
 Dữ liệu cá nhân được thu thập dưới cái nhìn của xác minh.
5. **Lấy cắp dữ liệu thanh toán:**  
 Nạn nhân bị lừa nhập thông tin thẻ, mà ngay lập tức được ghi lại.

## Bên Trong Darcula: Một Cái Nhìn về PhaaS

Darcula không chỉ là một bộ công cụ lừa đảo - mà là một nền tảng PhaaS hoàn chỉnh cho các cuộc lừa đảo. Trong khi theo dõi các chiến dịch này, CTM360 đã phát hiện một bảng điều khiển quản trị bị lộ được sử dụng bởi các kẻ tấn công quản lý Darcula Suite.

Điều này cung cấp một cái nhìn hiếm hoi về cách mà các hoạt động lừa đảo này được thực hiện:

* **Quản lý chiến dịch tập trung:** Nhiều tài khoản kẻ tấn công chạy các chiến dịch song song.
* **Ghi lại nạn nhân trực tiếp:** Địa chỉ IP, thông tin thiết bị, user agents và dữ liệu biểu mẫu được ghi lại theo thời gian thực.
* **Truy cập dựa trên đăng ký:** Các kẻ tấn công hoạt động theo mô hình phân cấp với các kiểm soát dựa trên tài khoản.
* **Công cụ cấu hình SMS:** Các công cụ tích hợp để quản lý các vùng mục tiêu và mẫu tin nhắn.

## Đọc báo cáo đầy đủ về PointyPhish & TollShark

Để có cái nhìn sâu hơn về các chiến dịch, bao gồm các ảnh chụp màn hình, mẫu miền và thông tin về cách các trò lừa đảo này được cấu trúc và hoạt động trên quy mô toàn cầu, hãy đọc báo cáo đầy đủ tại **<https://www.ctm360.com/reports/pointyphish-tollshark>**.

_Được tài trợ và viết bởi [CTM360](https://www.ctm360.com?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=article&utm%5Fcampaign=ctm360%5Fbleepingcomputer)._