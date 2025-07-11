# Lỗ hổng zero-day có thể đã xâm phạm mọi người dùng Cursor và Windsurf

![Logo của nền tảng lập trình và trình chỉnh sửa mã](https://www.bleepstatic.com/content/posts/2025/07/11/koi-header-image.jpg)

Một nhà nghiên cứu bảo mật từ [Koi Security](https://www.koi.security/?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx) đã phát hiện một lỗ hổng zero-day nghiêm trọng nằm sâu trong hạ tầng hỗ trợ các công cụ lập trình AI hiện nay. Nếu bị khai thác, một kẻ tấn công không tinh vi có thể đã chiếm đoạt hơn 10 triệu máy tính chỉ với một cú nhấp chuột.

Các trợ lý lập trình AI như Cursor và Windsurf đã bùng nổ về độ phổ biến, hứa hẹn tăng trưởng năng suất mạnh mẽ cho các lập trình viên trên toàn thế giới. Đằng sau giao diện đẹp mắt của chúng là một nền tảng chung: các nhánh VS Code do cộng đồng xây dựng và một thị trường mở cho các tiện ích mở rộng hỗ trợ những điều kỳ diệu đó. Nhưng với làn sóng mới của công cụ lập trình đi kèm là một điểm mù nguy hiểm.

**Được gọi là VSXPloit:** Một lỗi bị bỏ qua trong OpenVSX - một thành phần quan trọng trong chuỗi cung cấp lập trình viên - đã cho phép xâm phạm toàn hệ thống một cách lén lút trên bất kỳ máy nào chạy một nhánh VS Code. Một lỗi. Toàn quyền kiểm soát.

Hãy cùng khám phá.

Các trình chỉnh sửa do AI hỗ trợ hôm nay phụ thuộc rất nhiều vào các tiện ích mở rộng để cung cấp các chức năng cơ bản nhất. Các tính năng như đánh dấu cú pháp, linting và gỡ lỗi không được mã cứng vào trình chỉnh sửa - mà được cung cấp bởi các tiện ích mở rộng.

Mỗi tiện ích mở rộng này chạy với đầy đủ quyền trên máy của lập trình viên. Điều này có nghĩa là một tiện ích mở rộng bị xâm phạm có thể dẫn đến việc chiếm quyền kiểm soát toàn bộ máy của bất kỳ ai cài đặt nó.

![Tác động của Open VSX](https://www.bleepstatic.com/images/news/security/k/koi/zero-day-ai/open-vsx.jpg)

Chính kịch bản ác mộng này là điều mà nhà nghiên cứu bảo mật Oren Yomtov từ [Koi Security](https://www.koi.security/?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx), một công ty cung cấp nền tảng bảo mật cho việc cấp phát phần mềm và các tiện ích mở rộng, đã phát hiện.

[Trong một bài viết gần đây](https://blog.koi.security/marketplace-takeover-how-we-couldve-taken-over-every-developer-using-a-vscode-fork-f0f8cf104d44?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx) Yomtom giải thích rằng trong quá trình kiểm tra quy trình xây dựng đằng sau OpenVSX, thị trường mã nguồn mở hỗ trợ các tiện ích mở rộng cho các công cụ như Cursor, Windsurf, VSCodium và các công cụ khác, ông đã phát hiện một lỗ hổng nghiêm trọng.

Lỗ hổng này cho phép bất kỳ kẻ tấn công nào, không chỉ kiểm soát một tiện ích mở rộng, mà còn tạo ra một thảm họa chuỗi cung cấp, giành quyền kiểm soát toàn bộ thị trường.

Với lỗ hổng này, bất kỳ kẻ tấn công nào cũng có thể đẩy các bản cập nhật độc hại dưới tài khoản @open-vsx đáng tin cậy. Ban đầu, Yomtov cho rằng đây phải là một sai sót, mã này đã chạy trong nhiều năm, được sử dụng bởi hàng chục triệu người. Nhưng khi ông tái tạo cuộc tấn công trong phòng thí nghiệm của mình, mô phỏng hoạt động hoàn hảo.

Những gì có vẻ như không thể giờ đây rất thật: một thảm họa bảo mật quy mô lớn, lén lút đang hiện hữu ngay trước mắt.

## [Bảo mật môi trường phát triển của bạn khỏi các mối đe dọa tiện ích mở rộng ẩn giấu](https://www.koi.security/get-a-demo?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx)

Tìm hiểu cách Koi giúp các tổ chức phát hiện, đánh giá và quản lý các tiện ích mở rộng rủi ro trên VSCode, OpenVSX, Chrome và các thị trường khác.

Giành quyền kiểm soát hoàn toàn và bảo vệ chuỗi cung cấp phát triển của bạn.

[Yêu cầu bản demo](https://www.koi.security/get-a-demo?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx)

## Lỗ hổng: Một biến thể của “Pwn Request” cổ điển

Để hiểu cách lỗ hổng hoạt động, trước tiên bạn cần hiểu cách mà các tiện ích mở rộng vào được OpenVSX ngay từ đầu.

Nếu bạn muốn xuất bản một tiện ích mở rộng lên Open VSX, bạn có hai tùy chọn:

1. Tải lên Open VSX tự mình
2. Yêu cầu xuất bản tự động một tiện ích mở rộng bằng cách tạo một pull request thêm tiện ích mở rộng vào danh sách trong file extensions.json

![Tài liệu](https://www.bleepstatic.com/images/news/security/k/koi/zero-day-ai/auto-publish-request.jpg)

“Vấn đề nằm ở quy trình xây dựng hàng đêm,” Yomtov nói.

Mỗi đêm, OpenVSX chạy một quy trình tự động mà lấy các phiên bản mới nhất của các tiện ích mở rộng do cộng đồng đóng góp, xây dựng chúng và xuất bản chúng lên thị trường. Nó nhằm mục đích giúp cuộc sống dễ dàng hơn cho các lập trình viên, nhưng trong trường hợp này, nó đã giới thiệu một lỗ hổng nghiêm trọng.

Để một tiện ích mở rộng được xuất bản tự động, tất cả những gì một lập trình viên cần làm là gửi một pull request đơn giản thêm nó vào một danh sách công khai. Từ đó, OpenVSX đảm nhận: nó kéo mã, cài đặt các phụ thuộc, xây dựng tiện ích mở rộng và xuất bản nó bằng một mã thông báo bí mật mạnh mẽ thuộc về tài khoản @open-vsx đáng tin cậy.

Mã thông báo này được thiết kế để giữ bí mật, chỉ được xem bởi hạ tầng đáng tin cậy. Thật không may, do cách quy trình xây dựng chạy mã tùy ý từ các kho công khai, bất kỳ tác giả tiện ích mở rộng nào cũng có thể tạo ra một bản cập nhật độc hại mà **lén lút thu thập mã thông báo**.

Điều còn đáng lo ngại hơn là họ sẽ không cần phải gửi một tiện ích mở rộng độc hại trực tiếp. Họ có thể đã giấu mã của họ trong một phụ thuộc, hoặc thậm chí là trong một phụ thuộc của phụ thuộc, và hệ thống sẽ tự động thực thi nó trong quá trình xây dựng hàng đêm. Từ đó, việc đánh cắp mã thông báo trở nên hết sức dễ dàng.

Và với mã thông báo đó trong tay, một kẻ tấn công không chỉ kiểm soát tiện ích mở rộng của riêng mình. Họ có thể xuất bản các bản cập nhật, ghi đè lên các bản hiện có, và lén lút chiếm đoạt toàn bộ thị trường.

## Tác động: Một cơn ác mộng chuỗi cung ứng đã phơi bày hàng triệu nhà phát triển

Với quyền truy cập vào mã thông báo của tài khoản @open-vsx, một kẻ tấn công có thể đã tạo ra một cơn ác mộng chuỗi cung ứng trên toàn cầu. “Mã thông báo đó là một thông tin đăng nhập siêu quản trị,” Yomtov giải thích. “Nó có thể xuất bản các tiện ích mở rộng mới, ghi đè lên những tiện ích hiện có, và giả mạo bất kỳ nhà phát hành nào trong hệ sinh thái.”

Từ điểm đó, thiệt hại trở nên gần như không cần nỗ lực. Mỗi khi một lập trình viên cài đặt một tiện ích mở rộng hoặc trình chỉnh sửa của họ tự động cập nhật một tiện ích trong nền, điều này liên tục xảy ra, payload của kẻ tấn công sẽ được lén lút chuyển đến máy của họ. Không có cảnh báo. Không có thông báo. Không nghi ngờ. Toàn bộ bị chiếm đoạt.

Và payload đó có thể làm gì? “Hầu như bất cứ điều gì,” Yomtov nói. Các tiện ích mở rộng trong VS Code và các nhánh của nó chạy dưới dạng các quy trình Node.js, có nghĩa là chúng có thể truy cập tệp, khởi động các chương trình khác, thực hiện các yêu cầu mạng và thực thi mã tùy ý.

Một bản cập nhật độc hại cho một tiện ích mở rộng phổ biến, chẳng hạn như plugin Python, có thể một cách lén lút cài đặt một keylogger, đánh cắp cookie của trình duyệt, chiếm đoạt mã nguồn, nhiễm các bản xây dựng, hoặc tạo backdoor cho toàn bộ pipeline phát triển.

Đã có những trường hợp riêng lẻ các tiện ích mở rộng VS Code độc hại đánh cắp khóa SSH hoặc ví tiền ảo. Nhưng đây sẽ không phải là một kẻ xấu vượt qua lỗ hổng. Đây sẽ là một cuộc chiếm đoạt quy mô lớn, gây thiệt hại chuỗi cung ứng ở quy mô sinh thái. Giống như SolarWinds, nhưng cho các công cụ phát triển.

Trong khi tác động sẽ nghiêm trọng nhất đối với các trình chỉnh sửa desktop như Cursor, Windsurf và VSCodium, ngay cả các môi trường dựa trên trình duyệt như Gitpod hoặc StackBlitz cũng có thể bị ảnh hưởng, tùy thuộc vào mức độ tích hợp của các tiện ích mở rộng bị xâm phạm.

## Vậy bạn có thể làm gì về điều đó?

Chúng tôi đã hỏi Yomtov điều mà người dùng và các tổ chức nên rút ra từ sự cố này. Câu trả lời của anh ấy rất thẳng thắn: “Giả định rằng mọi tiện ích mở rộng đều không đáng tin cậy cho đến khi được chứng minh ngược lại.”

Các tiện ích mở rộng có thể cảm thấy như những phần mở rộng vô hại, nhưng ở bên trong, chúng là những thành phần phần mềm mạnh mẽ, thường được viết bởi các cá nhân, chạy với quyền truy cập đầy đủ, và tự động cập nhật mà không có sự giám sát.

“Không khác gì việc kéo một gói từ npm hoặc PyPI, và thông thường thậm chí còn tồi tệ hơn,” Yomtov nói. “Nếu bạn không muốn tin tưởng mù quáng một repository GitHub với quyền truy cập root vào máy của bạn, bạn cũng không nên tin tưởng một tiện ích mở rộng.”

Để bảo vệ bản thân, Yomtov khuyến cáo các tổ chức nên coi các tiện ích mở rộng như một phần trong bề mặt tấn công của họ và áp dụng cùng một kỷ luật mà họ sử dụng cho bất kỳ phụ thuộc nào khác. Điều đó có nghĩa là:

1. **Duy trì một danh mục thực sự** về những gì đã được cài đặt, trên những máy nào, và bởi ai
2. **Đánh giá rủi ro** dựa trên ai đã xây dựng tiện ích mở rộng, cách nó được duy trì, và những gì nó thực sự làm
3. **Thực thi các chính sách rõ ràng** về những gì được phép, và hành động khi điều gì đó trượt ra ngoài giới hạn
4. **Theo dõi liên tục**, vì các tiện ích mở rộng có thể cập nhật âm thầm và giới thiệu các rủi ro mới qua đêm

Nhóm nghiên cứu của Koi tiếp tục [tìm thấy cả các tiện ích mở rộng dễ bị tấn công và độc hại](https://www.bleepingcomputer.com/news/security/malicious-chrome-extensions-with-17m-installs-found-on-web-store/) - không chỉ trong OpenVSX, hoặc thị trường của Microsoft, thậm chí còn trong các thị trường tiện ích mở rộng khác như Chrome Web Store.

“Hệ sinh thái đã phát triển nhanh hơn cả hàng rào bảo vệ,” Yomtov nói. “Cho đến khi điều đó thay đổi, giả định an toàn nhất là không tin tưởng. Mọi tiện ích mở rộng đều là một cánh cửa hậu tiềm tàng trừ khi bạn đã xem xét và đang theo dõi nó.”

Yomtov và đội ngũ tại [Koi Security](https://www.koi.security/?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx) đã tiết lộ có trách nhiệm lỗ hổng cho Eclipse Foundation, đơn vị duy trì dự án OpenVSX. Trong những tuần tiếp theo, họ đã làm việc chặt chẽ với các quản trị viên để xác thực vấn đề, thiết kế một bản sửa lỗi mạnh mẽ, và đảm bảo rằng bản vá đã được thực hiện và triển khai đúng cách.

Nhờ sự hợp tác này, lỗ hổng đã được đóng lại và thị trường lại một lần nữa an toàn cho hàng triệu lập trình viên dựa vào nó hàng ngày.

Nhưng sự cố này đã trở thành một lời cảnh tỉnh - ngay cả hạ tầng đáng tin cậy cũng cần được giám sát thường xuyên, đặc biệt khi nó nắm giữ chìa khóa của toàn bộ hệ sinh thái phát triển.

**Tìm hiểu cách Koi giúp các tổ chức phát hiện, đánh giá, và quản lý các tiện ích mở rộng rủi ro trên VSCode, OpenVSX, Chrome, và các thị trường khác**

[**Nói chuyện với chúng tôi.**](http://www.koi.security/?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx)

_Được tài trợ và viết bởi [Koi Security](https://koi.security?utm%5Fsource=bleeping&utm%5Fmedium=referral&utm%5Fcampaign=openvsx)._