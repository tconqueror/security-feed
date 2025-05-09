# Google Chrome sẽ sử dụng AI trên thiết bị để phát hiện lừa đảo hỗ trợ kỹ thuật

![Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Google đang triển khai một tính năng bảo mật mới trong Chrome sử dụng mô hình ngôn ngữ lớn 'Gemini Nano' (LLM) tích hợp sẵn để phát hiện và chặn các cuộc lừa đảo hỗ trợ kỹ thuật khi trình duyệt web.

Lừa đảo hỗ trợ kỹ thuật là các trang web độc hại lừa người dùng nghĩ rằng máy tính của họ bị nhiễm virus hoặc có vấn đề khác. Những cảnh báo này được hiển thị dưới dạng cửa sổ trình duyệt toàn màn hình hoặc sẽ hiển thị thêm các cửa sổ pop-up, khiến chúng khó đóng lại.

Mục tiêu là thuyết phục nạn nhân gọi một số điện thoại được liệt kê để nhận trợ giúp nhằm bán các gói hỗ trợ từ xa không cần thiết hoặc truy cập từ xa vào thiết bị, điều này có thể dẫn đến [mất mát tài chính](https://www.bleepingcomputer.com/news/security/ftc-will-send-255-million-to-victims-of-tech-support-scams/) hoặc đánh cắp dữ liệu.

![Ví dụ lừa đảo hỗ trợ kỹ thuật](https://www.bleepstatic.com/images/news/security/t/tech-support-scams/recipe/tech-support-scam.jpg)

**Ví dụ lừa đảo hỗ trợ kỹ thuật**  
_Nguồn: BleepingComputer_

Google Chrome 126 sẽ cung cấp các tính năng AI trực tiếp trong trình duyệt để hỗ trợ nhanh chóng, tập trung vào quyền riêng tư.

Hệ thống chống lừa đảo mới của Chrome, được tích hợp vào 'Enhanced Protection' của trình duyệt, phân tích các trang web theo thời gian thực để phát hiện các tín hiệu lừa đảo như cảnh báo virus giả hoặc khóa toàn màn hình, đây là những dấu hiệu đặc trưng của các vụ lừa đảo hỗ trợ kỹ thuật.

Phân tích này diễn ra ngoại tuyến, tại chỗ trên thiết bị của người dùng bằng cách sử dụng Gemini Nano. Khi có khớp tích cực, dữ liệu (đầu ra LLM + siêu dữ liệu trang web) được gửi đến 'Google Safe Browsing' để đánh giá kỹ lưỡng hơn.

Nếu ý định độc hại được xác nhận, Chrome sẽ hiển thị một thông báo cảnh báo người dùng về rủi ro.

![Tổng quan về cách thức hoạt động của hệ thống mới](https://www.bleepstatic.com/images/news/u/1220909/2025/May/diagram.jpg)

**Tổng quan về cách thức hoạt động của hệ thống mới**  
_Nguồn: Google_

Google cho biết tính năng này tôn trọng quyền riêng tư của người dùng và chỉ có tác động tối thiểu đến hiệu suất, mặc dù không có nhiều chi tiết được đưa ra trong thông báo.

"Tất cả đều được thực hiện theo cách bảo tồn hiệu suất và quyền riêng tư," [Google thông báo](https://security.googleblog.com/2025/05/using-ai-to-stop-tech-support-scams-in.html).

"Để đảm bảo rằng LLM chỉ được kích hoạt một cách hạn chế và chạy cục bộ trên thiết bị, chúng tôi quản lý cẩn thận việc tiêu thụ tài nguyên bằng cách xem xét số lượng token được sử dụng, chạy quy trình bất đồng bộ để tránh làm gián đoạn hoạt động của trình duyệt, và thực hiện các cơ chế điều chỉnh và thắt chặt để giới hạn việc sử dụng GPU."

Tính năng bảo vệ dựa trên AI sẽ được triển khai trên Chrome 137, dự kiến phát hành vào tuần tới, và sẽ được bật theo mặc định cho tất cả người dùng nâng cấp lên phiên bản mới nhất và lựa chọn 'Enhanced Protection' trong cài đặt Safe Browsing của trình duyệt.

Mở **Cài đặt Chrome > Quyền riêng tư và Bảo mật > Bảo mật > Bảo vệ Tăng cường** để bật nó.

_Nguồn: BleepingComputer_

Google cho biết sẽ mở rộng hệ thống trong các bản phát hành trong tương lai và làm cho nó có khả năng phát hiện các loại lừa đảo khác, chẳng hạn như lừa đảo giao hàng giả hoặc thông báo thu phí. Ngoài ra, Chrome cho Android sẽ nhận được tính năng này vào năm 2025.

Tính năng chống lừa đảo mới của Google tương tự như những gì Microsoft [đã giới thiệu cho Edge](https://www.bleepingcomputer.com/news/microsoft/microsoft-tests-edge-scareware-blocker-to-block-tech-support-scams/) vào đầu năm nay, sử dụng một mô hình học máy được đào tạo đặc biệt để phát hiện và chặn các cuộc lừa đảo nhằm vào người dùng.