+-+- 
# Google Chrome sẽ chặn các lần khởi động trình duyệt với quyền quản trị để tăng cường bảo mật

![Chrome](https://www.bleepstatic.com/content/hl-images/2023/06/16/Google-Chrome-headpic.jpg)

Google đang triển khai một thay đổi cho Chromium để "giảm quyền" Google Chrome, khiến nó không chạy với tư cách là quản trị viên nhằm tăng cường bảo mật trên Windows.

Microsoft [trước đây đã giới thiệu](https://www.bleepingcomputer.com/news/security/new-microsoft-edge-to-warn-users-when-in-administrator-mode/) một tính năng tương tự vào năm 2019 cho trình duyệt Edge. Khi người dùng khởi động Edge với quyền cao, một cảnh báo sẽ xuất hiện, khuyên họ khởi động lại trình duyệt mà không có quyền quản trị.

![Thông báo về Microsoft Edge](https://www.bleepstatic.com/images/news/web-browsers/edge/chromium-edge/administrative-mode-alert/browser-alert.jpg)

Sau đó, Microsoft đã điều chỉnh tính năng này để tự động ngăn trình duyệt Edge khởi động với quyền cao.

Microsoft hiện đang mang các cải tiến tương tự đến Chromium, với các nhà phát triển đã gửi một cam kết cho mã nguồn Chromium.

Như [được phát hiện](https://x.com/Leopeva64/status/1921807525009064363) bởi Leo trên X, Microsoft đã xác nhận rằng Chrome sẽ tự động giảm quyền khi người dùng cố gắng khởi động nó với quyền cao.

" Tự động giảm quyền người dùng khởi động chrome với quyền cao. CL này dựa trên những thay đổi mà chúng tôi đã có trong Edge, vào khoảng năm 2019, cố gắng tự động giảm quyền trình duyệt khi nó được chạy với phần quyền cao của một token liên kết," Stefan Smolen, người làm việc với đội ngũ Microsoft Edge, đã viết trong một [cam kết của Chromium](https://chromium-review.googlesource.com/c/chromium/src/+/6515318).

" Điều này tự động cố gắng khởi động lại một lần, và sau đó nếu vẫn thất bại, nó sẽ quay về hành vi hiện tại (cố gắng khởi động với quyền quản trị)."

Microsoft cũng đã thêm một tùy chọn dòng lệnh, "-do-not-de-elevate," để ngăn ngừa việc giảm quyền sau khi khởi động lại tự động nhằm tránh vòng lặp vô hạn.

" Không giảm quyền trình duyệt khi khởi động. Được sử dụng sau khi giảm quyền để ngăn ngừa vòng lặp vô hạn," một bình luận trong mã nguồn cho biết.

Tính năng này không hoạt động cho các quy trình Chrome được khởi động với quyền cao khi ở chế độ tự động hóa, nhằm tránh cản trở các công cụ cần chạy tự động.

Tuy nhiên, nói chung, Microsoft cảnh báo rằng khởi động trình duyệt ở chế độ quản trị là một ý tưởng không hay.

Khi Chrome chạy với tư cách là Quản trị viên, nó kế thừa các quyền cao, điều này có nghĩa là bất cứ điều gì bạn tải xuống và mở qua trình duyệt cũng sẽ được khởi động với quyền Quản trị viên, điều này có thể gây ra rủi ro bảo mật nghiêm trọng.

Nếu bạn vô tình tải xuống và chạy một tệp độc hại, nó có thể thực thi với quyền truy cập đầy đủ vào hệ thống, có khả năng xâm phạm toàn bộ hệ điều hành của bạn mà không có bất kỳ cảnh báo nào.