# Các băng nhóm mã độc tống tiền chuyển sang bộ đóng gói EXE Shanya để che giấu các công cụ tiêu diệt EDR

![Các băng nhóm mã độc tống tiền chuyển sang bộ đóng gói EXE Shanya để che giấu các công cụ tiêu diệt EDR](https://www.bleepstatic.com/content/hl-images/2024/08/27/ransomware-2.jpg)

Nhiều băng nhóm ransomware đang sử dụng nền tảng packer-as-a-service có tên Shanya để giúp họ triển khai các payload vô hiệu hóa các giải pháp phát hiện và phản hồi điểm cuối (EDR) trên hệ thống nạn nhân.

Dịch vụ packer cung cấp cho tội phạm mạng các công cụ chuyên dụng để đóng gói payload sao cho làm mờ mã độc nhằm né tránh phát hiện bởi hầu hết công cụ bảo mật và engine antivirus đã biết.

Hoạt động bộ đóng gói Shanya xuất hiện cuối năm 2024 và đã tăng đáng kể về mức độ phổ biến, với các mẫu mã độc sử dụng nó được phát hiện ở Tunisia, UAE, Costa Rica, Nigeria và Pakistan, theo dữ liệu telemetry từ Sophos Security.

Trong số các nhóm ransomware được xác nhận đã sử dụng nó có Medusa, Qilin, Crytox và Akira, trong đó Akira là nhóm sử dụng dịch vụ packer này thường xuyên nhất.

![Occurrences of Shanya used in ransomware attacks](https://www.bleepstatic.com/images/news/u/1220909/2025/December/ransomware.jpg)

**Bộ đóng gói Shanya được sử dụng trong các cuộc tấn công mã độc tống tiền**  
_Source: Sophos_

## Shanya hoạt động như thế nào

Các tác nhân đe dọa gửi payload độc hại của họ cho Shanya, và dịch vụ trả về một phiên bản "packed" với một wrapper tùy chỉnh, sử dụng mã hóa và nén.

Dịch vụ quảng bá tính độc đáo của các payload kết quả, nhấn mạnh "non-standard module loading into memory, wrapper over the system loaderStub uniqueization," với "mỗi khách hàng nhận được stub của riêng họ (tương đối) độc nhất với một thuật toán mã hóa duy nhất khi mua."

![Junk code in the loader](https://www.bleepstatic.com/images/news/u/1220909/2025/December/loaderjunk.jpg)

**Junk code in the loader**  
_Source: Sophos_

Payload được chèn vào một bản sao được ánh xạ vào bộ nhớ của tệp Windows DLL ‘_shell32.dll_.’ Tệp DLL này có các phần thực thi và kích thước trông hợp lệ, và đường dẫn của nó có vẻ bình thường, nhưng header và phần .text của nó đã bị ghi đè bằng payload đã giải mã.

Trong khi payload được mã hóa bên trong tệp đã đóng gói, nó được giải mã và giải nén khi vẫn hoàn toàn nằm trong bộ nhớ, và sau đó được chèn vào tệp bản sao ‘_shell32.dll_’, không bao giờ chạm tới đĩa.

Các nhà nghiên cứu của Sophos [phát hiện](https://news.sophos.com/en-us/2025/12/06/inside-shanya-a-packer-as-a-service-fueling-modern-attacks/) rằng Shanya thực hiện các kiểm tra cho các giải pháp endpoint detection and response (EDR) bằng cách gọi hàm ‘_RtlDeleteFunctionTable_’ trong một ngữ cảnh không hợp lệ.

Điều này kích hoạt một ngoại lệ không được xử lý hoặc gây crash khi chạy dưới một trình gỡ lỗi ở chế độ user-mode, làm gián đoạn phân tích tự động trước khi payload thực thi đầy đủ.

## Vô hiệu hóa EDR

Các nhóm ransomware thường tìm cách vô hiệu hóa các công cụ EDR đang chạy trên hệ thống mục tiêu trước các giai đoạn trộm dữ liệu và mã hóa của cuộc tấn công.

Việc thực thi thường xảy ra thông qua DLL side-loading, kết hợp một chương trình Windows hợp pháp như ‘_consent.exe_’ với một DLL độc hại được đóng gói bởi Shanya như _msimg32.dll_, _version.dll_, _rtworkq.dll_ hoặc _wmsgapi.dll_.

Theo phân tích từ Sophos, công cụ tiêu diệt EDR thả hai driver: một ThrottleStop.sys được ký hợp lệ (_rwdrv.sys_) từ TechPowerUp, chứa một lỗi cho phép ghi tùy ý vào bộ nhớ kernel, và driver không được ký _hlpdrv.sys_.

Driver được ký được dùng để leo thang đặc quyền, trong khi _hlpdrv.sys_ vô hiệu hóa các sản phẩm bảo mật dựa trên các lệnh nhận từ user mode.

Thành phần user-mode liệt kê các tiến trình đang chạy và các dịch vụ đã cài đặt, sau đó so sánh kết quả với các mục trong một danh sách cứng mã hóa rộng lớn, gửi lệnh "kill" tới driver kernel độc hại cho mỗi khớp.

**Danh sách một phần các dịch vụ bị nhắm mục tiêu**  
_Source: Sophos_

Ngoài các toán ransomware tập trung vào việc vô hiệu hóa EDR, Sophos cũng quan sát các chiến dịch ClickFix gần đây sử dụng dịch vụ Shanya để đóng gói phần mềm độc hại CastleRAT.

Sophos ghi nhận rằng các băng nhóm ransomware thường dựa vào dịch vụ packer để chuẩn bị các công cụ tiêu diệt EDR nhằm triển khai mà không bị phát hiện.

Các nhà nghiên cứu cung cấp một phân tích kỹ thuật chi tiết về một số payload được đóng gói bằng Shanya.

Báo cáo cũng bao gồm các chỉ báo xâm nhập (IoCs) liên quan đến các chiến dịch sử dụng Shanya. (http://github.com/sophoslabs/IoCs/blob/master/2025-12%20shanya%20iocs.csv)