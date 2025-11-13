# Lỗ hổng RCE trong ImunifyAV đặt hàng triệu trang web lưu trữ trên Linux vào rủi ro

![Lỗ hổng RCE trong ImunifyAV đặt hàng triệu trang web lưu trữ trên Linux vào rủi ro](https://www.bleepstatic.com/content/hl-images/2025/11/05/Credit-card-hacker.jpg)

Trình quét phần mềm độc hại ImunifyAV cho các máy chủ Linux, được sử dụng bởi hàng chục triệu trang web, có lỗ hổng thực thi mã từ xa (remote code execution) có thể bị khai thác để xâm phạm môi trường lưu trữ.

Vấn đề ảnh hưởng đến các phiên bản của thành phần quét phần mềm độc hại AI-bolit trước bản 32.7.4.0. Thành phần này có trong bộ Imunify360, phiên bản trả phí ImunifyAV+, và trong ImunifyAV, phiên bản miễn phí của trình quét phần mềm độc hại.

Theo công ty bảo mật [Patchstack](https://patchstack.com/articles/remote-code-execution-vulnerability-found-in-imunify360/), lỗ hổng đã được biết từ cuối tháng 10, khi nhà cung cấp ImunifyAV là CloudLinux phát hành các bản sửa. Hiện tại, lỗ hổng chưa được gán một định danh (CVE).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP)

Vào ngày 10 tháng 11, nhà cung cấp đã [backport](https://changelog.imunify.com/imunify360)[ bản vá](http://changelog.imunify.com/imunify360) cho các phiên bản Imunify360 AV cũ hơn. Trong một thông báo hôm qua, CloudLinux cảnh báo khách hàng về “[a critical security vulnerability](https://cloudlinux.zendesk.com/hc/en-us/articles/23364954576540-Ai-Bolit-security-vulnerability-before-v32-7-4-0-incident99)” và khuyến nghị “cập nhật phần mềm càng sớm càng tốt” lên phiên bản 32.7.4.0

ImunifyAV là một phần của bộ bảo mật Imunify360, chủ yếu được các nhà cung cấp dịch vụ web-hosting hoặc các môi trường shared hosting Linux sử dụng.

Sản phẩm thường được cài đặt ở cấp nền tảng lưu trữ, không phải do người dùng cuối cài trực tiếp. Nó rất phổ biến trên các gói shared hosting, managed WordPress hosting, máy chủ cPanel/WHM và máy chủ Plesk.

Chủ sở hữu trang web hiếm khi tương tác trực tiếp với nó, nhưng đây vẫn là một công cụ phổ biến chạy âm thầm sau 56 triệu trang web, theo dữ liệu [Imunify](https://blog.imunify360.com/imunify360-stats-that-speak-volumes) từ tháng 10 năm 2024, đồng thời cho biết hơn 645.000 cài đặt Imunify360.

Nguyên nhân gốc rễ của lỗ hổng là logic giải mã (deobfuscation) của AI-bolit, vốn thực thi các tên hàm do kẻ tấn công kiểm soát và dữ liệu được trích xuất từ các tệp PHP bị obfuscate khi cố gắng giải nén phần mềm độc hại để quét nó.

Điều này xảy ra vì công cụ sử dụng '_call\_user\_func\_array_' mà không xác thực tên hàm, cho phép thực thi các hàm PHP nguy hiểm như system, exec, shell_exec, passthru, eval, và hơn thế nữa.

Patchstack lưu ý rằng việc khai thác lỗ hổng yêu cầu Imunify360 AV phải thực hiện việc deobfuscation đang hoạt động trong bước phân tích, điều này bị vô hiệu hóa trong cấu hình mặc định của AI-Bolit CLI độc lập.

Tuy nhiên, tích hợp của Imunify360 với thành phần trình quét đang ép buộc trạng thái 'luôn bật' cho các quét nền, quét theo yêu cầu, quét do người dùng khởi tạo và quét nhanh, điều này đáp ứng yêu cầu để khai thác.

Các nhà nghiên cứu đã chia sẻ một bằng chứng khai thác (PoC) tạo một tệp PHP trong thư mục tmp, tệp này sẽ kích hoạt thực thi mã từ xa khi được trình diệt virus quét.

![Proof of concept exploit](https://www.bleepstatic.com/images/news/u/1220909/2025/November/poc(1).png)

**Bằng chứng khai thác (PoC)**  
_Source: Patchstack_

Điều này có thể cho phép xâm phạm hoàn toàn trang web, và nếu trình quét chạy với đặc quyền cao trong các thiết lập shared hosting, hậu quả có thể mở rộng đến việc chiếm toàn bộ máy chủ.

Bản sửa của CloudLinux bổ sung cơ chế cho phép trắng (whitelisting) chỉ cho phép các hàm an toàn, có tính xác định được thực thi trong quá trình deobfuscation, điều này chặn việc thực thi hàm tùy ý.

Mặc dù không có cảnh báo rõ ràng từ nhà cung cấp hoặc một CVE-ID để giúp nâng cao cảnh báo và theo dõi vấn đề, quản trị viên hệ thống nên nâng cấp lên phiên bản v32.7.4.0 hoặc mới hơn.

Hiện tại, không có hướng dẫn chính thức về cách kiểm tra bị xâm phạm, không có hướng dẫn phát hiện, và không có xác nhận về việc khai thác tích cực trong tự nhiên.

BleepingComputer đã liên hệ với CloudLinux để yêu cầu bình luận, nhưng chúng tôi chưa nhận được phản hồi vào thời điểm bài viết được xuất bản.