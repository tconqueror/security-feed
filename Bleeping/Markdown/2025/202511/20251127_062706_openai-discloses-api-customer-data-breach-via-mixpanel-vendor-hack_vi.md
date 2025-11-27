# OpenAI tiết lộ vi phạm dữ liệu khách hàng API do hack nhà cung cấp Mixpanel

![OpenAI tiết lộ vi phạm dữ liệu khách hàng API do hack nhà cung cấp Mixpanel](https://www.bleepstatic.com/content/hl-images/2025/11/27/OpenAI.jpg)

OpenAI đang thông báo cho một số khách hàng ChatGPT API rằng một lượng hạn chế thông tin định danh đã bị lộ sau một vi phạm tại nhà cung cấp phân tích bên thứ ba Mixpanel.

Mixpanel cung cấp phân tích sự kiện mà OpenAI sử dụng để theo dõi tương tác của người dùng trên giao diện frontend cho sản phẩm API.

Theo công ty AI này, sự cố mạng đã ảnh hưởng “limited analytics data related to some users of the API” và không ảnh hưởng tới người dùng ChatGPT hoặc các sản phẩm khác.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

“Đây không phải là một vi phạm hệ thống của OpenAI. Không có cuộc trò chuyện, yêu cầu API, dữ liệu sử dụng API, mật khẩu, thông tin xác thực, API keys, chi tiết thanh toán, hoặc giấy tờ tùy thân của chính phủ nào bị xâm phạm hoặc tiết lộ,” OpenAI cho biết trong một thông cáo báo chí.

Mixpanel đã báo cáo rằng vụ tấn công “impacted a limited number of our customers” và bắt nguồn từ một chiến dịch smishing (lừa đảo qua SMS) mà công ty phát hiện vào ngày 8 tháng 11.

OpenAI nhận được chi tiết của bộ dữ liệu bị ảnh hưởng vào ngày 25 tháng 11 sau khi được thông báo về cuộc điều tra đang diễn ra của Mixpanel.

Công ty AI này lưu ý rằng thông tin bị lộ có thể bao gồm:

* Tên được cung cấp cho chúng tôi trên tài khoản API
* Địa chỉ email liên kết với tài khoản API
* Vị trí thô gần đúng dựa trên trình duyệt của người dùng API (thành phố, bang, quốc gia)
* Hệ điều hành và trình duyệt được sử dụng để truy cập tài khoản API
* Các trang web giới thiệu
* ID tổ chức hoặc ID người dùng liên kết với tài khoản API

Vì không có thông tin xác thực nhạy cảm nào bị lộ, người dùng không cần đặt lại mật khẩu hoặc sinh lại API keys.

Một số người dùng đang báo cáo rằng CoinTracker, một công cụ theo dõi danh mục tiền điện tử và nền tảng thuế, cũng đã bị ảnh hưởng, với dữ liệu bị lộ bao gồm cả siêu dữ liệu thiết bị và số lượng giao dịch hạn chế.

OpenAI đã bắt đầu một cuộc điều tra để xác định quy mô đầy đủ của sự cố. Như một biện pháp phòng ngừa, công ty đã gỡ Mixpanel khỏi dịch vụ production và đang thông báo trực tiếp cho các tổ chức, quản trị viên và người dùng cá nhân.

Trong khi OpenAI nhấn mạnh rằng chỉ người dùng API của họ bị ảnh hưởng, công ty đã thông báo cho tất cả người đăng ký.

Công ty cảnh báo rằng dữ liệu rò rỉ có thể bị lợi dụng trong các cuộc tấn công lừa đảo hoặc tấn công kỹ thuật xã hội và khuyên người dùng đề phòng các tin nhắn độc hại có vẻ thuyết phục liên quan tới sự cố.

Các tin nhắn chứa liên kết hoặc tệp đính kèm nên được xác minh để đảm bảo chúng xuất phát từ một tên miền chính thức của OpenAI.

Công ty cũng thúc giục người dùng bật 2FA và không bao giờ gửi thông tin nhạy cảm, bao gồm mật khẩu, API keys, hoặc mã xác thực, qua email, tin nhắn văn bản, hoặc trò chuyện.

CEO của Mixpanel, Jen Taylor, cho biết tất cả khách hàng bị ảnh hưởng đã được liên hệ trực tiếp. “If you have not heard from us, you were not impacted,” bà lưu ý.

Đáp lại cuộc tấn công, Mixpanel đã bảo vệ các tài khoản bị ảnh hưởng, thu hồi các phiên và đăng nhập đang hoạt động, thay đổi các thông tin xác thực bị xâm phạm, chặn địa chỉ IP của tác nhân đe dọa và đặt lại mật khẩu cho tất cả nhân viên. Công ty cũng đã triển khai các biện pháp kiểm soát mới để ngăn chặn các sự cố tương tự trong tương lai.