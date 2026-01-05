# NordVPN phủ nhận các cáo buộc vi phạm, nói rằng kẻ tấn công có "dữ liệu giả"

![NordVPN](https://www.bleepstatic.com/content/hl-images/2026/01/05/nordvpn.jpg)

NordVPN phủ nhận các cáo buộc rằng các máy chủ phát triển nội bộ Salesforce của họ đã bị xâm nhập, cho biết rằng tin tặc chỉ thu được "dữ liệu giả" từ một tài khoản thử nghiệm trên nền tảng kiểm thử tự động của bên thứ ba.

The company's statement comes after a threat actor (using the 1011 handle) claimed on a hacking forum over the weekend that they stole more than 10 databases containing sensitive information like Salesforce API keys and Jira tokens, following a brute-force attack against a NordVPN development server.

"Today i am leaking +10 DB's source codes from a nordvpn development server. This information was acquired by bruteforcing a misconfigured server of Nordypn, which has salesforce and jira information stored. Compromissed information: SalesForce api keys, jira tokens and more," the threat actor said.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Tuy nhiên, như NordVPN tiết lộ hôm nay, đây thực chất là dữ liệu kiểm thử bị đánh cắp từ một môi trường thử nghiệm tạm thời được triển khai nhiều tháng trước trong quá trình thử nghiệm một nhà cung cấp tiềm năng cho việc kiểm thử tự động.

Dịch vụ VPN của Lithuania bổ sung rằng môi trường thử nghiệm không có kết nối với hạ tầng của họ và dữ liệu bị đánh cắp không bao gồm thông tin nhạy cảm của khách hàng hoặc doanh nghiệp.

![NordVPN breach claims](https://www.bleepstatic.com/images/news/u/1109292/2026/NordVPN-breach_claims.jpg)

_Các cáo buộc vi phạm NordVPN (BleepingComputer)_

"The leaked elements, such as the specific API tables and database schemas can only be artifacts of an isolated third-party test environment, containing only dummy data used for functionality checks. While no data in the dump points to NordVPN, we have contacted the vendor for additional information," [NordVPN giải thích](https://nordvpn.com/blog/addressing-alleged-salesforce-breach/).

"Because this was a preliminary test and no contract was ever signed, no real customer data, production source code, or active sensitive credentials were ever uploaded to this environment.

"We ultimately chose a different vendor and did not proceed with the one we tested. The environment in question was never connected to our production systems."

Mặc dù đây chỉ là một báo động giả, vào năm 2019, các hacker đã [xâm nhập các máy chủ của NordVPN và TorGuard](https://www.bleepingcomputer.com/news/security/hacker-breached-servers-belonging-to-multiple-vpn-providers/), chiếm quyền root đầy đủ và đánh cắp các khóa riêng tư được sử dụng để bảo mật các máy chủ web và cấu hình VPN của họ.

Để đối phó với sự cố năm 2019, [NordVPN đã giới thiệu](https://www.bleepingcomputer.com/news/security/nordvpn-plans-security-and-privacy-upgrades-after-hack/) chương trình thưởng lỗi và thuê các chuyên gia an ninh mạng bên ngoài để tiến hành một cuộc kiểm toán an ninh bên thứ ba "toàn diện".

Công ty cũng công bố kế hoạch chuyển sang các máy chủ chuyên dụng do họ sở hữu độc quyền và nâng cấp toàn bộ cơ sở hạ tầng 5.100 máy chủ của họ lên các máy chủ RAM.