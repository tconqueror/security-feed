# Cloudflare: Sự cố không do sự cố an ninh, dữ liệu an toàn

![Cloudflare: Sự cố không do sự cố an ninh, dữ liệu an toàn](https://www.bleepstatic.com/content/hl-images/2023/11/02/cloudflare.jpg)

Cloudflare đã xác nhận rằng sự cố dịch vụ lớn vào ngày hôm qua không phải do sự cố an ninh và không có dữ liệu nào bị mất.

Vấn đề này đã được giảm thiểu phần lớn. Nó bắt đầu lúc 17:52 UTC ngày hôm qua khi hệ thống Workers KV (Key-Value) hoàn toàn ngừng hoạt động, gây ra [sự mất dịch vụ rộng rãi](https://www.bleepingcomputer.com/news/technology/google-cloud-and-cloudflare-hit-by-widespread-service-outages/) trên nhiều dịch vụ điện toán biên và AI.

Workers KV là một kho dữ liệu key-value phân phối toàn cầu và đồng nhất được sử dụng bởi Cloudflare Workers, nền tảng điện toán không máy chủ của công ty. Nó là một phần cơ bản trong nhiều dịch vụ của Cloudflare và một sự cố có thể gây ra các vấn đề nối tiếp qua nhiều thành phần.

Sự gián đoạn này cũng đã ảnh hưởng đến các dịch vụ khác mà hàng triệu người sử dụng, nổi bật nhất là Google Cloud Platform.

![Tỷ lệ lỗi Workers KV trong sự cố](https://www.bleepstatic.com/images/news/u/1220909/2025/June/error-rates.png)

**Tỷ lệ lỗi Workers KV trong sự cố**  
_Nguồn: Cloudflare_

Trong một báo cáo sau sự cố, Cloudflare giải thích rằng sự cố kéo dài gần 2,5 giờ và nguyên nhân gốc rễ là một sự cố trong hạ tầng lưu trữ của Workers KV do sự cố của nhà cung cấp dịch vụ đám mây bên thứ ba.

“Nguyên nhân của sự cố này là do sự cố trong hạ tầng lưu trữ nền tảng được sử dụng bởi dịch vụ Workers KV của chúng tôi, điều này là một phụ thuộc quan trọng cho nhiều sản phẩm Cloudflare và được dựa vào cho việc cấu hình, xác thực và cung cấp tài sản qua các dịch vụ bị ảnh hưởng,” [Cloudflare](https://blog.cloudflare.com/cloudflare-service-outage-june-12-2025/)[ nói](http://blog.cloudflare.com/cloudflare-service-outage-june-12-2025/).

“Một phần của hạ tầng này được hỗ trợ bởi một nhà cung cấp đám mây bên thứ ba, người đã gặp sự cố ngày hôm nay và ảnh hưởng trực tiếp đến khả năng sử dụng dịch vụ KV của chúng tôi.”

Cloudflare đã xác định tác động của sự cố trên từng dịch vụ:

* _**Workers KV**_ – đã trải qua tỷ lệ thất bại 90,22% do sự không khả dụng của lưu trữ backend, ảnh hưởng đến tất cả các đọc và ghi chưa được lưu vào cache.
* _**Access, WARP, Gateway**_ – tất cả đều gặp sự cố nghiêm trọng trong xác thực dựa trên danh tính, quản lý phiên và thực thi chính sách do dựa vào Workers KV, với WARP không thể đăng ký thiết bị mới, và gián đoạn trong proxy Gateway và truy vấn DoH.
* **_Dashboard, Turnstile, Challenges_** – đã trải qua các lỗi đăng nhập và xác thực CAPTCHA rộng rãi, với nguy cơ tái sử dụng mã thông báo được giới thiệu do việc kích hoạt công tắc tắt trên Turnstile.
* _**Browser Isolation & Browser Rendering**_ – không thể khởi động hoặc duy trì các phiên dựa trên liên kết và các nhiệm vụ xử lý trình duyệt do sự cố nối tiếp trong Access và Gateway.
* **_Stream, Images, Pages_** – đã trải qua sự cố chức năng nghiêm trọng: Phát lại Stream và phát trực tiếp đã thất bại, tải ảnh giảm xuống 0% thành công, và việc xây dựng/ phục vụ Pages đạt đỉnh  ~100% tỷ lệ thất bại.
* _**Workers AI & AutoRAG**_ – đã hoàn toàn không khả dụng do phụ thuộc vào KV cho việc cấu hình mô hình, định tuyến, và các chức năng lập chỉ mục.
* _**Durable Objects, D1, Queues**_ – các dịch vụ được xây dựng trên cùng một lớp lưu trữ như KV chịu tỷ lệ lỗi lên tới 22% hoặc không khả dụng hoàn toàn cho việc xếp hàng tin nhắn và các hoạt động dữ liệu.
* **_Realtime & AI Gateway_** – đã gặp phải sự gián đoạn gần như toàn bộ dịch vụ do không thể truy xuất cấu hình từ Workers KV, với các yêu cầu Realtime TURN/SFU và AI Gateway bị ảnh hưởng nặng nề.
* **_Zaraz & Workers Assets_** – đã thấy sự cố toàn bộ hoặc một phần trong việc tải hoặc cập nhật cấu hình và tài sản tĩnh, mặc dù tác động đến người dùng cuối được giới hạn trong phạm vi.
* _**CDN, Workers for Platforms, Workers Builds**_ – đã trải qua độ trễ tăng và lỗi vùng ở một số vị trí, với các bản xây dựng Workers mới gặp phải thất bại 100% trong sự cố.

Để đáp ứng với sự cố này, Cloudflare cho biết họ sẽ đẩy nhanh một số thay đổi tập trung vào khả năng phục hồi, chủ yếu là xóa bỏ sự phụ thuộc vào một nhà cung cấp đám mây bên thứ ba duy nhất cho lưu trữ backend Workers KV.

Dần dần, kho trung tâm của KV sẽ được chuyển sang lưu trữ đối tượng R2 của Cloudflare để giảm sự phụ thuộc bên ngoài.

Cloudflare cũng có kế hoạch triển khai các biện pháp bảo vệ giữa các dịch vụ và phát triển các công cụ mới để dần khôi phục các dịch vụ trong thời gian xảy ra sự cố lưu trữ, ngăn chặn sự gia tăng lưu lượng có thể làm quá tải các hệ thống đang phục hồi và gây ra các lỗi thứ cấp.