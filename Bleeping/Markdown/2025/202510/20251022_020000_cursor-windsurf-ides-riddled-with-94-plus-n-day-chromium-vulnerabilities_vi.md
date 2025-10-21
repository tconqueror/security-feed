# Cursor, Windsurf IDEs chứa hơn 94 lỗ hổng Chromium n-day

![Cursor, Windsurf IDEs riddled with 94+ n-day Chromium vulnerabilities](https://www.bleepstatic.com/content/hl-images/2025/01/31/Chromium-headpic.jpg)

Các bản phát hành mới nhất của Cursor và Windsurf integrated development environments có lỗ hổng hơn 94 vấn đề bảo mật đã được biết và đã được vá trong trình duyệt Chromium và engine V8 JavaScript.

Ước tính có 1,8 triệu nhà phát triển, tức cơ sở người dùng của hai IDE này, đang bị phơi nhiễm trước các rủi ro.

Các nhà nghiên cứu của Ox Security giải thích rằng cả hai môi trường phát triển đều được xây dựng trên phần mềm cũ bao gồm các phiên bản lỗi thời của trình duyệt mã nguồn mở Chromium và engine V8 của Google.

Họ cho biết Cursor và Windsurf dựa trên các phiên bản cũ của VS Code bao gồm các bản phát hành cũ của framework Electron để xây dựng ứng dụng đa nền tảng sử dụng công nghệ web (HTML, CSS, JavaScript).

"Vì Electron nhúng Chromium và V8, điều này có nghĩa là các IDE dựa trên các engine Chromium và V8 lỗi thời, khiến chúng bị phơi nhiễm với những lỗ hổng đã được vá trong các phiên bản mới hơn," các nhà nghiên cứu cho biết trong một [report](http://www.ox.security/blog/94-Vulnerabilities-in-Cursor-and-Windsurf-Put-1-8M-Developers-at-Risk/) được chia sẻ với BleepingComputer.

Các nhà nghiên cứu cho biết Cursor và Windsurf dễ bị tấn công bởi ít nhất 94 lỗ hổng có trong các bản dựng Chromium mà chúng sử dụng.

Mặc dù vấn đề bảo mật đã được tiết lộ một cách có trách nhiệm kể từ ngày 12 tháng Mười, các rủi ro vẫn tồn tại vì Cursor coi báo cáo là "out of scope" và Windsurf không phản hồi.

![Inheriting n-days from older Electron apps](https://www.bleepstatic.com/images/news/u/1220909/2025/October/image(1).jpg)

**Kế thừa lỗ hổng n-day từ các ứng dụng Electron cũ**  
_Nguồn: Ox Security_

## Rủi ro Chrome trên IDE

Cursor và Windsurf là các trình soạn thảo mã hỗ trợ AI được fork từ Visual Studio Code. Chúng tích hợp các large-language models (LLMs) để giúp nhà phát triển viết phần mềm dễ dàng và nhanh hơn.

Chúng được phân phối dưới dạng các ứng dụng Electron, tức là một runtime ứng dụng đóng gói một bản dựng Chromium cụ thể để hiển thị nội dung web, và bao gồm engine V8 JavaScript của trình duyệt trong nhị phân.

Phiên bản Electron cụ thể cố định một phiên bản Chromium + V8, và nếu nhà phát hành không nâng cấp nó, các lỗi đã được sửa trong mọi bản phát hành tiếp theo sẽ trở thành rủi ro có thể khai thác trong IDE.

Ox Security đã chứng minh rằng có thể khai thác Maglev JIT integer overflow được mô tả trong CVE-2025-7656 thông qua một deeplink, điều này khởi chạy Cursor và chèn một prompt hướng dẫn trình duyệt của nó truy cập một URL từ xa chứa payload khai thác.

Trang từ xa phục vụ JavaScript kích hoạt khai thác CVE-2025-7656, gây denial of service bằng cách làm crash renderer.

Nir Zadok và Moshe Siman Tov Bustan của Ox Security đã trình diễn phát hiện của họ bằng cách nhắm vào Cursor IDE với một khai thác cho CVE-2025-7656, một lỗ hổng tràn số nguyên trong engine V8 của Google Chrome [fixed](https://www.bleepingcomputer.com/news/security/google-fixes-actively-exploited-sandbox-escape-zero-day-in-chrome/) vào ngày 15 tháng Bảy.

Mẫu khai thác proof-of-concept đã khiến Cursor rơi vào tình trạng denial-of-service (crash), như được hiển thị trong video dưới đây:

Tuy nhiên, Ox Security lưu ý rằng thực tế có thể xảy ra thực thi mã tùy ý trong các cuộc tấn công thực tế.

Một kẻ tấn công sẽ có nhiều lựa chọn để kích hoạt lỗ hổng. Các nhà nghiên cứu cho biết một attacker có thể dùng một extension độc hại để kích hoạt khai thác hoặc chèn mã khai thác vào tài liệu và hướng dẫn.

Hackers cũng có thể dựa vào các cuộc tấn công phishing cổ điển hoặc lợi dụng các kho chứa bị đầu độc bằng cách cài đặt mã độc vào các tệp README được xem trước trong IDE.

![Overview of the attack](https://www.bleepstatic.com/images/news/u/1220909/2025/October/image%20(1).jpg)

**Tổng quan về cuộc tấn công**  
_Nguồn: Ox Security_

Ox Security lưu ý rằng khai thác không hoạt động trên VS Code mới nhất, vốn được cập nhật thường xuyên và khắc phục tất cả bug đã biết.

Khi nhận được mẫu proof-of-concept, Cursor đã bác bỏ báo cáo bằng cách nói rằng self-inflicted DoS nằm ngoài phạm vi.

Nhưng các nhà nghiên cứu lưu ý rằng quan điểm này bỏ qua tiềm năng khai thác nghiêm trọng hơn của lỗ hổng, bao gồm các primitives làm hỏng bộ nhớ, hoặc thậm chí tập hợp rộng hơn các CVE chưa được vá trong các ứng dụng Electron được sử dụng.

"Kể từ lần cập nhật Chromium cuối cùng của họ vào 2025-03-21 cho phiên bản 0.47.9 kể từ khi Chromium 132.0.6834.210 có sẵn, ít nhất 94 CVE đã được công bố. Chúng tôi chỉ weaponized một lỗ hổng. Bề mặt tấn công là rất lớn," Ox Security giải thích.

BleepingComputer đã liên hệ cả Cursor và Windsurf xin bình luận về báo cáo của Ox Security, nhưng chúng tôi chưa nhận được phản hồi tính đến thời điểm xuất bản.