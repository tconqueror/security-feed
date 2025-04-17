# CTM360 Theo Dõi Sự Tăng Trưởng Toàn Cầu trong Các Cuộc Lừa Đảo Dựa Trên SMS về Phần Thưởng và Thu Phí

![Báo cáo CTM360](https://www.bleepstatic.com/content/posts/2025/04/16/ctm360-header.jpg)

[CTM360](http://www.ctm360.com) đã quan sát thấy sự gia tăng đáng chú ý trong hai chiến dịch lừa đảo qua SMS: PointyPhish (lừa đảo phần thưởng) và TollShark (lừa đảo thanh toán thu phí).

PointyPhish liên kết với hơn 3.000 miền và trang web lừa đảo, lợi dụng sự khẩn cấp bằng cách tuyên bố rằng điểm thưởng sắp hết hạn để đánh lừa khách hàng vào các trang giả mạo đánh cắp thông tin thanh toán.

Tương tự, TollShark liên quan đến hơn 2.000 miền và trang web lừa đảo, lợi dụng nỗi sợ về việc chưa thanh toán thu phí để thu thập thông tin nhạy cảm từ những cá nhân không nghi ngờ.
  
CTM360 đã phát hiện hàng ngàn trang web lừa đảo này trên nhiều quốc gia, cho thấy rằng đây không chỉ là một vấn đề cục bộ - đây là một nỗ lực toàn cầu có phối hợp. Tính chất rộng rãi của các cuộc tấn công này cho thấy một ý định rõ ràng nhằm mục tiêu vào cá nhân trên quy mô lớn, với mục tiêu đánh cắp dữ liệu tài chính nhạy cảm.

Tác động của nó thật sâu rộng, ảnh hưởng không chỉ đến một khu vực mà còn hàng ngàn khách hàng của nhiều thương hiệu trên toàn thế giới.

Tại trung tâm của các chiến dịch này là Darcula Suite, một nền tảng Phishing-as-a-Service (PhaaS) mạnh mẽ. Được xây dựng trên React và Docker, Darcula cho phép tội phạm mạng khởi động các trang lừa đảo trong vòng chưa đầy 10 phút.

Nó hỗ trợ giao hàng SMS đa kênh (bao gồm iMessage và RCS), làm cho các trang web khó phát hiện hơn và dễ dàng mở rộng quy mô toàn cầu.

## **Hai Chiến Dịch Khác Nhau, Một Chiến Thuật Chung**

1. **PointyPhish –** Gửi tin nhắn SMS giả mạo về điểm thưởng sắp hết hạn cho khách hàng của các ngân hàng, hãng hàng không và cửa hàng bán lẻ, dẫn đến các trang lừa đảo đánh cắp thông tin thẻ tín dụng / thẻ ghi nợ.
1. **TollShark –** Giả làm cơ quan thu phí đường bộ, cảnh báo về các hóa đơn và khoản phạt chưa thanh toán. Nạn nhân được dẫn đến các trang thanh toán giả mạo thu thập dữ liệu cá nhân và tài chính.

Cả hai cuộc tấn công đều có cấu trúc đơn giản: bắt đầu bằng việc phân phối SMS, tạo sự khẩn cấp, mạo danh một thương hiệu đáng tin cậy, và dẫn dắt khách hàng vào việc cung cấp thông tin thanh toán.

![Tin nhắn lừa đảo Toll Shark](https://www.bleepstatic.com/images/news/security/c/ctm360/ctm360-report/ctm360-phishing.jpg)

## [Đọc báo cáo PlayPraetor mới của chúng tôi để khám phá hành vi, thông tin phát hiện](https://www.ctm360.com/reports/play-masquerading-party-report?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sidebar&utm%5Fcampaign=ctm360%5Fbleepingcomputer)

CTM360 đã xác định quy mô lớn hơn nhiều của chiến dịch PlayPraetor đang diễn ra.

Những gì bắt đầu với hơn 6.000 URL liên kết đến một cuộc tấn công ngân hàng cụ thể giờ đây đã phát triển lên hơn 16.000 trang giả mạo trên nhiều biến thể phần mềm độc hại. Nghiên cứu này đang tiếp diễn, với những phát hiện thêm dự kiến sẽ diễn ra trong những ngày tới.

[Đọc Báo cáo](https://www.ctm360.com/reports/play-masquerading-party-report?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sidebar&utm%5Fcampaign=ctm360%5Fbleepingcomputer)

## Cách Hoạt Động – Từng Bước Một

![Giai đoạn lừa đảo](https://www.bleepstatic.com/images/news/security/c/ctm360/ctm360-report/scam-stages.png)

Các nhà phân tích mối đe dọa của CTM360 đã lập bản đồ toàn bộ vòng đời tấn công bằng cách sử dụng CTM360 Scam Navigator và phân tích chi tiết từng bước.

1. **Phân phối SMS:**  
 Tin nhắn tạo ra sự khẩn cấp, hoặc một khoản phí chưa được thanh toán, hoặc điểm sắp hết hạn.
2. **Trang đích giả mạo:**  
 Nạn nhân được chuyển hướng đến các trang lừa đảo giả mạo các thương hiệu thực.
3. **Giao tiếp và mồi nhử:**  
 Nạn nhân được yêu cầu đổi điểm hoặc thanh toán phí để tránh phạt.
4. **Thu thập dữ liệu:**  
 Dữ liệu cá nhân được thu thập dưới hình thức xác minh.
5. **Đánh cắp dữ liệu thanh toán:**  
 Nạn nhân bị đánh lừa nhập thông tin thẻ, điều này được ghi lại ngay lập tức.

## Bên Trong Darcula: Một Lần Nhìn Về PhaaS

Darcula không chỉ là một bộ công cụ lừa đảo — nó là một nền tảng PhaaS hoàn chỉnh cho các trò lừa đảo. Trong khi theo dõi các chiến dịch này, CTM360 đã phát hiện một bảng điều khiển quản trị bị lộ được các kẻ tấn công sử dụng để quản lý Darcula Suite.

Điều này cung cấp một cái nhìn hiếm có về cách mà các hoạt động lừa đảo này được thực hiện:

* **Quản lý chiến dịch tập trung:** Nhiều tài khoản tấn công chạy các chiến dịch song song.
* **Ghi lại nạn nhân thời gian thực:** Địa chỉ IP, thông tin thiết bị, tác nhân người dùng và dữ liệu biểu mẫu được ghi lại trong thời gian thực.
* **Truy cập dựa trên đăng ký:** Các kẻ tấn công hoạt động theo mô hình phân tầng với các kiểm soát dựa trên tài khoản.
* **Công cụ cấu hình SMS:** Các công cụ tích hợp sẵn để quản lý các khu vực mục tiêu và mẫu tin nhắn.

## Đọc Báo Cáo Đầy Đủ về PointyPhish & TollShark

Để cái nhìn sâu hơn về các chiến dịch, bao gồm ảnh chụp màn hình, mẫu miền và thông tin về cách mà các trò lừa đảo được cấu trúc và hoạt động trên quy mô toàn cầu, hãy đọc báo cáo đầy đủ tại **<https://www.ctm360.com/reports/pointyphish-tollshark>**.

_Được tài trợ và viết bởi [CTM360](https://www.ctm360.com?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=article&utm%5Fcampaign=ctm360%5Fbleepingcomputer)._