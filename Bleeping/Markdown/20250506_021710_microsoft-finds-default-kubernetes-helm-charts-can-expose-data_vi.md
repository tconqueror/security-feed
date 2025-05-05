# Microsoft cảnh báo các biểu đồ Helm mặc định trong Kubernetes có thể phơi bày dữ liệu

![Kubernetes](https://www.bleepstatic.com/content/hl-images/2024/04/17/Kubernetes.jpg)

Microsoft đã cảnh báo về các rủi ro bảo mật do các cấu hình mặc định trong triển khai Kubernetes gây ra, đặc biệt là những cấu hình sử dụng các biểu đồ Helm từ đầu, điều này có thể công khai xác thực dữ liệu nhạy cảm.

Trong nhiều trường hợp, các biểu đồ Helm này không yêu cầu xác thực, để lại các cổng khai thác mở và sử dụng mật khẩu yếu hoặc mã hóa cứng không khó để phá.

Một báo cáo được công bố bởi các nhà nghiên cứu bảo mật Michael Katchinskiy và Yossi Weizman từ Microsoft Defender for Cloud Research đã nêu rõ ba trường hợp là ví dụ cho một vấn đề bảo mật rộng hơn, đặt các khối lượng công việc Kubernetes vào rủi ro.

## Sự tiện lợi vs bảo mật

Kubernetes là một nền tảng mã nguồn mở được sử dụng rộng rãi nhằm tự động hóa việc triển khai, mở rộng và quản lý các ứng dụng đã được container hóa.

Helm là một trình quản lý gói cho Kubernetes, và các biểu đồ là các mẫu/bản thiết kế cho việc triển khai ứng dụng trên nền tảng, cung cấp các tệp YAML định nghĩa các tài nguyên chính cần thiết để chạy một ứng dụng.

Các biểu đồ Helm rất phổ biến vì chúng đơn giản hóa và tăng tốc độ các triển khai phức tạp. Tuy nhiên, như được nêu trong báo cáo của Microsoft, trong nhiều trường hợp, các cài đặt mặc định trong những biểu đồ đó thiếu các biện pháp bảo mật phù hợp.

Người dùng thiếu kinh nghiệm với bảo mật đám mây thường triển khai những biểu đồ Helm đó như chúng là, không cố ý phơi bày các dịch vụ ra internet và cho phép kẻ tấn công quét và khai thác các ứng dụng được cấu hình sai.

![Hướng dẫn biểu đồ Helm Apache Pinot](https://www.bleepstatic.com/images/news/u/1220909/2025/May/image.jpg)

**Hướng dẫn biểu đồ Helm Apache Pinot**  
_Nguồn: Microsoft_

"Các cấu hình mặc định thiếu các kiểm soát bảo mật phù hợp tạo ra một mối đe dọa bảo mật nghiêm trọng," [cảnh báo các nhà nghiên cứu từ Microsoft](https://techcommunity.microsoft.com/blog/microsoftdefendercloudblog/the-risk-of-default-configuration-how-out-of-the-box-helm-charts-can-breach-your/4409560).

"Nếu không xem xét kỹ lưỡng các bản khai YAML và các biểu đồ Helm, các tổ chức có thể không biết đã triển khai các dịch vụ thiếu bất kỳ hình thức bảo vệ nào, để chúng hoàn toàn phơi bày trước các kẻ tấn công."

"Điều này đặc biệt đáng lo ngại khi ứng dụng được triển khai có thể truy vấn các API nhạy cảm hoặc cho phép các hành động quản trị, điều mà chính xác là điều chúng ta sẽ thấy ngay."

Các nhà nghiên cứu đã nêu rõ ba trường hợp của các biểu đồ Helm đặt các môi trường Kubernetes vào rủi ro tấn công, được tóm tắt như sau.

* **Apache Pinot**: Phơi bày các dịch vụ cốt lõi (pinot-controller và pinot-broker) qua các dịch vụ Kubernetes LoadBalancer mà không có bất kỳ hình thức xác thực nào.
* **Meshery**: Cho phép đăng ký công khai từ IP bị lộ, cho phép bất kỳ ai đăng ký và có quyền truy cập vào các hoạt động cụm.
* **Selenium Grid**: Một NodePort phơi bày dịch vụ qua tất cả các nút trong một cụm, chỉ dựa vào các quy tắc tường lửa bên ngoài để bảo vệ. Vấn đề này không ảnh hưởng đến biểu đồ Helm chính thức, nhưng ảnh hưởng đến nhiều dự án GitHub được tham khảo rộng rãi.

Về Selenium Grid, Wiz và các công ty an ninh mạng khác đã [quan sát trước đây](https://www.bleepingcomputer.com/news/security/misconfigured-selenium-grid-servers-abused-for-monero-mining/) các cuộc tấn công nhắm vào các phiên bản cấu hình sai để triển khai các thợ đào XMRig để khai thác tiền điện tử Monero.

Để giảm thiểu các rủi ro, Microsoft khuyến nghị xem xét kỹ lưỡng cấu hình mặc định của các biểu đồ Helm để đánh giá từ quan điểm bảo mật, đảm bảo rằng nó bao gồm xác thực và cách ly mạng.

Ngoài ra, cũng được khuyến nghị thực hiện quét thường xuyên để phát hiện các cấu hình sai gây phơi bày các giao diện khối lượng công việc ra công khai và theo dõi chặt chẽ các container cho hoạt động đáng ngờ.