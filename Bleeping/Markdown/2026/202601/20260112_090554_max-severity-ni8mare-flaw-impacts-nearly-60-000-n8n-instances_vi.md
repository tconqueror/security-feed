# Lỗ hổng Ni8mare mức độ nghiêm trọng tối đa ảnh hưởng gần 60.000 instance n8n

![n8n](https://www.bleepstatic.com/content/hl-images/2026/01/12/n8n-headpic.jpg)

Gần 60.000 instance n8n bị phơi bày trực tuyến vẫn chưa được vá trước một lỗ hổng mức độ nghiêm trọng tối đa mang tên "Ni8mare".

n8n là một nền tảng tự động hóa workflow mã nguồn mở cho phép người dùng kết nối các ứng dụng và dịch vụ khác nhau thông qua các connector có sẵn và một giao diện trực quan theo node để tự động hóa các tác vụ lặp đi lặp lại mà không cần viết mã.

Nền tảng tự động hóa này được sử dụng rộng rãi trong phát triển AI để [tự động hóa việc thu thập dữ liệu](https://n8n.io/integrations/solve-data/) và xây dựng AI agents và [RAG pipelines](https://blog.n8n.io/rag-pipeline/). Nó có hơn 100 triệu lượt pull trên Docker Hub và hơn 50.000 lượt tải xuống hàng tuần [trên npm](https://www.npmjs.com/package/n8n?activeTab=versions).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Vì n8n hoạt động như một trung tâm tự động hóa, nó thường lưu trữ khóa API, token OAuth, thông tin xác thực cơ sở dữ liệu, truy cập lưu trữ đám mây, bí mật CI/CD và dữ liệu kinh doanh, khiến nó trở thành mục tiêu hấp dẫn cho các tác nhân đe dọa.

Được theo dõi dưới mã [CVE-2026-21858](https://nvd.nist.gov/vuln/detail/CVE-2026-21858), lỗ hổng bảo mật này phát sinh từ một điểm yếu trong việc xác thực đầu vào không đúng cách cho phép kẻ tấn công từ xa, không xác thực chiếm quyền kiểm soát các instance n8n triển khai cục bộ sau khi có được quyền truy cập vào các tập tin trên máy chủ nền tảng.

"Một workflow dễ bị tấn công có thể cho phép một kẻ tấn công từ xa không xác thực truy cập. Điều này có thể dẫn tới việc lộ thông tin được lưu trữ trên hệ thống và có thể cho phép thỏa hiệp thêm tùy thuộc vào cấu hình triển khai và cách sử dụng workflow," [nhóm n8n giải thích](https://community.n8n.io/t/security-advisory-security-vulnerability-in-n8n-versions-1-65-1-120-4/247305).

"Một instance n8n có thể dễ bị tấn công nếu nó có một workflow đang hoạt động với trigger Form Submission chấp nhận một phần tử file, và một node Form Ending trả về một tệp nhị phân."

Nhóm nghiên cứu Cyera, những người phát hiện ra Ni8mare và báo cáo với n8n vào đầu tháng 11, cho biết lỗ hổng là một sự nhầm lẫn về content-type trong cách n8n phân tích dữ liệu, có thể bị lợi dụng để làm lộ các bí mật được lưu trữ trên instance, giả mạo cookie phiên để vượt qua xác thực, chèn các tệp nhạy cảm vào workflow, hoặc thậm chí thực thi lệnh tùy ý.

Trong cuối tuần, nhóm giám sát an ninh Internet Shadowserver phát hiện [105,753 instance chưa được vá bị phơi bày trực tuyến](https://bsky.app/profile/shadowserver.bsky.social/post/3mc3tfgjqk22o) và 59,558 [vẫn còn phơi bày](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=other%5Frange&d1=2026-01-08&d2=2026-01-11&source=http%5Fvulnerable&source=http%5Fvulnerable6&tag=cve-2026-21858%2B&dataset=unique%5Fips&limit=100&group%5Fby=geo&stacking=stacked&auto%5Fupdate=on) vào Chủ nhật, với hơn 28.000 IP được tìm thấy ở Hoa Kỳ và hơn 21.000 ở châu Âu.

![Vulnerable n8n instances exposed online](https://www.bleepstatic.com/images/news/u/1109292/2026/Vulnerable%20n8n%20instances%20exposed%20online.jpg)

_Các instance n8n dễ bị tấn công được phơi bày trực tuyến (Shadowserver)_

Để ngăn chặn các cuộc tấn công tiềm năng, quản trị viên được khuyến nghị nâng cấp các instance n8n lên phiên bản 1.121.0 hoặc mới hơn càng sớm càng tốt.

Mặc dù các nhà phát triển n8n cho biết hiện không có cách khắc phục chính thức cho Ni8mare, những quản trị viên không thể nâng cấp ngay có thể chặn các cuộc tấn công tiềm năng bằng cách hạn chế hoặc vô hiệu hóa các endpoint webhook và form có thể truy cập công khai.

Nhóm n8n cũng cung cấp [mẫu workflow này](https://community.n8n.io/uploads/short-url/cpAkGQqvp9xCkofHOVr7J8oSSvC.json) cho các quản trị viên muốn quét các instance của họ để tìm các workflow có khả năng bị tổn thương.