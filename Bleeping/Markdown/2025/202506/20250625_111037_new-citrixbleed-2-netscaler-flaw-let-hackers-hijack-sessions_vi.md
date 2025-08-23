# Lỗ hổng ‘CitrixBleed 2’ mới trên NetScaler cho phép tin tặc chiếm đoạt phiên

![Citrix](https://www.bleepstatic.com/content/hl-images/2023/10/25/citrix-bleed.jpg)

Một lỗ hổng mới trong Citrix NetScaler ADC và Gateway được gọi là "CitrixBleed 2," do sự tương đồng của nó với một lỗ hổng cũ đã bị khai thác cho phép kẻ tấn công không xác thực chiếm đoạt cookie phiên xác thực từ các thiết bị dễ bị tấn công.

Tuần trước, Citrix đã công bố một [thông báo bảo mật](https://support.citrix.com/support-home/kbsearch/article?articleNumber=CTX693420) cảnh báo về các lỗ hỏng được theo dõi với mã CVE-2025-5777 và CVE-2025-5349 ảnh hưởng đến các phiên bản NetScaler ADC và Gateway trước 14.1-43.56, các bản phát hành trước 13.1-58.32, và cả 13.1-37.235-FIPS/NDcPP và 2.1-55.328-FIPS.

CVE-2025-5777 là một lỗ hổng nghiêm trọng do lỗi đọc bộ nhớ ngoài giới hạn, cho phép các cuộc tấn công không xác thực truy cập vào các phần bộ nhớ mà họ không nên có quyền truy cập.

Lỗ hổng này ảnh hưởng đến các thiết bị NetScaler được cấu hình như một Gateway (máy chủ ảo VPN, ICA Proxy, Clientless VPN (CVPN), RDP Proxy) hoặc máy chủ ảo AAA.

Nhà nghiên cứu an ninh mạng [Kevin Beaumont cho biết](https://doublepulsar.com/citrixbleed-2-electric-boogaloo-cve-2025-5777-c7f5e349d206) lỗ hổng này tương tự như lỗ hổng '[CitrixBleed](https://www.bleepingcomputer.com/news/security/citrix-bleed-exploit-lets-hackers-hijack-netscaler-accounts/)' nổi tiếng (CVE-2023-4966), đã bị khai thác rộng rãi bởi các tác nhân đe dọa, bao gồm cả [ransomware](https://www.bleepingcomputer.com/news/security/lockbit-ransomware-exploits-citrix-bleed-in-attacks-10k-servers-exposed/) và [các cuộc tấn công chính phủ](https://www.bleepingcomputer.com/news/security/hackers-use-citrix-bleed-flaw-in-attacks-on-govt-networks-worldwide/).

Beaumont đã nhận định CVE-2025-5777 là '[CitrixBleed 2](https://doublepulsar.com/citrixbleed-2-electric-boogaloo-cve-2025-5777-c7f5e349d206),' cho rằng lỗ hổng này có thể cho phép kẻ tấn công truy cập vào các token phiên, thông tin xác thực và dữ liệu nhạy cảm khác từ các cổng và máy chủ ảo công khai.

Các token bị rò rỉ có thể bị phát lại để chiếm đoạt phiên người dùng và vượt qua xác thực đa yếu tố (MFA).

Thông báo bảo mật cùng liệt kê một lỗ hổng nghiêm trọng thứ hai được theo dõi là CVE-2025-5349.

Đây là một vấn đề kiểm soát truy cập không đúng cách trong Giao diện Quản lý NetScaler, có thể bị khai thác nếu kẻ tấn công có quyền truy cập vào NSIP (Địa chỉ IP Quản lý NetScaler), Cluster Management IP hoặc Local GSLB Site IP.

Để khắc phục cả hai rủi ro, người dùng được khuyến nghị cài đặt DC và NetScaler Gateway 14.1-43.56, 13.1-58.32 trở lên, 13.1-NDcPP 13.1-37.235 (FIPS), và 12.1-55.328 (FIPS).

Mặc dù Citrix chưa xác định liệu các lỗ hổng này có đang bị khai thác tích cực hay không, họ khuyến nghị rằng các quản trị viên nên kết thúc tất cả các phiên ICA và PCoIP đang hoạt động ngay khi tất cả các thiết bị đã được cập nhật. Lời khuyên này cũng đã được Citrix đưa ra liên quan đến các lỗ hổng CitrixBleed ban đầu.

Trước khi kết thúc các phiên hoạt động, các quản trị viên nên xem xét các phiên hiện có để tìm hoạt động đáng ngờ bằng cách sử dụng lệnh `show icaconnection` và **NetScaler Gateway** \> **PCoIP** \> **Connections** để xem các phiên PCoIP.

Sau khi xem xét các phiên hoạt động, các quản trị viên nên kết thúc chúng bằng cách sử dụng các lệnh sau:

```
kill icaconnection -all
kill pcoipconnection -all
```

Trong một [bài đăng LinkedIn](http://www.linkedin.com/posts/charlescarmakal%5Fcritical-alert-multiple-critical-vulnerabilities-activity-7343669191331262464-v0i2?utm%5Fsource=share&utm%5Fmedium=member%5Fdesktop&rcm=ACoAAAI-3eQB8RXQZlUx64%5F6arOKR8IFUX8Mj5k), Giám đốc công nghệ Mandiant Charles Carmakal cảnh báo rằng việc kết thúc các phiên sau khi cập nhật thiết bị là rất quan trọng để ngăn chặn việc sử dụng các phiên đã bị đánh cắp trước đó ngay cả khi các thiết bị không còn dễ bị tổn thương.

"Nhiều tổ chức đã không kết thúc các phiên khi khắc phục một lỗ hổng tương tự vào năm 2023 (CVE-2023-4966 hay 'Citrix Bleed')," Carmakal cảnh báo.

"Trong những trường hợp đó, bí mật phiên đã bị đánh cắp trước khi các công ty vá lỗ hổng, và các phiên đã bị chiếm đoạt sau khi vá. Nhiều vụ xâm phạm trong số đó đã dẫn đến gián điệp của các quốc gia hoặc triển khai ransomware."

Các lỗ hổng này cũng ảnh hưởng đến ADC / Gateway 12.1 (không phải FIPS) và ADC / Gateway 13.0 đã hết hạn sử dụng, sẽ không nhận được bản vá. Những ai vẫn sử dụng các phiên bản này nên nâng cấp lên bản phát hành đang được hỗ trợ càng sớm càng tốt.

Các quét trên internet của Beaumont trả về hơn 56,500 điểm cuối NetScaler ADC và Gateway bị lộ công khai, tuy nhiên không rõ tỷ lệ phần trăm trong số đó đang sử dụng các phiên bản dễ bị tổn thương với CVE-2025-5349 và CVE-2025-5777 là bao nhiêu.