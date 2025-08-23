# Hacker đánh cắp 1 triệu hồ sơ người dùng Cock.li trong vụ vi phạm dữ liệu webmail

![Email](https://www.bleepstatic.com/content/hl-images/2024/10/21/email.jpg)

Nhà cung cấp dịch vụ lưu trữ email Cock.li đã xác nhận rằng họ đã bị một vụ vi phạm dữ liệu sau khi các tác nhân đe dọa khai thác các lỗ hổng trong nền tảng webmail Roundcube đã ngừng hoạt động của họ để đánh cắp hơn một triệu hồ sơ người dùng.

Sự cố đã lộ thông tin của tất cả người dùng đã đăng nhập vào dịch vụ mail kể từ năm 2016, ước tính khoảng 1,023,800 người, cùng với thông tin liên lạc của 93,000 người dùng khác.

Cock.li là một nhà cung cấp dịch vụ lưu trữ email miễn phí có trụ sở tại Đức với triết lý bảo mật và chính sách kiểm duyệt lỏng lẻo, được điều hành bởi một người duy nhất được biết đến với tên gọi 'Vincent Canfield' từ năm 2013.

Nó được quảng bá như một lựa chọn thay thế cho các nhà cung cấp email chính thống, hỗ trợ các giao thức bảo mật tiêu chuẩn như SMTP, IMAP và TLS.

Cock.li được sử dụng bởi những người không tin tưởng vào các nhà cung cấp lớn, cũng như các thành viên của cộng đồng infosec và mã nguồn mở. Nó cũng phổ biến trong giới tội phạm mạng, chẳng hạn như các chi nhánh từ các băng nhóm ransomware như Dharma, Phobos.

Cuối tuần trước, dịch vụ Cock.li đã bị gián đoạn mà không có giải thích công khai, khiến người dùng tự hỏi điều gì đã xảy ra.

Ngay sau đó, một tác nhân đe dọa [khẳng định đang bán](http://x.com/ReyXBF/status/1933555211185819835) hai cơ sở dữ liệu chứa thông tin nhạy cảm của Cock.li, đề nghị bán chúng với mức giá tối thiểu là một Bitcoin (92,5k USD).

![Tác nhân đe dọa cố gắng bán cơ sở dữ liệu Cock.li](https://www.bleepstatic.com/images/news/security/d/data-breaches/c/cock.li/cock-li-data-for-sale.jpg)

**Tác nhân đe dọa cố gắng bán cơ sở dữ liệu Cock.li**  
_Nguồn: BleepingComputer_

Cock.li [đã công bố một tuyên bố](https://mail.cock.li/) trên trang web của họ vào ngày hôm qua, xác nhận vụ vi phạm và tính hợp lệ của các tuyên bố của tác nhân đe dọa.

Dịch vụ email xác nhận rằng thông tin sau đã bị lộ cho 1,023,800 tài khoản người dùng:

* Địa chỉ email
* Dấu thời gian đăng nhập đầu tiên và cuối cùng
* Số lần đăng nhập không thành công và tổng số
* Ngôn ngữ
* Một blob chuỗi thuộc tính của cài đặt Roundcube và chữ ký email
* Tên liên hệ (chỉ cho một tập hợp con của 10,400 tài khoản)
* Địa chỉ email liên hệ (chỉ cho một tập hợp con của 10,400 tài khoản)
* vCards (chỉ cho một tập hợp con của 10,400 tài khoản)
* Bình luận (chỉ cho một tập hợp con của 10,400 tài khoản)

Thông báo của dịch vụ làm rõ rằng mật khẩu tài khoản người dùng, nội dung email và địa chỉ IP không bị xâm phạm, vì chúng không có trong các cơ sở dữ liệu bị đánh cắp.

Trong khi đó, 10,400 người dùng có thông tin liên hệ bên thứ ba bị lộ sẽ nhận được thông báo riêng.

Đối với tất cả những ai đã sử dụng dịch vụ kể từ năm 2016, được khuyến nghị đặt lại mật khẩu tài khoản của họ.

Vụ vi phạm dữ liệu Cock.li có thể có giá trị đối với các nhà nghiên cứu và cơ quan thực thi pháp luật, vì thông tin bị lộ có thể được sử dụng để tìm hiểu thêm về các tác nhân đe dọa sử dụng nền tảng này.

## Cock.li loại bỏ Roundcube

Cock.li cho biết họ tin rằng dữ liệu đã bị đánh cắp bằng cách sử dụng một lỗ hổng SQL injection cũ trong RoundCube có mã CVE-2021-44026.

Vụ vi phạm này xảy ra ngay khi Cock.li gần đây đã phân tích một lỗ hổng RCE trong Roundcube, CVE-2025-49113, được [tin rằng đang bị khai thác tích cực trong các cuộc tấn công](https://www.bleepingcomputer.com/news/security/hacker-selling-critical-roundcube-webmail-exploit-as-tech-info-disclosed/). Phân tích của họ đã dẫn đến quyết định loại bỏ phần mềm này khỏi nền tảng của họ vào tháng 6 năm 2025.

"Cock.li sẽ không còn cung cấp dịch vụ webmail Roundcube," các quản trị viên dịch vụ giải thích.

"Bất kể phiên bản của chúng tôi có dễ bị tấn công hay không, chúng tôi đã học đủ về Roundcube để loại bỏ nó khỏi dịch vụ một cách triệt để."

"Webmail khác chắc chắn đang trong kế hoạch, nhưng chưa phải là ưu tiên ngay lập tức đối với chúng tôi."

Thông báo nhấn mạnh rằng các thực tiễn bảo mật tốt hơn có thể đã ngăn chặn được việc rò rỉ dữ liệu người dùng này, thừa nhận rằng "Cock.li không nên chạy Roundcube ngay từ đầu."

Đối với những ai muốn tiếp tục sử dụng Cock.li để gửi email, họ sẽ phải sử dụng một ứng dụng IMAP hoặc SMTP/POP3.