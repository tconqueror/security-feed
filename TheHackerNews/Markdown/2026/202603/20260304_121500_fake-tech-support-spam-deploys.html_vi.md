# Spam hỗ trợ kỹ thuật giả triển khai Havoc C2 tùy chỉnh trên nhiều tổ chức

Threat hunters đã chú ý đến một chiến dịch mới trong đó các tác nhân xấu ngụy trang thành hỗ trợ kỹ thuật giả để cung cấp framework [Havoc](https://github.com/HavocFramework/Havoc) command-and-control (C2) như tiền đề cho việc đánh cắp dữ liệu hoặc tấn công ransomware.

Các vụ xâm nhập, [được xác định](https://www.huntress.com/blog/fake-tech-support-havoc-command-control) bởi Huntress vào tháng trước trên năm tổ chức đối tác, liên quan đến việc các tác nhân đe dọa sử dụng email spam như mồi nhử, sau đó là cuộc gọi từ bàn hỗ trợ kỹ thuật kích hoạt đường ống cung cấp malware nhiều lớp.

"Trong một tổ chức, đối thủ đã di chuyển từ quyền truy cập ban đầu đến chín endpoint bổ sung trong vòng mười một giờ, triển khai hỗn hợp các payload [Havoc Demon](https://attack.mitre.org/software/S1229/) tùy chỉnh và các công cụ RMM hợp pháp để duy trì hiện diện, với tốc độ di chuyển ngang gợi ý mạnh mẽ rằng mục tiêu cuối cùng là đánh cắp dữ liệu, ransomware, hoặc cả hai," các nhà nghiên cứu Michael Tigges, Anna Pham, và Bryan Masters cho biết.

Đáng chú ý là phương thức hoạt động này nhất quán với các cuộc tấn công email bombing và phishing Microsoft Teams [được tổ chức](https://thehackernews.com/2025/01/qakbot-linked-bc-malware-adds-enhanced.html) bởi [các tác nhân đe dọa](https://thehackernews.com/2025/06/former-black-basta-members-use.html) liên kết với hoạt động ransomware Black Basta trong quá khứ. Mặc dù nhóm tội phạm mạng này dường như đã im lặng sau khi rò rỉ công khai nhật ký trò chuyện nội bộ của họ vào năm ngoái, sự hiện diện tiếp tục của playbook của nhóm này cho thấy hai kịch bản khả thi.

[](https://thehackernews.uk/not-fast-enough-d)

Một khả năng là các chi nhánh cũ của Black Basta đã chuyển sang các hoạt động ransomware khác và đang sử dụng chúng để tiến hành các cuộc tấn công mới, hoặc thứ hai, các tác nhân đe dọa đối thủ đã áp dụng cùng chiến lược để tiến hành kỹ thuật xã hội và có được quyền truy cập ban đầu.

Chuỗi tấn công bắt đầu với chiến dịch spam nhằm làm ngập hộp thư của mục tiêu với email rác. Ở bước tiếp theo, các tác nhân đe dọa, ngụy trang thành hỗ trợ kỹ thuật, liên hệ với người nhận và lừa họ cấp quyền truy cập từ xa vào máy của họ thông qua phiên Quick Assist hoặc bằng cách cài đặt các công cụ như AnyDesk để giúp khắc phục sự cố.

Với quyền truy cập đã được thiết lập, đối thủ không lãng phí thời gian khởi chạy trình duyệt web và điều hướng đến một trang landing page giả được lưu trữ trên Amazon Web Services (AWS) giả mạo Microsoft và hướng dẫn nạn nhân nhập địa chỉ email của họ để truy cập hệ thống cập nhật quy tắc chống spam của Outlook và cập nhật các quy tắc spam.

Nhấp vào nút "Cập nhật cấu hình quy tắc" trên trang giả mạo này kích hoạt việc thực thi một script hiển thị overlay yêu cầu người dùng nhập mật khẩu của họ.

"Cơ chế này phục vụ hai mục đích: nó cho phép tác nhân đe dọa (TA) thu thập thông tin đăng nhập, khi kết hợp với địa chỉ email bắt buộc, cung cấp quyền truy cập vào bảng điều khiển; đồng thời, nó thêm một lớp xác thực vào tương tác, thuyết phục người dùng rằng quy trình là hợp pháp," Huntress cho biết.

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEii4Lib-wKbh4pAovQsn5oiBbzv2fPcZbMECZ03FDMU0cFMzd5BNvg-qFAmq8OrTFYJ8f3%5FkhRg9aqLAcM5zOqiA8xzrmUTzvFrjnfcJQ%5F-NfgYvZCJl146UiHI4FONhE2zrMfOtmEm-8P3P1VRbh-pcegdvLp3LtXjhODwoNBeOq4A%5F4WS%5FRhQ0Cv2APDN/s1700-e365/anti.jpg)

Cuộc tấn công cũng dựa vào việc tải xuống bản vá chống spam được cho là, điều này, lần lượt, dẫn đến việc thực thi một nhị phân hợp pháp có tên "ADNotificationManager.exe" (hoặc "DLPUserAgent.exe" và "Werfault.exe") để sideload một DLL độc hại. Payload DLL này triển khai kỹ thuật đánh lạc hướng phòng thủ và thực thi payload shellcode Havoc bằng cách tạo một thread chứa agent Demon.

Ít nhất một trong các DLL được xác định ("vcruntime140_1.dll") tích hợp thêm các thủ thuật để né tránh phát hiện bởi phần mềm bảo mật sử dụng obfuscation luồng điều khiển, các vòng lặp trì hoãn dựa trên thời gian, và các kỹ thuật như [Hell's Gate](https://thehackernews.com/2025/04/lazarus-hits-6-south-korean-firms-via.html) và [Halo's Gate](https://blog.sektor7.net/#!res/2021/halosgate.md) để [hook](https://malwaretech.com/2023/12/an-introduction-to-bypassing-user-mode-edr-hooks.html) [các hàm ntdll.dll](https://0xmaz.me/posts/HookChain-A-Deep-Dive-into-Advanced-EDR-Bypass-Techniques/) và vượt qua các giải pháp phát hiện và đáp ứng điểm cuối (EDR).

"Sau khi triển khai thành công Havoc Demon trên host beachhead, các tác nhân đe dọa bắt đầu di chuyển ngang trong môi trường nạn nhân," các nhà nghiên cứu cho biết. "Mặc dù kỹ thuật xã hội và cung cấp malware ban đầu đã thể hiện một số kỹ thuật thú vị, hoạt động thao tác trực tiếp bằng bàn phím sau đó tương đối đơn giản."

Điều này bao gồm việc tạo các tác vụ theo lịch để khởi chạy payload Havoc Demon mỗi khi các endpoint bị nhiễm được khởi động lại, cung cấp cho các tác nhân đe dọa quyền truy cập từ xa liên tục. Điều đó nói lên rằng, tác nhân đe dọa đã được phát hiện triển khai các công cụ giám sát và quản lý từ xa hợp pháp (RMM) như Level RMM và XEOX trên một số host bị xâm phạm thay vì Havoc, do đó đa dạng hóa các cơ chế duy trì hiện diện của họ.

[](https://thehackernews.uk/fs-report-d)

Một số điểm chính từ các cuộc tấn công này là các tác nhân đe dọa sẵn sàng hơn để ngụy trang thành nhân viên hỗ trợ kỹ thuật và gọi các số điện thoại cá nhân nếu nó cải thiện tỷ lệ thành công, các kỹ thuật như đánh lạc hướng phòng thủ trước đây chỉ giới hạn trong các cuộc tấn công vào các công ty lớn hoặc chiến dịch được tài trợ bởi nhà nước đang trở nên ngày càng phổ biến, và malware commodity được tùy chỉnh để vượt qua các signature dựa trên mẫu.

Đáng chú ý là tốc độ mà các cuộc tấn công tiến triển nhanh chóng và quyết liệt từ xâm nhập ban đầu đến di chuyển ngang, cũng như các phương pháp đa dạng được sử dụng để duy trì hiện diện.

"Điều bắt đầu như một cuộc gọi từ 'hỗ trợ kỹ thuật' kết thúc với một sự xâm phạm mạng được trang bị đầy đủ – các Demon Havoc được sửa đổi được triển khai trên các endpoint, các công cụ RMM hợp pháp được tái sử dụng như hiện diện dự phòng," Huntress kết luận. "Chiến dịch này là một nghiên cứu điển hình về cách các đối thủ hiện đại xếp chồng tinh vi ở mọi giai đoạn: kỹ thuật xã hội để vào cửa, sideloading DLL để ẩn mình, và hiện diện đa dạng để tồn tại khắc phục sự cố."