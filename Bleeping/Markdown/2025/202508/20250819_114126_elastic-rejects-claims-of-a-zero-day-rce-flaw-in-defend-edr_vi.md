# Elastic từ chối các thông tin về lỗ hổng RCE zero-day trong Defend EDR

![Elastic từ chối các thông tin về lỗ hổng RCE zero-day trong Defend EDR](https://www.bleepstatic.com/content/hl-images/2024/12/10/hacker-box.jpg)

Công ty tìm kiếm và bảo mật doanh nghiệp Elastic đã bác bỏ các báo cáo về một lỗ hổng zero-day ảnh hưởng đến sản phẩm phát hiện và phản hồi điểm cuối (EDR) của mình, Defend.

Tuyên bố của công ty được đưa ra sau một bài viết trên blog của một công ty có tên AshES Cybersecurity, tuyên bố đã phát hiện lỗ hổng thực thi mã từ xa (RCE) trong Elastic Defend, cho phép kẻ tấn công vượt qua các biện pháp bảo vệ EDR.

Nhóm Kỹ thuật An ninh của Elastic "đã tiến hành một cuộc điều tra kỹ lưỡng" nhưng không thể tìm thấy "bằng chứng hỗ trợ cho các cáo buộc về một lỗ hổng vượt qua giám sát EDR và cho phép thực thi mã từ xa."

### Các cáo buộc zero-day

Theo [bài viết](http://ashes-cybersecurity.com/0-day-research/) của AshES Cybersecurity từ ngày 16 tháng 8, một lỗi tham chiếu con trỏ NULL trong trình điều khiển kernel của Elastic Defender, ‘elastic-endpoint-driver.sys’ có thể bị khai thác để vượt qua giám sát EDR, cho phép thực thi mã từ xa với khả năng hiển thị bị giảm và thiết lập sự tồn tại trên hệ thống.

"Để chứng minh khái niệm, tôi đã sử dụng một trình điều khiển tùy chỉnh để kích hoạt lỗi một cách đáng tin cậy trong điều kiện kiểm soát," nhà nghiên cứu của AshES Cybersecurity cho biết.

Để chứng minh tính hợp lệ của phát hiện, công ty đã công bố hai video, một video cho thấy Windows gặp sự cố vì trình điều khiển của Elastic đã thất bại, và video khác cho thấy khai thác được cho là khởi động calc.exe mà không có EDR Defend của Elastic hành động.

“Lỗi 0-day của trình điều khiển Elastic không chỉ là một lỗi ổn định. Nó cho phép một chuỗi tấn công đầy đủ mà kẻ thù có thể khai thác trong các môi trường thực tế," nhà nghiên cứu khẳng định.

### Sự từ chối của Elastic

Sau khi đánh giá các cáo buộc và báo cáo từ AshES Cybersecurity, Elastic không thể tái tạo lại lỗ hổng và các tác động của nó.

Hơn nữa, Elastic cho biết rằng các báo cáo mà họ nhận được từ AshES Cybersecurity về lỗ hổng zero-day bị cáo buộc "thiếu bằng chứng về các khai thác có thể tái tạo."

"Nhóm Kỹ thuật An ninh Elastic và đội ngũ phân loại bug bounty của chúng tôi đã hoàn thành một phân tích kỹ lưỡng để cố gắng tái tạo những báo cáo này nhưng không thành công. Các nhà nghiên cứu được yêu cầu chia sẻ các chứng minh khái niệm có thể tái tạo; tuy nhiên, họ đã từ chối" - [Elastic](https://www.elastic.co/blog/elastic-response-edr-0-day-vulnerability-blog)

AshES Cybersecurity [xác nhận](https://www.documentcloud.org/documents/26055314-ashes-cybersecurity-elastic-0-day-statement/) rằng họ đã chọn không gửi PoC cho Elastic hoặc các chi nhánh của công ty.

Elastic cho biết rằng nhà nghiên cứu đã không chia sẻ đầy đủ chi tiết về lỗ hổng mà thay vào đó quyết định công bố các cáo buộc của họ công khai thay vì theo các nguyên tắc của việc công bố có phối hợp.

Elastic đã khẳng định rằng họ xem tất cả các báo cáo bảo mật một cách nghiêm túc và, bắt đầu từ năm 2017, đã trả hơn 600,000 đô la cho các nhà nghiên cứu thông qua chương trình bug bounty của công ty.