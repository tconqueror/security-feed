# CTM360 Theo Dõi Tình Trạng Tăng Đột Biến Toàn Cầu Trong Các Chiến Dịch Lừa Đảo Qua SMS Về Tiền Thưởng và Phí Đường

![CTM360 report](https://www.bleepstatic.com/content/posts/2025/04/16/ctm360-header.jpg)

[CTM360](http://www.ctm360.com) đã quan sát thấy một sự gia tăng đáng chú ý trong hai chiến dịch lừa đảo qua SMS: PointyPhish (lừa đảo về tiền thưởng) và TollShark (lừa đảo về thanh toán phí đường).

PointyPhish liên quan đến hơn 3,000 miền và trang web lừa đảo, lợi dụng sự khẩn cấp bằng cách tuyên bố rằng điểm thưởng sắp hết hạn để lừa đảo khách hàng vào các trang web gian lận đánh cắp thông tin thanh toán.

Tương tự, TollShark liên quan đến hơn 2,000 miền và trang web lừa đảo, khai thác nỗi sợ về việc chưa thanh toán phí đường để thu thập thông tin nhạy cảm từ những cá nhân không nghi ngờ.  
CTM360 đã phát hiện hàng nghìn trang web lừa đảo này trên nhiều quốc gia, cho thấy rằng đây không chỉ là một vấn đề cục bộ — mà là một nỗ lực có phối hợp toàn cầu. Tính phổ biến của những cuộc tấn công này cho thấy một ý định rõ ràng nhằm mục tiêu vào các cá nhân ở quy mô lớn, với mục tiêu đánh cắp dữ liệu tài chính nhạy cảm.

Tác động rất rộng lớn, không chỉ ảnh hưởng đến một khu vực mà còn hàng nghìn khách hàng của nhiều thương hiệu trên toàn thế giới.

Tại cốt lõi của các chiến dịch này là Darcula Suite, một nền tảng Phishing-as-a-Service (PhaaS) mạnh mẽ. Được xây dựng trên React và Docker, Darcula cho phép tội phạm mạng khởi chạy các trang web lừa đảo trong chưa đầy 10 phút.

Nó hỗ trợ gửi SMS qua nhiều kênh (bao gồm iMessage và RCS), khiến các trang web khó phát hiện và dễ dàng mở rộng trên toàn cầu.

## **Hai Chiến Dịch Khác Nhau, Một Chiến Thuật Chung**

1. **PointyPhish –** Gửi thông báo SMS giả về điểm thưởng sắp hết hạn đến khách hàng của ngân hàng, hãng hàng không và cửa hàng bán lẻ, dẫn đến các trang lừa đảo đánh cắp thông tin thẻ tín dụng/thẻ ghi nợ.
1. **TollShark –** Giả mạo các cơ quan thu phí đường, cảnh báo về các hóa đơn và khoản phạt chưa thanh toán. Các nạn nhân được hướng đến các trang thanh toán giả mạo thu thập dữ liệu cá nhân và tài chính.

Cả hai cuộc tấn công đều có cấu trúc đơn giản: chúng bắt đầu với việc phân phối SMS, tạo sự khẩn cấp, mạo danh một thương hiệu đáng tin cậy và dẫn khách hàng vào việc cung cấp thông tin thanh toán.

![Toll Shark phishing texts](https://www.bleepstatic.com/images/news/security/c/ctm360/ctm360-report/ctm360-phishing.jpg)

## [Đọc báo cáo PlayPraetor mới của chúng tôi để khám phá hành vi, thông tin phát hiện](https://www.ctm360.com/reports/play-masquerading-party-report?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sidebar&utm%5Fcampaign=ctm360%5Fbleepingcomputer)

CTM360 hiện đã xác định được quy mô lớn hơn nhiều của chiến dịch PlayPraetor đang diễn ra.

Những gì bắt đầu với hơn 6,000 URL liên kết đến một cuộc tấn công ngân hàng cụ thể đã phát triển thành hơn 16,000 trang giả mạo trên nhiều biến thể malware khác nhau. Nghiên cứu này vẫn đang diễn ra, với nhiều phát hiện hơn được mong đợi trong những ngày tới.

[Đọc báo cáo](https://www.ctm360.com/reports/play-masquerading-party-report?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sidebar&utm%5Fcampaign=ctm360%5Fbleepingcomputer)

## Cách Thức Hoạt Động – Từng Bước Một

![Scam stages](https://www.bleepstatic.com/images/news/security/c/ctm360/ctm360-report/scam-stages.png)

Các nhà phân tích đe dọa của CTM360 đã lập bản đồ toàn bộ chu kỳ tấn công bằng cách sử dụng CTM360 Scam Navigator và phân tích từng bước chi tiết.

1. **Phân phối SMS:**  
 Các tin nhắn tạo ra sự khẩn cấp, hoặc phí chưa thanh toán, hoặc các điểm sắp hết hạn.
2. **Trang đích giả mạo:**  
 Các nạn nhân được chuyển hướng đến các trang web lừa đảo giả mạo các thương hiệu thực.
3. **Tương tác & mồi nhử:**  
 Các nạn nhân được yêu cầu đổi điểm hoặc thanh toán phí để tránh bị phạt.
4. **Thu thập dữ liệu:**  
 Dữ liệu cá nhân được thu thập dưới bình phong xác minh.
5. **Đánh cắp thông tin thanh toán:**  
 Các nạn nhân bị lừa nhập thông tin thẻ, thông tin sẽ được ghi lại ngay lập tức.

## Bên Trong Darcula: Một Cái Nhìn Về PhaaS

Darcula không chỉ là một bộ công cụ lừa đảo — mà là một nền tảng PhaaS hoàn chỉnh cho các chiêu trò lừa đảo. Trong khi theo dõi các chiến dịch này, CTM360 đã phát hiện một bảng điều khiển quản trị bị lộ được sử dụng bởi những kẻ tấn công quản lý Darcula Suite.

Điều này cung cấp cái nhìn hiếm có về cách thức các hoạt động lừa đảo này được vận hành:

* **Quản lý chiến dịch tập trung:** Nhiều tài khoản tấn công chạy các chiến dịch song song.
* **Ghi log nạn nhân trực tiếp:** Địa chỉ IP, thông tin thiết bị, user agents và dữ liệu biểu mẫu được ghi lại theo thời gian thực.
* **Truy cập dựa trên đăng ký:** Những kẻ tấn công hoạt động theo mô hình nhiều cấp với các kiểm soát dựa trên tài khoản.
* **Công cụ cấu hình SMS:** Các công cụ tích hợp để quản lý các khu vực mục tiêu và mẫu tin nhắn.

## Đọc báo cáo đầy đủ về PointyPhish & TollShark

Để tìm hiểu sâu hơn về các chiến dịch, bao gồm hình chụp màn hình, mẫu miền và thông tin về cách các chiêu trò này được cấu trúc và hoạt động trên quy mô toàn cầu, hãy đọc báo cáo đầy đủ tại **<https://www.ctm360.com/reports/pointyphish-tollshark>**.

_Được tài trợ và viết bởi [CTM360](https://www.ctm360.com?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=article&utm%5Fcampaign=ctm360%5Fbleepingcomputer)._