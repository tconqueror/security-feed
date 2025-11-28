# Các kho lưu trữ công khai trên GitLab đã phơi bày hơn 17.000 bí mật

![Các kho lưu trữ công khai trên GitLab đã phơi bày hơn 17.000 bí mật](https://www.bleepstatic.com/content/hl-images/2022/04/01/GitLab.jpg)

Sau khi quét toàn bộ 5,6 triệu kho lưu trữ công khai trên GitLab Cloud, một kỹ sư bảo mật đã phát hiện hơn 17.000 bí mật bị phơi bày trên hơn 2.800 tên miền riêng biệt.

Luke Marshall đã sử dụng công cụ mã nguồn mở TruffleHog để kiểm tra mã trong các kho lưu trữ nhằm tìm các thông tin nhạy cảm như khóa API, mật khẩu và token.

Nhà nghiên cứu trước đó đã [đã quét Bitbucket](https://trufflesecurity.com/blog/scanning-2-6-million-public-bitbucket-cloud-repositories-for-secrets), nơi ông tìm thấy 6.212 bí mật phân bố trên 2,6 triệu kho lưu trữ. Ông cũng kiểm tra [tập dữ liệu Common Crawl](https://www.bleepingcomputer.com/news/security/nearly-12-000-api-keys-and-passwords-found-in-ai-training-dataset/) được sử dụng để huấn luyện các mô hình AI, nơi phơi bày 12.000 bí mật hợp lệ.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

GitLab là một nền tảng Git dựa trên web được các lập trình viên, người duy trì và các nhóm DevOps sử dụng để lưu trữ mã, cho các hoạt động CI/CD, hợp tác phát triển và quản lý kho lưu trữ.

Marshall đã sử dụng một endpoint API công khai của GitLab để liệt kê mọi kho lưu trữ GitLab Cloud công khai, dùng một script Python tùy chỉnh để phân trang qua tất cả kết quả và sắp xếp chúng theo project ID.

Quá trình này trả về 5,6 triệu kho lưu trữ không trùng lặp, và tên của chúng được gửi đến AWS Simple Queue Service (SQS).

Tiếp theo, một hàm AWS Lambda lấy tên kho lưu trữ từ SQS, chạy TruffleHog trên kho đó và ghi lại kết quả.

“Mỗi lần gọi Lambda thực hiện lệnh quét TruffleHog đơn giản với concurrency được đặt thành 1000,” [miêu tả Marshall](https://trufflesecurity.com/blog/scanning-5-6-million-public-gitlab-repositories-for-secrets).

“Cấu hình này cho phép tôi hoàn thành việc quét 5.600.000 kho lưu trữ chỉ trong hơn 24 giờ.”

Tổng chi phí cho việc quét toàn bộ các kho lưu trữ công khai trên GitLab Cloud bằng phương pháp trên là $770.

Nhà nghiên cứu phát hiện 17.430 bí mật hợp lệ đang hoạt động, gần gấp ba lần so với Bitbucket, và với mật độ bí mật cao hơn 35% (số bí mật trên mỗi kho lưu trữ).

Dữ liệu lịch sử cho thấy hầu hết các bí mật bị rò rỉ có tuổi đời mới hơn 2018. Tuy nhiên, Marshall cũng tìm thấy một số bí mật rất cũ bắt nguồn từ 2009, và vẫn còn hợp lệ cho đến ngày nay.

![Volume of exposed secrets](https://www.bleepstatic.com/images/news/u/1220909/2025/November/volume.jpg)

**Khối lượng bí mật bị phơi bày**  
_Nguồn: Truffle Security_

Số lượng lớn nhất các bí mật rò rỉ, hơn 5.200 trong số đó, là thông tin đăng nhập Google Cloud Platform (GCP), tiếp theo là khóa MongoDB, token bot Telegram và khóa OpenAI.

Nhà nghiên cứu cũng tìm thấy hơn 400 khóa GitLab bị lộ trong các kho lưu trữ đã quét.

**Các loại bí mật bị phơi bày trên GitLab**  
_Nguồn: Truffle Security_

Theo tinh thần tiết lộ có trách nhiệm và vì các bí mật được phát hiện liên quan đến 2.804 tên miền riêng biệt, Marshall đã dựa vào tự động hóa để thông báo cho các bên bị ảnh hưởng và sử dụng Claude Sonnet 3.7 với khả năng tìm kiếm web cùng một script Python để tạo email.

Trong quá trình đó, nhà nghiên cứu đã thu được nhiều tiền thưởng bug bounty tổng cộng $9.000.

Nhà nghiên cứu báo cáo rằng nhiều tổ chức đã thu hồi bí mật của họ sau khi nhận được thông báo. Tuy nhiên, vẫn còn một số bí mật chưa được tiết lộ số lượng vẫn tiếp tục bị phơi bày trên GitLab.