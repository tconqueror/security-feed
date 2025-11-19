# Plugin W3 Total Cache của WordPress có lỗ hổng cho phép thực thi lệnh PHP

![Plugin W3 Total Cache của WordPress dễ bị tấn công cho phép thực thi lệnh PHP](https://www.bleepstatic.com/content/hl-images/2025/11/03/WordPress.jpg)

Một lỗ hổng nghiêm trọng trong plugin W3 Total Cache (W3TC) của WordPress có thể bị khai thác để chạy các lệnh PHP trên máy chủ bằng cách đăng một bình luận chứa payload độc hại.

Lỗ hổng, được theo dõi dưới mã [CVE-2025-9501](https://nvd.nist.gov/vuln/detail/CVE-2025-9501), ảnh hưởng tới tất cả các phiên bản của plugin W3TC trước 2.8.13 và được mô tả là một lỗ hổng chèn lệnh không cần xác thực.

W3TC được cài đặt trên hơn một triệu website để tăng hiệu năng và giảm thời gian tải.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Nhà phát triển đã phát hành phiên bản 2.8.13, khắc phục vấn đề bảo mật, vào ngày 20 tháng 10. Tuy nhiên, theo dữ liệu từ WordPress.org, hàng trăm nghìn website vẫn có thể còn dễ bị tấn công, vì đã có khoảng 430.000 lượt tải xuống kể từ khi bản vá được phát hành.

Công ty bảo mật WordPress WPScan cho biết kẻ tấn công có thể kích hoạt CVE-2025-9501 và chèn lệnh thông qua hàm _\_parse\_dynamic\_mfunc()_ chịu trách nhiệm xử lý các cuộc gọi hàm động nhúng trong nội dung đã được cache.

“Plugin [W3TC] dễ bị chèn lệnh thông qua hàm _\_parse\_dynamic\_mfunc()_, cho phép người dùng không cần xác thực thực thi các lệnh PHP bằng cách gửi một bình luận chứa payload độc hại tới một bài viết,” [WPScan](https://wpscan.com/vulnerability/6697a2c9-63ae-42f0-8931-f2e5d67d45ae/)

Kẻ tấn công khai thác thành công việc thực thi mã PHP này có thể nắm toàn quyền kiểm soát website WordPress bị lỗ hổng, vì họ có thể chạy bất kỳ lệnh nào trên máy chủ mà không cần xác thực.

Các nhà nghiên cứu của WPScan đã phát triển một mã khai thác proof-of-concept (PoC) cho CVE-2025-9501 và cho biết họ sẽ công bố nó vào ngày 24 tháng 11 để cho người dùng đủ thời gian cài đặt các bản cập nhật.

Thông thường, việc khai thác độc hại các lỗ hổng bắt đầu gần như ngay lập tức sau khi một mã PoC được công bố. Sau khi mã khai thác được công bố, kẻ tấn công sẽ tìm kiếm mục tiêu tiềm năng và cố gắng xâm nhập chúng.

Quản trị viên website không thể nâng cấp trước hạn chót nên cân nhắc vô hiệu hóa plugin W3 Total Cache hoặc thực hiện các biện pháp cần thiết để đảm bảo rằng bình luận không thể được dùng để chuyển payload độc hại có thể kích hoạt khai thác.

Hành động được khuyến nghị là nâng cấp lên W3 Total Cache phiên bản 2.8.13, phát hành vào ngày 20 tháng 10.