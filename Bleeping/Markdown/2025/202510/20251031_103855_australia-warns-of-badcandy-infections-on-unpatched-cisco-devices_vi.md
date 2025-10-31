# Australia cảnh báo về các nhiễm BadCandy trên các thiết bị Cisco chưa được vá

![Bí ngô](https://www.bleepstatic.com/content/hl-images/2025/10/31/pumpkin.jpg)

Chính phủ Australia cảnh báo về các cuộc tấn công mạng đang diễn ra nhắm vào các thiết bị Cisco IOS XE chưa được vá trong nước để cài đặt webshell BadCandy lên các bộ định tuyến.

Lỗ hổng bị khai thác trong những cuộc tấn công này là CVE-2023-20198, một lỗ hổng có mức độ nghiêm trọng tối đa cho phép các tác nhân đe dọa từ xa không xác thực tạo một tài khoản quản trị cục bộ qua giao diện web và chiếm quyền điều khiển thiết bị.

Cisco đã sửa lỗi này vào tháng 10 năm 2023, lỗ hổng sau đó được đánh dấu là một vấn đề [đang bị khai thác tích cực](https://www.bleepingcomputer.com/news/security/cisco-warns-of-new-ios-xe-zero-day-actively-exploited-in-attacks/). Một [exploit công khai](https://www.bleepingcomputer.com/news/security/exploit-released-for-critical-cisco-ios-xe-flaw-many-hosts-still-hacked/) có sẵn hai tuần sau đó, dẫn tới việc khai thác diện rộng để [cài backdoor](https://www.bleepingcomputer.com/news/security/hackers-update-cisco-ios-xe-backdoor-to-hide-infected-devices/) trên các thiết bị lộ ra Internet.

Các nhà chức trách Australia cho biết rằng các biến thể của cùng web shell BadCandy dựa trên Lua vẫn được sử dụng trong các cuộc tấn công xuyên suốt 2024 và 2025, cho thấy nhiều thiết bị Cisco vẫn chưa được vá.

Khi được cài đặt, BadCandy cho phép kẻ tấn công từ xa thực thi các lệnh với đặc quyền root trên các thiết bị bị xâm phạm.

Webshell sẽ bị xóa khỏi thiết bị sau khi khởi động lại. Tuy nhiên, do các thiết bị đó không có bản vá và giả sử giao diện web vẫn có thể truy cập được, các kẻ tấn công có thể dễ dàng cài đặt lại nó.

"Kể từ tháng 7 năm 2025, ASD đánh giá hơn 400 thiết bị có khả năng đã bị xâm phạm bởi BADCANDY tại Australia," [đọc bản thông báo](https://www.cyber.gov.au/about-us/view-all-content/alerts-and-advisories/badcandy). "Tính đến cuối tháng 10 năm 2025, vẫn còn hơn 150 thiết bị bị xâm phạm bởi BADCANDY tại Australia."

![Nhiễm BadCandy tại Australia](https://www.bleepstatic.com/images/news/u/1220909/2025/October/badcandy_graph.jpg)

**Nhiễm BadCandy tại Australia**  
_Source: ASD_

Mặc dù số lượng nhiễm đang giảm, cơ quan này đã thấy dấu hiệu tái khai thác lỗ hổng trên cùng các điểm cuối, ngay cả khi các tổ chức bị xâm phạm đã được thông báo đúng cách.

Theo cơ quan, các kẻ tấn công có thể phát hiện khi implant BadCandy bị gỡ bỏ và tiếp tục nhắm mục tiêu cùng thiết bị để cài lại nó.

Để ứng phó với các cuộc tấn công đang diễn ra, Australian Signals Directorate đang gửi thông báo cho các nạn nhân bao gồm hướng dẫn vá lỗi, tăng cường bảo mật thiết bị và tiến hành ứng phó sự cố. Đối với những thiết bị không thể xác định chủ sở hữu, ASD đang yêu cầu các nhà cung cấp dịch vụ Internet liên hệ với nạn nhân thay họ.

ASD nhắc rằng lỗ hổng này trước đây đã từng bị các tác nhân nhà nước lợi dụng như nhóm 'Salt Typhoon' của Trung Quốc, những kẻ được cho là chịu trách nhiệm cho một loạt các cuộc tấn công nhắm vào các nhà cung cấp dịch vụ viễn thông lớn [trên khắp U.S](https://www.bleepingcomputer.com/news/security/fbi-seeks-help-to-unmask-salt-typhoon-hackers-behind-telecom-breaches/). và [Canada](https://www.bleepingcomputer.com/news/security/canada-says-salt-typhoon-hacked-telecom-firm-via-cisco-flaw/).

Cơ quan tin rằng, mặc dù BadCandy về lý thuyết có thể được sử dụng bởi bất kỳ ai, nhưng các đợt gia tăng gần đây có thể được quy cho "các tác nhân mạng do nhà nước tài trợ."

Quản trị viên hệ thống Cisco IOS XE trên toàn cầu, bao gồm Australia, nên làm theo các khuyến nghị giảm thiểu của nhà cung cấp trong [bản thông báo bảo mật](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-iosxe-webui-privesc-j22SaA4z).

Cisco cũng đã công bố một [hướng dẫn tăng cường bảo mật chi tiết](https://sec.cloudapps.cisco.com/security/center/resources/IOS%5FXE%5Fhardening) cho các thiết bị IOS XE.