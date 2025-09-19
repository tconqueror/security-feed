# Fortra cảnh báo lỗ hổng mức nghiêm trọng tối đa trong License Servlet của GoAnywhere MFT

![Fortra](https://www.bleepstatic.com/content/hl-images/2025/09/19/Fortra_headpic.jpg)

Fortra đã phát hành các bản cập nhật bảo mật để vá một lỗ hổng có mức độ nghiêm trọng tối đa trong License Servlet của GoAnywhere MFT có thể bị khai thác trong các cuộc tấn công chèn lệnh.

GoAnywhere MFT là một công cụ quản lý truyền tệp dựa trên web giúp các tổ chức truyền tệp một cách an toàn và duy trì nhật ký kiểm toán về ai truy cập các tệp được chia sẻ.

Được theo dõi dưới mã CVE-2025-10035, lỗ hổng bảo mật này do một [lỗi deserialization dữ liệu không đáng tin cậy](https://cwe.mitre.org/data/definitions/502.html) gây ra và có thể bị khai thác từ xa trong các cuộc tấn công có độ phức tạp thấp không yêu cầu tương tác của người dùng. Mặc dù Fortra cho biết lỗ hổng này được phát hiện vào cuối tuần, công ty không nêu rõ ai đã báo cáo hoặc liệu lỗ hổng đã bị lợi dụng trong các cuộc tấn công hay chưa.

"Một lỗ hổng deserialization trong License Servlet của GoAnywhere MFT của Fortra cho phép một tác nhân có chữ ký phản hồi giấy phép được tạo hợp lệ thực hiện deserialise một đối tượng do tác nhân điều khiển, có thể dẫn đến chèn lệnh," công ty cho biết trong một [cảnh báo bảo mật](https://www.fortra.com/security/advisories/product-security/fi-2025-012) được công bố vào thứ Năm.

"Trong quá trình kiểm tra bảo mật được tiến hành ngày 11 tháng 9 năm 2025, chúng tôi xác định rằng khách hàng GoAnywhere có Admin Console có thể truy cập qua internet có thể đang bị lộ cho bên thứ ba trái phép," Fortra nói với BleepingComputer hôm nay. "Chúng tôi ngay lập tức phát triển một bản vá và cung cấp hướng dẫn giảm thiểu cho khách hàng để giúp giải quyết vấn đề. Khách hàng nên kiểm tra cấu hình ngay lập tức và loại bỏ quyền truy cập công khai từ Admin Console."

Công ty đã phát hành GoAnywhere MFT 7.8.4 và Sustain Release 7.6.3, bao gồm các bản vá cho CVE-2025-10035, và khuyến cáo các quản trị viên CNTT không thể nâng cấp phần mềm ngay lập tức hãy bảo đảm các hệ thống dễ bị tổn thương bằng cách đảm bảo rằng GoAnywhere Admin Console không thể truy cập được qua internet.

"Khai thác lỗ hổng này phụ thuộc nhiều vào việc hệ thống có bị phơi nhiễm ra internet hay không," Fortra bổ sung.

Các nhà phân tích bảo mật tại tổ chức phi lợi nhuận Shadowserver Foundation đang giám sát [hơn 470 hệ thống GoAnywhere MFT](https://dashboard.shadowserver.org/statistics/iot-devices/time-series/?date%5Frange=7&vendor=fortra&type=file-transfer&model=goanywhere+mft&dataset=count&limit=1000&group%5Fby=geo&stacking=stacked&auto%5Fupdate=on) bị phơi nhiễm trực tuyến, nhưng không rõ bao nhiêu trong số này đã được vá.

![GoAnywhere MFT exposed online](https://www.bleepstatic.com/images/news/u/1109292/2025/GoAnywhere%20MFT%20exposed%20online.jpg)

_Các instance GoAnywhere MFT bị lộ trực tuyến (Shadowserver)_

Mặc dù CVE-2025-10035 chưa được gắn nhãn là đang bị khai thác tích cực, các quản trị viên vẫn được khuyên nên vá các instance GoAnywhere MFT của họ, vì các tác nhân đe dọa xem các giải pháp truyền tệp an toàn (chẳng hạn như GoAnywhere MFT) là mục tiêu hấp dẫn bởi vì chúng thường được sử dụng để chia sẻ các tài liệu nhạy cảm.

Ví dụ, băng nhóm ransomware Clop đã tuyên bố rằng họ [xâm phạm hơn 130 tổ chức](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-it-breached-130-orgs-using-goanywhere-zero-day/) hai năm trước bằng cách khai thác một lỗ hổng thực thi mã từ xa nghiêm trọng (CVE-2023-0669) trong phần mềm GoAnywhere MFT [trong các cuộc tấn công zero-day](https://www.bleepingcomputer.com/news/security/exploit-released-for-actively-exploited-goanywhere-mft-zero-day/).

Fortra (trước đây được biết đến với tên HelpSystems), công ty an ninh mạng đứng sau GoAnywhere MFT và công cụ mô phỏng mối đe dọa Cobalt Strike vốn bị lạm dụng rộng rãi, cho biết họ cung cấp phần mềm và dịch vụ cho hơn 9.000 tổ chức trên toàn cầu.