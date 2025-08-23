# Dozens of malicious packages on NPM collect host and network data

![Dozens of malicious packages on NPM collect host and network data](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_head_pic.jpg)

60 gói đã được phát hiện trong chỉ mục NPM cố gắng thu thập dữ liệu nhạy cảm về host và mạng và gửi nó đến một Discord webhook do tác nhân đe dọa kiểm soát.

Theo [nhóm Nghiên cứu Đe dọa của Socket](https://socket.dev/blog/60-malicious-npm-packages-leak-network-and-host-data), các gói này đã được tải lên kho lưu trữ NPM bắt đầu từ ngày 12 tháng 5 từ ba tài khoản phát hành.

Mỗi gói độc hại đều chứa một kịch bản post-install tự động thực thi trong quá trình ‘npm install’ và thu thập thông tin sau đây:

* Tên miền
* Địa chỉ IP nội bộ
* Thư mục chính của người dùng
* Thư mục làm việc hiện tại
* Tên người dùng
* Máy chủ DNS của hệ thống

Kịch bản kiểm tra các tên miền liên quan đến các nhà cung cấp đám mây, các chuỗi DNS ngược, trong nỗ lực xác định xem nó có đang chạy trong môi trường phân tích hay không.

Socket không quan sát thấy việc phát tán của các payload giai đoạn hai, leo thang quyền hạn, hoặc bất kỳ cơ chế bền vững nào. Tuy nhiên, với loại dữ liệu thu thập được, nguy cơ của các cuộc tấn công mạng có mục tiêu là rất đáng kể.

## Các gói vẫn có sẵn trên NPM

Các nhà nghiên cứu đã báo cáo các gói độc hại nhưng vào thời điểm viết bài, chúng vẫn có sẵn trên NPM và cho thấy tổng số lượt tải là 3,000. Tuy nhiên, vào thời điểm xuất bản, không gói nào trong số đó có mặt trong kho lưu trữ.

Để đánh lừa các nhà phát triển sử dụng chúng, tác nhân đe dọa đứng sau chiến dịch đã sử dụng các tên tương tự như các gói hợp lệ trong chỉ mục, như ‘flipper-plugins’, ‘react-xterm2’, và ‘hermes-inspector-msggen’, với những tên gọi chung gợi lên lòng tin, và những tên khác gợi ý về việc kiểm tra, có thể nhắm tới các quy trình CI/CD.

Danh sách hoàn chỉnh của 60 gói độc hại có sẵn ở phần cuối của báo cáo từ Socket.

Nếu bạn đã cài đặt bất kỳ gói nào trong số đó, hãy loại bỏ chúng ngay lập tức và thực hiện quét toàn bộ hệ thống để loại bỏ bất kỳ dấu hiệu còn sót lại của sự nhiễm bệnh.

## Data wipers trên NPM

Một chiến dịch độc hại khác mà [Socket đã phát hiện](https://socket.dev/blog/malicious-npm-packages-target-react-vue-and-vite-ecosystems-with-destructive-payloads) vào ngày hôm qua trên NPM liên quan đến tám gói độc hại bắt chước các công cụ hợp lệ thông qua typosquatting nhưng có thể xóa tệp, làm hỏng dữ liệu, và tắt hệ thống.

Các gói này, nhắm mục tiêu vào các hệ sinh thái React, Vue.js, Vite, Node.js và Quill, đã tồn tại trên NPM trong suốt hai năm qua, với 6,200 lượt tải xuống.

Việc tránh bị phát hiện lâu như vậy một phần là do các payload được kích hoạt dựa trên các ngày hệ thống mã hóa cứng và được cấu trúc để từ từ tiêu diệt các tệp khung, làm hỏng các phương thức JavaScript chính, và phá hoại các cơ chế lưu trữ trình duyệt.

![Script designed to delete Vue.js-related files on June 19–30, 2023](https://www.bleepstatic.com/images/news/u/1220909/2025/May/code(1).jpg)

**Kịch bản được thiết kế để xóa các tệp liên quan đến Vue.js trong khoảng thời gian từ 19–30 tháng 6, 2023**  
_Nguồn: Socket_

Tác nhân đe dọa đứng sau chiến dịch này, người đã xuất bản chúng dưới tên ‘xuxingfeng’, cũng đã liệt kê một số gói hợp lệ để xây dựng lòng tin và tránh sự phát hiện.

Mặc dù nguy cơ đã trôi qua dựa trên các ngày mã hóa cứng, nhưng việc loại bỏ các gói này là điều cực kỳ quan trọng vì tác giả của chúng có thể giới thiệu các bản cập nhật sẽ kích hoạt lại các chức năng xóa của chúng trong tương lai.