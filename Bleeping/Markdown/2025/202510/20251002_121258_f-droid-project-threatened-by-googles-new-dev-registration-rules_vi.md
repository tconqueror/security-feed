# Dự án F-Droid bị đe dọa bởi quy định đăng ký nhà phát triển mới của Google

![Dự án F-Droid bị đe dọa bởi quy định đăng ký nhà phát triển mới của Google](https://www.bleepstatic.com/content/hl-images/2024/02/08/Android.jpg)

F-Droid đang cảnh báo rằng dự án có thể chấm dứt do các yêu cầu mới của Google bắt buộc tất cả nhà phát triển Android phải xác minh danh tính của họ.

Cửa hàng ứng dụng bên thứ ba này cho rằng Google trình bày sai lệch yêu cầu mới này như một biện pháp bảo mật chống phần mềm độc hại và mục đích thực sự là siết chặt kiểm soát trên "một hệ sinh thái từng cởi mở."

F-Droid là một cửa hàng ứng dụng bên thứ ba cho thiết bị Android phân phối phần mềm miễn phí và mã nguồn mở thông qua danh mục các ứng dụng được xây dựng trực tiếp từ mã nguồn công khai.

Trước khi phát hành một ứng dụng, nền tảng [kiểm tra chúng](http://f-droid.org/en/docs/Anti-Features/) để tìm các trình theo dõi ẩn hoặc phần mềm quảng cáo, và phân phối các [reproducible builds](https://f-droid.org/en/docs/Reproducible%5FBuilds/) cho người dùng ẩn danh, những người không cần tài khoản để truy cập chúng.

Vào tháng Tám, [Google announced](https://www.bleepingcomputer.com/news/security/google-to-verify-all-android-devs-to-protect-users-from-malware/) kế hoạch giới thiệu yêu cầu mới ‘Developer Verification’ vào năm 2026, nhằm ngăn chặn việc cài đặt phần mềm độc hại từ các ứng dụng sideloaded ngoài cửa hàng ứng dụng chính thức Google Play.

Nghị định mới yêu cầu tất cả các ứng dụng được cài đặt trên thiết bị Android được chứng nhận phải có nguồn gốc từ các nhà phát triển đã xác minh danh tính với Google; nếu không, việc cài đặt sẽ bị chặn và người dùng sẽ nhận được một thông báo cảnh báo.

Mặc dù hệ thống được đề xuất nhìn qua có vẻ là một bước tiến hướng tới bảo mật tốt hơn, F-Droid nói rằng nhiều nhà phát triển mã nguồn mở sẽ không cung cấp thông tin danh tính của họ cho Google.

F-Droid giải thích rằng họ không thể buộc các nhà phát hành này đăng ký với Google và trả các khoản phí liên quan, cũng như không thể chiếm đoạt các định danh ứng dụng thay cho họ.

"The F-Droid project cannot require that developers register their apps through Google, but at the same time, we cannot 'take over' the application identifiers for the open-source apps we distribute, as that would effectively seize exclusive distribution rights to those applications" - [F-Droid](https://f-droid.org/en/2025/09/29/google-developer-registration-decree.html)

Thành viên hội đồng dự án Marc Prud'hommeaux cho biết rằng "registration decree" của Google sẽ chấm dứt dự án F-Droid và các nguồn phân phối ứng dụng miễn phí/mã nguồn mở khác như chúng ta biết ngày nay.

Do đó, việc cưỡng chế hệ thống mới này có thể từ chối quyền truy cập vào một số lượng lớn các ứng dụng vốn đáng tin cậy, đồng thời ngăn người dùng cập nhật các cài đặt đã có.

F-Droid nhấn mạnh rằng yêu cầu xác định danh tính này không liên quan đến bảo mật, vì Android đã có hệ thống Play Protect, hệ thống này lẽ ra đã giải quyết tất cả các rủi ro mà Developer Verification dự định khắc phục.

“We do not believe that developer registration is motivated by security,” [states F-Droid](https://f-droid.org/en/2025/09/29/google-developer-registration-decree.html). “We believe it is about consolidating power and tightening control over a formerly open ecosystem.”

F-Droid kêu gọi các nhà quản lý xem xét phát triển này một cách phê phán trong khuôn khổ cạnh tranh và quyền số. Dự án cũng khuyến khích các nhà phát triển và người dùng vận động cho tự do phần mềm bằng cách tương tác với các nhà lập pháp.

BleepingComputer đã liên hệ với Google để yêu cầu bình luận về tuyên bố của F-Droid và liệu những lo ngại của họ có được chứng minh hay không, nhưng chúng tôi chưa nhận được phản hồi vào thời điểm xuất bản.

Trong khi đó, công ty đã [đăng một bài viết tiếp theo](https://android-developers.googleblog.com/2025/09/lets-talk-security-answering-your-top.html) ngày hôm qua, nơi họ nhắc lại rằng sideloading trên Android sẽ vẫn có thể, mặc dù chỉ dành cho các ứng dụng từ các nhà phát triển đã được xác minh.

Ngoại trừ được cho phép đối với các nhà phát triển nghiệp dư (hobbyist) phân phối ứng dụng chỉ cho một số lượng nhỏ thiết bị.

Google cũng làm rõ rằng nghị định mới sẽ không ảnh hưởng đến quy trình làm việc của Android Studio, vì giai đoạn phát triển và kiểm thử build sẽ không bị áp đặt các hạn chế mới.