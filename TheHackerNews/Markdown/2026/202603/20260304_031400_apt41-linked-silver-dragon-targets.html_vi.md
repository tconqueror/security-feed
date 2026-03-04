# APT41 Liên Kết Silver Dragon Tấn Công Chính Phủ Sử Dụng Cobalt Strike và Google Drive C2

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhGPaqQJe-7ak-qgx29%5Fh6G7zUiJhGiBSHZEiydrRzZzuKVlVMBzrJNLFndAvmu15EzX2SXQ8NUHKyH9ZJDQRQMnXukmrUfdPor35gswSxUuTNGGXo7h8eOhDNBVAaCGEo%5FohNYv2-8W-zpOuSSHYqCB5iURwesotjNTK9a3926UdkuqI2uz-zUBMzNP5cU/s1700-e365/dragon.jpg)

Các nhà nghiên cứu bảo mật đã tiết lộ chi tiết về một nhóm đe dọa APT (Advanced Persistent Threat) có tên **Silver Dragon**, được liên kết với các cuộc tấn công mạng nhắm vào các thực thể ở châu Âu và Đông Nam Á ít nhất từ giữa năm 2024.

"Silver Dragon đạt được quyền truy cập ban đầu bằng cách khai thác các máy chủ internet công khai và gửi email lừa đảo chứa các tệp đính kèm độc hại," Check Point [cho biết](https://research.checkpoint.com/2026/silver-dragon-targets-organizations-in-southeast-asia-and-europe/) trong một báo cáo kỹ thuật. "Để duy trì sự hiện diện, nhóm này chiếm quyền kiểm soát các dịch vụ Windows hợp pháp, cho phép các quy trình malware hòa nhập vào hoạt động hệ thống bình thường."

Silver Dragon được đánh giá đang hoạt động trong khuôn khổ [mái nhà APT41](https://thehackernews.com/2025/09/china-linked-apt41-hackers-target-us.html). APT41 là cryptonym được gán cho một nhóm hack Trung Quốc nổi tiếng, được biết đến với việc nhắm mục tiêu vào các lĩnh vực chăm sóc sức khỏe, viễn thông, công nghệ cao, giáo dục, dịch vụ du lịch và truyền thông để do thám mạng từ năm 2012\. Nó cũng được cho là tham gia vào các hoạt động vì động cơ tài chính tiềm năng ngoài sự kiểm soát của nhà nước.

Các cuộc tấn công do Silver Dragon thực hiện đã được phát hiện chủ yếu nhắm vào các thực thể chính phủ, với kẻ tấn công sử dụng các beacon Cobalt Strike để duy trì quyền truy cập trên các máy chủ bị xâm nhập. Nó cũng được biết đến với việc sử dụng các kỹ thuật như DNS tunneling cho giao tiếp điều khiển và kiểm soát (C2) để vượt qua phát hiện.

Check Point cho biết họ đã xác định ba chuỗi lây nhiễm khác nhau để phân phối Cobalt Strike: [AppDomain hijacking](https://attack.mitre.org/techniques/T1574/014/), service DLL, và lừa đảo qua email.

[](https://thehackernews.uk/not-fast-enough-d)

"Hai chuỗi lây nhiễm đầu tiên, AppDomain hijacking và Service DLL, cho thấy sự trùng lặp hoạt động rõ ràng," công ty bảo mật mạng cho biết. "Chúng đều được phân phối qua các kho lưu trữ nén, cho thấy việc sử dụng trong các tình huống hậu khai thác. Trong một số trường hợp, các chuỗi này được triển khai sau khi xâm nhập vào các máy chủ công khai dễ bị tổn thương."

Hai chuỗi này sử dụng một kho lưu trữ RAR chứa một tập lệnh batch, với chuỗi đầu tiên sử dụng nó để thả MonikerLoader, một trình tải dựa trên NET chịu trách nhiệm giải mã và thực thi giai đoạn thứ hai trực tiếp trong bộ nhớ. Giai đoạn thứ hai, cho phần của nó, bắt chước hành vi của MonikerLoader, hoạt động như một kênh để tải tải trọng beacon Cobalt Strike cuối cùng.

Mặt khác, chuỗi service DLL sử dụng một tập lệnh batch để phân phối một trình tải DLL shellcode có tên BamboLoader, được đăng ký là một dịch vụ Windows. Một malware C++ được obfuscate mạnh, nó được sử dụng để giải mã và nén shellcode được lưu trữ trên đĩa, và tiêm nó vào một quy trình Windows hợp pháp, chẳng hạn như "taskhost.exe." Binary mục tiêu để tiêm là có thể cấu hình trong BamboLoader.

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiPleTdpYzAN-hRx0ZQDAutOQ8NHCiTk-IGca5jGqaztyxqrArnvgmOhypgWJpvWbPPAbTOGyLe5yWXHEJXhKnCz83KXuRXrd%5F3yWt70Q-ZUemrenbKs42eM4n5OMsDEevSVM9LV3sfgrR9MIaHCq-u7UFwYWTcemgGEZUyuQfeDE15dcuLYqh41nXDfFWp/s1700-e365/cp.png)

Chuỗi lây nhiễm thứ ba liên quan đến một chiến dịch phishing chủ yếu nhắm vào Uzbekistan với các tệp rút gọn Windows độc hại (LNK) làm tệp đính kèm. Tệp LNK được vũ trang được thiết kế để khởi chạy mã PowerShell thông qua "cmd.exe," dẫn đến việc trích xuất và thực thi các tải trọng giai đoạn tiếp theo. Điều này bao gồm bốn tệp khác nhau -

* Tài liệu decoy
* Tệp thực thi hợp pháp dễ bị tổn thương bởi DLL side-loading ("GameHook.exe")
* DLL độc hại aka BamboLoader ("graphics-hook-filter64.dll")
* Tải trọng Cobalt Strike được mã hóa ("simhei.dat")

Là một phần của chiến dịch này, tài liệu decoy được hiển thị cho nạn nhân, trong khi đó, trong nền, DLL rogue được sideloaded qua "GameHook.exe" để cuối cùng khởi chạy Cobalt Strike. Các cuộc tấn công cũng được đặc trưng bởi việc triển khai các công cụ hậu khai thác khác nhau -

* **SilverScreen**, một công cụ giám sát màn hình .NET được sử dụng để chụp ảnh màn hình định kỳ về hoạt động của người dùng, bao gồm cả vị trí con trỏ chính xác.
* **SSHcmd**, một tiện ích dòng lệnh SSH .NET cung cấp khả năng thực thi lệnh từ xa và chuyển tệp qua SSH.
* **GearDoor**, một backdoor NET có điểm tương đồng với MonikerLoader và giao tiếp với cơ sở hạ tầng C2 của nó qua Google Drive.

[](https://thehackernews.uk/fs-report-d)

Sau khi được thực thi, backdoor xác thực vào tài khoản Google Drive do kẻ tấn công kiểm soát và tải lên một tệp nhịp tim chứa thông tin hệ thống cơ bản. Thú vị thay, backdoor sử dụng các phần mở rộng tệp khác nhau để chỉ ra bản chất của tác vụ cần thực hiện trên máy chủ bị nhiễm. Kết quả thực thi tác vụ được thu thập và tải lên Drive.

* **\*.png**, để gửi các tệp nhịp tim.
* **\*.pdf**, để nhận và thực thi lệnh, liệt kê nội dung của một thư mục, tạo thư mục mới, và xóa tất cả các tệp trong một thư mục được chỉ định. Kết quả của hoạt động được gửi đến máy chủ dưới dạng tệp \*.db.
* **\*.cab**, để nhận và thực thi lệnh để thu thập thông tin máy chủ và danh sách các quy trình đang chạy, liệt kê các tệp và thư mục, chạy lệnh qua "cmd.exe" hoặc các tác vụ được lên lịch, tải tệp lên Google Drive, và chấm dứt implant. Trạng thái thực thi được tải lên dưới dạng tệp .bak.
* **\*.rar**, để nhận và thực thi tải trọng. Nếu tệp RAR được đặt tên là "wiatrace.bak," backdoor xem nó như một gói tự cập nhật. Kết quả được tải lên dưới dạng các tệp .bak.
* **\*.7z**, để nhận và thực thi các plugin trong bộ nhớ. Kết quả được tải lên dưới dạng các tệp .bak.

Liên kết của Silver Dragon với APT41 bắt nguồn từ sự trùng lặp kỹ thuật với [các tập lệnh cài đặt hậu khai thác](https://thehackernews.com/2021/06/chinese-hackers-believed-to-be-behind.html) trước đây [được gán cho cái sau](https://cloud.google.com/blog/topics/threat-intelligence/apt41-initiates-global-intrusion-campaign-using-multiple-exploits/) và thực tế rằng cơ chế giải mã được sử dụng bởi BamboLoader đã được quan sát trong các trình tải shellcode liên kết đến hoạt động APT có nguồn gốc từ Trung Quốc.

"Nhóm này liên tục phát triển các công cụ và kỹ thuật của mình, tích cực thử nghiệm và triển khai các khả năng mới trên các chiến dịch khác nhau," Check Point cho biết. "Việc sử dụng các lỗ hổng khai thác đa dạng, các trình tải tùy chỉnh, và giao tiếp C2 dựa trên tệp tin tinh vi phản ánh một nhóm mối đe dọa được trang bị tốt và linh hoạt."