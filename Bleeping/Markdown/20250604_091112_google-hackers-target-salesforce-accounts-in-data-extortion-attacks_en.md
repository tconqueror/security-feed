# Google: Hackers target Salesforce accounts in data extortion attacks

![Salesforce](https://www.bleepstatic.com/content/hl-images/2023/07/07/salesforce.jpg)

Google has observed hackers claiming to be the ShinyHunters extortion group conducting social engineering attacks against multi-national companies to steal data from organization's SalesForce platforms.

According to Google's Threat Intelligence Group (GTIG), which tracks the threat cluster as 'UNC6040,' the attacks target English-speaking employees with voice phishing attacks to trick them into connecting a modified version of Salesforce's Data Loader application.

The attackers impersonate IT support personnel, requesting the target employee to accept a connection to Salesforce Data Loader, a client application that allows users to import, export, update, or delete data within Salesforce environments.

"The application supports OAuth and allows for direct 'app' integration via the 'connected apps' functionality in Salesforce," explain the researchers.

"Threat actors abuse this by persuading a victim over the phone to open the Salesforce connect setup page and enter a 'connection code,' thereby linking the actor-controlled Data Loader to the victim's environment.

![Prompt to enter connection code](https://www.bleepstatic.com/images/news/u/1220909/2025/June/prompt.jpg)

**Prompt to enter connection code**  
_Source: Google_

The target organizations already use the Salesforce cloud-based customer relationship management (CRM) platform, so the malicious request to install the tool appears legitimate within the context of their workflow.

In the UNC6040 attacks, the app is used to export data stored in Salesforce instances and then use the access to move laterally through connected platforms such as Okta, Microsoft 365, and Workplace.

Accessing these additional cloud platforms allows the threat actors to access more sensitive information stored on those platforms, which can include sensitive communications, authorization tokens, documents, and more.

"UNC6040 is a financially motivated threat cluster that accesses victim networks by voice phishing social engineering," describes the GTIG report.

"Upon obtaining access, UNC6040 has been observed immediately exfiltrating data from the victim's Salesforce environment using Salesforce's Data Loader application."

"Following this initial data theft, UNC6040 was observed moving laterally through the victim's network, accessing and exfiltrating data from other platforms such as Okta, Workplace, and Microsoft 365."

![Overview of the UNC6040 attack](https://www.bleepstatic.com/images/news/u/1220909/2025/June/attack-path.jpg)

**Overview of the UNC6040 attack**  
_Source: Google_

In some cases, the data exfiltration process was stopped prematurely, as protection systems that detected unauthorized activity intervened to revoke access. The threat actors appeared to be aware of this risk, experimenting with various packet sizes before escalating their attack.

UNC6040 also used modified versions of the Salesforce Data Loader appropriately named to fit the social engineering context. For example, renaming it to "My Ticket Portal" and tricking victims into installing the app on their systems during an alleged support phone call.

GTIG reports the threat actors use Mullvad VPN IPs when exfiltrating the Salesforce data to obfuscate the activity.

Google says that attacks used phishing pages impersonating Okta, linking them back to threat actors associated with "The Com."

Once data is stolen, the threat actors will eventually attempt to extort the company into paying a ransom not to leak the data. Google says that these extortion demands can come months later, claiming to be from the infamous ShinyHunters extortion group.

"In some instances, extortion activities haven't been observed until several months after the initial UNC6040 intrusion activity, which could suggest that UNC6040 has partnered with a second threat actor that monetizes access to the stolen data," explains Google.

"During these extortion attempts, the actor has claimed affiliation with the well-known hacking group ShinyHunters, likely as a method to increase pressure on their victims."

Google proposes restriction of "API Enabled" permissions, limitation of app installation authorization, and blocking access from commercial VPNs like Mullvad.

More information on how to protect Salesforce from social engineering attacks is [available here](https://www.salesforce.com/blog/protect-against-social-engineering/).

+-+-+-+-+-+-+-+-
# Google: Tin tặc nhắm vào tài khoản Salesforce trong các cuộc tấn công tống tiền dữ liệu

![Salesforce](https://www.bleepstatic.com/content/hl-images/2023/07/07/salesforce.jpg)

Google đã quan sát thấy những tin tặc tự xưng là nhóm tống tiền ShinyHunters tiến hành các cuộc tấn công kỹ thuật xã hội nhắm vào các công ty đa quốc gia để đánh cắp dữ liệu từ nền tảng Salesforce của tổ chức.

Theo Nhóm Tình báo Đe dọa của Google (GTIG), theo dõi nhóm đe dọa được gọi là 'UNC6040', các cuộc tấn công nhắm vào những nhân viên nói tiếng Anh bằng các cuộc tấn công lừa đảo qua giọng nói nhằm đánh lừa họ kết nối với phiên bản sửa đổi của ứng dụng Data Loader của Salesforce.

Các tin tặc mạo danh nhân viên hỗ trợ CNTT, yêu cầu nhân viên mục tiêu chấp nhận kết nối với Salesforce Data Loader, một ứng dụng khách cho phép người dùng nhập, xuất, cập nhật hoặc xóa dữ liệu trong các môi trường Salesforce.

"Ứng dụng này hỗ trợ OAuth và cho phép tích hợp 'ứng dụng' trực tiếp thông qua chức năng 'ứng dụng đã kết nối' trong Salesforce," các nhà nghiên cứu giải thích.

"Các tác nhân đe dọa lợi dụng điều này bằng cách thuyết phục nạn nhân qua điện thoại mở trang thiết lập kết nối Salesforce và nhập 'mã kết nối', từ đó liên kết Data Loader do tác nhân điều khiển với môi trường của nạn nhân.

![Đề nghị nhập mã kết nối](https://www.bleepstatic.com/images/news/u/1220909/2025/June/prompt.jpg)

**Đề nghị nhập mã kết nối**  
_Nguồn: Google_

Các tổ chức mục tiêu đã sử dụng nền tảng quản lý quan hệ khách hàng (CRM) dựa trên đám mây của Salesforce, vì vậy yêu cầu độc hại để cài đặt công cụ này có vẻ hợp pháp trong bối cảnh quy trình làm việc của họ.

Trong các cuộc tấn công UNC6040, ứng dụng này được sử dụng để xuất dữ liệu lưu trữ trong các phiên bản Salesforce và sau đó sử dụng quyền truy cập để di chuyển theo chiều ngang qua các nền tảng kết nối như Okta, Microsoft 365 và Workplace.

Việc truy cập vào những nền tảng đám mây bổ sung này cho phép các tác nhân đe dọa truy cập nhiều thông tin nhạy cảm hơn được lưu trữ trên những nền tảng đó, bao gồm thông tin liên lạc nhạy cảm, mã thông báo ủy quyền, tài liệu và hơn thế nữa.

"UNC6040 là một nhóm đe dọa được thúc đẩy bởi tài chính, tiếp cận mạng lưới nạn nhân thông qua lừa đảo qua giọng nói," báo cáo của GTIG mô tả.

"Sau khi có được quyền truy cập, UNC6040 đã được quan sát thấy ngay lập tức xuất dữ liệu từ môi trường Salesforce của nạn nhân bằng ứng dụng Data Loader của Salesforce."

"Ngay sau vụ đánh cắp dữ liệu đầu tiên, UNC6040 đã được quan sát thấy di chuyển theo chiều ngang qua mạng lưới của nạn nhân, truy cập và xuất dữ liệu từ các nền tảng khác như Okta, Workplace và Microsoft 365."

![Tổng quan về cuộc tấn công UNC6040](https://www.bleepstatic.com/images/news/u/1220909/2025/June/attack-path.jpg)

**Tổng quan về cuộc tấn công UNC6040**  
_Nguồn: Google_

Trong một số trường hợp, quá trình xuất dữ liệu đã bị dừng lại quá sớm, vì các hệ thống bảo vệ đã phát hiện hoạt động không được ủy quyền và can thiệp để thu hồi quyền truy cập. Các tác nhân đe dọa dường như nhận thức được rủi ro này, thử nghiệm với kích thước gói khác nhau trước khi gia tăng cuộc tấn công của họ.

UNC6040 cũng đã sử dụng các phiên bản được sửa đổi của ứng dụng Data Loader của Salesforce được đặt tên phù hợp để phù hợp với ngữ cảnh kỹ thuật xã hội. Chẳng hạn, đổi tên thành "Cổng thông tin ticket của tôi" và đánh lừa nạn nhân cài đặt ứng dụng này trên hệ thống của họ trong một cuộc gọi điện thoại giả danh hỗ trợ.

GTIG báo cáo rằng các tác nhân đe dọa sử dụng địa chỉ IP của Mullvad VPN khi xuất dữ liệu Salesforce để che giấu hoạt động này.

Google cho biết các cuộc tấn công đã sử dụng các trang lừa đảo mạo danh Okta, liên kết chúng trở lại với các tác nhân đe dọa liên quan đến "The Com".

Khi dữ liệu bị đánh cắp, các tác nhân đe dọa sẽ cuối cùng cố gắng tống tiền công ty để không tiết lộ dữ liệu. Google cho biết các yêu cầu tống tiền này có thể được đưa ra vài tháng sau, tự xưng là từ nhóm tống tiền nổi tiếng ShinyHunters.

"Trong một số trường hợp, các hoạt động tống tiền chưa được quan sát cho đến vài tháng sau hoạt động xâm nhập UNC6040 ban đầu, điều này có thể gợi ý rằng UNC6040 đã hợp tác với một tác nhân đe dọa thứ hai kiếm tiền từ quyền truy cập vào dữ liệu bị đánh cắp," Google giải thích.

"Trong những nỗ lực tống tiền này, tác nhân đã tuyên bố có mối liên hệ với nhóm hacker nổi tiếng ShinyHunters, có khả năng là một phương pháp để tăng áp lực lên các nạn nhân của họ."

Google đề xuất hạn chế quyền "API Enabled", giới hạn ủy quyền cài đặt ứng dụng và chặn quyền truy cập từ các VPN thương mại như Mullvad.

Thêm thông tin về cách bảo vệ Salesforce khỏi các cuộc tấn công kỹ thuật xã hội có sẵn [tại đây](https://www.salesforce.com/blog/protect-against-social-engineering/).