# Các gói npm độc hại giả làm tiện ích xóa thư mục dự án

![NPM](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_logo_headpic.jpg)

Hai gói độc hại đã được phát hiện trong chỉ mục gói npm JavaScript, giả làm các tiện ích hữu ích nhưng trên thực tế lại là những công cụ xóa dữ liệu hủy diệt, xóa toàn bộ thư mục ứng dụng.

Các gói xóa dữ liệu là 'express-api-sync' và 'system-health-sync-api,' và giả làm các công cụ đồng bộ cơ sở dữ liệu và giám sát sức khỏe hệ thống.

Theo công ty bảo mật phần mềm nguồn mở Socket, cả hai gói này đều chứa backdoor cho phép thực hiện các hành động xóa dữ liệu từ xa trên máy tính bị nhiễm.

Các gói này được xuất bản trên npm vào tháng 5 năm 2025 và đã bị gỡ bỏ sau khi được Socket báo cáo.

Số liệu lịch sử của công ty cho thấy express-api-sync đã được các nhà phát triển không nghi ngờ tải về [855 lần](https://socket.dev/npm/package/system-health-sync-api), trong khi express-api-sync đã có [104 lượt tải](https://socket.dev/npm/package/express-api-sync).

Gói đầu tiên, express-api-sync, đăng ký một endpoint POST ẩn (/api/this/that) và chờ các yêu cầu chứa khóa bí mật 'DEFAULT\_123.'

Khi nhận được, nó thực thi "rm -rf \*" trong thư mục ứng dụng, xóa tất cả các tệp.

"Khi được kích hoạt, lệnh rm -rf \* sẽ được thực thi trong thư mục làm việc của ứng dụng, xóa tất cả các tệp, bao gồm mã nguồn, tệp cấu hình, tài sản đã tải lên và bất kỳ cơ sở dữ liệu cục bộ nào," giải thích [báo cáo của Socket](http://socket.dev/blog/destructive-npm-packages-enable-remote-system-wipe).

"Endpoint trả về thông báo trạng thái cho kẻ tấn công cho biết thành công ({"message":"Tất cả các tệp đã bị xóa"}) hoặc thất bại của việc phá hủy."

Gói thứ hai, 'system-health-sync-api,' tinh vi hơn.

Nó đăng ký nhiều endpoint backdoor tại:

* GET /\_/system/health → trả về trạng thái máy chủ
* POST /\_/system/health → endpoint phá hủy chính
* POST /\_/sys/maintenance → endpoint phá hủy dự phòng

Trong trường hợp này, khóa bí mật là 'HelloWorld,' kích hoạt hoạt động do thám theo sau là sự hủy diệt riêng của hệ điều hành từ xa.

Công cụ xóa hỗ trợ cả lệnh xóa trên Linux ('rm -rf \*') và Windows ('rd /s /q .'), do đó nó sử dụng lệnh phù hợp tùy thuộc vào kiến trúc được phát hiện.

![Multi-platform destruction](https://www.bleepstatic.com/images/news/u/1220909/2025/June/winlinux.jpg)

**Xóa đa nền tảng**  
_Nguồn: Socket_

Khi hành động hoàn tất, công cụ xóa gửi email cho kẻ tấn công đến ‘anupm019@gmail.com' với URL backend, dấu vân tay hệ thống và kết quả của việc xóa tệp.

Kẻ tấn công cũng nhận được phản hồi ngay lập tức cho yêu cầu ban đầu của họ qua một phản hồi HTTP, xác nhận liệu lệnh phá hủy có thành công trong thời gian thực hay không.

Trường hợp các công cụ xóa dữ liệu trong npm là rất hiếm, vì chúng không phục vụ mục đích thu lợi tài chính hoặc đánh cắp dữ liệu, điều này là thường thấy khi malware xâm nhập vào các nền tảng phân phối phần mềm.

Socket nhận xét về điều này bằng cách mô tả hai gói này là "một bổ sung đáng lo ngại cho bối cảnh mối đe dọa của npm," điều này có thể báo hiệu hoạt động từ cấp nhà nước hoặc phá hoại đang len lỏi vào hệ sinh thái.

"Các gói này không đánh cắp tiền điện tử hoặc thông tin đăng nhập—chúng xóa mọi thứ," kết luận Socket.

"Điều này cho thấy các kẻ tấn công được thúc đẩy bởi sự phá hoại, cạnh tranh hoặc sự gián đoạn cấp nhà nước thay vì chỉ đơn thuần là động cơ tài chính."