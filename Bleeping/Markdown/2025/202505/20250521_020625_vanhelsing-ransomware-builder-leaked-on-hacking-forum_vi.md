# Mã nguồn của phần mềm mã hóa VanHelsing bị rò rỉ trên diễn đàn tội phạm mạng

![VanHelsing](https://www.bleepstatic.com/content/hl-images/2025/03/24/vanhelsing.jpg)

Mô hình ransomware-as-a-service (RaaS) VanHelsing đã công bố mã nguồn cho bảng điều khiển chi nhánh, blog rò rỉ dữ liệu và trình xây dựng phần mềm mã hóa Windows sau khi một nhà phát triển cũ đã cố gắng bán nó trên diễn đàn tội phạm mạng RAMP.

VanHelsing là một hoạt động RaaS [được ra mắt vào tháng 3 năm 2025,](https://www.bleepingcomputer.com/news/security/new-vanhelsing-ransomware-targets-windows-arm-esxi-systems/) quảng bá khả năng nhắm mục tiêu các hệ thống Windows, Linux, BSD, ARM và ESXi.

Kể từ đó, hoạt động này đã đạt được một số thành công, với [Ransomware.live](https://www.ransomware.live/group/VanHelsing) cho biết có tám nạn nhân được biết đến của băng nhóm ransomware này.

## Mã nguồn VanHelsing bị rò rỉ trên diễn đàn tội phạm mạng

Sáng nay, một người sử dụng bí danh 'th30c0der' đã cố gắng bán mã nguồn cho bảng điều khiển chi nhánh VanHelsing và các trang Tor rò rỉ dữ liệu, cũng như các bộ xây dựng cho phần mềm mã hóa Windows và Linux với giá 10.000 đô la.

"mã nguồn ransomware vanhelsing để bán: bao gồm TOR keys + bảng điều khiển cho quản trị viên + chat + máy chủ tệp + blog bao gồm cơ sở dữ liệu tất cả mọi thứ," th30c0der đã đăng trên diễn đàn RAMP.

![th30c0der cố gắng bán mã nguồn VanHelsing](https://www.bleepstatic.com/images/news/ransomware/v/vanhelsing/leaked-code/builder-for-sale.jpg)

**th30c0der cố gắng bán mã nguồn VanHelsing**

Như đã được báo cáo đầu tiên bởi [Emanuele De Lucia](https://x.com/Manu%5FDe%5FLucia/status/1924792567461294492), các nhà điều hành VanHelsing đã quyết định phản đòn người bán, tự mình phát hành mã nguồn và tuyên bố rằng th30c0der là một trong những nhà phát triển cũ của họ đang cố gắng lừa đảo mọi người.

"Hôm nay chúng tôi thông báo rằng chúng tôi đang công bố mã nguồn cũ và sẽ sớm trở lại với phiên bản mới và cải tiến của locker (VanHelsing 2.0)," các nhà điều hành VanHelsing đã đăng trên RAMP.

![VanHelsin RaaS công bố mã nguồn trên RAMP​​​​​](https://www.bleepstatic.com/images/news/ransomware/v/vanhelsing/leaked-code/vanhelsing-leaking-source-code.jpg)

**VanHelsin RaaS công bố mã nguồn trên RAMP**​​​​​

Tuy nhiên, dữ liệu bị rò rỉ này không đầy đủ so với những gì 30c0der cho biết họ có, vì nó không bao gồm bộ xây dựng Linux hoặc bất kỳ cơ sở dữ liệu nào, điều này sẽ rất hữu ích cho cơ quan thực thi pháp luật và các nhà nghiên cứu an ninh mạng.

BleepingComputer đã thu thập mã nguồn rò rỉ và xác nhận rằng nó chứa bộ xây dựng hợp pháp cho phần mềm mã hóa Windows và mã nguồn cho bảng điều khiển chi nhánh và trang rò rỉ dữ liệu.

**Mã nguồn bị rò rỉ**  
_Nguồn: BleepingComputer_

Mã nguồn của bộ xây dựng khá lộn xộn, với các tệp dự án Visual Studio được tìm thấy trong thư mục "Release", thường được sử dụng để chứa các tệp nhị phân và tài sản xây dựng đã biên dịch.

Mặc dù hoàn chỉnh, việc sử dụng bộ xây dựng VanHelsing sẽ yêu cầu một số công việc, vì nó kết nối lại với bảng điều khiển chi nhánh, đang chạy 31.222.238\[.\]208, để nhận dữ liệu được sử dụng cho quy trình xây dựng.

**tệp tiêu đề common.h được sử dụng bởi bộ xây dựng**  
_Nguồn: BleepingComputer_

Tuy nhiên, rò rỉ cũng bao gồm mã nguồn cho bảng điều khiển chi nhánh, nơi chứa điểm cuối api.php, vì vậy các tác nhân đe dọa có thể chỉnh sửa mã hoặc chạy phiên bản riêng của bảng điều khiển này để làm cho bộ xây dựng hoạt động.

Bản lưu trữ cũng chứa mã nguồn cho phần mềm mã hóa Windows, có thể được sử dụng để tạo một bản xây dựng độc lập, bộ giải mã và một trình tải.

**Mã nguồn mã hóa VanHelsing**  
_Nguồn: BleepingComputer_

Mã nguồn bị rò rỉ cũng tiết lộ rằng các tác nhân đe dọa đang cố gắng xây dựng một MBR locker sẽ thay thế bản ghi khởi động chính bằng một bootloader tùy chỉnh hiển thị thông điệp khóa.

**Mã nguồn MBRLocker VanHelsing**  
_Nguồn: BleepingComputer_

Rò rỉ này không phải là lần đầu tiên mã nguồn của bộ xây dựng ransomware hoặc phần mềm mã hóa bị rò rỉ trực tuyến, cho phép các nhóm ransomware mới hoặc các tác nhân đe dọa cá nhân nhanh chóng thực hiện các cuộc tấn công.

Vào tháng 6 năm 2021, [mã xây dựng ransomware Babuk bị rò rỉ](https://www.bleepingcomputer.com/news/security/leaked-babuk-locker-ransomware-builder-used-in-new-attacks/), cho phép bất kỳ ai tạo ra các trình mã hóa và giải mã cho Windows và VMware ESXi. Rò rỉ Babuk đã trở thành một trong những [bộ xây dựng được sử dụng rộng rãi nhất](https://www.bleepingcomputer.com/news/security/babuk-code-used-by-9-ransomware-gangs-to-encrypt-vmware-esxi-servers/) để thực hiện các cuộc tấn công vào các máy chủ VMware ESXi.

Vào tháng 3 năm 2022, khi [hoạt động ransomware Conti gặp phải một vụ rò rỉ dữ liệu](https://www.bleepingcomputer.com/news/security/conti-ransomwares-internal-chats-leaked-after-siding-with-russia/), [mã nguồn của nó cũng bị rò rỉ trực tuyến](https://www.bleepingcomputer.com/news/security/conti-ransomware-source-code-leaked-by-ukrainian-researcher/). Các tác nhân đe dọa khác đã nhanh chóng sử dụng mã nguồn này trong các cuộc tấn công của riêng họ.

Vào tháng 9 năm 2022, khi [hoạt động ransomware LockBit gặp phải một vụ rò rỉ](https://www.bleepingcomputer.com/news/security/lockbit-ransomware-builder-leaked-online-by-angry-developer/) khi một nhà phát triển được cho là không hài lòng đã rò rỉ bộ xây dựng của băng nhóm này. Điều này cũng đã trở thành rất được sử dụng bởi các tác nhân đe dọa khác cho đến nay.