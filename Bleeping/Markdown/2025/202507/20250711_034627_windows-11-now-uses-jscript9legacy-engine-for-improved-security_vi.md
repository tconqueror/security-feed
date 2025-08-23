# Windows 11 hiện sử dụng engine JScript9Legacy để cải thiện bảo mật

![Windows 11 hiện sử dụng engine JScript9Legacy để cải thiện bảo mật](https://www.bleepstatic.com/content/hl-images/2025/02/07/Windows-11.jpg)

Microsoft thông báo rằng họ đã thay thế engine lập trình mặc định JScript bằng JScript9Legacy mới hơn và an toàn hơn trên Windows 11 phiên bản 24H2 và các phiên bản sau.

Quyết định này được thúc đẩy bởi những lo ngại về bảo mật, vì JScript9Legacy được kỳ vọng sẽ cung cấp sự bảo vệ tốt hơn chống lại các mối đe dọa trên web, chẳng hạn như cross-site scripting (XSS), và cũng cải thiện hiệu suất.

"Để cung cấp một trải nghiệm an toàn hơn, bắt đầu từ Windows 11, phiên bản 24H2, JScript9Legacy được kích hoạt mặc định để xử lý tất cả các quy trình và thao tác lập trình trước đây sử dụng JScript," [ông Naveen Shankar của Microsoft thông báo](https://techcommunity.microsoft.com/blog/windows-itpro-blog/jscript9legacy-scripting-engine-now-enabled-by-default/4431326).

JScript (jscript.dll), được giới thiệu vào năm 1996, là triển khai của Microsoft về ECMAScript, tương tự như JavaScript, và chủ yếu được sử dụng trong Internet Explorer và như một ngôn ngữ lập trình cho Windows để tự động hóa các tác vụ, xác thực biểu mẫu hoặc tạo các script quản trị.

Engine này hiện được xem là đã lỗi thời nghiêm trọng, không tuân thủ các tiêu chuẩn bảo mật JavaScript hiện đại, và là mục tiêu thường xuyên của các lỗ hổng liên quan đến corruption bộ nhớ, thực thi mã tùy ý, và các lỗ hổng XSS được kích hoạt thông qua các tài liệu, email và trang web độc hại.

Mặc dù có tình trạng này, nó vẫn là engine mặc định trên Windows cho đến nay để đảm bảo tính tương thích ngược và tránh phá vỡ quy trình làm việc trong các hệ thống quan trọng.

Nhưng với việc Internet Explorer hiện đã bị ngừng sử dụng và mức độ sử dụng trình duyệt Edge tăng cao, Microsoft đã vạch ra một biên giới và cuối cùng thay thế JScript bằng JScript9Legacy (jscript9legacy.dll) bắt đầu từ Windows 11 24H2.

Engine mới là một phiên bản hiện đại hóa của JScript9, có thể được sử dụng bên ngoài trình duyệt, và được thiết kế để hỗ trợ nhu cầu lập trình kế thừa với bảo mật và khả năng tương thích tốt hơn.

Không yêu cầu hành động của người dùng để sự chuyển đổi có hiệu lực trên phiên bản Windows mới nhất, và các script hiện có sẽ tiếp tục hoạt động như mong đợi.

Nếu xảy ra vấn đề tương thích, Microsoft cho biết việc quay lại engine cũ là khả thi bằng cách liên hệ với đội hỗ trợ.