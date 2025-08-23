# Pi-hole công bố lỗ hổng dữ liệu qua lỗ hổng plugin GiveWp WordPress

![Pi-hole](https://www.bleepstatic.com/content/hl-images/2025/08/01/Pi-hole-headpic.jpg)

Pi-hole, một phần mềm chặn quảng cáo cấp mạng phổ biến, đã công bố rằng tên và địa chỉ email của các nhà tài trợ đã bị lộ qua một lỗ hổng bảo mật trong plugin quyên góp GiveWP của WordPress.

Pi-hole hoạt động như một DNS sinkhole, lọc bỏ nội dung không mong muốn trước khi nó đến thiết bị của người dùng. Trong khi ban đầu được thiết kế để chạy trên máy tính đơn Raspberry Pi, nó hiện hỗ trợ nhiều hệ thống Linux trên phần cứng chuyên dụng hoặc máy ảo.

Tổ chức này cho biết họ lần đầu tiên biết về sự cố vào thứ Hai, ngày 28 tháng 7, sau khi các nhà tài trợ [bắt đầu báo cáo](https://www.reddit.com/r/pihole/comments/1mbks5z/pihole%5Fdonation%5Femail%5Frecipient%5Flist%5Fleaked/) rằng họ đã nhận được email nghi ngờ tại [các địa chỉ chỉ được sử dụng cho việc quyên góp](https://www.reddit.com/r/pihole/comments/1mblu68/spam%5Fcoming%5Fto%5Fme%5Ffrom%5Femail%5Fonly%5Fused%5Fwith/).

Như đã giải thích trong một [bài viết sau sự cố vào thứ Sáu](http://pi-hole.net/blog/2025/07/30/compromised-donor-emails-a-post-mortem/), lỗ hổng ảnh hưởng đến người dùng đã quyên góp qua biểu mẫu quyên góp trên trang web Pi-hole để hỗ trợ phát triển, làm lộ thông tin cá nhân mà bất kỳ ai xem mã nguồn của trang web đều có thể thấy do một lỗ hổng bảo mật của GiveWP.

[Lỗ hổng này](https://github.com/impress-org/givewp/issues/8042) xuất phát từ GiveWP, một plugin WordPress được sử dụng để xử lý quyên góp trên trang web Pi-hole. Plugin này vô tình làm cho thông tin của các nhà tài trợ có thể truy cập công khai mà không yêu cầu xác thực hoặc quyền truy cập đặc biệt.

Mặc dù Pi-hole không tiết lộ số lượng khách hàng bị ảnh hưởng, dịch vụ thông báo lỗ hổng dữ liệu "Have I Been Pwned" đã thêm lỗ hổng của Pi-hole, cho biết rằng nó ảnh hưởng đến gần 30.000 nhà tài trợ, với 73% hồ sơ bị lộ đã có trong cơ sở dữ liệu của nó.

[![https://bsky.app/profile/haveibeenpwned.com/post/3lvca3viu322x](https://www.bleepstatic.com/images/news/u/1109292/2025/HIBP-Pi-hole.png)](https://bsky.app/profile/haveibeenpwned.com/post/3lvca3viu322x)

## Không có thông tin tài chính nào bị lộ

Pi-hole bổ sung rằng không có dữ liệu tài chính của các nhà tài trợ bị xâm phạm, vì thông tin thẻ tín dụng và các chi tiết thanh toán khác được xử lý trực tiếp bởi Stripe và PayPal. Nó cũng làm rõ rằng sản phẩm phần mềm Pi-hole không bị ảnh hưởng theo bất kỳ cách nào.

"Chúng tôi làm rõ trong biểu mẫu quyên góp rằng chúng tôi không yêu cầu tên hoặc địa chỉ email hợp lệ, đó chỉ là để người dùng thấy và quản lý các khoản quyên góp của họ," [Pi-hole nói](https://pi-hole.net/blog/2025/07/30/compromised-donor-emails-a-post-mortem/). "Cũng cần lưu ý rằng sản phẩm Pi-hole không phải là đối tượng của lỗ hổng này. Không cần có hành động từ phía những người dùng có Pi-hole được cài đặt trên mạng của họ."

Mặc dù GiveWP đã phát hành một bản vá trong vòng vài giờ sau khi lỗ hổng được báo cáo trên GitHub, Pi-hole đã phê bình phản ứng của nhà phát triển plugin, cho rằng đã có sự chậm trễ 17.5 giờ trước khi thông báo cho người dùng và những gì họ mô tả là sự thừa nhận không đủ về tác động tiềm tàng của lỗ hổng bảo mật đối với tên và địa chỉ email của các nhà tài trợ.

Pi-hole đã xin lỗi các nhà tài trợ bị ảnh hưởng và thừa nhận khả năng thiệt hại về danh tiếng phát sinh từ sự cố bảo mật này, cho biết rằng trong khi lỗ hổng không thể dự đoán, họ chấp nhận trách nhiệm cho việc xâm phạm dữ liệu xảy ra.

"Tên và địa chỉ email của bất kỳ ai đã từng quyên góp qua trang quyên góp của chúng tôi đã ở đó để cả thế giới thấy (miễn là họ đủ khéo léo để nhấp chuột phải -> Xem mã nguồn trang). Chỉ trong vài giờ sau khi báo cáo này được công bố, họ đã vá mã xấu và phát hành phiên bản 4.6.1," Pi-hole đã thêm trong một bài viết trên blog phân tích sự cố.

"Chúng tôi hoàn toàn chịu trách nhiệm cho phần mềm mà chúng tôi triển khai. Chúng tôi đã đặt niềm tin vào một plugin được sử dụng rộng rãi, và niềm tin đó đã bị phá vỡ."