# Microsoft làm gián đoạn các cuộc tấn công ransomware nhắm vào người dùng Teams

![Microsoft](https://www.bleepstatic.com/content/hl-images/2025/03/12/Microsoft_headpic.jpg)

Microsoft đã làm gián đoạn một làn sóng các cuộc tấn công Rhysida ransomware vào đầu tháng Mười bằng cách thu hồi hơn 200 chứng chỉ được sử dụng để ký các trình cài đặt Teams độc hại.

Vanilla Tempest, nhóm mối đe dọa đứng sau các cuộc tấn công, đã sử dụng các tên miền bắt chước Microsoft Teams, chẳng hạn như teams-install[.]top, teams-download[.]buzz, teams-download[.]top và teams-install[.]run, để phân phối các tệp MSTeamsSetup.exe giả đã lây nhiễm nạn nhân bằng cửa hậu Oyster.

Các cuộc tấn công này là một phần của một [chiến dịch malvertising cuối tháng 9](https://www.bleepingcomputer.com/news/security/fake-microsoft-teams-installers-push-oyster-malware-via-malvertising/) đã sử dụng quảng cáo trên công cụ tìm kiếm và SEO poisoning để đẩy các trình cài đặt Microsoft Teams giả, đặt cửa hậu lên các thiết bị Windows bằng phần mềm độc hại Oyster (còn được biết đến với tên Broomstick và CleanUpLoader).

Các quảng cáo và các tên miền dẫn đến các trang web mạo danh trang tải xuống Microsoft Teams. Nhấp vào liên kết tải xuống được hiển thị nổi bật sẽ tải về một tệp có tên "MSTeamsSetup.exe," cùng tên tệp được sử dụng bởi trình cài đặt Teams chính thức.

Khi được thực thi, các trình cài đặt Teams độc hại khởi chạy một loader đã triển khai phần mềm độc hại Oyster được ký, cho phép các tác nhân mối đe dọa truy cập từ xa vào hệ thống bị nhiễm và cho phép họ đánh cắp tệp, thực thi lệnh và thả thêm các payload độc hại.

![Trang tải xuống Microsoft Teams giả](https://www.bleepstatic.com/images/news/security/malvertising/microsoft-teams/teams-phishing-site.jpg)

_Trang tải xuống Microsoft Teams giả (Blackpoint)_

Vanilla Tempest đã sử dụng cửa hậu Oyster từ tháng 6 năm 2025, lợi dụng Trusted Signing cùng với dịch vụ ký mã từ SSL.com, DigiCert, và GlobalSign bắt đầu từ tháng 9 năm 2025.

Phần mềm độc hại này, lần đầu được phát hiện vào giữa năm 2023, cũng đã được sử dụng trong các [cuộc tấn công Rhysida trước đây](https://www.threatdown.com/blog/rhysida-using-oyster-backdoor-to-deliver-ransomware/) để xâm nhập mạng lưới doanh nghiệp và thường được [phân phối](https://arcticwolf.com/resources/blog/malvertising-campaign-delivers-oyster-broomstick-backdoor-via-seo-poisoning-trojanized-tools/) [thông qua malvertising](https://arcticwolf.com/resources/blog/malvertising-campaign-delivers-oyster-broomstick-backdoor-via-seo-poisoning-trojanized-tools/) mạo danh các công cụ CNTT như PuTTY và WinSCP.

"Vanilla Tempest, được theo dõi bởi các nhà cung cấp an ninh khác dưới tên VICE SPIDER và Vice Society, là một tác nhân có động cơ tài chính tập trung vào việc triển khai ransomware và trích xuất dữ liệu để tống tiền," [Microsoft cho biết](https://x.com/MsftSecIntel/status/1978592789857251490).

"Tác nhân mối đe dọa đã sử dụng nhiều payload ransomware khác nhau, bao gồm BlackCat, Quantum Locker và Zeppelin, nhưng gần đây chủ yếu triển khai Rhysida ransomware."

Hoạt động ít nhất từ tháng 6 năm 2021, Vanilla Tempest thường xuyên tấn công các tổ chức trong các ngành giáo dục, chăm sóc sức khỏe, CNTT và sản xuất. Khi hoạt động dưới tên [Vice Society](https://www.bleepingcomputer.com/tag/vice-society/), tác nhân mối đe dọa từng được biết đến là sử dụng nhiều giống ransomware, bao gồm Hello Kitty/Five Hands và Zeppelin ransomware.

Ba năm trước, vào tháng 9 năm 2022, FBI và CISA đã phát hành một khuyến cáo chung cảnh báo rằng [Vice Society đã nhắm mục tiêu không tương xứng](https://www.bleepingcomputer.com/news/security/fbi-warns-of-vice-society-ransomware-attacks-on-school-districts/) vào ngành giáo dục Hoa Kỳ sau khi băng nhóm tội phạm mạng xâm nhập Los Angeles Unified (LAUSD), quận trường lớn thứ hai ở Hoa Kỳ.