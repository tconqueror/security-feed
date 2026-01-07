# ownCloud kêu gọi người dùng bật MFA sau báo cáo trộm thông tin đăng nhập

![ownCloud](https://www.bleepstatic.com/content/hl-images/2026/01/07/ownCloud.jpg)

Nền tảng chia sẻ tập tin ownCloud hôm nay cảnh báo người dùng hãy bật xác thực đa yếu tố (MFA) để ngăn những kẻ tấn công dùng thông tin đăng nhập bị xâm phạm đánh cắp dữ liệu của họ.

ownCloud có hơn 200 triệu người dùng trên toàn thế giới, bao gồm hàng trăm tổ chức doanh nghiệp và khu vực công như European Organization for Nuclear Research, the European Commission, công ty công nghệ Đức ZF Group, công ty bảo hiểm Swiss Life, và European Investment Bank.

Trong một thông báo an ninh được công bố hôm nay, công ty kêu gọi người dùng bật MFA sau một [báo cáo từ công ty an ninh mạng Israel Hudson Rock](https://www.infostealers.com/article/dozens-of-global-companies-hacked-via-cloud-credentials-from-infostealer-infections-more-at-risk/), báo cáo tiết lộ rằng nhiều tổ chức đã bị xâm nhập các nền tảng chia sẻ tập tin tự lưu trữ của họ (bao gồm một số instance ownCloud Community Edition) trong các cuộc tấn công trộm thông tin đăng nhập.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

"OwnCloud platform was not hacked or breached. The Hudson Rock report explicitly confirms that no zero-day exploits or platform vulnerabilities were involved," [ownCloud cho biết](https://owncloud.com/security-advisories/security-advisory-credential-theft-incidents/).

"Các sự cố xảy ra thông qua một chuỗi tấn công khác: các tác nhân đe dọa có được thông tin đăng nhập người dùng thông qua phần mềm độc hại infostealer (như RedLine, Lumma, hoặc Vidar) được cài trên thiết bị nhân viên. Những thông tin đăng nhập này sau đó được dùng để đăng nhập vào các tài khoản ownCloud không bật Multi-Factor Authentication (MFA)."

ownCloud khuyến cáo người dùng ngay lập tức bật MFA trên instance ownCloud của họ để bảo vệ dữ liệu khỏi các cuộc tấn công trong tương lai và ngăn truy cập trái phép ngay cả khi thông tin đăng nhập bị xâm phạm.

Ngoài ra, ownCloud khuyến nghị đặt lại tất cả mật khẩu người dùng, vô hiệu hóa tất cả phiên hoạt động để buộc xác thực lại, và xem lại nhật ký truy cập để phát hiện hoạt động đăng nhập đáng ngờ.

Cảnh báo này xuất hiện sau khi một tác nhân đe dọa (được biết đến với tên Zestix) đã [rao bán dữ liệu doanh nghiệp](https://www.bleepingcomputer.com/news/security/cloud-file-sharing-sites-targeted-for-corporate-data-theft-attacks/) bị đánh cắp từ hàng chục công ty, có thể lấy được sau khi xâm nhập các instance ShareFile, Nextcloud, và ownCloud của họ.

Trong báo cáo ngày 5 tháng 1, Hudson Rock cho rằng kẻ tấn công có thể đã có được quyền truy cập ban đầu vào các máy chủ chia sẻ tập tin của các công ty bằng cách sử dụng thông tin đăng nhập bị đánh cắp bởi phần mềm infostealer như RedLine, Lumma, và Vidar, vốn đã lây nhiễm lên thiết bị của nhân viên.

Công ty tình báo tội phạm mạng này đã xác định được hàng nghìn máy tính bị nhiễm, bao gồm một số máy trên mạng của các tổ chức danh tiếng như Deloitte, KPMG, Samsung, Honeywell, Walmart, và U.S. CDC (Centers for Disease Control and Prevention).