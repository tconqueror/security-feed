# Nhân viên Target xác nhận mã nguồn rò rỉ là chính xác

![Target](https://www.bleepstatic.com/content/hl-images/2026/01/11/Target.com-1600x900-min.png)

Nhiều nhân viên hiện tại và trước đây của Target đã liên hệ với BleepingComputer để xác nhận rằng mã nguồn và tài liệu được một tác nhân đe dọa chia sẻ trực tuyến khớp với các hệ thống nội bộ thực tế.

Một nhân viên hiện tại cũng chia sẻ các thông báo nội bộ thông báo về một thay đổi bảo mật "được tăng tốc" giới hạn quyền truy cập vào Enterprise Git server của Target, được triển khai một ngày sau khi BleepingComputer lần đầu liên hệ với công ty về cáo buộc rò rỉ.

## Nhân viên xác minh tính xác thực của tài liệu rò rỉ

Hôm qua, BleepingComputer [độc quyền đưa tin](https://www.bleepingcomputer.com/news/security/targets-dev-server-offline-after-hackers-claim-to-steal-source-code/) rằng các hacker tuyên bố đang bán mã nguồn nội bộ của Target sau khi công bố một mẫu các repository bị đánh cắp trên Gitea, một nền tảng phát triển phần mềm công khai.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Kể từ đó, nhiều nguồn có kiến thức trực tiếp về các pipeline CI/CD và hạ tầng nội bộ của Target đã liên hệ để cung cấp thông tin xác thực minh bạch rằng dữ liệu rò rỉ là xác thực.

Một cựu nhân viên Target xác nhận rằng các tên hệ thống nội bộ xuất hiện trong mẫu, chẳng hạn "BigRED" và "TAP \[Provisioning\]," tương ứng với các nền tảng thực tế được công ty sử dụng cho việc triển khai và điều phối ứng dụng trên đám mây và tại chỗ.

Cả một nhân viên hiện tại và cựu nhân viên đều xác nhận rằng các yếu tố của ngăn xếp công nghệ, bao gồm các bộ dữ liệu Hadoop, được đề cập trong mẫu rò rỉ phù hợp với các hệ thống được sử dụng nội bộ.

Điều này bao gồm các công cụ xây dựng xung quanh một nền tảng CI/CD tùy chỉnh có tên là Vela — một thực tế mà Target [cũng từng đề cập công khai](https://archive.md/u55rZ), cũng như việc sử dụng hạ tầng chuỗi cung ứng như JFrog Artifactory, như cũng thấy rõ từ [thông tin kinh doanh bên thứ ba](https://archive.md/5r3WV).

Các nhân viên cũng độc lập tham chiếu các tên mã dự án độc quyền và định danh phân loại, chẳng hạn những thứ được biết trong nội bộ là "blossom IDs," xuất hiện trong bộ dữ liệu rò rỉ.

Sự xuất hiện của các tham chiếu hệ thống này, tên nhân viên, tên dự án và các URL khớp trong mẫu càng củng cố rằng tài liệu phản ánh một môi trường phát triển nội bộ thực sự chứ không phải mã giả mạo hay mã chung chung.

Nếu bạn là nhân viên Target hoặc có bất kỳ thông tin nào liên quan đến sự việc này, hãy gửi cho chúng tôi một tip một cách bảo mật [send us a tip](https://www.bleepingcomputer.com/news-tip/) trực tuyến hoặc qua [Signal](https://signal.org/en/) tại @axsharma.01.

## Target triển khai thay đổi truy cập 'được tăng tốc'

Một nhân viên hiện tại, người yêu cầu giấu tên, cũng chia sẻ ảnh chụp màn hình một tin nhắn Slack gửi toàn công ty trong đó một quản lý sản phẩm cấp cao thông báo một thay đổi bảo mật bất ngờ, một ngày sau khi BleepingComputer đã liên hệ với Target:

"Effective January 9th, 2026, access to git.target.com (Target's on-prem GitHub Enterprise Server) now requires connection to a Target-managed network (either on-site or via VPN). This change was accelerated and aligns with how we're handling access to GitHub.com," quản lý được thấy tuyên bố.

Enterprise Git servers có thể lưu trữ cả các repository riêng tư, chỉ hiển thị cho nhân viên đã xác thực, và các dự án mã nguồn mở công khai.

Tuy nhiên, tại Target, mã nguồn mở thường được [hosted on GitHub.com](https://github.com/target), trong khi git.target.com được sử dụng cho phát triển nội bộ và yêu cầu xác thực nhân viên.

Như đã đưa tin hôm qua, git.target.com có thể truy cập qua web cho đến tuần trước và yêu cầu nhân viên đăng nhập. Hiện trang không còn truy cập được từ internet công cộng và chỉ có thể truy cập từ mạng nội bộ của Target hoặc VPN doanh nghiệp, cho thấy việc phong tỏa quyền truy cập vào môi trường mã nguồn sở hữu của công ty.

![git.target.com site before it was taken offline (BleepingComputer)](https://www.bleepstatic.com/images/news/u/1164866/2026/Jan/target.com-source-code-sale-claims/target-git-vpn-redirect.jpg)

**_git.target.com_ site before it was taken offline** (BleepingComputer)

## Rò rỉ dữ liệu, vi phạm hay có liên quan nội bộ?

Nguyên nhân gốc rễ khiến dữ liệu rơi vào tay tác nhân đe dọa vẫn chưa được xác định.

Tuy nhiên, nhà nghiên cứu bảo mật Alon Gal, CTO và đồng sáng lập của Hudson Rock, đã nói với BleepingComputer rằng nhóm của ông đã xác định một workstation của nhân viên Target bị nhiễm malware infostealer vào cuối tháng 9 năm 2025 và có quyền truy cập rộng rãi vào các dịch vụ nội bộ.

"There is a recently infected computer of a Target employee with access to IAM, Confluence, wiki, and Jira," Gal nói với BleepingComputer.

"It's especially relevant because, despite tens of infected Target employees we've seen, almost none had IAM credentials and none had wiki access, except for one other case."

Chưa có xác nhận rằng cuộc nhiễm này có liên hệ trực tiếp với mã nguồn hiện đang được quảng cáo để bán. Tuy nhiên, không hiếm khi các tác nhân đe dọa trích xuất dữ liệu và chỉ cố gắng kiếm tiền hoặc rò rỉ nó vài tháng sau đó. Ví dụ, băng nhóm ransomware Clop [bắt đầu tống tiền nạn nhân](https://www.bleepingcomputer.com/news/security/oracle-links-clop-extortion-attacks-to-july-security-flaws/) thông qua các mối đe dọa rò rỉ dữ liệu vào tháng 10 năm 2025 đối với các tài liệu bị đánh cắp [còn sớm từ tháng 7](https://www.bleepingcomputer.com/news/security/logitech-confirms-data-breach-after-clop-extortion-attack/) trong năm đó.

Tác nhân đe dọa tuyên bố toàn bộ tập dữ liệu khoảng 860GB. Trong khi BleepingComputer chỉ xem xét một mẫu 14MB gồm năm repository một phần, các nhân viên nói rằng ngay cả tập con hạn chế này cũng chứa mã nội bộ và các tham chiếu hệ thống xác thực, làm dấy lên câu hỏi về phạm vi và mức độ nhạy cảm của những gì kho lưu trữ lớn hơn có thể chứa.

BleepingComputer đã chia sẻ các liên kết repository Gitea với Target vào tuần trước và sau đó đề nghị chuyển các phát hiện tình báo mối đe dọa của Hudson Rock để hỗ trợ điều tra. Công ty chưa trả lời các câu hỏi tiếp theo và vẫn im lặng về việc liệu họ có đang điều tra một vụ vi phạm hay khả năng liên quan nội bộ hay không.