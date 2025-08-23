# Hơn 29,000 máy chủ Exchange chưa được vá trước lỗ hổng nghiêm trọng

![Microsoft Exchange](https://www.bleepstatic.com/content/hl-images/2025/04/15/Exchange_headpic.jpg)

Hơn 29,000 máy chủ Exchange được lộ diện trực tuyến vẫn chưa được vá trước một lỗ hổng nghiêm trọng có thể cho phép kẻ tấn công di chuyển bên trong các môi trường đám mây của Microsoft, dẫn tới việc chiếm quyền hoàn toàn miền.

Lỗi bảo mật ([theo dõi là CVE-2025-53786](https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-high-severity-flaw-in-hybrid-exchange-deployments/)) giúp các đối tượng đe dọa có được quyền truy cập quản trị vào các máy chủ Exchange tại chỗ để nâng cao quyền hạn trong môi trường đám mây kết nối của tổ chức bằng cách giả mạo hoặc thao tác các mã thông báo hoặc cuộc gọi API đáng tin cậy, mà không để lại dấu vết dễ phát hiện và khiến việc phát hiện khai thác trở nên khó khăn.

CVE-2025-53786 ảnh hưởng đến Exchange Server 2016, Exchange Server 2019 và Microsoft Exchange Server Subscription Edition, thay thế mô hình giấy phép vĩnh viễn bằng mô hình dựa trên đăng ký, trong các cấu hình lai.

Lỗi này đã được tiết lộ sau khi Microsoft [phát hành hướng dẫn](https://techcommunity.microsoft.com/blog/exchange/exchange-server-security-changes-for-hybrid-deployments/4396833) và một [bản vá máy chủ Exchange](https://techcommunity.microsoft.com/blog/exchange/released-april-2025-exchange-server-hotfix-updates/4402471) vào tháng 4 năm 2025 như một phần của Sáng kiến Tương lai An toàn của nó, hỗ trợ một kiến trúc mới sử dụng một ứng dụng lai chuyên dụng thay thế cho danh tính chung không an toàn trước đó được sử dụng bởi máy chủ Exchange tại chỗ và Exchange Online.

Mặc dù Redmond chưa tìm thấy bằng chứng nào về hành vi lạm dụng trong các cuộc tấn công, lỗ hổng này vẫn được gán nhãn là "Khai thác có khả năng cao hơn" vì Redmond coi rằng mã khai thác cho phép khai thác nhất quán có thể được phát triển, tăng sức hấp dẫn của nó đối với kẻ tấn công.

Theo [các quét](https://bsky.app/profile/shadowserver.bsky.social/post/3lvvh76iuss2c) từ nền tảng giám sát mối đe dọa bảo mật Shadowserver, hơn 29,000 máy chủ Exchange vẫn chưa được vá trước các cuộc tấn công tiềm ẩn CVE-2025-53786.

Trong tổng số [29,098 máy chủ chưa được vá](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=7&source=exchange&source=exchange6&tag=cve-2025-53786%2B&dataset=unique%5Fips&limit=100&group%5Fby=geo&stacking=stacked&auto%5Fupdate=on) được phát hiện vào ngày 10 tháng 8, [hơn 7,200 địa chỉ IP](https://dashboard.shadowserver.org/statistics/combined/map/?date%5Frange=1&map%5Ftype=std&source=exchange&source=exchange6&tag=cve-2025-53786%2B&data%5Fset=count&scale=log&auto%5Fupdate=on) được tìm thấy ở Hoa Kỳ, hơn 6,700 ở Đức và hơn 2,500 ở Nga.

![Máy chủ Exchange chưa được vá](https://www.bleepstatic.com/images/news/u/1109292/2025/Exchange_Servers_unpatched_against_cve-2025-53786.jpg)

_Máy chủ Exchange chưa được vá (Shadowserver)_

## Cơ quan liên bang được yêu cầu giảm thiểu vào cuối tuần

Một ngày sau khi Microsoft tiết lộ lỗ hổng, [CISA](https://www.bleepingcomputer.com/news/security/cisa-orders-fed-agencies-to-patch-new-cve-2025-53786-exchange-flaw/) đã [ban hành Chỉ thị Khẩn cấp 25-02](https://www.bleepingcomputer.com/news/security/cisa-orders-fed-agencies-to-patch-new-cve-2025-53786-exchange-flaw/), yêu cầu tất cả các cơ quan hành pháp dân sự liên bang (FCEB), bao gồm Bộ An ninh Nội địa, Bộ Tài chính và Bộ Năng lượng, phải giảm thiểu lỗ hổng Microsoft Exchange nghiêm trọng này trước thứ Hai lúc 9:00 sáng ET.

Các cơ quan liên bang phải giảm thiểu lỗ hổng này bằng cách trước tiên kiểm kê môi trường Exchange của họ bằng cách sử dụng [kịch bản Kiểm tra Sức khỏe của Microsoft](https://microsoft.github.io/CSS-Exchange/Diagnostics/HealthChecker/) và ngắt kết nối các máy chủ công khai không còn được hỗ trợ bởi bản vá tháng 4 năm 2025 khỏi internet, như các phiên bản máy chủ Exchange đã hết hạn (EOL) hoặc hết dịch vụ.

Tất cả các máy chủ còn lại phải được cập nhật lên các bản cập nhật tích lũy mới nhất (CU14 hoặc CU15 cho Exchange 2019, và CU23 cho Exchange 2016) và vá bằng bản vá tháng 4 của Microsoft.

Trong một [thông báo riêng được phát hành vào thứ Năm](https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-high-severity-flaw-in-hybrid-exchange-deployments/), cơ quan an ninh mạng của Hoa Kỳ đã cảnh báo rằng việc không giảm thiểu CVE-2025-53786 có thể dẫn đến "tổng thể sự chiếm đoạt miền của đám mây lai và tại chỗ."

Mặc dù các tổ chức phi chính phủ không bắt buộc phải thực hiện hành động nào theo Chỉ thị Khẩn cấp 25-02, CISA đã khuyến khích tất cả các tổ chức thực hiện các biện pháp tương tự để bảo vệ các hệ thống của họ trước các cuộc tấn công tiềm năng.

"Các rủi ro liên quan đến lỗ hổng Microsoft Exchange này kéo dài đến mọi tổ chức và lĩnh vực sử dụng môi trường này," Giám đốc tạm quyền CISA Madhu Gottumukkala cho biết.

"Khi các cơ quan liên bang bị bắt buộc, chúng tôi kêu gọi mạnh mẽ tất cả các tổ chức thực hiện các hành động trong Chỉ thị Khẩn cấp này."