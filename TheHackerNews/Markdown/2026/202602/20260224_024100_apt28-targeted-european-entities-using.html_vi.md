# APT28 Tấn Công Các Thực Thể Châu Âu Sử Dụng Malware Macro Dựa Trên Webhook

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjSwbKDzax%5FHh%5FRHSU7qEInhqGvzoEncnUbB3WgxiRorJPzrvWGo2GCCC0%5F94YDAdaIs3gBMgO8N4iM4FoMzMiaM1icI-NX2qTf5Dflmv25XR66ni1JEcMl0HxwApTpA5W48R9KLgF5oo7uB8FAjoUrI3h7FxPgoER%5FFCPPgJ2gHZQyk3BR4kZkt-tU6CFG/s1700-e365/malware-attack-eu.jpg)

Nhóm đe dọa được tài trợ bởi nhà nước có liên kết với Nga được theo dõi là [APT28](https://thehackernews.com/2026/02/apt28-uses-microsoft-office-cve-2026.html) đã được quy cho một chiến dịch mới nhắm vào các thực thể cụ thể ở Tây và Trung Âu.

Hoạt động này, theo nhóm tình báo đe dọa LAB52 của S2 Grupo, đã hoạt động từ tháng 9 năm 2025 đến tháng 1 năm 2026\. Nó đã được mã hóa là **Operation MacroMaze**. "Chiến dịch dựa vào các công cụ cơ bản và khai thác các dịch vụ hợp pháp cho cơ sở hạ tầng và thu thập dữ liệu," công ty an ninh mạng [cho biết](https://lab52.io/blog/operation-macromaze-new-apt28-campaign-using-basic-tooling-and-legit-infrastructure/).

Các chuỗi tấn công sử dụng email lừa đảo có chủ đích làm điểm khởi đầu để phân phối các tài liệu mồi nhử chứa một yếu tố cấu trúc chung trong XML của chúng, một trường có tên "INCLUDEPICTURE" trỏ đến URL webhook\[.\]site lưu trữ hình ảnh JPG. Điều này, lần lượt, khiến tệp hình ảnh được lấy từ máy chủ từ xa khi tài liệu được mở.

Nói cách khác, cơ chế này hoạt động như một cơ chế beaconing tương tự như một pixel theo dõi kích hoạt yêu cầu HTTP đi ra ngoài đến URL webhook\[.\]site khi mở tài liệu. Người điều hành máy chủ có thể đăng nhập siêu dữ liệu liên quan đến yêu cầu, xác nhận rằng tài liệu đã thực sự được mở bởi người nhận.

[](https://thehackernews.uk/ztw-hands-on-d)

LAB52 cho biết họ đã xác định nhiều tài liệu với macro hơi được điều chỉnh giữa cuối tháng 9 năm 2025 và tháng 1 năm 2026, tất cả đều hoạt động như một dropper để thiết lập chân trong trên máy chủ bị xâm nhập và giao thêm tải trọng.

"Mặc dù logic cốt lõi của tất cả các macro được phát hiện vẫn nhất quán, các script cho thấy sự tiến hóa trong các kỹ thuật lẩn tránh, từ việc thực thi trình duyệt 'không đầu' trong phiên bản cũ hơn đến việc sử dụng mô phỏng bàn phím (SendKeys) trong các phiên bản mới hơn để có khả năng bỏ qua các lời nhắc bảo mật," công ty an ninh mạng Tây Ban Nha giải thích.

Macro được thiết kế để thực thi Visual Basic Script (VBScript) để chuyển nhiễm sang giai đoạn tiếp theo. Script, cho phần của nó, chạy một tệp CMD để thiết lập tính liên tục thông qua các tác vụ theo lịch trình và khởi chạy một script batch để hiển thị một tải trọng HTML được mã hóa Base64 nhỏ trong Microsoft Edge ở chế độ không đầu để lẩn tránh phát hiện, lấy lệnh từ điểm cuối webhook\[.\]site, thực thi nó, chụp đầu ra của nó, và thu thập dữ liệu đến một thể hiện webhook\[.\]site khác dưới dạng tệp HTML.

Một biến thể thứ hai của script batch đã được phát hiện là tránh thực thi không đầu để ưu tiên di chuyển cửa sổ trình duyệt ra khỏi màn hình, sau đó chấm dứt quyết liệt tất cả các quá trình trình duyệt Edge khác để đảm bảo một môi trường được kiểm soát.

"Khi tệp HTML kết quả được hiển thị bởi Microsoft Edge, biểu mẫu được gửi, khiến đầu ra lệnh thu thập được được thu thập dữ liệu đến điểm cuối webhook từ xa mà không cần tương tác của người dùng," LAB52 cho biết. "Kỹ thuật thu thập dữ liệu dựa trên trình duyệt này tận dụng chức năng HTML tiêu chuẩn để truyền dữ liệu trong khi giảm thiểu các hiện vật có thể phát hiện trên đĩa."

"Chiến dịch này chứng minh rằng sự đơn giản có thể mạnh mẽ. Kẻ tấn công sử dụng các công cụ rất cơ bản (tệp batch, trình khởi chạy VBS nhỏ và HTML đơn giản) nhưng sắp xếp chúng một cách cẩn thận để tối đa hóa tính lén lút: Di chuyển hoạt động vào các phiên trình duyệt ẩn hoặc ngoài màn hình, dọn dẹp hiện vật, và thuê ngoài cả việc giao tải trọng và thu thập dữ liệu cho các dịch vụ webhook được sử dụng rộng rãi."