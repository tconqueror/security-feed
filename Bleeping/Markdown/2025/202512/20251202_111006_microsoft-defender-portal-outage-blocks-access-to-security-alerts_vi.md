# Microsoft Defender portal ngừng hoạt động làm gián đoạn các cảnh báo săn tìm mối đe dọa

![Microsoft Defender for Endpoint](https://www.bleepstatic.com/content/hl-images/2023/10/11/Microsoft-Defender_for_Endpoint.jpg)

Microsoft đang nỗ lực giảm thiểu một sự cố đang diễn ra vốn đã chặn truy cập tới một số khả năng của Defender XDR portal trong 10 giờ qua.

Theo một cảnh báo dịch vụ trong admin center ([DZ1191468](https://admin.microsoft.com/#/MessageCenter/:/messages/DZ1191468)) mà BleepingComputer đã thấy, sự cố này có thể ảnh hưởng đến khách hàng đang cố truy cập hoặc sử dụng các tính năng trong Defender portal.

Các vấn đề được gây ra bởi cái mà Microsoft mô tả là "đột biến lưu lượng gây ra mức sử dụng Central Processing Unit (CPU) cao trên các thành phần hỗ trợ chức năng của Microsoft Defender portal."

Khi công nhận sự cố sáng nay lúc 06:10 UTC, Microsoft cũng gắn nhãn đây là một incident, một phân loại thường dùng cho các sự cố dịch vụ nghiêm trọng mà thường gây tác động đáng kể tới người dùng.

Kể từ đó Microsoft đã áp dụng các biện pháp giảm thiểu để giải quyết tác động và tăng thông lượng xử lý, với dữ liệu telemetry cho thấy tính khả dụng đã phục hồi cho một số khách hàng bị ảnh hưởng, theo một bản cập nhật lúc 8 AM UTC.

![Defender XDR portal outage](https://www.bleepstatic.com/images/news/u/1109292/2025/Defender-portal-outage.png)

Microsoft hiện đang phân tích các HTTP Archive (HAR) traces do khách hàng bị ảnh hưởng cung cấp và cho biết rằng, ngoài việc truy cập bị chặn, các chức năng portal bị ảnh hưởng hiện bao gồm, nhưng không giới hạn ở, việc thiếu các cảnh báo advanced threat-hunting và thiết bị không xuất hiện.

"Chúng tôi đã nhận được xác nhận từ các tổ chức bổ sung rằng sự cố đã được giải quyết đối với họ, và dữ liệu giám sát telemetry tiếp tục cho thấy mức sử dụng CPU vẫn nằm trong ngưỡng chấp nhận được," họ bổ sung khoảng hai giờ sau đó.

"Chúng tôi đang làm việc với một số ít tổ chức báo cáo rằng sự cố vẫn còn tồn tại và phối hợp với họ để thu thập thêm chẩn đoán phía client và các HTTP Archive format (HAR) traces nhằm hỗ trợ cuộc điều tra của chúng tôi."

_Đây là một tin đang phát triển..._