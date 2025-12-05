# Cloudflare đổ lỗi cho sự cố hôm nay do bản vá khẩn cấp React2Shell

![Cloudflare](https://www.bleepstatic.com/content/hl-images/2025/09/02/Cloudflare.jpg)

Hôm nay, [Cloudflare đã gặp sự cố ngừng hoạt động diện rộng](https://www.bleepingcomputer.com/news/technology/cloudflare-down-websites-offline-with-500-internal-server-error/) khiến các trang web và nền tảng trực tuyến trên toàn thế giới ngừng hoạt động và trả về thông báo "500 Internal Server Error".

Trong một cập nhật trên trang trạng thái, công ty hạ tầng Internet hiện đã đổ lỗi cho sự cố này là do một bản vá khẩn cấp được thiết kế để xử lý lỗ hổng thực thi mã từ xa nghiêm trọng trong React Server Components, lỗ hổng hiện đang bị khai thác tích cực trong các cuộc tấn công.

"Một thay đổi được thực hiện đối với cách Web Application Firewall của Cloudflare phân tích các yêu cầu đã khiến mạng lưới của Cloudflare không khả dụng trong vài phút sáng nay," [Cloudflare cho biết](https://www.cloudflarestatus.com/incidents/lfrm31y6sw9q#:~:text=Posted%204%20hours%20ago%2E%20Dec%2005%2C%202025%20%2D%2009%3A20%20UTC).

"Đây không phải là một cuộc tấn công; thay đổi này đã được đội ngũ của chúng tôi triển khai để giúp giảm nhẹ lỗ hổng trong toàn ngành được tiết lộ tuần này trong React Server Components. Chúng tôi sẽ chia sẻ thêm thông tin khi có trong ngày hôm nay."

Được theo dõi dưới mã [CVE-2025-55182](https://www.bleepingcomputer.com/news/security/critical-react2shell-flaw-in-react-nextjs-lets-hackers-run-javascript-code/), lỗ hổng bảo mật mức độ tối đa này (được gọi là React2Shell) ảnh hưởng tới thư viện mã nguồn mở React dành cho giao diện web và gốc, cũng như các framework phụ thuộc React như Next.js, React Router, Waku, @parcel/rsc, @vitejs/plugin-rsc, và RedwoodSDK.

Lỗ hổng được tìm thấy trong React Server Components (RSC) 'Flight' protocol, và nó cho phép kẻ tấn công không cần xác thực thực hiện thực thi mã từ xa trong các ứng dụng React và Next.js bằng cách gửi các yêu cầu HTTP được chế tạo độc hại tới các endpoint React Server Function.

Trong khi nhiều gói React ở cấu hình mặc định (tức là react-server-dom-parcel, react-server-dom-turbopack, và react-server-dom-webpack) bị tổn thương, lỗ hổng chỉ ảnh hưởng tới các phiên bản React 19.0, 19.1.0, 19.1.1, và 19.2.0 được phát hành trong năm vừa qua.

## Khai thác React2Shell đang diễn ra

Mặc dù tác động không rộng như ban đầu tin rằng, các nhà nghiên cứu bảo mật của AWS đã báo cáo rằng nhiều nhóm tin tặc liên kết với China (bao gồm Earth Lamia và Jackpot Panda) [đã bắt đầu khai thác lỗ hổng React2Shell](https://www.bleepingcomputer.com/news/security/react2shell-critical-flaw-actively-exploited-in-china-linked-attacks/) vài giờ sau khi lỗ hổng mức độ tối đa được tiết lộ.

NHS England National CSOC cũng [nói vào thứ Năm](https://digital.nhs.uk/cyber-alerts/2025/cc-4723) rằng một số mã khai thác proof-of-concept cho CVE-2025-55182 [đã có sẵn](http://x.com/stephenfewer/status/1996697494525264219) và cảnh báo rằng "khả năng tiếp tục bị khai thác thành công ngoài thực địa là rất cao."

Tháng trước, Cloudflare đã trải qua [một sự cố toàn cầu khác](https://www.bleepingcomputer.com/news/technology/cloudflare-blames-this-weeks-massive-outage-on-database-issues/) làm sập Global Network của công ty gần 6 giờ, một sự cố được CEO Matthew Prince mô tả là "sự cố tồi tệ nhất kể từ năm 2019."

Cloudflare [đã sửa một sự cố lớn khác](https://www.bleepingcomputer.com/news/technology/google-cloud-and-cloudflare-hit-by-widespread-service-outages/) vào tháng Sáu, khiến lỗi xác thực Access và sự cố kết nối Zero Trust WARP trên nhiều khu vực, và cũng ảnh hưởng đến hạ tầng của Google Cloud.