# Microsoft fixes highest-severity ASP.NET Core flaw ever

![Microsoft](https://www.bleepstatic.com/content/hl-images/2025/08/06/Microsoft.jpg)

Đầu tuần này, Microsoft đã vá một lỗ hổng được gán mức độ nghiêm trọng "cao nhất từ trước tới nay" dành cho một lỗ hổng bảo mật trong ASP.NET Core.

Lỗ hổng "HTTP request smuggling" này ([CVE-2025-55315](https://nvd.nist.gov/vuln/detail/CVE-2025-55315)) được phát hiện trong Kestrel ASP.NET Core web server, và cho phép kẻ tấn công đã được xác thực smuggle một yêu cầu HTTP khác để chiếm đoạt thông tin đăng nhập của người dùng khác hoặc vượt qua các kiểm soát bảo mật phía trước.

"Người tấn công nếu khai thác thành công lỗ hổng này có thể xem thông tin nhạy cảm như thông tin đăng nhập của người dùng khác (Bảo mật) và thay đổi nội dung tệp trên máy chủ mục tiêu (Tính toàn vẹn), và họ có thể buộc máy chủ bị sự cố (Tính sẵn sàng)," Microsoft cho biết trong một [thông báo ngày Thứ Ba](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-55315).

Để đảm bảo các ứng dụng ASP.NET Core được bảo vệ trước các cuộc tấn công tiềm tàng, Microsoft khuyên nhà phát triển và người dùng thực hiện các biện pháp sau:

* Nếu đang chạy .NET 8 hoặc mới hơn, cài đặt bản cập nhật .NET từ Microsoft Update, sau đó khởi động lại ứng dụng hoặc khởi động lại máy.
* Nếu đang chạy .NET 2.3, cập nhật tham chiếu gói Microsoft.AspNet.Server.Kestrel.Core lên 2.3.6, sau đó biên dịch lại ứng dụng và triển khai lại.
* Nếu đang chạy ứng dụng self-contained/single-file, cài đặt bản cập nhật .NET, biên dịch lại và triển khai lại.

Để khắc phục lỗ hổng, Microsoft [đã phát hành bản cập nhật bảo mật](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-55315#securityUpdates) cho Microsoft Visual Studio 2022, ASP.NET Core 2.3, ASP.NET Core 8.0 và ASP.NET Core 9.0, cũng như gói Microsoft.AspNetCore.Server.Kestrel.Core cho các ứng dụng ASP.NET Core 2.x.

Như Barry Dorrans, .NET security technical program manager, giải thích, tác động của các cuộc tấn công CVE-2025-55315 sẽ phụ thuộc vào ứng dụng ASP.NET được nhắm tới, và khai thác thành công có thể cho phép tác nhân đe dọa đăng nhập dưới tư cách một người dùng khác (tăng đặc quyền), thực hiện một yêu cầu nội bộ (trong các cuộc tấn công SSRF), vượt qua kiểm tra cross-site request forgery (CSRF), hoặc thực hiện các cuộc tấn công injection.

"Nhưng chúng tôi không biết điều gì là có thể vì nó phụ thuộc vào cách bạn viết ứng dụng của mình. Vì vậy, chúng tôi chấm điểm với trường hợp xấu nhất trong đầu, một bypass tính năng bảo mật làm thay đổi phạm vi," [Dorrans nói](http://github.com/dotnet/aspnetcore/issues/64033#issuecomment-3403054914).

"Liệu điều đó có khả năng xảy ra? Không, có lẽ không trừ khi mã ứng dụng của bạn đang làm điều gì đó bất thường và bỏ qua một loạt các kiểm tra mà lẽ ra nó nên thực hiện trên mỗi yêu cầu. Tuy nhiên, xin hãy cập nhật."

Trong Patch Tuesday tháng này, Microsoft [phát hành các bản cập nhật bảo mật cho 172 lỗ hổng](https://www.bleepingcomputer.com/news/microsoft/microsoft-october-2025-patch-tuesday-fixes-6-zero-days-172-flaws/), bao gồm tám lỗ hổng "Critical" và sáu lỗ hổng zero-day (ba trong số đó đã bị khai thác trong các cuộc tấn công).

Tuần này, Microsoft cũng xuất bản KB5066791, một bản cập nhật tích lũy bao gồm [các bản cập nhật bảo mật cuối cùng của Windows 10] khi hệ điều hành này đạt đến cuối vòng đời hỗ trợ.