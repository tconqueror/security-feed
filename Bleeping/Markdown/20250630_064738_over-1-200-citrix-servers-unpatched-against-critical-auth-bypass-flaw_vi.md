# Hơn 1,200 máy chủ Citrix chưa được vá đối với lỗ hổng bỏ qua xác thực nghiêm trọng

![Citrix](https://www.bleepstatic.com/content/hl-images/2023/07/20/Citrix-headpic.jpg)

Hơn 1,200 thiết bị Citrix NetScaler ADC và NetScaler Gateway được phơi bày trực tuyến chưa được vá đối với một lỗ hổng nghiêm trọng được tin là đang bị khai thác tích cực, cho phép kẻ tấn công bỏ qua xác thực bằng cách chiếm đoạt phiên người dùng.

Được theo dõi là CVE-2025-5777 và được gọi là Citrix Bleed 2, lỗ hổng đọc bộ nhớ ngoài phạm vi này là kết quả của việc kiểm tra đầu vào không đủ, cho phép những kẻ tấn công không xác thực truy cập vào các khu vực bộ nhớ hạn chế.

Một lỗ hổng bảo mật Citrix tương tự, được gọi là "CitrixBleed," đã được khai thác trong các [cuộc tấn công ransomware](https://www.bleepingcomputer.com/news/security/lockbit-ransomware-exploits-citrix-bleed-in-attacks-10k-servers-exposed/) và [các vụ vi phạm nhắm vào chính phủ](https://www.bleepingcomputer.com/news/security/hackers-use-citrix-bleed-flaw-in-attacks-on-govt-networks-worldwide/) vào năm 2023 để hack các thiết bị NetScaler và di chuyển theo chiều ngang qua các mạng bị xâm phạm.

Việc khai thác thành công CVE-2025-5777 có thể cho phép các kẻ tấn công đánh cắp mã thông báo phiên, thông tin xác thực và dữ liệu nhạy cảm khác từ các cổng và máy chủ ảo trung gian công khai, cho phép họ [chiếm đoạt phiên người dùng](https://www.bleepingcomputer.com/news/security/new-citrixbleed-2-netscaler-flaw-let-hackers-hijack-sessions/) và bỏ qua xác thực đa yếu tố (MFA).

Trong một thông báo ngày 17 tháng 6, Citrix đã [cảnh báo](https://support.citrix.com/support-home/kbsearch/article?articleNumber=CTX693420) khách hàng ngừng tất cả các phiên ICA và PCoIP đang hoạt động sau khi nâng cấp tất cả các thiết bị NetScaler của họ lên phiên bản đã được vá để chặn các cuộc tấn công tiềm năng.

Vào thứ Hai, các nhà phân tích bảo mật từ tổ chức phi lợi nhuận Shadowserver Foundation [đã phát hiện](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=other%5Frange&d1=2025-06-17&d2=2025-06-29&source=http%5Fvulnerable&source=http%5Fvulnerable6&tag=cve-2025-5777%2B&dataset=unique%5Fips&limit=100&group%5Fby=tag&stacking=overlap&auto%5Fupdate=on) vào cuối tuần qua rằng 2,100 thiết bị vẫn còn dễ bị tấn công bằng CVE-2025-5777.

![CVE-2025-5777 exposure Shadowserver](https://www.bleepstatic.com/images/news/u/1109292/2025/CVE-2025-5777_exposure_Shadowserver.png)

_Các thiết bị NetScaler chưa được vá phơi bày trực tuyến (Shadowserver)_

Trong khi Citrix vẫn chưa xác nhận rằng lỗ hổng bảo mật này đang bị khai thác ở các môi trường hoạt động, [nói](https://www.netscaler.com/blog/news/netscaler-critical-security-updates-for-cve-2025-6543-and-cve-2025-5777/) rằng "hiện tại không có bằng chứng nào cho thấy lỗ hổng CVE-2025-5777 đã bị khai thác," công ty an ninh mạng ReliaQuest đã báo cáo hôm thứ Năm với sự tự tin ở mức trung bình rằng lỗ hổng này đã bị lạm dụng trong các cuộc tấn công có mục tiêu.

"Mặc dù chưa có khai thác công khai nào cho CVE-2025-5777, được gọi là 'Citrix Bleed 2,' đã được báo cáo, ReliaQuest đánh giá với sự tự tin ở mức trung bình rằng các kẻ tấn công đang tích cực khai thác lỗ hổng này để có được quyền truy cập ban đầu vào các môi trường có mục tiêu," [ReliaQuest đã cảnh báo](https://www.bleepingcomputer.com/news/security/citrix-bleed-2-flaw-now-believed-to-be-exploited-in-attacks/).

ReliaQuest xác định các chỉ số cho thấy hoạt động sau khai thác sau khi truy cập trái phép vào Citrix, bao gồm một phiên web Citrix bị chiếm đoạt cho thấy một nỗ lực bỏ qua MFA thành công, tái sử dụng phiên trên nhiều địa chỉ IP (bao gồm những địa chỉ nghi ngờ), và các truy vấn LDAP liên quan đến các hoạt động nhận dạng Active Directory.

Shadowserver cũng [đã tìm thấy](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=other%5Frange&d1=2025-06-17&d2=2025-06-29&source=http%5Fvulnerable&source=http%5Fvulnerable6&tag=cve-2025-6543%2B&dataset=unique%5Fips&limit=100&group%5Fby=tag&stacking=overlap&auto%5Fupdate=on) hơn 2,100 thiết bị NetScaler chưa được vá đối với một lỗ hổng nghiêm trọng khác (CVE-2025-6543), hiện đang bị [khai thác trong các cuộc tấn công từ chối dịch vụ (DoS)](https://www.bleepingcomputer.com/news/security/citrix-warns-of-netscaler-vulnerability-exploited-in-dos-attacks/).

Với cả hai lỗ hổng đều được phân loại là lỗ hổng nghiêm trọng, các quản trị viên nên triển khai bản vá mới nhất từ Citrix càng sớm càng tốt. Các công ty cũng nên xem xét lại các kiểm soát truy cập của họ và theo dõi các thiết bị Citrix NetScaler để phát hiện các phiên và hoạt động người dùng đáng ngờ.