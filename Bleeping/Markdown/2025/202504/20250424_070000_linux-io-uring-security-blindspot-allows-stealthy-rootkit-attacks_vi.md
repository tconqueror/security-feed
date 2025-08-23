# Lỗ hổng bảo mật 'io\_uring' trên Linux cho phép tấn công rootkit âm thầm

![Linux](https://www.bleepstatic.com/content/hl-images/2024/11/27/Linux-bootkit.jpg)

Một lỗ hổng bảo mật đáng kể trong bảo mật runtime của Linux do giao diện 'io\_uring' gây ra cho phép các rootkit hoạt động không bị phát hiện trên các hệ thống trong khi vượt qua phần mềm bảo mật doanh nghiệp tiên tiến.

Lỗi này được các nhà nghiên cứu bảo mật [ARMO](https://www.armosec.io/blog/io%5Furing-rootkit-bypasses-linux-security/) phát hiện, những người đã phát triển một rootkit nguyên mẫu gọi là "Curing" để chứng minh tính thực tiễn và khả thi của các cuộc tấn công tận dụng io\_uring để lẩn tránh.

io\_uring là một giao diện trong kernel Linux nhằm thực hiện các hoạt động I/O không đồng bộ một cách hiệu quả. Nó được giới thiệu vào năm 2019 với Linux 5.1 để giải quyết các vấn đề về hiệu suất và khả năng mở rộng của hệ thống I/O truyền thống.

Thay vì phụ thuộc vào các hệ thống gọi có nhiều overhead và gây treo quy trình, io\_uring sử dụng các bộ đệm vòng được chia sẻ giữa các chương trình và kernel hệ thống để xếp hàng các yêu cầu I/O sẽ được xử lý không đồng bộ, cho phép chương trình tiếp tục chạy.

![xếp hàng tác vụ io\_uring và các vòng hoàn thành](https://www.bleepstatic.com/images/news/u/1220909/2025/April/circles.jpg)

**xếp hàng tác vụ io\_uring và các vòng hoàn thành**  
_Nguồn: Donald Hunter_

Vấn đề, theo ARMO, phát sinh từ thực tế rằng hầu hết các công cụ bảo mật theo dõi các syscalls và hooking nghi ngờ (như 'ptrace' hoặc 'seccomp'), hoàn toàn bỏ qua mọi thứ liên quan đến io\_ring, tạo ra một lỗ hổng rất nguy hiểm.

Các nhà nghiên cứu giải thích rằng io\_uring hỗ trợ một [loạt các hoạt động rộng](https://developers.redhat.com/articles/2023/04/12/why-you-should-use-iouring-network-io) thông qua 61 loại hoạt động, bao gồm đọc/ghi tệp, tạo và chấp nhận kết nối mạng, tạo ra các quy trình, sửa đổi quyền truy cập tệp và đọc nội dung thư mục, khiến nó trở thành một vectơ rootkit mạnh mẽ.

Rủi ro đáng lo ngại đến mức Google đã quyết định [tắt tính năng này theo mặc định](https://security.googleblog.com/2023/06/learnings-from-kctf-vrps-42-linux.html) trên Android và ChromeOS, những hệ điều hành này sử dụng kernel Linux và thừa hưởng nhiều lỗ hổng tiềm ẩn của nó.

Để đưa lý thuyết vào thử nghiệm, ARMO đã tạo ra Curing, một rootkit chuyên dụng lợi dụng io\_uring để kéo lệnh từ một máy chủ từ xa và thực hiện các hoạt động tùy ý mà không kích hoạt các hooks hệ thống gọi.

Thử nghiệm Curing chống lại một số công cụ bảo mật runtime nổi tiếng cho thấy hầu hết không thể phát hiện được hoạt động của nó.

Cụ thể, Falco đã hoàn toàn mù lòa ngay cả khi có quy tắc phát hiện tùy chỉnh, trong khi Tetragon cho thấy không thể đánh dấu hoạt động độc hại trong cấu hình mặc định.

Tuy nhiên, Tetragon không coi nền tảng của mình là dễ bị tổn thương khi có thể bật tính năng giám sát để phát hiện rootkit này.

"Chúng tôi đã báo cáo điều này cho nhóm Tetragon và phản hồi của họ cho biết từ quan điểm của họ, Tetragon không 'dễ bị tổn thương' vì họ cung cấp sự linh hoạt để gắn bất kỳ đâu," các nhà nghiên cứu giải thích.

"Họ đã chỉ ra một [bài viết tốt](https://isovalent.com/blog/post/file-monitoring-with-ebpf-and-tetragon-part-1/) mà họ đã viết về chủ đề này."

Thử nghiệm với các công cụ thương mại, ARMO tiếp tục xác nhận khả năng không phát hiện được malware dựa trên io\_uring và các tương tác kernel không liên quan đến syscalls. Tuy nhiên, ARMO đã không chia sẻ các chương trình thương mại nào mà họ đã thử nghiệm.

Đối với những ai muốn thử nghiệm môi trường của họ chống lại mối đe dọa này, ARMO đã làm cho Curing [có sẵn miễn phí trên GitHub](https://github.com/armosec/curing).

ARMO gợi ý rằng vấn đề có thể được giải quyết bằng việc áp dụng Kernel Runtime Security Instrumentation (KRSI), cho phép các chương trình eBPF được gắn vào các sự kiện kernel liên quan đến bảo mật.