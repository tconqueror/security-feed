# PyPI hiện chặn các cuộc tấn công phục hồi miền được sử dụng để chiếm đoạt tài khoản

![PyPI hiện chặn các cuộc tấn công phục hồi miền được sử dụng để chiếm đoạt tài khoản](https://www.bleepstatic.com/content/hl-images/2024/03/28/back.jpg)

Python Package Index (PyPI) đã giới thiệu các biện pháp bảo vệ mới chống lại các cuộc tấn công phục hồi miền cho phép chiếm đoạt tài khoản thông qua việc đặt lại mật khẩu.

PyPI là kho lưu trữ chính thức cho các gói Python mã nguồn mở. Nó được sử dụng bởi các nhà phát triển phần mềm, những người duy trì sản phẩm và các công ty làm việc với các thư viện, công cụ và khung làm việc Python.

Các tài khoản của những người duy trì dự án xuất bản phần mềm trên PyPI được liên kết với các địa chỉ email. Trong trường hợp của một số dự án, địa chỉ email liên quan đến một tên miền.

Nếu một tên miền hết hạn, kẻ tấn công có thể đăng ký nó và sử dụng nó để kiểm soát một dự án trên PyPi sau khi thiết lập máy chủ email và gửi yêu cầu đặt lại mật khẩu cho tài khoản.

Mối đe dọa từ điều này chính là cuộc tấn công chuỗi cung ứng, trong đó các dự án bị chiếm đoạt đẩy các phiên bản độc hại của các gói Python phổ biến, mà trong nhiều trường hợp sẽ được cài đặt tự động bằng cách sử dụng pip.

Một trường hợp đáng chú ý trong số các cuộc tấn công như vậy là [sự xâm nhập vào gói ‘ctx’](https://www.bleepingcomputer.com/news/security/popular-python-and-php-libraries-hijacked-to-steal-aws-keys/) vào tháng 5 năm 2022, khi một kẻ tấn công đã thêm mã nhắm mục tiêu vào các khóa AWS và thông tin xác thực tài khoản của Amazon.

Trong nỗ lực giải quyết vấn đề này, PyPI hiện kiểm tra xem các miền của các địa chỉ email đã được xác minh trên nền tảng có hết hạn hoặc đang tiến vào giai đoạn hết hạn hay không, và đánh dấu những địa chỉ đó là chưa được xác minh.

Về mặt kỹ thuật, PyPI sử dụng API Trạng thái của Domainr để xác định giai đoạn vòng đời của một miền (hoạt động, thời gian ân hạn, thời gian phục hồi, đang chờ xóa) để quyết định xem có cần hành động nào trên một tài khoản nhất định hay không.

![Các giai đoạn vòng đời của miền](https://www.bleepstatic.com/images/news/u/1220909/2025/August/diagram(1).jpg)

**Các giai đoạn vòng đời của miền**  
_Nguồn: PyPI_

Khi các địa chỉ email vào trạng thái đó, chúng không thể được sử dụng cho việc đặt lại mật khẩu hoặc các hành động khôi phục tài khoản khác, do đó khóa cơ hội khai thác ngay cả khi một kẻ tấn công đăng ký miền.

Các [biện pháp mới](https://blog.pypi.org/posts/2025-08-18-preventing-domain-resurrections/) thực sự đã bắt đầu phát triển vào tháng 4, khi các quét tạm thời được thực hiện để đánh giá tình hình. Cuối cùng, chúng được giới thiệu vào tháng 6 năm 2025, với các quét hàng ngày. Kể từ đó, hơn 1,800 địa chỉ email đã được đánh dấu là chưa được xác minh theo hệ thống mới.

Mặc dù không hoàn hảo hoặc đủ để chống lại tất cả các kịch bản tấn công, các biện pháp mới này đã giảm thiểu đáng kể nguy cơ kẻ tấn công chiếm đoạt tài khoản PyPI bằng cách khai thác các miền hết hạn.

PyPI khuyến nghị người dùng thêm một email sao lưu từ miền không tùy chỉnh vào tài khoản của họ để tránh gián đoạn, và kích hoạt xác thực hai yếu tố trên tài khoản PyPI của họ để bảo vệ tốt hơn chống lại việc chiếm đoạt.