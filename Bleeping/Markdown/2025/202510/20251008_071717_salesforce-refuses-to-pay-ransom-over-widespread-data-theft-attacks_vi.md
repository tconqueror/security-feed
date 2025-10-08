# Salesforce từ chối trả tiền chuộc sau các vụ đánh cắp dữ liệu quy mô lớn

![Salesforce](https://www.bleepstatic.com/content/hl-images/2025/10/07/salesforce-red.jpg)

Salesforce đã xác nhận rằng họ sẽ không thương lượng hoặc trả tiền chuộc cho các tác nhân đe dọa đứng sau một làn sóng đánh cắp dữ liệu lớn đã ảnh hưởng đến khách hàng của công ty trong năm nay.

Như đã được [Bloomberg](https://www.bloomberg.com/news/articles/2025-10-07/salesforce-tells-clients-it-won-t-pay-hackers-for-data-extortion) đưa tin lần đầu, Salesforce đã gửi email cho khách hàng vào thứ Ba để thông báo họ sẽ không trả tiền chuộc và cảnh báo rằng "thông tin tình báo mối đe dọa đáng tin cậy" chỉ ra các tác nhân đe dọa đang lên kế hoạch rò rỉ dữ liệu bị đánh cắp.

"Chúng tôi có thể xác nhận Salesforce sẽ không tham gia, thương lượng với, hoặc trả bất kỳ yêu cầu tống tiền nào," Salesforce cũng xác nhận với BleepingComputer.

Tuyên bố này xuất hiện sau khi một trang rò rỉ dữ liệu được khởi chạy bởi các tác nhân đe dọa được biết đến dưới tên "Scattered Lapsus$ Hunters," [những người đang cố gắng tống tiền 39 công ty](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/) có dữ liệu bị đánh cắp từ Salesforce. Trang web được đặt trên tên miền breachforums[.\]hn, tên này lấy cảm hứng từ trang BreachForums khét tiếng, một diễn đàn hacker nổi tiếng vì bán và rò rỉ dữ liệu bị đánh cắp.

Các công ty bị tống tiền trên trang rò rỉ dữ liệu bao gồm các thương hiệu và tổ chức nổi tiếng, bao gồm FedEx, Disney/Hulu, Home Depot, Marriott, Google, Cisco, Toyota, Gap, Kering, McDonald's, Walgreens, Instacart, Cartier, Adidas, Sake Fifth Avenue, Air France & KLM, Transunion, HBO MAX, UPS, Chanel và IKEA.

Tổng cộng, các tác nhân đe dọa tuyên bố đã đánh cắp gần 1 tỷ bản ghi dữ liệu, sẽ được công bố công khai nếu một yêu cầu tống tiền được trả bởi từng công ty riêng lẻ hoặc như một khoản thanh toán duy nhất từ Salesforce để bao phủ tất cả khách hàng bị ảnh hưởng được liệt kê trên trang.

![ShinyHunters Salesforce data leak site](https://www.bleepstatic.com/images/news/u/1109292/2025/ShinyHunters_Salesforce_leaks.png)

**ShinyHunters Salesforce - trang rò rỉ dữ liệu**  
_Nguồn: BleepingComputer_

Dữ liệu này đã bị đánh cắp từ các instance Salesforce trong hai chiến dịch riêng biệt diễn ra vào năm 2025.

Chiến dịch đánh cắp dữ liệu đầu tiên bắt đầu vào cuối năm 2024, khi các tác nhân đe dọa bắt đầu [thực hiện các cuộc tấn công lừa đảo xã hội](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/) giả danh nhân viên hỗ trợ IT để lừa nhân viên kết nối một ứng dụng OAuth độc hại với instance Salesforce của công ty họ.

Khi được liên kết, các tác nhân đe dọa đã sử dụng kết nối đó để tải xuống và đánh cắp cơ sở dữ liệu, sau đó sử dụng chúng để tống tiền công ty thông qua email.

Các cuộc tấn công lừa đảo xã hội này đã ảnh hưởng đến Google, Cisco, Qantas, Adidas, Allianz Life, Farmers Insurance, Workday, Kering, và các công ty con của LVMH, chẳng hạn như Dior, Louis Vuitton và Tiffany & Co.

Một chiến dịch đánh cắp dữ liệu Salesforce thứ hai bắt đầu vào đầu tháng Tám năm 2025, khi các tác nhân đe dọa sử dụng [các token OAuth SalesLoft Drift bị đánh cắp](https://www.bleepingcomputer.com/news/security/salesloft-breached-to-steal-oauth-tokens-for-salesforce-data-theft-attacks/) để pivot vào môi trường CRM của khách hàng và trích xuất dữ liệu.

Các cuộc tấn công đánh cắp dữ liệu từ Salesloft chủ yếu tập trung vào việc đánh cắp dữ liệu ticket hỗ trợ để quét tìm thông tin đăng nhập, token API, token xác thực và các thông tin nhạy cảm khác có thể cho phép kẻ tấn công xâm nhập vào hạ tầng và dịch vụ đám mây của công ty.

Một trong các tác nhân đe dọa đứng sau các cuộc tấn công Salesloft, được biết đến với tên ShinyHunters, nói với BleepingComputer rằng họ đã đánh cắp khoảng 1.5 tỷ bản ghi dữ liệu cho hơn 760 công ty trong chiến dịch này.

Nhiều công ty đã xác nhận họ bị ảnh hưởng bởi cuộc tấn công chuỗi cung ứng Salesloft, bao gồm Google, Cloudflare, Zscaler, Tenable, CyberArk, Elastic, BeyondTrust, Proofpoint, JFrog, Nutanix, Qualys, Rubrik, Cato Networks, Palo Alto Networks, và nhiều công ty khác.

Trang rò rỉ dữ liệu vừa được khởi chạy chủ yếu được sử dụng để tống tiền các khách hàng trong các cuộc tấn công lừa đảo xã hội ban đầu, với các tác nhân đe dọa tuyên bố họ sẽ bắt đầu tống tiền công khai những người bị ảnh hưởng bởi các cuộc tấn công Salesloft sau ngày 10 tháng Mười.

Tuy nhiên, trang rò rỉ dữ liệu hiện đã bị đóng, với tên miền hiện sử dụng nameserver surina.ns.cloudflare.com và hans.ns.cloudflare.com, cả hai [đã từng được FBI sử dụng trong quá khứ](https://www.justice.gov/d9/2024-07/affidavit%5Ffor%5Ftwo%5Fdomains.pdf) khi thu giữ tên miền.

BleepingComputer đã liên hệ với FBI để hỏi xem họ có thu giữ tên miền hay không nhưng chưa nhận được phản hồi vào thời điểm này.