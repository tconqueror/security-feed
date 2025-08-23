# Phần mềm độc hại Anubis thêm chức năng xóa để tiêu hủy các tệp không thể phục hồi

![Phần mềm độc hại Anubis](https://www.bleepstatic.com/content/hl-images/2025/06/13/Anubis.jpg)

Hoạt động ransomware-as-a-service (RaaS) Anubis đã thêm vào phần mềm độc hại mã hóa tệp của mình một mô-đun xóa để phá hủy các tệp bị nhắm đến, khiến việc phục hồi trở nên không thể ngay cả khi tiền chuộc được trả.

Anubis (không nên nhầm lẫn với [phần mềm độc hại Android cùng tên](https://www.bleepingcomputer.com/news/security/anubis-android-malware-returns-to-target-394-financial-apps/) có một [mô-đun ransomware](https://www.bleepingcomputer.com/news/security/anubis-android-trojan-spotted-with-almost-functional-ransomware-module/)) là một RaaS tương đối mới được phát hiện lần đầu vào tháng 12 năm 2024 nhưng trở nên hoạt động nhiều hơn vào đầu năm.

Vào ngày 23 tháng 2, các nhà điều hành đã công bố chương trình liên kết trên diễn đàn RAMP.

Một [báo cáo từ KELA](https://www.kelacyber.com/blog/anubis-a-new-ransomware-threat/) vào thời điểm đó giải thích rằng Anubis đã cung cấp cho các đối tác ransomware một phần trăm 80% từ lợi nhuận của họ. Các đối tác tống tiền dữ liệu được cung cấp 60%, và các nhà môi giới truy cập ban đầu được cắt 50%.

Hiện tại, trang tống tiền của Anubis trên dark web chỉ liệt kê tám nạn nhân, cho thấy rằng nó có thể tăng cường khối lượng tấn công khi sự tự tin vào khía cạnh kỹ thuật được củng cố.

Trong báo cáo của Trend Micro được công bố hôm qua cho thấy rằng các nhà điều hành của Anubis đang tích cực làm việc để thêm những tính năng mới, một trong những tính năng bất thường là chức năng xóa tệp.

Các nhà nghiên cứu đã tìm thấy chức năng xóa trong các mẫu Anubis mới nhất mà họ phân tích, và tin rằng tính năng này được giới thiệu nhằm tăng áp lực lên nạn nhân để trả tiền nhanh hơn thay vì trì hoãn đàm phán hoặc hoàn toàn không phản hồi.

“Điều gì khiến Anubis khác biệt so với các RaaS khác và tạo lợi thế cho các hoạt động của nó là việc sử dụng tính năng xóa tệp, được thiết kế để phá hủy nỗ lực phục hồi ngay cả sau khi mã hóa,” [giải thích Trend Micro](https://www.trendmicro.com/en%5Fus/research/25/f/anubis-a-closer-look-at-an-emerging-ransomware.html).

“Xu hướng hủy diệt này gia tăng áp lực lên các nạn nhân và nâng cao độ nghiêm trọng của một cuộc tấn công đã gây tổn hại.”

Hành vi phá hoại được kích hoạt bằng cách sử dụng tham số dòng lệnh '/WIPEMODE,' yêu cầu xác thực dựa trên khóa để thực hiện.

![Chế độ xóa của Anubis](https://www.bleepstatic.com/images/news/u/1220909/2025/June/wipemode.jpg)

**Chế độ xóa của Anubis**  
_Nguồn: Trend Micro_

Khi được kích hoạt, chức năng xóa sẽ xóa tất cả nội dung tệp, giảm kích thước của chúng xuống 0 KB trong khi giữ nguyên tên tệp và cấu trúc.

Nạn nhân vẫn sẽ thấy tất cả các tệp trong các thư mục mà họ mong đợi, nhưng nội dung của chúng sẽ bị phá hủy một cách không thể phục hồi, khiến việc phục hồi không thể.

![Các tệp trước mã hóa (trên) và sau (dưới)](https://www.bleepstatic.com/images/news/u/1220909/2025/June/before.jpg)

**Các tệp trước mã hóa (trên) và sau (dưới)**  
_Nguồn: Trend Micro_

Phân tích của Trend Micro tiết lộ rằng Anubis hỗ trợ một số lệnh khi khởi động, bao gồm cả việc nâng cao quyền hạn, loại trừ thư mục và các đường dẫn mục tiêu cho mã hóa.

Các thư mục hệ thống và chương trình quan trọng được loại trừ theo mặc định để tránh khiến hệ thống hoàn toàn không sử dụng được.

Phần mềm độc hại này xóa Volume Shadow Copies và kết thúc các quy trình và dịch vụ có thể gây cản trở quy trình mã hóa.

Hệ thống mã hóa sử dụng ECIES (Elliptic Curve Integrated Encryption Scheme), và các nhà nghiên cứu đã nhận thấy sự tương đồng trong triển khai với ransomware EvilByte và Prince.

Các tệp đã mã hóa được thêm phần đuôi '.anubis', một ghi chú tiền chuộc HTML được thả vào các thư mục bị ảnh hưởng, và phần mềm độc hại cũng thực hiện một nỗ lực (thất bại) để thay đổi hình nền desktop.

**Ghi chú tiền chuộc Anubis**  
_Nguồn: Trend Micro_

Trend Micro đã quan sát rằng các cuộc tấn công Anubis bắt đầu bằng các email lừa đảo chứa các liên kết hoặc tệp đính kèm độc hại.

Danh sách đầy đủ các chỉ báo của việc xâm phạm (IoCs) liên quan đến các cuộc tấn công Anubis có thể được [tìm thấy ở đây](https://www.trendmicro.com/content/dam/trendmicro/global/en/research/25/f/anubis--a-closer-look-at-an-emerging-ransomware-with-built-in-wiper/Anubis%5FA%5FCloser%5FLook%5Fat%5Fa%5FEmerging%5FRansomware%5Fwith%5FBuilt-in%5FWiper%5FIOCs.txt).