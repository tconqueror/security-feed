# Sự kiện hack Zeroday Cloud trao $320,0000 cho 11 lỗ hổng zero-day

![Sự kiện hack Zeroday Cloud trao $320,0000 cho 11 lỗ hổng zero-day](https://www.bleepstatic.com/content/hl-images/2025/10/06/logo.jpg)

Cuộc thi hack Zeroday Cloud tại London đã trao cho các nhà nghiên cứu $320,000 vì đã chứng minh các lỗ hổng nghiêm trọng cho phép thực thi mã từ xa trong các thành phần được sử dụng trong hạ tầng đám mây.

Sự kiện hack đầu tiên tập trung vào hệ thống đám mây, cuộc thi do Wiz Research tổ chức phối hợp với Amazon Web Services, Microsoft và Google Cloud.

Các nhà nghiên cứu đã thành công trong 85% các lần tấn công trong 13 phiên hack, chứng minh 11 lỗ hổng zero-day.

[![Wiz](https://www.bleepstatic.com/content/webinar-images/Action1-970x250-watch-now.jpg)](/mgo/72/) 

Một [blog post](https://www.wiz.io/blog/wiz-zeroday-cloud-hacking-competition-behind-the-scenes) tóm tắt sự kiện ghi nhận $200,000 đã được trao trong ngày đầu tiên cho việc khai thác thành công các vấn đề trong Redis, PostgreSQL, Grafana và Linux kernel.

Trong ngày thứ hai, các nhà nghiên cứu kiếm thêm $120,000, trình diễn các khai thác trong Redis, PostgreSQL và MariaDB, các cơ sở dữ liệu phổ biến nhất được hệ thống đám mây sử dụng để lưu trữ thông tin quan trọng (ví dụ: credentials, secrets, thông tin nhạy cảm của người dùng).

![Overview of Zeroday Cloud 2025](https://www.bleepstatic.com/images/news/u/1220909/2025/December/overview.jpg)

**Tổng quan về Zeroday Cloud 2025**  
_Nguồn: Wiz_

Linux kernel đã bị xâm phạm thông qua một lỗ hổng thoát container, cho phép kẻ tấn công phá vỡ cơ chế cô lập giữa các tenant trên đám mây, làm suy yếu một đảm bảo an ninh cốt lõi của môi trường đám mây.

Các nhà nghiên cứu tại các công ty an ninh mạng Zellic và DEVCORE đã được trao $40,000 cho thành công của họ.

**Team CCC nhận khoản tiền thưởng cá nhân cao nhất trong cuộc thi**  
_Nguồn: Wiz_

Trí tuệ nhân tạo cũng là một chủ đề, với các lần tấn công nhắm vào các mô hình vLLM và Ollama, có khả năng lộ các mô hình AI riêng tư, bộ dữ liệu và prompt, nhưng cả hai nỗ lực đều thất bại do hết thời gian.

Kết thúc Zeroday Cloud đầu tiên, Team Xint Code được xưng vương khi khai thác thành công Redis, MariaDB và PostgreSQL. Với ba khai thác đó, Team Xint Code nhận $90,000.

**Team Xint Code chiến thắng sự kiện Zeroday Cloud đầu tiên**  
_Nguồn: Wiz_

Mặc dù kết quả tích cực, số tiền trao chỉ là một phần nhỏ của [tổng quỹ giải thưởng $4.5 million](https://www.bleepingcomputer.com/news/security/zeroday-cloud-hacking-contest-offers-45-million-in-bounties/) dành cho các nhà nghiên cứu trình diễn khai thác cho nhiều mục tiêu khác nhau.

Các hạng mục và sản phẩm đủ điều kiện nhưng không thấy khai thác trong cuộc thi bao gồm AI (Ollama, vLLM, Nvidia Container Toolkit), Kubernetes, Docker, web servers (ngnix, Apache Tomcat, Envoy, Caddy), Apache Airflow, Jenkins và GitLab CE.