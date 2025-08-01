# Các thiết bị tường lửa SonicWall bị tấn công trong làn sóng tấn công ransomware Akira

![SonicWall](https://www.bleepstatic.com/content/hl-images/2025/04/18/SonicWall.jpg)

Các thiết bị tường lửa SonicWall đã trở thành mục tiêu ngày càng tăng kể từ cuối tháng Bảy trong một làn sóng tấn công ransomware Akira, có khả năng khai thác một lỗ hổng bảo mật chưa được biết đến trước đó, theo công ty an ninh mạng Arctic Wolf.

Akira [xuất hiện](https://www.bleepingcomputer.com/news/security/meet-akira-a-new-ransomware-operation-targeting-the-enterprise/) vào tháng Ba năm 2023 và nhanh chóng đã gây ra nhiều nạn nhân trên toàn thế giới trong các ngành công nghiệp khác nhau. Trong hai năm qua, Akira đã bổ sung hơn 300 tổ chức vào cổng leak trên dark web của mình và đã nhận trách nhiệm về nhiều nạn nhân nổi tiếng, bao gồm Nissan ([Oceania](https://www.bleepingcomputer.com/news/security/nissan-confirms-ransomware-attack-exposed-data-of-100-000-people/) và [Australia](https://www.bleepingcomputer.com/news/security/nissan-australia-cyberattack-claimed-by-akira-ransomware-gang/)), [Hitachi](https://www.bleepingcomputer.com/news/security/hitachi-vantara-takes-servers-offline-after-akira-ransomware-attack/), và [Đại học Stanford](https://www.bleepingcomputer.com/news/security/stanford-data-of-27-000-people-stolen-in-september-ransomware-attack/).

FBI cho biết băng nhóm ransomware Akira đã thu được hơn 42 triệu USD từ các khoản thanh toán tiền chuộc tính đến tháng Tư năm 2024 từ [hơn 250 nạn nhân](https://www.bleepingcomputer.com/news/security/fbi-akira-ransomware-raked-in-42-million-from-250-plus-victims/).

Như Arctic Wolf Labs đã quan sát, nhiều cuộc xâm nhập ransomware đã liên quan đến việc truy cập trái phép qua các kết nối SonicWall SSL VPN, bắt đầu từ ngày 15 tháng Bảy. Tuy nhiên, trong khi một lỗ hổng zero-day đang bị khai thác trong các cuộc tấn công này là rất có thể, Arctic Wolf không loại trừ các cuộc tấn công dựa trên thông tin xác thực.

"Các phương pháp truy cập ban đầu chưa được xác nhận trong chiến dịch này," các nhà nghiên cứu của Arctic Wolf Labs đã cảnh báo. "Mặc dù khả năng tồn tại một lỗ hổng zero-day là rất có thể, việc truy cập thông tin xác thực thông qua brute force, dictionary attacks và credential stuffing vẫn chưa được loại trừ một cách dứt khoát trong tất cả các trường hợp."

Trong suốt làn sóng hoạt động ransomware này, kẻ tấn công đã nhanh chóng chuyển đổi từ việc truy cập mạng ban đầu thông qua các tài khoản SSL VPN sang mã hóa dữ liệu, một mẫu hình nhất quán với các cuộc tấn công tương tự được phát hiện từ ít nhất tháng Mười năm 2024, cho thấy một chiến dịch kéo dài nhắm vào các thiết bị SonicWall.

Ngoài ra, Arctic Wolf đã lưu ý rằng các nhà điều hành ransomware đã được quan sát sử dụng hosting máy chủ riêng ảo cho xác thực VPN, trong khi các kết nối VPN hợp pháp thường xuất phát từ nhà cung cấp dịch vụ Internet băng thông rộng.

Các nhà nghiên cứu bảo mật vẫn đang điều tra các phương pháp tấn công được sử dụng trong chiến dịch này và sẽ cung cấp thêm thông tin cho các nhà bảo vệ ngay khi có thông tin mới.

Do khả năng cao là một lỗ hổng zero-day của SonicWall đang bị khai thác trong môi trường thực, Arctic Wolf đã khuyến cáo các quản trị viên tạm thời vô hiệu hóa các dịch vụ SSL VPN của SonicWall. Ngoài ra, họ nên thực hiện các biện pháp bảo mật bổ sung, chẳng hạn như ghi log nâng cao, giám sát endpoint và chặn xác thực VPN từ các nhà cung cấp mạng liên quan đến hosting, cho đến khi có bản vá.

## Khuyến cáo quản trị viên bảo mật các thiết bị SMA 100

Báo cáo của Arctic Wolf xuất hiện một tuần sau khi [SonicWall cảnh báo khách hàng](https://www.bleepingcomputer.com/news/security/sonicwall-warns-of-critical-rce-flaw-in-sma-100-VPN-appliances/) phải cập nhật các thiết bị SMA 100 của họ trước một lỗ hổng bảo mật nghiêm trọng (CVE-2025-40599) có thể bị khai thác để thực hiện mã từ xa trên các thiết bị chưa được cập nhật.

Như công ty đã giải thích, mặc dù kẻ tấn công sẽ cần quyền quản trị để khai thác CVE-2025-40599, và không có bằng chứng cho thấy lỗ hổng này đang bị khai thác một cách chủ động, nhưng công ty vẫn kêu gọi các quản trị viên bảo mật các thiết bị SMA 100 của họ, vì chúng đã trở thành mục tiêu trong [các cuộc tấn công sử dụng thông tin xác thực bị xâm phạm](https://www.bleepingcomputer.com/news/security/sonicwall-sma-devices-hacked-with-overstep-rootkit-tied-to-ransomware/) để triển khai phần mềm độc hại OVERSTEP rootkit mới, theo các nhà nghiên cứu của Google Threat Intelligence Group (GTIG).

SonicWall 'mạnh mẽ' khuyến cáo các khách hàng sử dụng thiết bị SMA 100 ảo hoặc vật lý kiểm tra chúng xem có dấu hiệu bị xâm phạm (IoCs) từ báo cáo của GTIG bằng cách kiểm tra sự truy cập trái phép và xem xét các log của thiết bị và lịch sử kết nối để tìm kiếm hoạt động đáng ngờ. Nếu họ phát hiện bất kỳ bằng chứng nào về sự xâm phạm, các quản trị viên được khuyên nên ngay lập tức liên hệ với Bộ phận Hỗ trợ của SonicWall để được trợ giúp.

SonicWall cũng 'mạnh mẽ' khuyến cáo các khách hàng có thiết bị SMA 100 ảo hoặc vật lý kiểm tra dấu hiệu bị xâm phạm (IoCs) từ báo cáo của GTIG, gợi ý rằng các quản trị viên nên xem xét các log để tìm kiếm truy cập trái phép và bất kỳ hoạt động đáng ngờ nào và liên hệ ngay với Bộ phận Hỗ trợ của SonicWall nếu họ phát hiện bất kỳ bằng chứng nào về sự xâm phạm.

Một phát ngôn viên của SonicWall đã không ngay lập tức có mặt để bình luận khi được BleepingComputer liên hệ vào hôm nay.