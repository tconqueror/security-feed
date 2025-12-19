# Lỗ hổng UEFI mới cho phép tấn công trước khi khởi động trên bo mạch chủ của Gigabyte, MSI, ASUS, ASRock

![Lỗ hổng UEFI mới cho phép tấn công trước khi khởi động trên bo mạch chủ của Gigabyte, MSI, ASUS, ASRock](https://www.bleepstatic.com/content/hl-images/2022/06/02/cpu-motherboard.jpg)

Việc triển khai firmware UEFI trên một số bo mạch chủ từ ASUS, Gigabyte, MSI và ASRock có thể bị tấn công direct memory access (DMA) cho phép bỏ qua các cơ chế bảo vệ bộ nhớ ở giai đoạn khởi động ban đầu.

Vấn đề bảo mật đã nhận được nhiều mã định danh (CVE-2025-11901, CVE-2025‑14302, CVE-2025-14303, và CVE-2025-14304) do khác biệt trong cách triển khai của từng nhà sản xuất.

DMA là một tính năng phần cứng cho phép các thiết bị như card đồ họa, thiết bị Thunderbolt và thiết bị PCIe đọc và ghi trực tiếp vào RAM mà không cần thông qua CPU.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

IOMMU là một tường lửa bộ nhớ được thực thi bằng phần cứng nằm giữa các thiết bị và RAM, kiểm soát những vùng bộ nhớ nào có thể truy cập cho từng thiết bị.

Trong giai đoạn khởi động sớm, khi firmware UEFI khởi tạo, IOMMU phải được kích hoạt trước khi các cuộc tấn công DMA có thể xảy ra; nếu không, sẽ không có cơ chế bảo vệ để ngăn việc đọc hoặc ghi lên các vùng bộ nhớ thông qua truy cập vật lý.

### Valorant không khởi chạy trên các hệ thống dễ bị tấn công

Lỗ hổng được phát hiện bởi các nhà nghiên cứu của Riot Games là Nick Peterson và Mohamed Al-Sharifi. Nó khiến firmware UEFI hiển thị rằng bảo vệ DMA đã được bật ngay cả khi IOMMU không khởi tạo đúng cách, khiến hệ thống bị lộ trước các cuộc tấn công.

Peterson và Al-Sharifi đã tiết lộ vấn đề một cách có trách nhiệm và làm việc với [CERT](https://tinyurl.com/twcert)[ Taiwan](https://www.twcert.org.tw/en/lp-139-2.html) để phối hợp phản ứng và liên hệ các nhà cung cấp bị ảnh hưởng.

Các nhà nghiên cứu [giải thích](https://www.riotgames.com/en/news/vanguard-security-update-motherboard) rằng khi một hệ thống máy tính được bật, nó đang ở "trạng thái có đặc quyền cao nhất: nó có quyền truy cập đầy đủ, không giới hạn tới toàn bộ hệ thống và tất cả phần cứng được kết nối."

Các cơ chế bảo vệ chỉ trở nên khả dụng sau khi nạp firmware ban đầu, thường là UEFI, cái mà khởi tạo phần cứng và phần mềm theo cách an toàn. Hệ điều hành là một trong những thành phần được tải cuối cùng trong chuỗi khởi động.

Trên các hệ thống dễ bị tấn công, một số tựa game của Riot Games, chẳng hạn như Valorant phổ biến, sẽ không khởi chạy. Điều này là do hệ thống Vanguard hoạt động ở cấp kernel để bảo vệ chống gian lận.

"Nếu một phần mềm gian lận được tải trước chúng tôi, nó có cơ hội tốt hơn để ẩn nơi chúng tôi không thể tìm thấy. Điều này tạo cơ hội cho phần mềm gian lận cố gắng không bị phát hiện, gây rối trong trò chơi của bạn lâu hơn mức chúng tôi chấp nhận được" - [Riot Games](https://www.riotgames.com/en/news/vanguard-security-update-motherboard)

Mặc dù các nhà nghiên cứu mô tả lỗ hổng từ góc nhìn của ngành công nghiệp trò chơi, nơi các phần mềm gian lận có thể được tải sớm, rủi ro bảo mật mở rộng đến mã độc có thể làm xâm phạm hệ điều hành.

Các cuộc tấn công đòi hỏi truy cập vật lý, nơi một thiết bị PCIe độc hại cần được kết nối để thực hiện tấn công DMA trước khi hệ điều hành khởi động. Trong thời gian đó, thiết bị xấu có thể đọc hoặc sửa đổi RAM một cách tự do.

"Ngay cả khi firmware khẳng định rằng các bảo vệ DMA đang hoạt động, nó vẫn không cấu hình và kích hoạt IOMMU đúng cách trong giai đoạn chuyển giao sớm của chuỗi khởi động," theo [thông báo](https://www.kb.cert.org/vuls/id/382314) từ Carnegie Mellon CERT Coordination Center (CERT/CC).

"Khe hở này cho phép một thiết bị Peripheral Component Interconnect Express (PCIe) có khả năng DMA độc hại với truy cập vật lý đọc hoặc sửa đổi bộ nhớ hệ thống trước khi các biện pháp bảo vệ ở cấp hệ điều hành được thiết lập."

Do việc khai thác xảy ra trước khi hệ điều hành khởi động, sẽ không có cảnh báo từ các công cụ bảo mật, không có lời nhắc yêu cầu quyền và không có cảnh báo để thông báo cho người dùng.

## Phạm vi ảnh hưởng rộng được xác nhận

Carnegie Mellon CERT/CC xác nhận rằng lỗ hổng ảnh hưởng một số mẫu bo mạch chủ từ ASRock, ASUS, GIGABYTE và MSI, nhưng các sản phẩm từ các nhà sản xuất phần cứng khác cũng có thể bị ảnh hưởng.

Các mẫu cụ thể bị ảnh hưởng cho từng nhà sản xuất được liệt kê trong các bản tin bảo mật và bản cập nhật firmware từ các nhà sản xuất ([ASUS](https://www.asus.com/security-advisory/), [MSI](https://csr.msi.com/global/product-security-advisories), [Gigabyte](https://www.gigabyte.com/Support/Security?type=1), [ASRock](https://www.asrock.com/support/Security.asp)).

Người dùng được khuyến nghị kiểm tra các bản cập nhật firmware có sẵn và cài đặt chúng sau khi sao lưu dữ liệu quan trọng.

Riot Games đã cập nhật Vanguard, hệ thống chống gian lận ở cấp kernel cung cấp bảo vệ chống bot và script trong các trò chơi như Valorant và League of Legends.

Nếu một hệ thống bị ảnh hưởng bởi lỗ hổng UEFI, Vannguard sẽ chặn Valorant không cho khởi chạy và hiển thị một cửa sổ bật lên cung cấp chi tiết về những gì cần thiết để bắt đầu trò chơi.

"Hệ thống VAN:Restriction của chúng tôi là cách Vanguard thông báo cho bạn rằng chúng tôi không thể đảm bảo tính toàn vẹn hệ thống do các tính năng bảo mật được nêu đã bị vô hiệu hóa," các nhà nghiên cứu của Riot Games nói.