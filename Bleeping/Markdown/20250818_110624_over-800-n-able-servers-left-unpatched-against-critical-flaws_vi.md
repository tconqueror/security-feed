# Hơn 800 máy chủ N-able không được cập nhật trước các lỗ hổng bảo mật nghiêm trọng

![N-able](https://www.bleepstatic.com/content/hl-images/2025/08/18/N-able.jpg)

Hơn 800 máy chủ N-central của N-able vẫn không được cập nhật trước một cặp lỗ hổng bảo mật nghiêm trọng đã được gán là đang bị khai thác tích cực vào tuần trước.

N-central là một nền tảng phổ biến được nhiều nhà cung cấp dịch vụ quản lý (MSP) và các phòng IT sử dụng để theo dõi và quản lý mạng cũng như thiết bị từ một bảng điều khiển dựa trên web trung tâm.

Hai lỗ hổng được theo dõi là [CVE-2025-8875](https://nvd.nist.gov/vuln/detail/CVE-2025-8875) và [CVE-2025-8876](https://nvd.nist.gov/vuln/detail/CVE-2025-8876), có thể cho phép những kẻ tấn công đã xác thực tiêm lệnh do không xử lý đúng dữ liệu đầu vào của người dùng và thực hiện các lệnh trên các thiết bị chưa được cập nhật bằng cách khai thác một lỗ hổng deserialization không an toàn, tương ứng.

N-able đã vá chúng trong N-central 2025.3.1 và thông báo cho BleepingComputer vào thứ Năm rằng các lỗ hổng bảo mật hiện đang bị khai thác tích cực, kêu gọi các quản trị viên bảo mật máy chủ của họ trước khi có thêm thông tin về các lỗi này được phát hành.

"Cuộc điều tra bảo mật của chúng tôi đã cho thấy bằng chứng về loại khai thác này trong một số lượng môi trường on-premises hạn chế. Chúng tôi chưa thấy bất kỳ bằng chứng nào về việc khai thác trong các môi trường đám mây do N-able cung cấp," N-able đã nói với BleepingComputer.

"Bạn phải nâng cấp N-central on-premises của mình lên 2025.3.1. (Chi tiết về các CVEs sẽ được công bố ba tuần sau khi phát hành theo quy trình bảo mật của chúng tôi)," [N-able đã thêm vào một thông báo vào thứ Tư](https://status.n-able.com/2025/08/13/announcing-the-ga-of-n-central-2025-3-1/).

Vào thứ Sáu, tổ chức phi lợi nhuận về an ninh mạng Shadowserver Foundation [đang theo dõi](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=7&source=http%5Fvulnerable&source=http%5Fvulnerable6&tag=cve-2025-8875%2B&tag=cve-2025-8876%2B&dataset=unique%5Fips&limit=100&group%5Fby=geo&stacking=stacked&auto%5Fupdate=on) 880 máy chủ N-central vẫn còn dễ bị tấn công khai thác hai lỗ hổng này, [đa phần chúng](https://bsky.app/profile/shadowserver.bsky.social/post/3lwm7agqrtc2e) nằm ở Hoa Kỳ, Canada và Hà Lan.

![N-able N-central servers left unpatched](https://www.bleepstatic.com/images/news/u/1109292/2025/Unpatched%20N-able%20N-central%20devices.png)

_Các máy chủ N-able N-central chưa được cập nhật (Shadowserver)_

"Những kết quả này đã được tính toán bằng cách cộng số lượng các địa chỉ IP duy nhất, có nghĩa là một địa chỉ IP 'duy nhất' có thể đã được đếm nhiều hơn một lần. Bất kỳ con số nào cũng nên được coi là chỉ mang tính chất tham khảo thay vì chính xác," Shadowserver nói.

Tổng cộng, khoảng 2.000 phiên bản N-central hiện đang được công khai trên mạng, theo [các tìm kiếm Shodan](https://beta.shodan.io/search?query=html%3An-central) [tìm kiếm](https://beta.shodan.io/search?query=http.html%5Fhash%3A944222210).

## Các cơ quan liên bang được yêu cầu giảm thiểu trong vòng một tuần

CISA cũng [đã thêm các lỗ hổng](https://www.cisa.gov/news-events/alerts/2025/08/13/cisa-adds-two-known-exploited-vulnerabilities-catalog) vào [Danh mục các lỗ hổng đã biết bị khai thác](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=SysAid&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=), gán chúng là bị khai thác trong các cuộc tấn công zero-day một ngày trước khi N-able xác nhận rằng các lỗ hổng này đang bị lạm dụng trên thực tế.

Cơ quan an ninh mạng của Hoa Kỳ đã ra lệnh cho tất cả các cơ quan Cơ quan Hành chính Dân sự Liên bang (FCEB), bao gồm Bộ An ninh Nội địa, Bộ Tài chính và Bộ Năng lượng, phải vá hệ thống của họ trong vòng một tuần, trước ngày 20 tháng 8, theo yêu cầu của Chỉ thị Điều hành Ràng buộc (BOD) 22-01 vào tháng 11 năm 2021.

Mặc dù các tổ chức phi chính phủ không bắt buộc phải hành động, vì BOD 22-01 chủ yếu nhắm đến các cơ quan liên bang của Hoa Kỳ, CISA đã kêu gọi tất cả các nhà bảo vệ mạng phải bảo mật các hệ thống của họ trước các cuộc tấn công đang diễn ra.

"Thực hiện các biện pháp giảm thiểu theo hướng dẫn của nhà cung cấp, tuân theo hướng dẫn BOD 22-01 áp dụng cho dịch vụ đám mây, hoặc ngừng sử dụng sản phẩm nếu không có biện pháp giảm thiểu," [CISA nói](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-8875&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=).

"Các loại lỗ hổng này thường là các vectơ tấn công cho các tác nhân độc hại và gây ra những rủi ro đáng kể cho cơ quan liên bang."