# CTM360 Theo Dõi Cuộc Tấn Công Gia Tăng Toàn Cầu Qua SMS Dựa Trên Giải Thưởng và Thu Phí

![CTM360 report](https://www.bleepstatic.com/content/posts/2025/04/16/ctm360-header.jpg)

[CTM360](http://www.ctm360.com) đã quan sát thấy sự gia tăng đáng kể trong hai chiến dịch lừa đảo qua SMS: PointyPhish (lừa đảo giải thưởng) và TollShark (lừa đảo thu phí).

PointyPhish liên kết với hơn 3.000 miền và các trang web lừa đảo, lợi dụng cảm giác khẩn cấp bằng cách tuyên bố các điểm thưởng sắp hết hạn để đánh lừa khách hàng vào các trang web giả mạo để đánh cắp thông tin thanh toán.

Tương tự, TollShark liên quan đến hơn 2.000 miền và các trang web lừa đảo, khai thác nỗi lo về việc không thanh toán phí qua đường để thu thập thông tin nhạy cảm từ những người không nghi ngờ.  

CTM360 phát hiện hàng ngàn trang web lừa đảo này ở nhiều quốc gia, cho thấy rằng đây không chỉ là một vấn đề địa phương — mà là một nỗ lực toàn cầu có phối hợp. Tính chất lan rộng của các cuộc tấn công này cho thấy một ý định rõ ràng để nhắm mục tiêu vào các cá nhân trên quy mô lớn, với mục tiêu là đánh cắp dữ liệu tài chính nhạy cảm.

Ảnh hưởng là rất lớn, ảnh hưởng không chỉ đến một khu vực mà còn hàng nghìn khách hàng của nhiều thương hiệu trên toàn cầu.

Tại trung tâm của những chiến dịch này là Darcula Suite, một nền tảng mạnh mẽ Phishing-as-a-Service (PhaaS). Được xây dựng trên React và Docker, Darcula cho phép tội phạm mạng khởi chạy các trang web lừa đảo chỉ trong vòng chưa đầy 10 phút.

Nó hỗ trợ phân phối SMS đa kênh (bao gồm iMessage và RCS), làm cho các trang web khó bị phát hiện và dễ mở rộng toàn cầu hơn.

## **Hai Chiến Dịch Khác Biệt, Một Chiến Thuật Chung**

1. **PointyPhish –** Gửi tin nhắn SMS giả về các điểm thưởng sắp hết hạn đến khách hàng của ngân hàng, hãng hàng không, và các cửa hàng bán lẻ, dẫn đến các trang lừa đảo đánh cắp thông tin thẻ tín dụng/thẻ ghi nợ đầy đủ.
1. **TollShark –** Giả mạo là các cơ quan thu phí đường bộ, cảnh báo về các hóa đơn và khoản phạt chưa thanh toán. Nạn nhân được hướng đến các trang thanh toán giả mạo thu thập thông tin cá nhân và tài chính.

Cả hai cuộc tấn công đều đơn giản về cấu trúc: chúng bắt đầu bằng việc phân phối tin nhắn SMS, tạo sự khẩn cấp, giả mạo một thương hiệu đáng tin cậy, và dẫn khách hàng đến việc cung cấp thông tin thanh toán.

![Toll Shark phishing texts](https://www.bleepstatic.com/images/news/security/c/ctm360/ctm360-report/ctm360-phishing.jpg)

## [Đọc báo cáo PlayPraetor mới của chúng tôi để khám phá hành vi, thông tin phát hiện](https://www.ctm360.com/reports/play-masquerading-party-report?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sidebar&utm%5Fcampaign=ctm360%5Fbleepingcomputer)

CTM360 hiện đã xác định một quy mô lớn hơn nhiều của chiến dịch PlayPraetor đang diễn ra.

Bắt đầu từ 6.000+ URL liên kết với một cuộc tấn công ngân hàng cụ thể, giờ đây đã phát triển lên hơn 16.000 trang giả mạo trên nhiều biến thể malware khác nhau. Nghiên cứu này đang được tiếp tục, với những phát hiện thêm dự kiến trong những ngày tới.

[Đọc Báo cáo](https://www.ctm360.com/reports/play-masquerading-party-report?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sidebar&utm%5Fcampaign=ctm360%5Fbleepingcomputer)

## Cách Thức Hoạt Động – Bước Từng Bước

![Scam stages](https://www.bleepstatic.com/images/news/security/c/ctm360/ctm360-report/scam-stages.png)

Các nhà phân tích đe dọa của CTM360 đã lập bản đồ toàn bộ vòng đời tấn công bằng cách sử dụng CTM360 Scam Navigator và phân tích từng bước một cách chi tiết.

1. **Phân phối SMS:**  
 Các tin nhắn tạo ra sự khẩn cấp, hoặc một khoản phí chưa được thanh toán, hoặc các điểm sắp hết hạn.
2. **Trang đích giả:**  
 Nạn nhân bị chuyển hướng đến các trang phishing giả mạo thương hiệu thực.
3. **Sự thu hút & mồi nhử:**  
 Nạn nhân được yêu cầu đổi điểm hoặc thanh toán phí để tránh bị phạt.
4. **Thu thập dữ liệu:**  
 Dữ liệu cá nhân được thu thập dưới vỏ bọc xác minh.
5. **Đánh cắp dữ liệu thanh toán:**  
 Nạn nhân bị lừa nhập thông tin thẻ, được ghi lại ngay lập tức.

## Bên Trong Darcula: Một Cái Nhìn Về PhaaS

Darcula không chỉ là một bộ công cụ lừa đảo — mà là một nền tảng PhaaS đầy đủ cho các trò lừa đảo. Trong quá trình theo dõi các chiến dịch này, CTM360 đã phát hiện một bảng điều khiển quản trị được lộ ra của những kẻ tấn công đang quản lý Darcula Suite.

Điều này cung cấp một cái nhìn hiếm hoi về cách thức điều hành các hoạt động lừa đảo này:

* **Quản lý chiến dịch tập trung:** Nhiều tài khoản tấn công chạy các chiến dịch song song.
* **Ghi lại nạn nhân trực tiếp:** Địa chỉ IP, thông tin thiết bị, user agents, và dữ liệu biểu mẫu được ghi lại theo thời gian thực.
* **Truy cập dựa trên đăng ký:** Những kẻ tấn công hoạt động theo mô hình phân cấp với các điều khiển dựa trên tài khoản.
* **Công cụ cấu hình SMS:** Các công cụ tích hợp để quản lý các khu vực mục tiêu và mẫu tin nhắn.

## Đọc báo cáo đầy đủ về PointyPhish & TollShark

Để có cái nhìn sâu hơn vào các chiến dịch. bao gồm chụp màn hình, mẫu miền và thông tin chi tiết về cách mà các trò lừa đảo được cấu trúc và hoạt động trên quy mô toàn cầu, hãy đọc báo cáo đầy đủ tại **<https://www.ctm360.com/reports/pointyphish-tollshark>**.

_Nội dung được tài trợ và viết bởi [CTM360](https://www.ctm360.com?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=article&utm%5Fcampaign=ctm360%5Fbleepingcomputer)._