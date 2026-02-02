# Các phiên bản MongoDB lộ thiên vẫn bị nhắm mục tiêu trong các cuộc tấn công tống tiền dữ liệu

![Các phiên bản MongoDB lộ thiên vẫn bị nhắm mục tiêu trong các cuộc tấn công tống tiền dữ liệu](https://www.bleepstatic.com/content/hl-images/2025/12/27/mongodb.jpg)

Một tác nhân đe dọa đang nhắm mục tiêu vào các phiên bản MongoDB lộ thiên trong các cuộc tấn công tống tiền dữ liệu tự động, yêu cầu khoản tiền chuộc thấp từ chủ sở hữu để khôi phục dữ liệu.

Kẻ tấn công tập trung vào các mục tiêu dễ dàng nhất, các cơ sở dữ liệu không an toàn do cấu hình sai cho phép truy cập không hạn chế. Khoảng 1.400 máy chủ lộ thiên đã bị xâm nhập và yêu cầu tiền chuộc khoảng $500 bằng Bitcoin.

Đến năm 2021, một loạt các cuộc tấn công đã xảy ra, xóa hàng nghìn cơ sở dữ liệu và yêu cầu tiền chuộc để khôi phục thông tin [[1](https://www.bleepingcomputer.com/news/security/over-12-000-mongodb-databases-deleted-by-unistellar-attackers/), [2](https://www.bleepingcomputer.com/news/security/surge-of-mongodb-ransom-attacks-use-gdpr-as-extortion-leverage/)]. Đôi khi, kẻ tấn công [chỉ xóa các cơ sở dữ liệu](https://www.bleepingcomputer.com/news/security/new-meow-attack-has-deleted-almost-4-000-unsecured-databases/) mà không yêu cầu tài chính.

[![Wiz](https://www.bleepstatic.com/c/w/MCP-Best-Practices-970x250.png)](https://www.wiz.io/lp/model-context-protocol-mcp-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FMCP-BestPractices-Cheat-Sheet&sfcid=701Py00000TCZuBIAX&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=MCP-Best-Practices) 

Một bài tập kiểm thử thâm nhập từ các nhà nghiên cứu tại công ty an ninh mạng Flare tiết lộ rằng các cuộc tấn công này vẫn tiếp diễn, chỉ ở quy mô nhỏ hơn.

Các nhà nghiên cứu đã phát hiện hơn 208.500 máy chủ MongoDB lộ thiên trên mạng công cộng. Trong số đó, 100.000 máy chủ để lộ thông tin hoạt động và 3.100 có thể truy cập được mà không cần xác thực.

![Kết quả tìm kiếm Shodan](https://www.bleepstatic.com/images/news/u/1220909/2026/January/shodan.jpg)

**Kết quả tìm kiếm Shodan**  
_Nguồn: Flare_

Gần một nửa (45.6%) trong số các cơ sở dữ liệu có quyền truy cập không hạn chế đã bị xâm nhập khi Flare kiểm tra. Cơ sở dữ liệu đã bị xóa sạch và một lời nhắn đòi tiền chuộc được để lại.

Phân tích các thông điệp tống tiền cho thấy hầu hết yêu cầu thanh toán 0.005 BTC trong vòng 48 giờ.

"Các tác nhân đe dọa yêu cầu thanh toán bằng Bitcoin (thường khoảng 0.005 BTC, tương đương $500-600 USD ngày nay) đến một địa chỉ ví được chỉ định, hứa hẹn khôi phục dữ liệu," [báo cáo của Flare cho biết](https://flare.io/learn/resources/blog/mongodb-ransom/).

"Tuy nhiên, không có gì đảm bảo rằng kẻ tấn công có dữ liệu hoặc sẽ cung cấp khóa giải mã hoạt động nếu được thanh toán."

**Mẫu thông điệp tống tiền**  
_Nguồn: Flare_

Chỉ có năm địa chỉ ví Bitcoin khác biệt trong các thông điệp tống tiền, và một trong số đó xuất hiện trong khoảng 98% trường hợp, cho thấy một tác nhân đe dọa duy nhất tập trung vào các cuộc tấn công này.

Flare cũng nhận xét về các phiên bản lộ thiên còn lại dường như chưa bị tấn công, mặc dù chúng đã bị phơi bày và bảo mật kém, giả thuyết rằng các trường hợp này có thể đã trả tiền chuộc cho kẻ tấn công.

Ngoài các biện pháp xác thực kém, các nhà nghiên cứu cũng phát hiện gần một nửa (95.000) tổng số máy chủ MongoDB tiếp xúc với internet chạy các phiên bản cũ dễ bị tổn thương bởi các lỗ hổng n-day. Tuy nhiên, tiềm năng khai thác hầu hết trong số này chỉ giới hạn ở các cuộc tấn công từ chối dịch vụ, không cung cấp khả năng thực thi mã từ xa.

**Phân phối CVEs trên 95.000 phiên bản lộ thiên**  
_Nguồn: Flare_

Flare khuyến nghị quản trị viên MongoDB tránh phơi bày các phiên bản ra công cộng trừ khi thực sự cần thiết, sử dụng xác thực mạnh, thực thi các quy tắc tường lửa và chính sách mạng Kubernetes chỉ cho phép các kết nối đáng tin cậy, đồng thời tránh sao chép cấu hình từ các hướng dẫn triển khai.

MongoDB nên được cập nhật lên phiên bản mới nhất và liên tục giám sát việc lộ thiên. Trong trường hợp lộ thiên, cần xoay vòng thông tin xác thực và kiểm tra nhật ký cho các hoạt động trái phép.