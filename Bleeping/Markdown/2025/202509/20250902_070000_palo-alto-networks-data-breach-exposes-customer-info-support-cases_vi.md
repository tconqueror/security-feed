# Palo Alto Networks data breach exposes customer info, support cases

![Palo Alto Networks](https://www.bleepstatic.com/content/hl-images/2024/10/09/Palo-Alto-Networks.jpg)

Palo Alto Networks đã chịu một vi phạm dữ liệu làm lộ thông tin khách hàng và các trường hợp hỗ trợ sau khi kẻ tấn công lợi dụng các OAuth token bị xâm phạm từ vụ vi phạm Salesloft Drift để truy cập vào instance Salesforce của công ty.

Công ty cho biết họ là một trong hàng trăm công ty bị ảnh hưởng bởi một [cuộc tấn công chuỗi cung ứng được tiết lộ tuần trước](https://www.bleepingcomputer.com/news/security/salesloft-breached-to-steal-oauth-tokens-for-salesforce-data-theft-attacks/), trong đó các tác nhân đe dọa lợi dụng các token xác thực bị đánh cắp để rút dữ liệu.

BleepingComputer biết về cuộc xâm phạm vào cuối tuần này từ các khách hàng của Palo Alto Networks, những người bày tỏ lo ngại rằng vụ xâm phạm đã tiết lộ thông tin nhạy cảm, chẳng hạn như thông tin IT và mật khẩu, được chia sẻ trong các trường hợp hỗ trợ.

Palo Alto Networks sau đó xác nhận với BleepingComputer rằng sự cố chỉ giới hạn trong Salesforce CRM của họ và không ảnh hưởng đến bất kỳ sản phẩm, hệ thống hoặc dịch vụ nào khác.

"Palo Alto Networks xác nhận rằng họ là một trong hàng trăm khách hàng bị ảnh hưởng bởi cuộc tấn công chuỗi cung ứng rộng lớn nhắm vào ứng dụng Salesloft Drift đã làm lộ dữ liệu Salesforce," Palo Alto Networks nói với BleepingComputer.

"Chúng tôi đã nhanh chóng kiềm chế sự cố và vô hiệu hóa ứng dụng khỏi môi trường Salesforce của mình. Cuộc điều tra của Unit 42 xác nhận rằng tình huống này không ảnh hưởng đến bất kỳ sản phẩm, hệ thống hoặc dịch vụ nào của Palo Alto Networks."

"Kẻ tấn công chủ yếu trích xuất thông tin liên hệ doanh nghiệp và thông tin tài khoản liên quan, cùng với các hồ sơ tài khoản bán hàng nội bộ và dữ liệu trường hợp cơ bản. Chúng tôi đang trong quá trình thông báo trực tiếp đến bất kỳ khách hàng nào bị ảnh hưởng."

Palo Alto Networks nói với BleepingComputer rằng dữ liệu trường hợp hỗ trợ bị rút chỉ chứa thông tin liên hệ và bình luận bằng văn bản, chứ không chứa các tệp hỗ trợ kỹ thuật hoặc tệp đính kèm.

Chiến dịch, lần đầu tiên [được đội Tình báo Mối đe dọa của Google theo dõi với tên UNC6395](https://www.bleepingcomputer.com/news/security/salesloft-breached-to-steal-oauth-tokens-for-salesforce-data-theft-attacks/), đã nhắm mục tiêu cụ thể vào các trường hợp hỗ trợ để xác định dữ liệu nhạy cảm, chẳng hạn như token xác thực, mật khẩu và bí mật đám mây, có thể được sử dụng để chuyển hướng vào các dịch vụ đám mây khác và đánh cắp dữ liệu.

"Các quan sát của chúng tôi cho thấy tác nhân đe dọa đã thực hiện việc rút dữ liệu nhạy cảm hàng loạt từ các đối tượng Salesforce khác nhau, bao gồm các bản ghi Account, Contact, Case và Opportunity," Palo Alto Networks cảnh báo trong [một bản tin về mối đe dọa](https://unit42.paloaltonetworks.com/threat-brief-compromised-salesforce-instances/) được chia sẻ với BleepingComputer.

"Sau khi rút dữ liệu, tác nhân dường như đã chủ động quét dữ liệu thu được để tìm kiếm thông tin xác thực, có khả năng với ý định tạo điều kiện cho các cuộc tấn công tiếp theo hoặc mở rộng mức truy cập. Chúng tôi đã quan sát thấy tác nhân đe dọa xóa các truy vấn để che giấu bằng chứng về các công việc họ chạy, có khả năng như một kỹ thuật chống pháp chứng."

Palo Alto Networks báo cáo rằng kẻ tấn công đã tìm kiếm các bí mật, bao gồm AWS access keys (AKIA), Snowflake tokens, chuỗi đăng nhập VPN và SSO, và các từ khóa chung như "password," "secret," hoặc "key."

Những thông tin xác thực này sau đó có thể được sử dụng để xâm phạm các nền tảng đám mây bổ sung nhằm đánh cắp dữ liệu cho các cuộc tống tiền.

Google và Palo Alto Networks cho biết rằng các tác nhân đe dọa đã sử dụng các công cụ tự động để đánh cắp dữ liệu, với các chuỗi user-agent cho thấy các công cụ Python tùy chỉnh đã được sử dụng:

```
python-requests/2.32.4

Python/3.11 aiohttp/3.12.15

Salesforce-Multi-Org-Fetcher/1.0

Salesforce-CLI/1.0
```

Trong một phần của các cuộc tấn công này, tác nhân đe dọa đã rút dữ liệu hàng loạt từ các đối tượng Salesforce Account, Contact, Case và Opportunity.

Để tránh bị phát hiện, tác nhân đe dọa đã xóa nhật ký và sử dụng Tor để làm mờ nguồn gốc của họ.

Palo Alto Networks cho biết họ đã thu hồi các token liên quan và thay đổi các thông tin xác thực sau sự cố.

Công ty khuyến nghị khách hàng Salesloft Drift coi sự cố là "khẩn cấp ngay lập tức" và thực hiện các hành động sau:

* Điều tra nhật ký Salesforce, nhà cung cấp danh tính và mạng để phát hiện khả năng bị xâm phạm.
* Xem xét tất cả các tích hợp Drift để tìm các kết nối đáng ngờ.
* Thu hồi và thay đổi các khóa xác thực, thông tin xác thực và bí mật.
* Sử dụng các công cụ tự động, như Trufflehog và Gitleaks, để quét kho mã nguồn tìm các khóa xác thực hoặc token được nhúng.
* Nếu dữ liệu được xác nhận đã bị rút, cần xem xét nó để tìm sự hiện diện của thông tin xác thực.

Palto Alto Networks, Salesforce, và Google hiện đã vô hiệu hóa các tích hợp Drift trong khi cuộc điều tra về cách các OAuth token bị đánh cắp vẫn đang tiếp tục.

Cuộc tấn công chuỗi cung ứng đã ảnh hưởng đến các công ty khác, bao gồm [Zscaler](https://www.bleepingcomputer.com/news/security/zscaler-data-breach-exposes-customer-info-after-salesloft-drift-compromise/) và [Google](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/).

## Salesforce data theft attacks

Kể từ đầu năm, [Salesforce đã trở thành mục tiêu của các cuộc tấn công đánh cắp dữ liệu](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/) do các thành viên liên quan đến nhóm tống tiền ShinyHunters thực hiện.

Trong các cuộc tấn công trước đây, các tác nhân đe dọa đã thực hiện lừa đảo thoại (vishing) để lừa nhân viên liên kết một ứng dụng OAuth độc hại với instance Salesforce của công ty họ.

Khi được liên kết, các tác nhân đe dọa đã sử dụng kết nối đó để tải xuống và đánh cắp cơ sở dữ liệu, sau đó dùng để tống tiền công ty thông qua email.

Tuy nhiên, với vụ vi phạm Salesloft, các tác nhân đe dọa có thể đánh cắp dữ liệu bằng cách sử dụng các OAuth token bị đánh cắp.

Kể từ khi [Google lần đầu tiên báo cáo các cuộc tấn công](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) vào tháng Sáu, nhiều vi phạm dữ liệu đã được liên kết với các cuộc tấn công xã hội hóa, bao gồm [Google itself](http://ogle-suffers-data-breach-in-ongoing-salesforce-data-theft-attacks/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), [Farmers Insurance](https://www.bleepingcomputer.com/news/security/farmers-insurance-data-breach-impacts-11m-people-after-salesforce-attack/), [Workday](https://www.bleepingcomputer.com/news/security/hr-giant-workday-discloses-data-breach-amid-salesforce-attacks/), [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/), và các chi nhánh của LVMH [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), và [Tiffany & Co.](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/)

Trong khi một số nhà nghiên cứu đã nói với BleepingComputer rằng họ tin rằng các cuộc tấn công chuỗi cung ứng Salesloft liên quan đến cùng một nhóm tác nhân đe dọa, Google nói rằng không có bằng chứng kết luận nào cho thấy chúng có liên quan.

"Chúng tôi chưa thấy bất kỳ bằng chứng thuyết phục nào kết nối chúng vào thời điểm này," Austin Larsen, Principal Threat Analyst. Google Threat Intelligence Group, nói với BleepingComputer.

_Cập nhật 9/2/25: Tiêu đề bài báo được cập nhật để phản ánh rằng vụ xâm phạm không chứa toàn bộ phiếu hỗ trợ._