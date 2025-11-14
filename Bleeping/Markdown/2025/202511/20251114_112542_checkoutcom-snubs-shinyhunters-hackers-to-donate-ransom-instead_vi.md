# Checkout.com phớt lờ tin tặc sau vụ rò rỉ dữ liệu, sẽ quyên góp tiền chuộc thay vì trả

![Checkout](https://www.bleepstatic.com/content/hl-images/2021/12/15/credit-card.jpg)

Công ty công nghệ tài chính của Vương quốc Anh Checkout thông báo rằng nhóm tội phạm mạng ShinyHunters đã xâm nhập một trong những hệ thống lưu trữ đám mây kế thừa của họ và hiện đang tống tiền công ty bằng tiền chuộc.

Công ty cho biết mặc dù dữ liệu bị đánh cắp ảnh hưởng đến một phần đáng kể cơ sở thương gia của họ, họ sẽ không trả tiền chuộc mà thay vào đó sẽ đầu tư để tăng cường bảo mật.

Checkout vận hành _checkout.com_ và là một công ty xử lý thanh toán toàn cầu cung cấp một API thanh toán hợp nhất, các cổng thanh toán được lưu trữ, SDK di động và các plugin để sử dụng trên các nền tảng hiện có.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Nó hỗ trợ nhiều phương thức thanh toán khác nhau và có các tính năng phát hiện gian lận, xác minh danh tính (KYC), và cung cấp hệ thống giải quyết tranh chấp.

Hệ thống của họ được tích hợp vào một số doanh nghiệp lớn nhất thế giới, bao gồm eBay, Uber Eats, adidas, GE Healthcare, IKEA, Klarna, Pinterest, Alibaba, Shein, Sainsbury's, Sony, DocuSign, Samsung và HelloFresh, [xử lý doanh thu trị giá hàng tỷ](https://www.checkout.com/newsroom/checkout-com-surpasses-10-billion-in-revenue-unlocked-for-enterprise-merchants-using-ai-powered-boost).

Checkout cho biết ShinyHunters đã truy cập vào một hệ thống lưu trữ tệp đám mây bên thứ ba kế thừa mà chưa được ngừng sử dụng đúng cách, hệ thống này chứa dữ liệu thương gia từ năm 2020 và trước đó, bao gồm tài liệu vận hành nội bộ và tài liệu hướng dẫn onboarding.

"Tuần trước, Checkout.com đã được một nhóm tội phạm được biết đến với tên 'ShinyHunters' liên hệ, những người tuyên bố đã thu được dữ liệu liên quan đến Checkout.com và đòi tiền chuộc," [đọc thông báo của công ty](https://www.checkout.com/blog/protecting-our-merchants-standing-up-to-extortion).

"Qua điều tra, chúng tôi xác định dữ liệu này được lấy bằng cách có được quyền truy cập trái phép vào một hệ thống lưu trữ tệp đám mây bên thứ ba kế thừa, được sử dụng vào năm 2020 và các năm trước đó."

Checkout ước tính điều này ảnh hưởng đến dưới 25% cơ sở thương gia hiện tại của họ, nhưng mức lộ lọt còn lan tới cả khách hàng cũ.

ShinyHunters là một nhóm tội phạm mạng quốc tế chuyên trích xuất dữ liệu từ các tổ chức lớn, thường xâm nhập họ bằng cách lừa đảo, tấn công OAuth hoặc kỹ thuật xã hội, rồi sau đó đòi các khoản thanh toán lớn để không công khai dữ liệu.

Nhóm tội phạm này gần đây đã bị liên kết với [khai thác lỗ hổng zero-day của Oracle E-Business Suite](https://www.bleepingcomputer.com/news/security/oracle-silently-fixes-zero-day-exploit-leaked-by-shinyhunters/) (CVE-2025-61884), cũng như [các cuộc tấn công vào Salesforce/Drift](https://www.bleepingcomputer.com/news/security/shinyhunters-claims-15-billion-salesforce-records-stolen-in-drift-hacks/) đã ảnh hưởng đến [một số lượng lớn tổ chức](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/) vào đầu năm nay.

Checkout.com cho biết họ sẽ không trả tiền cho ShinyHunters và thay vào đó sẽ quyên góp số tiền tương ứng cho Carnegie Mellon University và University of Oxford Cyber Security Center để tài trợ các dự án nghiên cứu liên quan đến tội phạm mạng.

Đồng thời, công ty cam kết củng cố các biện pháp bảo mật và bảo vệ khách hàng tốt hơn trong tương lai.

Checkout.com không tiết lộ hệ thống lưu trữ tệp đám mây bên thứ ba nào đã bị xâm phạm hoặc phương pháp vi phạm.

BleepingComputer đã liên hệ với nhà cung cấp giải pháp thanh toán để tìm hiểu thêm, và chúng tôi sẽ bổ sung cập nhật khi nhận được phản hồi.