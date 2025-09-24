# SolarWinds phát hành bản vá khẩn cấp cho lỗ hổng thực thi mã từ xa nghiêm trọng CVE-2025-26399

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhFO1p2qWLIaLkEjXvBexuWL8MRzvAn8rhnkmU8V%5F%5FGge5ajRgr8Hz1rgLcSPqi5igX4xCZ5%5FNMO8XjmonjH2PXyDK7ADHR3zlRfwUDZxrQDoIV5LkcVG7LseBYfLT5rkBM8bC1kyWcB5%5F2ndJ3Ijt-1LYzjr5D9lIIx2xM%5F4JtRQfPsI8mFvhzUtFYxnGi/s728-rw-e365/solar.jpg)

SolarWinds đã phát hành các bản vá khẩn cấp để giải quyết một lỗ hổng bảo mật nghiêm trọng ảnh hưởng đến phần mềm Web Help Desk của hãng, nếu bị khai thác thành công, có thể cho phép kẻ tấn công thực thi lệnh tùy ý trên các hệ thống dễ bị tổn thương.

Lỗ hổng, được theo dõi bằng mã **CVE-2025-26399** (điểm CVSS: 9.8), được mô tả là một trường hợp deserialization dữ liệu không tin cậy có thể dẫn đến thực thi mã. Nó ảnh hưởng đến SolarWinds Web Help Desk 12.8.7 và tất cả các phiên bản trước đó.

"SolarWinds Web Help Desk được phát hiện có thể bị tấn công bởi một lỗ hổng deserialization AjaxProxy thực thi mã từ xa không yêu cầu xác thực mà, nếu bị khai thác, sẽ cho phép kẻ tấn công chạy lệnh trên máy chủ," SolarWinds [said](https://www.solarwinds.com/trust-center/security-advisories/cve-2025-26399) trong một thông báo phát hành vào ngày 17 tháng 9 năm 2025.

[](https://thehackernews.uk/exec-guide-d)

Một nhà nghiên cứu ẩn danh làm việc với Trend Micro Zero Day Initiative (ZDI) đã được ghi nhận là người phát hiện và báo cáo lỗ hổng.

SolarWinds cho biết CVE-2025-26399 là một bypass của bản vá cho CVE-2024-28988 (điểm CVSS: 9.8), vốn là một bypass cho [CVE-2024-28986](https://thehackernews.com/2024/08/solarwinds-releases-patch-for-critical.html) (điểm CVSS: 9.8) mà công ty đã xử lý lần đầu vào tháng 8 năm 2024.

" Lỗ hổng này cho phép kẻ tấn công từ xa thực thi mã tùy ý trên các cài đặt SolarWinds Web Help Desk bị ảnh hưởng. Không cần xác thực để khai thác lỗ hổng này," theo một [ZDI advisory](https://www.zerodayinitiative.com/advisories/ZDI-25-407/) cho CVE-2024-28988.

" Lỗi cụ thể tồn tại trong AjaxProxy. Vấn đề xuất phát từ việc thiếu kiểm tra hợp lệ đối với dữ liệu do người dùng cung cấp, điều này có thể dẫn đến deserialization dữ liệu không tin cậy. Kẻ tấn công có thể lợi dụng lỗ hổng này để thực thi mã trong ngữ cảnh của SYSTEM."

Mặc dù không có bằng chứng cho thấy lỗ hổng đã bị khai thác trên thực tế, người dùng được khuyến cáo cập nhật các phiên bản của họ lên [SolarWinds Web Help Desk 12.8.7 HF1](https://documentation.solarwinds.com/en/success%5Fcenter/whd/content/release%5Fnotes/whd%5F12-8-7-hotfix-1%5Frelease%5Fnotes.htm) để được bảo vệ tốt nhất.

Cần nhấn mạnh rằng lỗi gốc CVE-2024-28986 đã được thêm vào danh mục Known Exploited Vulnerabilities (KEV) của U.S. Cybersecurity and Infrastructure Security Agency (CISA) ngay sau khi công khai. Hiện chưa có thông tin công khai về bản chất của các cuộc tấn công lợi dụng lỗi này.

[](https://thehackernews.uk/cis-security-suite)

"SolarWinds là một tên tuổi không cần giới thiệu trong giới CNTT và an ninh mạng. Vụ tấn công chuỗi cung ứng khét tiếng năm 2020, được gán cho Russia's Foreign Intelligence Service (SVR), đã cho phép truy cập kéo dài hàng tháng vào nhiều cơ quan chính phủ phương Tây và để lại dấu ấn lâu dài trong ngành," Ryan Dewhurst, người đứng đầu proactive threat intelligence tại watchTowr, nói trong một tuyên bố.

"Nhìn lại tới 2024: một lỗ hổng deserialization từ xa không yêu cầu xác thực (CVE-2024-28986) đã được vá... rồi lại được vá tiếp (CVE-2024-28988). Và giờ, chúng ta lại có một bản vá nữa (CVE-2025-26399) xử lý cùng một lỗi.

"Third time's the charm? Lỗi ban đầu đã bị khai thác tích cực ngoài thực địa, và mặc dù chúng tôi chưa biết về việc khai thác tích cực của bypass vá mới nhất này, lịch sử cho thấy chỉ là vấn đề thời gian."