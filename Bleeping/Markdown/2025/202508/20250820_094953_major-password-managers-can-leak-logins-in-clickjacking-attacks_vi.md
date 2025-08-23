# Các trình quản lý mật khẩu lớn có thể rò rỉ thông tin đăng nhập trong các cuộc tấn công clickjacking

![Các trình quản lý mật khẩu lớn có thể rò rỉ thông tin đăng nhập trong các cuộc tấn công clickjacking](https://www.bleepstatic.com/content/hl-images/2024/01/29/padlock.jpg)

Sáu trình quản lý mật khẩu lớn với hàng chục triệu người dùng hiện đang bị tổn thương bởi các lỗ hổng clickjacking chưa được vá, có thể cho phép các kẻ tấn công đánh cắp thông tin tài khoản, mã 2FA và chi tiết thẻ tín dụng.

Các tác nhân mối đe dọa có thể khai thác các vấn đề bảo mật khi nạn nhân truy cập một trang web độc hại hoặc các trang web dễ bị tấn công Cross-Site Scripting (XSS) hoặc làm hỏng bộ nhớ đệm, nơi mà các kẻ tấn công chồng các phần tử HTML vô hình lên giao diện của trình quản lý mật khẩu.

Trong khi người dùng nghĩ rằng họ đang tương tác với các phần tử có thể nhấp an toàn, họ kích hoạt các hành động tự động điền thông tin mà làm lộ thông tin nhạy cảm.

Các lỗ hổng này đã được trình bày trong hội nghị hacker DEF CON 33 gần đây bởi nhà nghiên cứu độc lập [Marek Tóth](https://marektoth.com/blog/dom-based-extension-clickjacking/). Các nhà nghiên cứu tại công ty an ninh mạng Socket sau đó đã [xác minh các phát hiện này](http://socket.dev/blog/password-manager-clickjacking) và giúp thông báo cho các nhà cung cấp bị ảnh hưởng và phối hợp công bố công khai.

Nhà nghiên cứu đã thử nghiệm cuộc tấn công của mình trên một số phiên bản của 1Password, Bitwarden, Enpass, iCloud Passwords, LastPass và LogMeOnce, và phát hiện rằng tất cả các biến thể dựa trên trình duyệt của chúng đều có thể rò rỉ thông tin nhạy cảm trong một số kịch bản nhất định.

## Phương pháp khai thác

Cơ chế tấn công chính là chạy một script trên một trang web độc hại hoặc bị xâm phạm sử dụng các cài đặt độ mờ, các lớp phủ, hoặc thủ thuật sự kiện con trỏ để ẩn menu tự động điền của trình quản lý mật khẩu dựa trên trình duyệt.

![Điều chỉnh độ mờ của phần tử trình quản lý mật khẩu](https://www.bleepstatic.com/images/news/u/1220909/2025/August/opacity.jpg)

**Điều chỉnh độ mờ của phần tử trình quản lý mật khẩu**  
_Nguồn: Marek Tóth_

Kẻ tấn công sau đó chồng các phần tử gây rối giả mạo (ví dụ như banner cookie, popup hoặc CAPTCHA) sao cho các cú nhấp của người dùng rơi vào các điều khiển trình quản lý mật khẩu ẩn, dẫn đến việc hoàn thành các biểu mẫu với thông tin nhạy cảm.

Tóth đã trình bày nhiều loại phụ thuộc vào DOM mà cấu thành các biến thể khai thác của cùng một lỗ hổng, bao gồm thao tác độ mờ của phần tử DOM trực tiếp, thao tác độ mờ của phần tử gốc, thao tác độ mờ của phần tử cha, và lớp phủ từng phần hoặc toàn bộ.

Nhà nghiên cứu cũng đã chứng minh khả năng sử dụng một phương pháp mà trong đó giao diện người dùng theo dõi con trỏ chuột, vì vậy bất kỳ cú nhấp nào của người dùng, không quan trọng vị trí của nó, sẽ kích hoạt tự động điền dữ liệu.

![Rò rỉ dữ liệu nhạy cảm](https://www.bleepstatic.com/images/news/u/1220909/2025/August/data-leak.jpg)

**Rò rỉ dữ liệu nhạy cảm**  
_Nguồn: Marek Tóth_

Tóth nói rằng một script tấn công chung có thể được sử dụng để xác định trình quản lý mật khẩu đang hoạt động trên trình duyệt của mục tiêu và sau đó điều chỉnh cuộc tấn công theo thời gian thực.

## Ảnh hưởng và phản hồi từ các nhà cung cấp

Nhà nghiên cứu đã thử nghiệm 11 trình quản lý mật khẩu được chọn vì độ phổ biến của chúng và phát hiện rằng tất cả đều có độ dễ bị tổn thương với ít nhất một phương pháp tấn công.

**Độ dễ bị tổn thương với các phương pháp tấn công**  
_Nguồn: Marek Tóth_

Với sự giúp đỡ của Socket, tất cả các nhà cung cấp đã được thông báo về các vấn đề trong tháng 4 năm 2025. Nhà nghiên cứu cũng đã cảnh báo họ rằng việc công bố công khai sẽ diễn ra vào tháng 8 tại DEF CON 33.

1Password đã từ chối báo cáo, phân loại nó là “ngoài phạm vi/thông tin”, lập luận rằng clickjacking là một rủi ro web chung mà người dùng cần giảm thiểu.

Tương tự, LastPass đã đánh dấu báo cáo là “thông tin”, trong khi Bitwarden đã thừa nhận các vấn đề nhưng đã giảm nhẹ mức độ nghiêm trọng. Tuy nhiên, Bitwarden đã nói với BleepingComputer rằng các vấn đề đã được sửa chữa trong phiên bản 2025.8.0, sẽ được phát hành trong tuần này.

Hiện tại chưa rõ LastPass và 1Password có kế hoạch giải quyết vấn đề hay không.

LogMeOnce không phản hồi bất kỳ nỗ lực giao tiếp nào, cả từ Tóth hay Socket.

Hiện tại, các trình quản lý mật khẩu sau đây, tổng cộng có khoảng 40 triệu người dùng, đang dễ bị tổn thương với các phương pháp tấn công của Tóth

* 1Password 8.11.4.27
* Bitwarden 2025.7.0
* Enpass 6.11.6 (sửa chữa một phần đã được thực hiện trong 6.11.4.2)
* iCloud Passwords 3.1.25
* LastPass 4.146.3
* LogMeOnce 7.12.4

Các nhà cung cấp đã thực hiện các sửa chữa là Dashlane (v6.2531.1 phát hành vào ngày 1 tháng 8), NordPass, ProtonPass, RoboForm và Keeper (v17.2.0 phát hành vào tháng 7). Tuy nhiên, người dùng cần đảm bảo rằng họ đang sử dụng các phiên bản mới nhất có sẵn của các sản phẩm.

**Trạng thái độ dễ bị tổn thương hiện tại**  
_Nguồn: Marek Tóth_

Cho đến khi có các bản sửa lỗi, Tóth khuyến nghị người dùng tắt chức năng tự động điền trong các trình quản lý mật khẩu của họ và chỉ sử dụng copy/paste.

BleepingComputer đã liên hệ với tất cả các nhà cung cấp chưa thực hiện sửa chữa và sẽ cập nhật bài viết này với phản hồi của họ khi nhận được.