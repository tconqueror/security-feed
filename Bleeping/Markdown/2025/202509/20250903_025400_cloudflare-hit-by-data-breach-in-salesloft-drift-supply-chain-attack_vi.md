# Cloudflare bị rò rỉ dữ liệu trong cuộc tấn công chuỗi cung ứng Salesloft Drift

![Cloudflare](https://www.bleepstatic.com/content/hl-images/2025/09/02/0_Cloudflare.jpg)

Cloudflare là công ty mới nhất bị ảnh hưởng trong chuỗi các vụ rò rỉ do Salesloft Drift, một phần của cuộc tấn công chuỗi cung ứng được công bố tuần trước.

Công ty khổng lồ mạng internet cho biết thứ thứ ba rằng kẻ tấn công đã truy cập vào phiên bản Salesforce mà họ sử dụng cho quản lý trường hợp khách hàng nội bộ và hỗ trợ khách hàng, trong đó có 104 mã API Cloudflare.

Cloudflare được thông báo về vụ rò rỉ vào ngày 23 tháng 8, và họ đã thông báo cho những khách hàng bị ảnh hưởng về sự cố vào ngày 2 tháng 9. Trước khi thông báo cho khách hàng, họ cũng đã xoay vòng (rotate) tất cả 104 mã token do nền tảng phát hành trục xuất trong vụ rò rỉ, mặc dù họ chưa phát hiện bất kỳ hoạt động đáng ngờ nào liên quan đến những mã này.

> “Hầu hết thông tin này là dữ liệu liên hệ khách hàng và dữ liệu mẫu hỗ trợ cơ bản, nhưng một số tương tác hỗ trợ có thể tiết lộ thông tin về cấu hình của khách hàng và có thể chứa dữ liệu nhạy cảm như mã truy cập,” Cloudflare nói.

> “Do dữ liệu mẫu hỗ trợ Salesforce chứa nội dung của các vé hỗ trợ với Cloudflare, bất kỳ thông tin nào mà khách hàng có thể đã chia sẻ với Cloudflare qua hệ thống hỗ trợ của chúng tôi — bao gồm nhật ký, mã token hoặc mật khẩu — nên được xem là đã bị xâm phạm, và chúng tôi khuyến nghị mạnh mẽ bạn xoay vòng bất kỳ thông tin xác thực nào mà bạn có thể đã chia sẻ với chúng tôi qua kênh này.”

Nghiên cứu của công ty phát hiện ra nhân tố tấn công chỉ lấy lại văn bản chứa trong các đối tượng case của Salesforce (bao gồm vé hỗ trợ khách hàng và dữ liệu liên quan; không có tệp đính kèm) giữa ngày 12 và 17 tháng 8, sau một giai đoạn khảo sát ban đầu vào ngày 9 tháng 8.

Các đối tượng case trục xuất này chỉ chứa dữ liệu dạng văn bản, bao gồm:

* Dòng tiêu đề của case Salesforce
* Nội dung của case (có thể bao gồm khóa, bí mật, vv., nếu được khách hàng cung cấp cho Cloudflare)
* Thông tin liên hệ khách hàng (ví dụ, tên công ty, địa chỉ email người yêu cầu và số điện thoại, tên miền công ty và quốc gia công ty)

> “Chúng ta tin rằng sự cố này không phải là một sự kiện một lần mà nhân tố tấn công muốn thu thập thông tin xác thực và thông tin khách hàng cho các cuộc tấn công của mình trong tương lai,” Cloudflare thêm.

> “Vì hàng trăm tổ chức đã bị ảnh hưởng qua cuộc rò rỉ Drift, chúng tôi nghi ngờ nhân tố tấn công sẽ sử dụng thông tin này để triển khai các cuộc tấn công mục tiêu đối với khách hàng qua các tổ chức bị ảnh hưởng.”

## Dòng lác dữ liệu Salesforce

Từ đầu năm, nhóm ShinyHunters đã **đánh giá công ty Salesforce** trong các cuộc tấn công trộm dữ liệu, sử dụng **voice phishing (vishing)** để đánh lừa nhân viên kết nối các ứng dụng OAuth độc hại với instance Salesforce của công ty của họ. Kỹ thuật này cho phép kẻ tấn công trộm các cơ sở dữ liệu, sau đó được sử dụng để chuộc thù.

Kể từ khi **Google** lần đầu đề cập đến những cuộc tấn công này trong tháng 6, nhiều vụ rò rỉ dữ liệu đã được liên kết với các kỹ thuật kỹ thuật xã hội của ShinyHunters, bao gồm **đánh mồi Google**, **Cisco**, **Qantas**, **Allianz Life**, **Farmers Insurance**, **Workday**, **Adidas**, cũng như các công ty con của LVMH — **Louis Vuitton**, **Dior**, và **Tiffany & Co.**

Trong khi một số nhà nghiên cứu bảo mật của BleepingComputer cho biết các cuộc tấn công chuỗi cung ứng Salesloft liên quan đến cùng các nhân tố tấn công, Google chưa tìm thấy bằng chứng xác thực liên quan.

**Palo Alto Networks** cũng **đã xác nhận cuối tuần trước** rằng nhân tố tấn công đứng sau các vụ rò rỉ Drift của Salesloft đã trộm một số dữ liệu hỗ trợ được khách hàng gửi, gồm thông tin liên hệ và bình luận văn bản.

Vụ tấn công của Palo Alto Networks cũng chỉ giới hạn trong CRM Salesforce của họ và, theo công ty, nó chưa ảnh hưởng bất kỳ sản phẩm, hệ thống hoặc dịch vụ nào.

Công ty bảo mật đã quan sát kẻ tấn công tìm kiếm các bí mật, bao gồm khóa truy cập AWS (AKIA), chuỗi đăng nhập VPN và SSO, token Snowflake, cũng như các từ khoá chung như “secret”, “password” hoặc “key”, có thể được sử dụng để xâm nhập nhiều nền tảng đám mây khác nhau để trộm dữ liệu trong các cuộc tấn công chuộc thù khác.