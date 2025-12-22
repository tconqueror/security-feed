# Docker Hardened Images hiện là mã nguồn mở và có sẵn miễn phí

![Docker](https://www.bleepstatic.com/content/hl-images/2022/04/21/Docker_header.jpg)

Hơn 1.000 Docker Hardened Images (DHI) hiện được cung cấp miễn phí và là mã nguồn mở cho những người phát triển phần mềm, theo giấy phép Apache 2.0.

Docker là một nền tảng phổ biến cho phép các nhà phát triển xây dựng, kiểm thử và triển khai ứng dụng nhanh chóng bên trong các container images bao gồm các phụ thuộc cần thiết, cho phép kết quả có thể dự đoán và lặp lại trên nhiều hệ thống và môi trường khác nhau.

DHIs, ra mắt vào tháng Năm năm nay, là các Docker base images an toàn, tối giản, sẵn sàng cho môi trường sản xuất được Docker duy trì trực tiếp. Chúng được thiết kế để giảm bề mặt tấn công và rủi ro chuỗi cung ứng ở lớp container.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

DHIs được chạy ở chế độ rootless, đã loại bỏ các thành phần không cần thiết, không có lỗ hổng đã biết và hỗ trợ tiêu chuẩn Vulnerability Exploitability eXchange (VEX) để quản lý an ninh gọn nhẹ hơn.

Chúng cũng được đảm bảo sẽ đẩy các bản sửa cho các lỗ hổng mới trong các thành phần DHI hiện có trong vòng 7 ngày kể từ khi được công bố.

Vào tháng Mười, đội ngũ Docker đã thông báo rằng họ sẽ [mở quyền truy cập không giới hạn](https://www.bleepingcomputer.com/news/security/docker-makes-hardened-images-catalog-affordable-for-small-businesses/) cho toàn bộ danh mục DHI gồm 1.000 image cho tất cả các đội phát triển và cũng cung cấp dùng thử miễn phí 30 ngày cho tất cả người đăng ký.

Tuy nhiên, Docker đã quyết định chuyển DHIs từ một dịch vụ thương mại sang cung cấp miễn phí không cần đăng ký cho tất cả các nhà phát triển.

“Ngày hôm nay, chúng tôi đang thiết lập một tiêu chuẩn mới cho ngành bằng cách làm cho DHI được cung cấp miễn phí và là mã nguồn mở cho mọi người xây dựng phần mềm. Tất cả 26 Million+ developers trong hệ sinh thái container,” [đọc thông báo](https://www.docker.com/blog/docker-hardened-images-for-every-developer/).

“DHI hoàn toàn mở và miễn phí để sử dụng, chia sẻ và phát triển mà không có bất ngờ về giấy phép, được bảo trợ bởi giấy phép Apache 2.0. DHI giờ đây cung cấp cho thế giới một nền tảng an toàn, tối giản, sẵn sàng cho sản xuất ngay từ lần pull đầu tiên,” công ty cho biết.

Docker nhấn mạnh rằng động thái này không đi kèm với giảm bớt các tiêu chuẩn an ninh cho DHI, vì các image vẫn có thể xác minh bằng SBOM, các build cung cấp nguồn gốc SLSA Build Level 3, và mỗi image đều đi kèm bằng chứng về tính xác thực.

Tuy nhiên, cam kết vá CVE nghiêm trọng trong vòng 7 ngày (SLA) vẫn là đặc quyền dành cho hạng thương mại, DHI Enterprise, mà vẫn đang được cung cấp. Các bản vá vẫn sẽ được cung cấp cho hạng miễn phí, nhưng không trong một khoảng thời gian xác định trước.

Về DHI Enterprise và thời gian để sửa lỗi, Docker cho biết họ đặt mục tiêu giảm xuống còn một ngày hoặc thậm chí ngắn hơn. Hạng thương mại cũng cho phép sửa đổi các image DHI, cấu hình runtime và cài đặt các công cụ bổ sung.

Người dùng Docker có thể truy cập toàn bộ danh mục DHI và các tùy chọn đăng ký [từ đây](https://www.docker.com/products/hardened-images/).