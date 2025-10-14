# Rủi ro vượt qua Secure Boot trên gần 200.000 hệ thống Linux Framework

![Rủi ro vượt qua Secure Boot trên gần 200.000 hệ thống Linux Framework](https://www.bleepstatic.com/content/hl-images/2025/10/14/framework.jpg)

Khoảng 200.000 máy tính chạy Linux từ nhà sản xuất máy tính Mỹ Framework được xuất xưởng kèm các thành phần shell UEFI đã được ký mà có thể bị lợi dụng để vượt qua cơ chế bảo vệ Secure Boot.

Kẻ tấn công có thể lợi dụng điều này để tải các bootkit (ví dụ [BlackLotus](https://www.bleepingcomputer.com/news/security/blacklotus-bootkit-bypasses-uefi-secure-boot-on-patched-windows-11/), [HybridPetya](https://www.bleepingcomputer.com/news/security/new-hybridpetya-ransomware-can-bypass-uefi-secure-boot/), và [Bootkitty](https://www.bleepingcomputer.com/news/security/bootkitty-uefi-malware-exploits-logofail-to-infect-linux-systems/)) có thể né tránh các cơ chế bảo mật ở cấp hệ điều hành và tồn tại qua cả việc cài đặt lại hệ điều hành.

### Lệnh _mm_ mạnh mẽ

Theo công ty bảo mật firmware Eclypsium, vấn đề bắt nguồn từ việc bao gồm một lệnh 'memory modify' (_mm_) trong các shell UEFI được ký hợp pháp mà Framework đã cung cấp trên các hệ thống của họ.

Lệnh này cung cấp quyền truy cập đọc/ghi trực tiếp vào bộ nhớ hệ thống và được dự định cho chẩn đoán ở mức thấp và gỡ lỗi firmware. Tuy nhiên, nó cũng có thể bị lợi dụng để phá vỡ chuỗi tin cậy Secure Boot bằng cách nhắm vào biến gSecurity2, một thành phần quan trọng trong quá trình xác minh chữ ký của các module UEFI.

Lệnh _mm_ có thể bị lạm dụng để ghi đè gSecurity2 bằng NULL, về cơ bản vô hiệu hóa việc xác minh chữ ký.

"Once the address is identified, the mm command can overwrite the security handler pointer with NULL or redirect it to a function that always returns "success" without performing any verification," - [Eclypsium](https://eclypsium.com/blog/bombshell-the-signed-backdoor-hiding-in-plain-sight-on-framework-devices/)

"Lệnh này ghi các giá trị không vào vị trí bộ nhớ chứa con trỏ trình xử lý bảo mật, về cơ bản vô hiệu hóa việc xác minh chữ ký cho tất cả các lần nạp module sau đó."

Các nhà nghiên cứu cũng lưu ý rằng cuộc tấn công có thể được tự động hóa thông qua các script khởi động để tồn tại qua các lần khởi động lại.

### Khoảng 200.000 hệ thống bị ảnh hưởng

Framework là một công ty phần cứng có trụ sở tại US, nổi tiếng với việc thiết kế các laptop và desktop mô-đun và dễ sửa chữa.

Sự tồn tại của lệnh _mm_ rủi ro không phải là kết quả của một sự xâm phạm mà có vẻ là một sơ suất. Sau khi biết về vấn đề, Framework đã bắt đầu làm việc để khắc phục các lỗ hổng.

Các nhà nghiên cứu của Eclypsium ước tính rằng vấn đề đã ảnh hưởng khoảng 200.000 máy Framework:

* Framework 13 (11th Gen Intel), fix planned in 3.24
* Framework 13 (12th Gen Intel), fixed in 3.18, DBX update planned in 3.19
* Framework 13 (13th Gen Intel), fixed in 3.08, DBX update issued in 3.09
* Framework 13 (Intel Core Ultra), fixed in 3.06
* Framework 13 (AMD Ryzen 7040), fixed in 3.16
* Framework 13 (AMD Ryzen AI 300), fixed in 3.04, DBX update planned in 3.05
* Framework 16 (AMD Ryzen 7040), fixed in 3.06 (Beta), DBX update issued in 3.07
* Framework Desktop (AMD Ryzen AI 300 MAX), fixed in 3.01, DBX update planned in 3.03

Người dùng bị ảnh hưởng được khuyến nghị áp dụng các bản cập nhật bảo mật có sẵn. Ở những trường hợp chưa có bản vá, các biện pháp bảo vệ bổ sung như ngăn chặn truy cập vật lý là rất quan trọng. Một biện pháp giảm nhẹ tạm thời khác là xóa khóa DB của Framework thông qua BIOS.