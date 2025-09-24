# PyPI kêu gọi người dùng đặt lại thông tin đăng nhập sau các cuộc tấn công lừa đảo mới

![Python](https://www.bleepstatic.com/content/hl-images/2025/09/24/Python.jpg)

Python Software Foundation đã cảnh báo các nạn nhân của một làn sóng tấn công lừa đảo mới sử dụng một trang web giả mạo Python Package Index (PyPI) để yêu cầu đặt lại thông tin đăng nhập.

Truy cập được tại pypi.org, PyPI là nguồn mặc định cho công cụ quản lý gói của Python, lưu trữ hàng trăm nghìn gói và cung cấp cho các nhà phát triển một nền tảng tập trung để phân phối thư viện phần mềm bên thứ ba.

Nhà phát triển của Python Software Foundation, Seth Larson, cho biết các email lừa đảo yêu cầu mục tiêu "verify their email address" cho "account maintenance and security procedures," đe dọa họ bằng việc đình chỉ tài khoản và chuyển hướng tới một trang đích lừa đảo tại pypi-mirror[.]org.

"Nếu bạn đã nhấp vào liên kết và cung cấp thông tin đăng nhập, chúng tôi khuyến nghị thay đổi mật khẩu trên PyPI ngay lập tức," [Larson nói](https://blog.pypi.org/posts/2025-09-23-plenty-of-phish-in-the-sea/). "Kiểm tra Lịch sử Bảo mật của tài khoản bạn xem có điều gì bất thường không. Báo cáo hoạt động đáng ngờ, chẳng hạn như chiến dịch lừa đảo có thể nhắm vào PyPI, tới security@pypi.org."

Kẻ đe dọa nhằm đánh cắp thông tin đăng nhập của nạn nhân, sau đó nhiều khả năng sẽ sử dụng những thông tin này trong các cuộc tấn công tiếp theo để xâm phạm các gói Python mà họ đã xuất bản trên PyPI bằng mã độc hoặc để xuất bản các gói độc hại mới.

Những cuộc tấn công này là một phần của chiến dịch lừa đảo đã từng sử dụng tên miền pypj[.]org vào tháng Bảy để lừa nạn nhân tiềm năng đăng nhập vào một trang PyPI giả mạo.

![Trang pypj[.]org giả mạo](https://www.bleepstatic.com/images/news/u/1109292/2025/Fake-pypj_org-website.png)

_Trang pypj[.]org giả mạo (BleepingComputer)_

Larson khuyên các người duy trì gói trên PyPI không bao giờ nhấp vào liên kết trong email và nên sử dụng trình quản lý mật khẩu tự động điền thông tin đăng nhập dựa trên tên miền.

Để đảm bảo tài khoản được bảo vệ trước các nỗ lực xâm nhập, họ cũng nên sử dụng phương pháp xác thực hai yếu tố (2FA) chống lừa đảo, chẳng hạn như khóa phần cứng, và chia sẻ các email đáng ngờ với người khác trước khi thực hiện hành động.

Người dùng cũng có thể giúp dẹp bỏ các chiến dịch lừa đảo này bằng cách báo cáo các tên miền là độc hại và liên hệ với các registrar để yêu cầu gỡ bỏ tên miền, nhằm ngăn chặn nỗ lực lừa đảo người dùng PyPI khác của kẻ tấn công.

Tuần trước, nhóm Python Software Foundation cũng đã vô hiệu hóa tất cả các PyPI tokens bị đánh cắp trong cuộc tấn công chuỗi cung ứng GhostAction vào đầu tháng Chín, xác nhận rằng các tác nhân không lạm dụng chúng để xuất bản phần mềm độc hại.

Vào tháng Ba 2024, PyPI cũng tạm thời đình chỉ đăng ký người dùng và việc tạo dự án mới sau khi các tác nhân xuất bản hàng trăm gói độc hại giả dạng gói hợp lệ.