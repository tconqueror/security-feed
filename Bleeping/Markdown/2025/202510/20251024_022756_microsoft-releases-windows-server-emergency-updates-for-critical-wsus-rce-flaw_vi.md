# Bản vá khẩn cấp cho Windows Server sửa lỗi WSUS có PoC khai thác công khai

![Windows](https://www.bleepstatic.com/content/hl-images/2025/08/22/Windows.jpg)

Microsoft đã phát hành cập nhật bảo mật ngoài lịch (out-of-band - OOB) để vá một lỗ hổng WSUS có mức độ nghiêm trọng là critical, kèm theo mã khai thác proof-of-concept công khai.

WSUS là một sản phẩm của Microsoft cho phép quản trị viên CNTT quản lý và phân phối các bản cập nhật Windows tới các máy tính trong mạng của họ.

Tracked as [CVE-2025-59287](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59287) và đã được vá trong [this month's Patch Tuesday](https://www.bleepingcomputer.com/news/microsoft/microsoft-october-2025-patch-tuesday-fixes-6-zero-days-172-flaws/), lỗ hổng thực thi mã từ xa (RCE) này chỉ ảnh hưởng đến các máy chủ Windows có chức năng WSUS Server Role được kích hoạt, một tính năng không được bật theo mặc định.

Lỗ hổng có thể bị khai thác từ xa bằng các tấn công có độ phức tạp thấp và không yêu cầu tương tác của người dùng, cho phép các tác nhân đe dọa không có đặc quyền nhắm vào hệ thống dễ bị tổn thương và chạy mã độc với đặc quyền SYSTEM. Điều này khiến nó có khả năng lây lan giữa các máy chủ WSUS.

"Windows servers that do not have the WSUS server role enabled are not vulnerable to this vulnerability. If the WSUS server role is enabled, the server will become vulnerable if the fix is not installed before the WSUS server role is enabled," [Microsoft explained](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59287).

"A remote, unauthenticated attacker could send a crafted event that triggers unsafe object deserialization in a legacy serialization mechanism, resulting in remote code execution."

Microsoft đã phát hành các bản cập nhật bảo mật cho tất cả các phiên bản Windows Server bị ảnh hưởng và khuyên khách hàng cài đặt chúng càng sớm càng tốt:

* Windows Server 2025 ([KB5070881](https://support.microsoft.com/help/5070881))
* Windows Server, version 23H2 ([KB5070879](https://support.microsoft.com/help/5070879))
* Windows Server 2022 ([KB5070884](https://support.microsoft.com/help/5070884))
* Windows Server 2019 ([KB5070883](https://support.microsoft.com/help/5070883))
* Windows Server 2016 ([KB5070882](https://support.microsoft.com/help/5070882))
* Windows Server 2012 R2 ([KB5070886](https://support.microsoft.com/help/5070886))
* Windows Server 2012 ([KB5070887](https://support.microsoft.com/help/5070887))

Như Microsoft tiết lộ trong một bản cập nhật vào thứ Năm cho thông báo bảo mật gốc, mã khai thác proof-of-concept cho CVE-2025-59287 hiện cũng đã có sẵn trực tuyến, khiến việc vá các máy chủ dễ bị tổn thương trở nên cấp bách hơn.

Microsoft cũng chia sẻ các biện pháp giảm thiểu tạm thời cho quản trị viên không thể cài đặt các bản vá khẩn cấp ngay lập tức, bao gồm vô hiệu hóa WSUS Server Role để loại bỏ vectơ tấn công hoặc chặn toàn bộ lưu lượng đến cổng 8530 và 8531 trên tường lửa của máy chủ để làm cho WSUS không thể hoạt động.

Tuy nhiên, cần lưu ý rằng các endpoint Windows sẽ ngừng nhận các bản cập nhật từ máy chủ cục bộ sau khi WSUS bị vô hiệu hóa hoặc lưu lượng bị chặn.

"This is a cumulative update, so you do not need to apply any previous updates before installing this update, as it supersedes all previous updates for affected versions," Microsoft added.

"Nếu bạn chưa cài đặt bản cập nhật bảo mật Windows tháng 10 năm 2025, chúng tôi khuyên bạn nên áp dụng bản cập nhật OOB này thay thế. Sau khi cài đặt bản cập nhật, bạn sẽ cần khởi động lại hệ thống."