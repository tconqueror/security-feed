# Những lỗ hổng mới trên CPU Intel rò rỉ dữ liệu nhạy cảm từ bộ nhớ được cấp quyền

![Intel CPU](https://www.bleepstatic.com/content/hl-images/2021/01/26/Intel-CPU.jpg)

Một lỗ hổng mới mang tên "Branch Privilege Injection" trong tất cả các CPU Intel hiện đại cho phép kẻ tấn công rò rỉ dữ liệu nhạy cảm từ các vùng bộ nhớ được phân bổ cho phần mềm có quyền như kernel của hệ điều hành.

Thông thường, các vùng này chứa thông tin như mật khẩu, khóa mã hóa, bộ nhớ của các quy trình khác và cấu trúc dữ liệu của kernel, do đó việc bảo vệ chúng khỏi bị rò rỉ là rất quan trọng.

Theo các nhà nghiên cứu đến từ [ETH Zurich](https://comsec.ethz.ch/bprc) Sandro Rüegge, Johannes Wikner và Kaveh Razavi, những biện pháp giảm thiểu Spectre v2 đã tồn tại trong sáu năm, nhưng khai thác mới mang tên "Branch Predictor Race Conditions" của họ đã vượt qua chúng một cách hiệu quả.

Lỗi này được gọi là 'branch privilege injection' và được theo dõi dưới mã CVE-2024-45332, là một điều kiện đua trên hệ thống con của các bộ dự đoán nhánh được sử dụng trong CPU Intel.

Các bộ dự đoán nhánh như Branch Target Buffer (BTB) và Indirect Branch Predictor (IBP) là các thành phần phần cứng chuyên biệt, cố gắng đoán kết quả của một lệnh nhánh trước khi nó được giải quyết, nhằm giữ cho đường ống của CPU luôn đầy để tối ưu hóa hiệu suất.

Những dự đoán này là giả định, nghĩa là chúng sẽ bị xóa bỏ nếu sai. Tuy nhiên, nếu đúng, nó sẽ gia tăng hiệu suất.

Các nhà nghiên cứu phát hiện ra rằng việc cập nhật dự đoán nhánh của Intel không được đồng bộ hóa với việc thực thi lệnh, dẫn đến các cập nhật này vượt qua các ranh giới về quyền truy cập.

Nếu có sự chuyển đổi quyền, chẳng hạn từ chế độ người dùng sang chế độ kernel, sẽ có một khoảng thời gian nhỏ trong đó cập nhật liên quan đến mức quyền sai.

Kết quả là sự phân cách giữa người dùng và kernel bị phá vỡ, và một người dùng không có quyền có thể rò rỉ dữ liệu từ các quy trình có quyền.

Nhóm nghiên cứu tại ETH Zurich đã phát triển một exploit mà đào tạo CPU để dự đoán một đích nhánh cụ thể, sau đó thực hiện một cuộc gọi hệ thống để di chuyển thực thi vào kernel của OS, dẫn đến việc thực thi giả định sử dụng đích kiểm soát bởi kẻ tấn công ("gadget").

Mã này truy cập dữ liệu bí mật được tải vào bộ nhớ đệm, và sử dụng phương pháp kênh bên, nội dung bị rò rỉ đến kẻ tấn công.

Các nhà nghiên cứu đã chứng minh cuộc tấn công của họ trên Ubuntu 24.04 với các biện pháp giảm thiểu mặc định được kích hoạt để đọc nội dung của tệp '/etc/shadow/' chứa mật khẩu tài khoản đã được băm. Lỗ hổng này có thể đạt được tỷ lệ rò rỉ tối đa 5,6 KB/giây với độ chính xác 99,8%.

## Tác động và biện pháp khắc phục

CVE-2024-45332 ảnh hưởng đến tất cả các CPU Intel kể từ thế hệ thứ chín trở đi, bao gồm Coffee Lake, Comet Lake, Rocket Lake, Alder Lake và Raptor Lake.

"Tất cả các bộ vi xử lý Intel kể từ thế hệ thứ 9 (Coffee Lake Refresh) đều bị ảnh hưởng bởi Branch Privilege Injection," các nhà nghiên cứu giải thích.

"Tuy nhiên, chúng tôi đã quan sát thấy các dự đoán vượt qua Indirect Branch Prediction Barrier (IBPB) trên các bộ xử lý từ thế hệ thứ 7 (Kaby Lake) trở lên."

Các nhà nghiên cứu ETH Zurich chưa kiểm tra các thế hệ cũ hơn vào thời điểm này, nhưng do chúng không hỗ trợ Enhanced Indirect Branch Restricted Speculation (eIBRS), chúng ít liên quan hơn đến lỗ hổng cụ thể này và có thể dễ bị tổn thương hơn với các cuộc tấn công kiểu Spectre v2 cũ hơn.

Các chip Arm Cortex-X1, Cortex-A76 và AMD Zen 5 và Zen 4 cũng được kiểm tra, nhưng chúng không biểu hiện cùng hành vi bộ dự đoán không đồng bộ, vì vậy chúng không dễ bị tổn thương với CVE-2024-45332.

![Các họ bộ xử lý đã được đánh giá](https://www.bleepstatic.com/images/news/u/1220909/2025/May/table.jpg)

**Các họ bộ xử lý đã được đánh giá**  
_Nguồn: ETH Zurich_

Mặc dù cuộc tấn công đã được chứng minh trên Linux, lỗ hổng vẫn hiện hữu trên cấp độ phần cứng, vì vậy về lý thuyết, nó cũng có thể khai thác trên Windows.

Các nhà nghiên cứu đã báo cáo phát hiện của họ đến Intel vào tháng 9 năm 2024, và gã khổng lồ công nghệ này đã phát hành các bản cập nhật mã vi điều khiển giúp giảm thiểu CVE-2024-45332 trên các mẫu bị ảnh hưởng.

Các biện pháp giảm thiểu ở cấp độ firmware giới thiệu chi phí hiệu suất là 2.7%, trong khi các biện pháp giảm thiểu phần mềm có tác động hiệu suất từ 1.6% đến 8.3%, tùy thuộc vào CPU.

Nguy cơ cho người dùng thông thường là thấp và các cuộc tấn công có nhiều điều kiện mạnh mẽ để mở ra các kịch bản khai thác thực tế. Tuy nhiên, việc áp dụng các bản cập nhật BIOS/UEFI và hệ điều hành mới nhất là cần thiết.

ETH Zurich sẽ trình bày chi tiết đầy đủ về exploit của họ trong một tài liệu kỹ thuật tại hội thảo [USENIX Security 2025](https://www.usenix.org/conference/usenixsecurity25) sắp tới.

BleepingComputer đã liên hệ với Intel để xem liệu có thông báo nào sẽ được phát hành hôm nay không và sẽ cập nhật bài viết với phản hồi.