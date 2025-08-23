+-+-+-+-+-+-
# Botnet tấn công hơn 9,000 bộ định tuyến ASUS để thêm backdoor SSH vĩnh viễn

![ASUS](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

Hơn 9,000 bộ định tuyến ASUS đã bị xâm phạm bởi một botnet mới được gọi là "AyySSHush", cũng đã được quan sát nhằm vào các bộ định tuyến SOHO từ Cisco, D-Link và Linksys.

Chiến dịch này được các nhà nghiên cứu an ninh từ [GreyNoise](https://www.greynoise.io/blog/stealthy-backdoor-campaign-affecting-asus-routers) phát hiện vào giữa tháng 3 năm 2025, và họ cho biết nó mang dấu hiệu của một tác nhân đe dọa nhà nước, mặc dù không có sự chỉ định cụ thể nào được đưa ra.

Công ty giám sát mối đe dọa cho biết các cuộc tấn công kết hợp việc brute-force thông tin đăng nhập, vượt qua xác thực và khai thác các lỗ hổng cũ để xâm phạm các bộ định tuyến ASUS, bao gồm các mẫu RT-AC3100, RT-AC3200 và RT-AX55.

![Những nỗ lực brute-forcing đã quan sát](https://www.bleepstatic.com/images/news/u/1220909/2025/May/bruteforce.jpg)

**Những nỗ lực brute-forcing đã quan sát**  
_Nguồn: GreyNoise_

Cụ thể, những kẻ tấn công khai thác một lỗ hổng tiêm lệnh cũ được theo dõi là [CVE-2023-39780](https://nvd.nist.gov/vuln/detail/CVE-2023-39780) để thêm khóa công khai SSH của chúng và kích hoạt daemon SSH lắng nghe trên cổng TCP không chuẩn 53282. Những thay đổi này cho phép các tác nhân đe dọa giữ quyền truy cập backdoor vào thiết bị ngay cả khi khởi động lại và cập nhật firmware.

"Bởi vì khóa này được thêm vào bằng các tính năng chính thức của ASUS, nên thay đổi cấu hình này vẫn tồn tại qua các bản nâng cấp firmware," giải thích một báo cáo [liên quan khác](http://www.labs.greynoise.io/grimoire/2025-03-28-ayysshush/) bởi GreyNoise.

"Nếu bạn đã bị xâm phạm trước đó, việc nâng cấp firmware của bạn sẽ **KHÔNG** xóa bỏ backdoor SSH."

Cuộc tấn công này đặc biệt kín đáo, không bao gồm phần mềm độc hại, trong khi những kẻ tấn công cũng tắt việc ghi nhật ký và AiProtection của Trend Micro để tránh bị phát hiện.

Tính đến giờ, GreyNoise chỉ ghi nhận 30 yêu cầu độc hại liên quan đến chiến dịch này trong ba tháng qua, mặc dù 9,000 bộ định tuyến ASUS đã bị nhiễm.

![Các yêu cầu độc hại nhắm vào các bộ định tuyến ASUS](https://www.bleepstatic.com/images/news/u/1220909/2025/May/timeline(1).jpg)

**Các yêu cầu độc hại nhắm vào các bộ định tuyến ASUS**  
_Nguồn: GreyNoise_

Tuy nhiên, ba trong số những yêu cầu đó đã đủ để kích hoạt công cụ phân tích dựa trên AI của GreyNoise đánh dấu chúng cho kiểm tra của con người.

Chiến dịch này có khả năng trùng lặp với hoạt động mà Sekoia theo dõi là "[Vicious Trap](https://blog.sekoia.io/vicioustrap-infiltrate-control-lure-turning-edge-devices-into-honeypots-en-masse/)," được công bố tuần trước, mặc dù công ty an ninh mạng Pháp cho biết các tác nhân đe dọa đã khai thác CVE-2021-32030 để xâm nhập vào các bộ định tuyến ASUS.

Trong chiến dịch được Sekoia quan sát, các tác nhân đe dọa đã được ghi nhận đã nhắm đến các bộ định tuyến SOHO, SSL VPNs, DVRs và bộ điều khiển BMC từ D-Link, Linksys, QNAP và Araknis Networks.

Mục tiêu hoạt động chính xác của AyySSHush vẫn chưa rõ ràng, vì không có dấu hiệu nào của từ chối dịch vụ phân tán (DDoS) hoặc việc sử dụng các thiết bị để proxy lưu lượng độc hại thông qua các bộ định tuyến ASUS.

Tuy nhiên, trong các vụ vi phạm bộ định tuyến được Sekoia quan sát, một kịch bản độc hại đã được tải xuống và thực thi để chuyển hướng lưu lượng mạng từ hệ thống bị xâm phạm sang các thiết bị bên thứ ba do kẻ tấn công kiểm soát.

Hiện tại, có vẻ như chiến dịch này đang âm thầm xây dựng một mạng lưới các bộ định tuyến có backdoor để tạo nền tảng cho một botnet trong tương lai.

## Bảo vệ các bộ định tuyến ASUS của bạn

ASUS đã phát hành các bản cập nhật bảo mật khắc phục CVE-2023-39780 cho các bộ định tuyến bị ảnh hưởng, mặc dù thời gian chính xác có thể khác nhau theo từng mẫu.

Người dùng được khuyên nên nâng cấp firmware càng sớm càng tốt và tìm kiếm các tệp đáng ngờ cùng với việc thêm khóa SSH của kẻ tấn công ([IoCs ở đây](https://www.labs.greynoise.io/grimoire/2025-03-28-ayysshush/)) trên tệp 'authorized\_keys'.

Ngoài ra, GreyNoise cung cấp bốn địa chỉ IP liên quan đến hoạt động này, nên được thêm vào danh sách chặn.

```
101.99.91[.]151
101.99.94[.]173 
79.141.163[.]179   
111.90.146[.]237
```

Nếu nghi ngờ bị xâm phạm, nên thực hiện cài đặt lại nhà máy để làm sạch bộ định tuyến một cách chắc chắn và sau đó cấu hình lại từ đầu với một mật khẩu mạnh.