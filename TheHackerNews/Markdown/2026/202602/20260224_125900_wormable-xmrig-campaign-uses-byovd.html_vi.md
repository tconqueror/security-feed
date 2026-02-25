# Chiến dịch XMRig có khả năng lây lan sử dụng khai thác BYOVD và logic bomb thời gian

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiSN4m24uNLL9rLCwHv89KIT-P1ExHG8D2EAk0TBI7XClmXn4JxBe0NWurC0iazjhxVKll6ZmSfMPbfD3ohlUDAXCscVdXkLmFicuwIoz9ya4Lvx6FCcgAdu75R72rx%5FW1-1I5UGbtgJMkSCR1MaZAGUxzHM5uSDAhNj5FBHGpCq%5F%5F7yUclLAQg7IGhUhdW/s1700-e365/miners.jpg)

Các nhà nghiên cứu an ninh mạng đã tiết lộ chi tiết về một chiến dịch cryptojacking mới sử dụng các gói phần mềm lậu làm mồi nhử để triển khai chương trình đào XMRig tùy chỉnh trên các máy chủ bị xâm nhập.

"Phân tích trình cài đặt đã thu hồi, các trình kích hoạt độ bền và tải trọng khai thác cho thấy một quá trình nhiễm độc đa giai đoạn tinh vi, ưu tiên tối đa hóa tốc độ băm khai thác tiền điện tử, thường làm mất ổn định hệ thống nạn nhân," nhà nghiên cứu Trellix Aswath A [cho biết](https://www.trellix.com/blogs/research/technical-deep-dive-the-monero-mining-campaign/) trong một báo cáo kỹ thuật được công bố vào tuần trước.

"Thêm vào đó, phần mềm độc hại thể hiện khả năng giống như sâu, lây lan qua các thiết bị lưu trữ ngoài, cho phép di chuyển ngang ngay cả trong môi trường không kết nối mạng."

Điểm vào của cuộc tấn công là sử dụng các mồi nhử lừa đảo xã hội, quảng cáo phần mềm cao cấp miễn phí dưới dạng các gói phần mềm lậu, chẳng hạn như trình cài đặt cho các bộ ứng dụng văn phòng, để đánh lừa người dùng không nghi ngờ tải xuống các tệp thực thi có nhúng phần mềm độc hại.

Tệp nhị phân đóng vai trò như hệ thần kinh trung tâm của quá trình nhiễm độc, đảm nhận các vai trò khác nhau như trình cài đặt, trình giám sát, quản lý tải trọng và trình dọn dẹp để giám sát các khía cạnh khác nhau của vòng đời tấn công. Nó có thiết kế mô-đun tách biệt các tính năng giám sát khỏi các tải trọng cốt lõi chịu trách nhiệm khai thác tiền điện tử, leo thang đặc quyền và độ bền nếu nó bị chấm dứt.

[](https://thehackernews.uk/sse-customer-awards-d)

Sự linh hoạt này, hay chuyển đổi chế độ, được thực hiện thông qua các tham số dòng lệnh -

* Không có tham số, để xác thực và di chuyển môi trường trong giai đoạn cài đặt sớm.
* 002 Re:0, để thả các tải trọng chính, bắt đầu trình đào và vào vòng lặp giám sát.
* 016, để khởi động lại quá trình đào nếu nó bị giết.
* barusu, để bắt đầu chuỗi tự hủy bằng cách chấm dứt tất cả các thành phần phần mềm độc hại và xóa tệp.

Có trong phần mềm độc hại là một logic bomb hoạt động bằng cách lấy thời gian hệ thống cục bộ và so sánh nó với một dấu thời gian được định nghĩa trước -

* Nếu nó trước ngày 23 tháng 12 năm 2025, phần mềm độc hại tiến hành cài đặt các mô-đun độ bền và khởi chạy trình đào.
* Nếu nó sau ngày 23 tháng 12 năm 2025, tệp nhị phân được khởi chạy với tham số "barusu", dẫn đến việc "giải thể có kiểm soát" của quá trình nhiễm độc.

Ngày hết hạn cứng ngày 23 tháng 12 năm 2025 cho thấy chiến dịch được thiết kế để chạy vô thời hạn trên các hệ thống bị xâm nhập, với ngày này có thể báo hiệu sự hết hạn của cơ sở hạ tầng điều khiển và kiểm soát (C2) thuê, một sự thay đổi được dự đoán trong thị trường tiền điện tử, hoặc một động thái được lên kế hoạch sang một biến thể phần mềm độc hại mới, Trellix cho biết.

| [](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh-GqKd7kMAr7HhOTtPWnstkNRy3jg6LMSzFkuMOsuWxDO6xuLOK34oX0sCezT255yyj3q5pUx-hC5M6UZ20rGyubX8%5Fb88NEtBC1Vq4gI0GWnqn%5FPfJGNtTRRTYeJ4M5XPHScAR60CHwkICCL-u9wBntgimH6ULm3okJWKg3no08wV-sj1mWSRBm8majUn/s1700-e365/1.jpg) |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Tổng quan về danh sách tệp                                                                                                                                                                                                                                                             |

Trong trường hợp của quy trình nhiễm độc tiêu chuẩn, tệp nhị phân - hoạt động như một "bộ mang tự chứa" cho tất cả các tải trọng độc hại - ghi các thành phần khác nhau vào đĩa, bao gồm một tệp thực thi dịch vụ Telemetry Windows hợp pháp được sử dụng để tải kèm DLL trình đào.

Cũng được thả ra là các tệp để đảm bảo độ bền, chấm dứt các công cụ bảo mật và thực thi trình đào với đặc quyền cao hơn bằng cách sử dụng một trình điều khiển hợp pháp nhưng có lỗ hổng ("[WinRing0x64.sys](https://thehackernews.com/2025/08/shadowcaptcha-exploits-wordpress-sites.html)") như một phần của kỹ thuật được gọi là bring your own vulnerable driver ([BYOVD](https://thehackernews.com/2026/02/reynolds-ransomware-embeds-byovd-driver.html)). Trình điều khiển này dễ bị tổn thương bởi lỗ hổng được theo dõi là [CVE-2020-14979](https://nvd.nist.gov/vuln/detail/cve-2020-14979) (CVSS score: 7.8) cho phép leo thang đặc quyền.

Việc tích hợp khai thác này vào trình đào XMRig là để có quyền kiểm soát tốt hơn cấu hình cấp thấp của CPU và tăng hiệu suất khai thác (tức là tốc độ băm RandomX) từ 15% đến 50%.

"Một tính năng đặc biệt của biến thể XMRig này là khả năng lây lan hung hăng," Trellix cho biết. "Nó không chỉ dựa vào việc người dùng tải xuống trình cài đặt; nó tích cực cố gắng lây lan sang các hệ thống khác thông qua phương tiện có thể tháo rời. Điều này biến phần mềm độc hại từ một Trojan đơn giản thành một con sâu."

Bằng chứng cho thấy hoạt động khai thác diễn ra, mặc dù không thường xuyên, trong suốt tháng 11 năm 2025, trước khi tăng đột biến vào ngày 8 tháng 12 năm 2025.

"Chiến dịch này phục vụ như một lời nhắc nhở mạnh mẽ rằng phần mềm độc hại phổ biến tiếp tục đổi mới," công ty an ninh mạng kết luận. "Bằng cách kết hợp các kỹ thuật lừa đảo xã hội, ngụy trang phần mềm hợp pháp, lây lan giống như sâu và khai thác ở cấp kernel, những kẻ tấn công đã tạo ra một botnet bền bỉ và cực kỳ hiệu quả."

| [](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj-woeqTeTeyKibXugWqe3PyJjZ6VwQzpJJlq4%5FeYvvZzCvyZCF3WY3M6effGHTE8JOgMcYHS2Gg%5FuDp3sJVaFQNmKl1NMckd4kuUcuKUKbwPIYCTnyMTFqhR35DNsBXj6dM%5Fo4ZBwMsoiduwDRszkxABLLkctTAHU7ZLv2oeh55F%5F2%5FmrceI4VQ2Mz6%5FuK/s1700-e365/2.jpg) |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Một "topology giám sát vòng tròn" để đảm bảo độ bền                                                                                                                                                                                                                                       |

Thông báo được đưa ra khi Darktrace cho biết họ đã xác định được một hiện vật phần mềm độc hại có khả năng được tạo bằng một mô hình ngôn ngữ lớn (LLM) khai thác lỗ hổng [React2Shell](https://thehackernews.com/2025/12/react2shell-vulnerability-actively.html) (CVE-2025-55182, CVSS score: 10.0) để tải xuống một bộ công cụ Python, sử dụng quyền truy cập để thả một trình đào XMRig bằng cách chạy một lệnh shell.

"Mặc dù số tiền được tạo ra bởi kẻ tấn công trong trường hợp này tương đối thấp, và khai thác tiền điện tử còn xa lạ với một kỹ thuật mới, chiến dịch này là bằng chứng cho thấy các LLM AI đã làm cho tội phạm mạng trở nên dễ tiếp cận hơn bao giờ hết," các nhà nghiên cứu Nathaniel Bill và Nathaniel Jones [cho biết](https://www.darktrace.com/blog/ai-llm-generated-malware-used-to-exploit-react2shell).

"Một phiên nhắc lệnh duy nhất với một mô hình là đủ để kẻ tấn công này tạo ra một khung khai thác hoạt động và xâm nhập hơn chín mươi máy chủ, cho thấy giá trị vận hành của AI cho các đối thủ không nên bị đánh giá thấp."

[](https://thehackernews.uk/ztw-hands-on-d)

Những kẻ tấn công cũng đã bắt đầu sử dụng một bộ công cụ có tên là [ILOVEPOOP](https://main.whoisxmlapi.com/blog/to-cache-a-predator-ilovepoop-toolkit-react2shell-cve-2025-55182) để quét các hệ thống bị phơi bày vẫn dễ bị tổn thương bởi React2Shell, có thể trong nỗ lực đặt nền móng cho các cuộc tấn công trong tương lai, theo WhoisXML API. Hoạt động dò tìm đặc biệt nhắm vào các tổ chức chính phủ, quốc phòng, tài chính và công nghiệp ở Hoa Kỳ.

"Điều làm cho ILOVEPOOP trở nên bất thường là sự không khớp giữa cách nó được xây dựng và cách nó được sử dụng," Alex Ronquillo, phó chủ tịch sản phẩm tại WhoisXML API cho biết. "Chính mã phản ánh kiến thức chuyên môn về React Server Components internals và sử dụng các kỹ thuật tấn công không được tìm thấy trong bất kỳ bộ công cụ React2Shell nào khác được ghi nhận."

"Nhưng những người triển khai nó đã mắc những sai lầm vận hành cơ bản khi tương tác với các hệ thống giám sát honeypot của WhoisXML API - những lỗi mà một kẻ tấn công tinh vi thường tránh. Về mặt thực tế, khoảng cách này chỉ ra sự phân chia lao động."

"Chúng ta có thể đang nhìn vào hai nhóm khác nhau: một nhóm xây dựng công cụ và một nhóm sử dụng nó. Chúng ta thấy mô hình này trong các hoạt động được tài trợ bởi nhà nước - một nhóm có khả năng phát triển công cụ, sau đó chuyển giao cho các nhà khai thác chạy các chiến dịch quét hàng loạt. Các nhà khai thác không cần hiểu cách công cụ hoạt động - họ chỉ cần chạy nó."