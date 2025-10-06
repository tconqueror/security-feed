# Steam và Microsoft cảnh báo về lỗ hổng Unity khiến game thủ dễ bị tấn công

![Steam and Microsoft cảnh báo về lỗ hổng Unity khiến game thủ dễ bị tấn công](https://www.bleepstatic.com/content/hl-images/2025/10/06/Unity.jpg)

Một lỗ hổng thực thi mã trong engine trò chơi Unity có thể bị khai thác để thực thi mã trên Android và leo thang đặc quyền trên Windows.

Unity là một engine trò chơi đa nền tảng và nền tảng phát triển cung cấp các công cụ dựng hình, vật lý, hoạt hình và scripting cho các nhà phát triển để tạo các tựa game cho Windows, macOS, Android, iOS, consoles và web.

Rất nhiều trò chơi di động được xây dựng bằng Unity, cũng như các tựa game indie và tầm trung trên PC/console. Nền tảng này cũng được sử dụng trong các ngành ngoài trò chơi cho các ứng dụng 3D thời gian thực.

### Valve và Microsoft cảnh báo người dùng

Để ứng phó với rủi ro, Steam đã hành động bằng cách phát hành một [new Client update](https://steamcommunity.com/groups/steamworks/announcements/detail/524229329545071275) chặn việc khởi chạy các custom URI schemes nhằm ngăn khai thác qua nền tảng phân phối của họ.

Đồng thời, Valve khuyến nghị các nhà phát hành biên dịch lại trò chơi của họ bằng một phiên bản Unity an toàn, hoặc cắm một phiên bản đã được vá của file 'UnityPlayer.dll' ngay vào bản build hiện có.

Microsoft cũng đã [published a bulletin](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59489) để cảnh báo về vấn đề này, khuyến nghị người dùng gỡ cài đặt các trò chơi dễ bị tấn công cho đến khi các phiên bản mới sửa CVE-2025-59489 có sẵn.

Công ty cho biết một số tựa game phổ biến dễ bị tổn thương, bao gồm Hearthstone, The Elder Scrolls: Blades, Fallout Shelter, DOOM (2019), Wasteland 3 và Forza Customs.

Unity khuyến nghị các nhà phát triển cập nhật editor lên nhánh phiên bản mới nhất rồi biên dịch lại và triển khai lại trò chơi hoặc ứng dụng của họ.

### Bản vá mở rộng sang một số phiên bản không được hỗ trợ

Lỗ hổng được theo dõi là [CVE-2025-59489](https://nvd.nist.gov/vuln/detail/CVE-2025-59489) và ảnh hưởng đến thành phần Runtime. Nó cho phép tải file không an toàn và chèn file cục bộ (local file inclusion), và có thể dẫn tới thực thi mã và lộ thông tin.

Nghiên cứu viên của GMO Flatt Security, ‘RyotaK’, đã phát hiện lỗ hổng vào tháng Năm, tại Meta Bug Bounty Researcher Conference và cho biết nó ảnh hưởng tới tất cả các trò chơi được xây dựng trên các phiên bản engine bắt đầu từ 2017.1.

“[The vulnerability] có thể cho phép thực thi mã cục bộ và truy cập thông tin mật trên các thiết bị đầu cuối chạy ứng dụng được xây dựng bằng Unity,” Unity cảnh báo trong [security bulletin](https://unity.com/security/sept-2025-01).

“Thực thi mã sẽ bị giới hạn ở mức đặc quyền của ứng dụng dễ bị tổn thương, và lộ thông tin sẽ bị giới hạn ở thông tin mà ứng dụng dễ bị tổn thương có thể truy cập được.”

Trong một [technical writeup](http://flatt.tech/research/posts/arbitrary-code-execution-in-unity-runtime/), RyotaK đã chỉ ra rằng cách Unity xử lý Android Intents cho phép bất kỳ ứng dụng độc hại nào được cài trên cùng thiết bị với trò chơi dễ bị tổn thương tải và thực thi một thư viện native do attacker cung cấp.

Điều này cho phép kẻ tấn công đạt được thực thi mã tuỳ ý với các đặc quyền của trò chơi mục tiêu.

Trong khi RyotaK phát hiện vấn đề trên Android, nguyên nhân gốc rễ - cách Unity xử lý đối số dòng lệnh _\-xrsdk-pre-init-library_ mà không kiểm tra hoặc làm sạch đúng cách, cũng tồn tại trên các nền tảng Windows, macOS và Linux.

Có các đường nhập dữ liệu khác nhau trên những hệ thống này có thể cung cấp các đối số không đáng tin cậy hoặc thay đổi đường dẫn tìm kiếm thư viện trên ứng dụng bị tấn công, nên khi các điều kiện đạt, việc khai thác là khả dĩ.

Unity cho biết họ chưa quan sát thấy khai thác tích cực tính đến khi bản tin của họ được công bố vào ngày 2 tháng 10.

Các bản vá đã có và các bước khắc phục bao gồm cập nhật "Unity Editor lên phiên bản mới nhất rồi biên dịch lại và triển khai ứng dụng" và thay thế binary runtime của Unity bằng phiên bản đã được vá.

Unity đã phát hành bản vá cho các phiên bản đã hết hỗ trợ bắt đầu từ 2019.1 trở đi. Các phiên bản cũ hơn không còn được hỗ trợ sẽ không nhận được bản vá.