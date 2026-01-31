# Mandiant tiết lộ cách ShinyHunters lợi dụng SSO để đánh cắp dữ liệu đám mây

![Hacker nhìn chằm chằm vào một chiếc hộp](https://www.bleepstatic.com/content/hl-images/2024/05/07/hacker-box.jpg)

Mandiant cho biết làn sóng tấn công đánh cắp dữ liệu SaaS gần đây của ShinyHunters được thúc đẩy bởi các cuộc tấn công lừa đảo qua điện thoại (vishing) có chủ đích và các trang phishing mạo danh công ty nhằm đánh cắp thông tin đăng nhập SSO cùng mã xác thực đa yếu tố (MFA).

Như [BleepingComputer đã đưa tin trước đó](https://www.bleepingcomputer.com/news/security/shinyhunters-claim-to-be-behind-sso-account-data-theft-attacks/), các tác nhân đe dọa đã mạo danh nhân viên IT và bộ phận hỗ trợ để gọi trực tiếp cho nhân viên, tuyên bố rằng cần cập nhật cài đặt MFA. Trong cuộc gọi, nạn nhân được hướng dẫn truy cập vào một trang phishing giống với cổng đăng nhập của công ty họ.

Theo [Okta](https://www.okta.com/blog/threat-intelligence/phishing-kits-adapt-to-the-script-of-callers/), các trang này sử dụng bộ công cụ phishing tiên tiến cho phép kẻ tấn công hiển thị hộp thoại tương tác trong khi đang gọi điện với nạn nhân.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Trong khi vẫn đang nói chuyện với nạn nhân, kẻ tấn công chuyển tiếp thông tin đăng nhập bị đánh cắp theo thời gian thực, kích hoạt thử thách MFA hợp pháp, và hướng dẫn nạn nhân cách phản hồi, bao gồm phê duyệt thông báo đẩy hoặc nhập mã dùng một lần.

Điều này cho phép kẻ tấn công xác thực thành công với thông tin đăng nhập bị đánh cắp và đăng ký thiết bị MFA của chính chúng.

Sau khi chiếm được quyền truy cập vào tài khoản, chúng đăng nhập vào bảng điều khiển SSO Okta, Microsoft Entra hoặc Google của tổ chức - nơi liệt kê tập trung tất cả ứng dụng SaaS mà người dùng có quyền truy cập.

![Ví dụ bảng điều khiển SSO Microsoft Entra](https://www.bleepstatic.com/images/news/security/s/shinyhunters/sso-attacks/microsoft-entra-sso-dashboard.jpg)

**Ví dụ bảng điều khiển SSO Microsoft Entra**

Các ứng dụng này bao gồm Salesforce - [mục tiêu chính của ShinyHunters](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/), Microsoft 365, SharePoint, DocuSign, Slack, Atlassian, Dropbox, Google Drive và nhiều nền tảng nội bộ/bên thứ ba khác.

Đối với các tác nhân đe dọa tập trung vào đánh cắp dữ liệu và tống tiền, bảng điều khiển SSO trở thành bàn đạp để tiếp cận dữ liệu đám mây của công ty, cho phép chúng truy cập vào nhiều dịch vụ chỉ từ một tài khoản bị xâm phạm.

Nhóm tống tiền ShinyHunters [đã xác nhận với BleepingComputer](https://www.bleepingcomputer.com/news/security/shinyhunters-claim-to-be-behind-sso-account-data-theft-attacks/) rằng chúng và một số đối tác liên kết là thủ phạm đằng sau các cuộc tấn công này. Nhóm này cũng tuyên bố các tác nhân đe dọa khác đã thực hiện các cuộc tấn công tương tự.

Ngay sau khi thông tin về các cuộc tấn công này được công khai, nhóm tống tiền ShinyHunters đã khởi chạy một trang rò rỉ dữ liệu để bắt đầu tiết lộ dữ liệu liên quan.

Hôm nay, Nhóm Tình báo Đe dọa Google/Mandiant [đã phát hành báo cáo](https://cloud.google.com/blog/topics/threat-intelligence/expansion-shinyhunters-saas-data-theft) cho biết họ đang theo dõi hoạt động này trên các cụm đe dọa khác nhau được theo dõi là **UNC6661**, **UNC6671** và **UNC6240** (ShinyHunters).

## Nhiều tác nhân đe dọa đang tiến hành tấn công

Mandiant tiết lộ UNC6661 mạo danh nhân viên IT khi gọi cho nạn nhân và hướng họ tới các tên miền phishing mạo danh công ty để thu thập thông tin đăng nhập SSO và mã MFA. Sau khi đăng nhập, kẻ tấn công đã đăng ký thiết bị MFA của riêng chúng để duy trì quyền truy cập.

Chúng sử dụng quyền truy cập này để đánh cắp dữ liệu từ các ứng dụng đám mây dựa trên bất kỳ quyền hạn nào có sẵn thông qua phiên SSO bị xâm phạm. Mandiant tin rằng hoạt động này mang tính cơ hội, với các tác nhân đe dọa nhắm mục tiêu vào bất kỳ ứng dụng SaaS nào có sẵn.

Tuy nhiên, cần lưu ý rằng ShinyHunters đã nói với BleepingComputer trước đây rằng trọng tâm chính của chúng là dữ liệu Salesforce.

**Các giai đoạn tấn công vishing**  
_Nguồn: Mandiant_

Mandiant chia sẻ ví dụ về nhật ký được tạo trong các cuộc tấn công đánh cắp dữ liệu:

* Sự kiện Microsoft 365 và SharePoint cho thấy tải xuống tệp với User-Agent xác định là PowerShell, chỉ ra các tập lệnh hoặc công cụ được sử dụng để tải dữ liệu.
* Hoạt động đăng nhập Salesforce bắt nguồn từ các địa chỉ IP sau này được xác định thuộc về kẻ tấn công.
* Nhật ký kiểm tra DocuSign cho thấy việc tải xuống tài liệu hàng loạt liên quan đến cùng các IOC.

Trong một vụ vi phạm liên quan đến khách hàng Okta, Mandiant cho biết kẻ tấn công đã kích hoạt tiện ích bổ sung Google Workspace có tên "[ToogleBox Recall](https://www.tooglebox.com/features/email-recall)" - công cụ chúng sử dụng để tìm kiếm và xóa email nhằm che giấu hành vi.

"Trong ít nhất một sự cố nơi kẻ đe dọa giành quyền truy cập vào tài khoản khách hàng Okta, UNC6661 đã kích hoạt tiện ích ToogleBox Recall cho tài khoản Google Workspace của nạn nhân - một công cụ được thiết kế để tìm kiếm và xóa vĩnh viễn email," Mandiant giải thích.

"Chúng sau đó đã xóa email 'Security method enrolled' từ Okta, gần như chắc chắn để ngăn nhân viên phát hiện tài khoản của họ được liên kết với thiết bị MFA mới."

Mandiant cho biết các tên miền internet được sử dụng trong các cuộc tấn công của UNC6661 được đăng ký thông qua NICENIC và thường sử dụng định dạng <companyname>sso.com hoặc <companyname>internal.com.

Mặc dù các cuộc xâm nhập ban đầu và tấn công đánh cắp dữ liệu được cho là do UNC6661 thực hiện, Mandiant tiết lộ yêu cầu tống tiền được gửi bởi ShinyHunters (aka UNC6240) và bao gồm ID Tox messenger mà chúng đã sử dụng trong các nỗ lực tống tiền trước đây.

**Đoạn trích ghi chú tống tiền của ShinyHunters**  
_Nguồn: Mandiant_

Mandiant cho biết một cụm đe dọa khác được theo dõi là UNC6671 cũng sử dụng kỹ thuật vishing tương tự, nhưng với các tên miền phishing được đăng ký qua Tucows.

Không giống UNC6661, yêu cầu tống tiền của UNC6671 không được gửi dưới tên ShinyHunters, sử dụng ID Tox khác để đàm phán và áp dụng chiến thuật gây áp lực mạnh mẽ, bao gồm quấy rối nhân sự công ty.

Mandiant tiết lộ các tên miền phishing được sử dụng trong các cuộc tấn công này tuân theo các mẫu đặt tên phổ biến nhằm mạo danh cổng công ty:

* **Cổng SSO công ty:** <companyname>sso\[.\]com, my<companyname>sso\[.\]com và my-<companyname>sso\[.\]com
* **Cổng nội bộ:** <companyname>internal\[.\]com, www.<companyname>internal\[.\]com và my<companyname>internal\[.\]com
* **Chủ đề hỗ trợ và helpdesk:** <companyname>support\[.\]com, ticket-<companyname>\[.\]support và support-<companyname>\[.\]com
* **Mạo danh nhà cung cấp danh tính:** <companyname>okta\[.\]com, <companyname>azure\[.\]com và on<companyname>zendesk\[.\]com
* **Cổng truy cập:** <companyname>access\[.\]com, www.<companyname>access\[.\]com và my<companyname>acess\[.\]com

Ví dụ, **matchinternal\[.\]com** đã được sử dụng trong [vụ vi phạm gần đây tại Match Group](https://www.bleepingcomputer.com/news/security/match-group-breach-exposes-data-from-hinge-tinder-okcupid-and-match/), làm lộ dữ liệu của các trang hẹn hò phổ biến Hinge, Tinder, OkCupid và Match.

Mandiant lưu ý nhiều địa chỉ IP liên quan đến chiến dịch thuộc về dịch vụ VPN thương mại hoặc mạng proxy dân cư như Mullvad, Oxylabs, NetNut, 9Proxy, Infatica và nsocks.

Mandiant cũng khuyến nghị các bên bảo vệ nên ưu tiên phát hiện các hành vi sau để xác định các loại tấn công này:

* Tài khoản SSO bị xâm phạm theo sau bởi việc xuất dữ liệu nhanh chóng từ nền tảng SaaS
* User-Agent PowerShell truy cập SharePoint hoặc OneDrive
* Ủy quyền OAuth Google Workspace bất ngờ cho ToogleBox Recall
* Xóa thông báo email về thay đổi MFA

Để giúp các tổ chức phòng thủ chống lại các loại tấn công này, [Mandiant đã phát hành](https://cloud.google.com/blog/topics/threat-intelligence/defense-against-shinyhunters-cybercrime-saas) các khuyến nghị tăng cường bảo mật, ghi nhật ký và phát hiện chống lại tấn công vishing của ShinyHunters.

Hướng dẫn này được tổ chức xoay quanh việc tăng cường bảo mật quy trình làm việc danh tính và đặt lại xác thực, ghi nhật ký telemetry phù hợp cùng các biện pháp phát hiện nhằm tìm hành vi hậu vishing trước khi đánh cắp dữ liệu xảy ra.

Mandiant cũng [đã phát hành các quy tắc](https://security.googlecloudcommunity.com/community-blog-42/new-to-google-secops-leveraging-okta-curated-detections-to-detect-shinyhunters-related-activity-6693) cho Google SecOps để phát hiện hoạt động liên quan đến ShinyHunters.