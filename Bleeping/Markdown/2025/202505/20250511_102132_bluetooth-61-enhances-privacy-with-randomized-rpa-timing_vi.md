# Bluetooth 6.1 nâng cao quyền riêng tư với thời gian RPA ngẫu nhiên

![Bluetooth](https://www.bleepstatic.com/content/hl-images/2025/05/09/bluetooth.jpg)

Nhóm Chuyên Gia Bluetooth (SIG) đã công bố Tiêu chuẩn Core Bluetooth 6.1, mang đến những cải tiến quan trọng cho giao thức truyền thông không dây phổ biến.

Một tính năng mới được nhấn mạnh trong phiên bản gần đây là tăng cường quyền riêng tư cho thiết bị thông qua việc cập nhật Địa chỉ Riêng Có Thể Giải Quyết (RPA) ngẫu nhiên.

"Việc ngẫu nhiên hóa thời gian thay đổi địa chỉ khiến cho việc theo dõi hoặc tương quan hoạt động của thiết bị theo thời gian trở nên khó khăn hơn rất nhiều," [đọc thông báo của SIG](https://www.bluetooth.com/blog/delivering-on-the-bi-annual-release-schedule-bluetooth-core-6-1-is-here/).

Một Địa chỉ Riêng Có Thể Giải Quyết (RPA) là một địa chỉ Bluetooth được tạo ra để có vẻ ngẫu nhiên và được sử dụng thay cho địa chỉ MAC cố định của thiết bị nhằm bảo vệ quyền riêng tư của người dùng. Nó cho phép các thiết bị đáng tin cậy kết nối lại một cách an toàn mà không tiết lộ danh tính thực sự của chúng.

Hiện tại, RPAs được cập nhật theo các khoảng thời gian cố định, thường là mỗi 15 phút, điều này tạo ra một mức độ có thể dự đoán. Mức độ có thể dự đoán này có thể bị khai thác trong các cuộc tấn công tương quan, làm cho việc theo dõi lâu dài trở nên khả thi.

Bluetooth 6.1 cải thiện quyền riêng tư bằng cách ngẫu nhiên hóa các cập nhật RPA trong khoảng từ 8 đến 15 phút (mặc định), đồng thời cũng cho phép các giá trị tùy chỉnh trong khoảng từ 1 giây đến 1 giờ.

Bộ điều khiển chọn một giá trị ngẫu nhiên trong phạm vi đã xác định bằng cách sử dụng một bộ phát sinh số ngẫu nhiên được NIST phê duyệt, và cập nhật RPA. Điều này làm cho việc theo dõi trở nên khó khăn hơn đáng kể, vì không có mẫu nào trong việc chọn giá trị.

Thêm chi tiết về cách hoạt động của tính năng quyền riêng tư mới có thể được tìm thấy trong [tài liệu thông số kỹ thuật](https://files.bluetooth.com/download/core%5Fv6-1/) được công bố cùng với thông báo.

Một tính năng khác được nêu bật trong thông báo là hiệu suất năng lượng tốt hơn bắt đầu từ Bluetooth 6.1, xuất phát từ việc cho phép chip (Bộ điều khiển) tự xử lý các cập nhật RPA ngẫu nhiên.

Cụ thể, chip Bluetooth sẽ chọn các khoảng thời gian ngẫu nhiên và tự tạo ra và cập nhật RPA mà không cần đánh thức thiết bị chủ.

Điều này giúp tiết kiệm chu kỳ CPU và các thao tác bộ nhớ, do đó tiết kiệm rất nhiều năng lượng khi các điều kiện được đáp ứng. Đối với các thiết bị nhỏ hơn như vòng tay thể dục, tai nghe không dây và cảm biến IoT, điều này có thể tạo ra sự khác biệt lớn về tuổi thọ pin.

Mặc dù Bluetooth 6.1 đã có những bước tiến thú vị, nhưng quan trọng để nhấn mạnh rằng hỗ trợ thực tế trên phần cứng và firmware có thể mất vài năm để có mặt.

Làn sóng đầu tiên của các chip với Bluetooth 6.1 có thể không được kỳ vọng thực tế trước năm 2026, và ngay cả khi đó, việc triển khai sớm có thể không ngay lập tức tiết lộ tất cả các tính năng mới có sẵn, vì có thể cần thử nghiệm và xác minh.