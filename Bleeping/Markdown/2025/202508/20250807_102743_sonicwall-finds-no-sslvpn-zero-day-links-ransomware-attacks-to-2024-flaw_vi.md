# SonicWall không tìm thấy lỗ hổng zero-day SSLVPN, liên kết các cuộc tấn công ransomware với lỗ hổng năm 2024

![Sonicwall](https://www.bleepstatic.com/content/hl-images/2022/05/13/SonicWall_headpic.jpeg)

SonicWall cho biết rằng các cuộc tấn công ransomware gần đây của Akira khai thác các tường lửa Gen 7 với SSLVPN được bật đang khai thác một lỗ hổng cũ hơn thay vì một lỗ hổng zero-day.

Công ty cho biết rằng các kẻ tấn công đang nhắm đến CVE-2024-40766, một lỗ hổng truy cập trái phép đã được sửa vào tháng 8 năm 2024.

"Chúng tôi hiện có độ tin cậy cao rằng hoạt động SSLVPN gần đây không liên quan đến một lỗ hổng zero-day," đọc cập nhật trên thông báo của SonicWall được công bố trong tuần này.

"Thay vào đó, có một mối tương quan đáng kể với hoạt động mối đe dọa liên quan đến CVE-2024-40766, đã được công bố và ghi nhận trong thông báo công khai của chúng tôi [SNWLID-2024-0015](https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2024-0015)."

CVE‑2024‑40766 là một [lỗ hổng kiểm soát truy cập SSLVPN](https://www.bleepingcomputer.com/news/security/sonicwall-warns-of-critical-access-control-flaw-in-sonicos/) nghiêm trọng trong SonicOS, cho phép truy cập trái phép vào các điểm cuối dễ bị tổn thương, cho phép các kẻ tấn công chiếm đoạt phiên hoặc có được quyền truy cập VPN trong các môi trường đã được bảo vệ.

Lỗi này đã được [khai thác một cách rộng rãi](https://www.bleepingcomputer.com/news/security/sonicwall-sslvpn-access-control-flaw-is-now-exploited-in-attacks/) sau khi nó được công bố cách đây khoảng một năm, bao gồm cả các nhà điều hành [Akira](https://www.bleepingcomputer.com/news/security/critical-sonicwall-sslvpn-bug-exploited-in-ransomware-attacks/) và [Fog ransomware](https://www.bleepingcomputer.com/news/security/fog-ransomware-targets-sonicwall-vpns-to-breach-corporate-networks/) đã tận dụng nó để xâm nhập vào các mạng công ty.

Vào thứ Sáu, Arctic Wolf Labs lần đầu tiên gợi ý về sự tồn tại tiềm ẩn của một lỗ hổng zero-day trong các tường lửa SonicWall Gen 7, sau khi nhận thấy các mẫu tấn công của ransomware Akira hỗ trợ giả thuyết này.

SonicWall nhanh chóng xác nhận rằng họ nhận thức được một chiến dịch đang diễn ra, và [khuyên khách hàng](https://www.bleepingcomputer.com/news/security/sonicwall-urges-admins-to-disable-sslvpn-amid-rising-attacks/) nên tắt dịch vụ SSL VPN và hạn chế kết nối chỉ đến các địa chỉ IP được tin cậy cho đến khi tình hình được giải quyết.

Sau khi điều tra nội bộ về 40 sự cố, nhà cung cấp hiện tại phủ nhận khả năng các kẻ tấn công khai thác một lỗ hổng zero-day trong sản phẩm của mình.

Thay vào đó, SonicWall cho biết các cuộc tấn công của Akira nhắm vào các điểm cuối không làm theo các hành động khuyến nghị để giảm thiểu CVE-2024-40766 khi di chuyển từ tường lửa Gen 6 sang Gen 7.

"Nhiều sự cố liên quan đến việc di chuyển từ tường lửa Gen 6 sang Gen 7, nơi mà các mật khẩu người dùng địa phương đã được chuyển giao trong quá trình di chuyển và không được đặt lại," [giải thích SonicWall](https://www.sonicwall.com/support/notices/gen-7-and-newer-sonicwall-firewalls-sslvpn-recent-threat-activity/250804095336430).

"Đặt lại mật khẩu là một bước quan trọng được nêu trong thông báo ban đầu."

Hành động được khuyến nghị hiện nay là cập nhật firmware lên phiên bản 7.3.0 hoặc mới hơn, có các bảo vệ phương pháp tấn công brute-force và MFA mạnh mẽ hơn, và đặt lại tất cả các mật khẩu người dùng địa phương, đặc biệt là những mật khẩu được sử dụng cho SSLVPN.

Khi SonicWall cũng đã gửi email cho khách hàng cập nhật mới nhất, nhiều người [đã lên Reddit](https://www.reddit.com/r/msp/comments/1mjk7k7/sonicwall%5Fwalks%5Fback%5Fzero%5Fday%5Fnotice%5Fon%5Fsslvpn/) để bày tỏ sự nghi ngờ về độ chính xác của các tuyên bố của nhà cung cấp, cho biết rằng không phải mọi thứ trong đó đều khớp với trải nghiệm của họ.

Một số người [đã lưu ý](https://www.reddit.com/r/sonicwall/comments/1mjin7r/sonicwall%5Fzeroday%5Fupdate%5F230pm%5F86/) rằng họ đã có các vụ vi phạm trên các tài khoản không tồn tại trước khi di chuyển sang các tường lửa Gen 7, và thậm chí còn tuyên bố rằng SonicWall từ chối kiểm tra các nhật ký của họ.

Những báo cáo mâu thuẫn này, kết hợp với ngôn từ không rõ ràng mà SonicWall đã sử dụng trong cập nhật của mình, để lại chỗ cho sự không chắc chắn, vì vậy sự cảnh giác và việc áp dụng ngay lập tức các biện pháp được khuyến nghị vẫn rất quan trọng.