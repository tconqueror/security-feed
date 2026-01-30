# Vụ rò rỉ dữ liệu của Match Group ảnh hưởng đến Hinge, Tinder, OkCupid và Match

![Match Group breach exposes data from Hinge, Tinder, OkCupid, and Match](https://www.bleepstatic.com/content/hl-images/2026/01/29/Match_Group.png)

Match Group, chủ sở hữu của nhiều dịch vụ hẹn hò trực tuyến phổ biến như Tinder, Match.com, Meetic, OkCupid và Hinge, đã xác nhận một sự cố an ninh mạng làm lộ dữ liệu người dùng.

Công ty cho biết tin tặc đã đánh cắp "một lượng hạn chế dữ liệu người dùng" sau khi nhóm đe dọa ShinyHunters rò rỉ 1,7 GB tập tin nén được cho là chứa 10 triệu hồ sơ thông tin người dùng từ Hinge, Match, OkCupid cùng các tài liệu nội bộ.

Trong một tuyên bố gửi BleepingComputer, phát ngôn viên của Match Group đã xác nhận sự việc.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

"Chúng tôi đã biết về các tuyên bố được đăng tải trực tuyến liên quan đến sự cố bảo mật gần đây," phát ngôn viên của công ty cho biết.

"Match Group luôn coi trọng tính an toàn và bảo mật của người dùng, đã nhanh chóng hành động để chấm dứt việc truy cập trái phép."

![The Match Group data leak](https://www.bleepstatic.com/images/news/u/1220909/2026/January/shiny.jpg)

**Vụ rò rỉ dữ liệu của Match Group**  
_Nguồn: BleepingComputer_

Công ty cho biết đang tiến hành điều tra sự việc với sự hỗ trợ của các chuyên gia bên ngoài và hiện không có dấu hiệu cho thấy tin tặc đã tiếp cận thông tin đăng nhập, dữ liệu tài chính hoặc trao đổi riêng tư của người dùng.

"Chúng tôi tin rằng sự cố này chỉ ảnh hưởng đến một lượng nhỏ dữ liệu người dùng và đang trong quá trình thông báo cho các cá nhân liên quan," Match Group cho biết thêm.

Match Group là một gã khổng lồ trong lĩnh vực hẹn hò trực tuyến với doanh thu hàng năm đạt 3,5 tỷ USD và hơn 80 triệu người dùng tích cực trên tất cả các ứng dụng của hãng.

Sự cố mới nhất này là một phần trong chiến dịch lừa đảo qua điện thoại (vishing) mới của ShinyHunters nhằm vào [các tài khoản đăng nhập một lần (SSO)](https://www.bleepingcomputer.com/news/security/shinyhunters-claim-to-be-behind-sso-account-data-theft-attacks/) tại Okta, Microsoft và Google trên [hơn một trăm](https://www.silentpush.com/blog/slsh-alert/) tổ chức giá trị cao, bằng cách sử dụng các liên kết giả mạo đến cổng đăng nhập nội bộ.

Trường hợp của Match Group, BleepingComputer được biết rằng kẻ tấn công đã đánh cắp dữ liệu sau khi xâm nhập vào tài khoản SSO Okta, qua đó chiếm quyền truy cập vào hệ thống phân tích tiếp thị AppsFlyer và các tài khoản lưu trữ đám mây Google Drive, Dropbox của công ty.

BleepingComputer đã phát hiện rằng cuộc tấn công kỹ thuật xã hội này sử dụng tên miền lừa đảo 'matchinternal.com.'

Tin tặc cho biết dữ liệu bị đánh cắp có chứa thông tin nhận dạng cá nhân (PII) nhưng không nhiều, phần lớn là thông tin theo dõi hoạt động người dùng.

Các doanh nghiệp có thể tăng cường phòng thủ trước các cuộc tấn công dựa trên kỹ thuật xã hội bằng cách triển khai các giải pháp chống lừa đảo hiệu quả.

"Dù đây không phải kết quả từ lỗ hổng bảo mật trong sản phẩm hoặc cơ sở hạ tầng của nhà cung cấp, chúng tôi mạnh mẽ khuyến nghị chuyển sang sử dụng MFA chống lừa đảo, như khóa bảo mật FIDO2 hoặc passkeys bất cứ khi nào có thể, vì những biện pháp này có khả năng chống lại các cuộc tấn công kỹ thuật xã hội mà phương thức xác thực qua tin nhắn SMS hoặc push-based không đáp ứng được," Charles Carmakal, Giám đốc Công nghệ tại Mandiant chia sẻ.

Ngoài ra, "quản trị viên cũng nên thiết lập chính sách ủy quyền ứng dụng nghiêm ngặt và theo dõi nhật ký để phát hiện hoạt động API bất thường hoặc thiết bị đăng ký trái phép."

Trong một bài đăng tuần trước, Okta cũng khuyến nghị sử dụng cơ chế chống lừa đảo để ngăn chặn truy cập trái phép. "Khi sử dụng Okta để xác thực nhân sự, điều này đồng nghĩa với việc đăng ký người dùng vào Okta FastPass, passkeys hoặc cả hai để tạo tính dự phòng," [theo Moussa Diallo](https://www.okta.com/en-gb/blog/threat-intelligence/phishing-kits-adapt-to-the-script-of-callers/), nhà nghiên cứu mối đe dọa tại Okta Threat Intelligence.

"Các tác nhân kỹ thuật xã hội cũng có thể bị ngăn chặn bằng cách thiết lập vùng mạng hoặc danh sách kiểm soát truy cập từ chối kết nối qua các dịch vụ ẩn danh mà tin tặc thường sử dụng. Điều quan trọng là phải biết yêu cầu hợp pháp đến từ đâu và cho phép các mạng đó," Diallo cho biết thêm.

Nhà nghiên cứu lưu ý rằng một số tổ chức tài chính như [Monzo Bank](https://monzo.com/help/monzo-fraud-category/monzo-call-status-web) và [sàn giao dịch tiền điện tử Crypto.com](https://crypto.com/eea/product-news/live-inapp-call-warning) hiện đang thử nghiệm tính năng kiểm tra cuộc gọi trực tiếp, cho phép người dùng xác minh trên ứng dụng di động chính thức của công ty xem người gọi có phải là đại diện được ủy quyền hay không.