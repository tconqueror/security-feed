# Microsoft: Lỗ hổng Sploitlight trên macOS rò rỉ dữ liệu Apple Intelligence

![Apple](https://www.bleepstatic.com/content/hl-images/2025/07/28/Apple.jpg)

Các tên tội phạm có thể lợi dụng một lỗ hổng gần đây đã được vá trên macOS để vượt qua các kiểm tra bảo mật của Transparency, Consent, and Control (TCC) và đánh cắp thông tin nhạy cảm của người dùng, bao gồm dữ liệu được lưu trữ của Apple Intelligence.

TCC là một công nghệ bảo mật và một khuôn khổ quyền riêng tư ngăn chặn các ứng dụng truy cập dữ liệu cá nhân của người dùng bằng cách cung cấp cho macOS quyền kiểm soát cách mà dữ liệu của họ được truy cập và sử dụng bởi các ứng dụng trên các thiết bị của Apple.

Apple đã [sửa lỗ hổng bảo mật](https://support.apple.com/en-us/122373) được theo dõi là CVE-2025-31199 (được báo cáo bởi Jonathan Bar Or, Alexia Wilson và Christine Fossaceca của Microsoft) trong các bản vá được phát hành vào tháng 3 cho macOS Sequoia 15.4 với "cải thiện việc xóa dữ liệu".

Khi Apple chỉ cho phép truy cập TCC cho các ứng dụng có quyền truy cập toàn bộ ổ đĩa và tự động chặn việc thực thi mã trái phép, các nhà nghiên cứu bảo mật của Microsoft phát hiện rằng các tên tội phạm có thể sử dụng quyền truy cập đặc quyền của các plugin Spotlight để truy cập các tập tin nhạy cảm và đánh cắp nội dung của chúng.

Họ đã cho thấy trong một báo cáo được công bố hôm nay rằng lỗ hổng (được gọi là **Sploitlight** và được Apple mô tả là một "vấn đề ghi lại") có thể bị khai thác để thu thập dữ liệu quý giá, bao gồm thông tin liên quan đến Apple Intelligence và thông tin từ các thiết bị khác liên kết với tài khoản iCloud.

Điều này bao gồm, nhưng không giới hạn ở, metadata về ảnh và video, dữ liệu định vị chính xác, dữ liệu nhận diện khuôn mặt và người, bối cảnh hoạt động và sự kiện của người dùng, album ảnh và thư viện chia sẻ, lịch sử tìm kiếm và sở thích người dùng, cũng như các ảnh và video đã bị xóa.

![Spoitlight exploit](https://www.bleepstatic.com/images/news/u/1109292/2025/Spoitlight-exploit.jpg)

_Lỗ hổng Spoitlight (Microsoft)_

Kể từ năm 2020, Apple đã vá các lỗ hổng TCC khác khai thác các mount của Time Machine ([CVE-2020-9771](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-9771)), tấn công tiêm biến môi trường ([CVE-2020-9934](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-9934)), và vấn đề kết luận gói ([CVE-2021-30713](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-30713))_. Trong quá khứ, các nhà nghiên cứu bảo mật của Microsoft cũng đã phát hiện nhiều lỗ hổng TCC khác, bao gồm [powerdir](https://www.bleepingcomputer.com/news/microsoft/microsoft-powerdir-bug-gives-access-to-protected-macos-user-data/) ([CVE-2021-30970](https://www.microsoft.com/security/blog/2022/01/10/new-macos-vulnerability-powerdir-could-lead-to-unauthorized-user-data-access/)) và [HM-Surf](https://www.microsoft.com/security/blog/2024/10/17/new-macos-vulnerability-hm-surf-could-lead-to-unauthorized-data-access/), cũng có thể bị lạm dụng để truy cập dữ liệu riêng tư của người dùng.

"Trong khi tương tự như các lỗ hổng TCC trước đây như HM-Surf và powerdir, những ảnh hưởng của lỗ hổng này, mà chúng tôi gọi là 'Sploitlight' vì việc sử dụng các plugin Spotlight, nghiêm trọng hơn do khả năng truy xuất và rò rỉ thông tin nhạy cảm được lưu trữ bởi Apple Intelligence, chẳng hạn như dữ liệu định vị chính xác, metadata về ảnh và video, dữ liệu nhận diện khuôn mặt và người, lịch sử tìm kiếm và sở thích người dùng và nhiều hơn nữa," [Microsoft cho biết](https://www.microsoft.com/en-us/security/blog/2025/07/28/sploitlight-analyzing-a-spotlight-based-macos-tcc-vulnerability/) vào thứ Hai.

"Các rủi ro này càng trở nên phức tạp và tăng cao bởi khả năng liên kết từ xa giữa các tài khoản iCloud, có nghĩa là một kẻ tấn công có quyền truy cập vào thiết bị macOS của người dùng cũng có thể khai thác lỗ hổng để xác định thông tin từ xa của các thiết bị khác liên kết với cùng một tài khoản iCloud."

Trong những năm gần đây, các nhà nghiên cứu bảo mật của Microsoft đã phát hiện nhiều lỗ hổng macOS nghiêm trọng khác, bao gồm một lỗ hổng vượt qua SIP được gọi là 'Shrootless' ([CVE-2021-30892](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-30892)), được báo cáo vào năm 2021, cho phép kẻ tấn công cài đặt rootkits trên các Mac bị xâm phạm.

Gần đây hơn, họ đã phát hiện một lỗ hổng SIP được gọi là 'Migraine' ([CVE-2023-32369](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2023-32369)) và một lỗ hổng bảo mật được gọi là Achilles ([CVE-2022-42821](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2022-42821)), có thể bị khai thác để cài đặt phần mềm độc hại bằng cách sử dụng các ứng dụng không tin cậy vượt qua các hạn chế thực thi của Gatekeeper.

Năm ngoái, họ đã báo cáo [một lỗ hổng vượt qua SIP](https://www.bleepingcomputer.com/news/security/microsoft-macos-bug-lets-hackers-install-malicious-kernel-drivers/) khác ([CVE-2024-44243](https://nvd.nist.gov/vuln/detail/CVE-2024-44243)) cho phép các tác nhân gây hại triển khai các trình điều khiển kernel độc hại bằng cách tải các phần mở rộng kernel của bên thứ ba.