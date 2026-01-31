# Nhà nghiên cứu tiết lộ bằng chứng về việc ảnh từ hồ sơ Instagram riêng tư bị rò rỉ

![Instagram](https://www.bleepstatic.com/content/hl-images/2023/12/20/instagram.jpg)

Một nhà nghiên cứu bảo mật đã công bố bằng chứng chi tiết cho thấy một số hồ sơ Instagram riêng tư trả về liên kết đến ảnh người dùng cho những khách truy cập chưa được xác thực.

Tính năng tài khoản riêng tư của Instagram được thiết kế để hạn chế xem ảnh, video, stories và reels chỉ cho những người theo dõi đã được phê duyệt. Tuy nhiên, phát hiện của nhà nghiên cứu cho thấy trong một số trường hợp, nội dung hồ sơ riêng tư đã được nhúng vào các phản hồi máy chủ có thể truy cập công khai.

Theo nhà nghiên cứu, Meta đã khắc phục vấn đề sau khi báo cáo của ông được gửi đi nhưng sau đó đóng báo cáo với nhận định "không áp dụng", nói rằng không thể tái tạo lỗ hổng này.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

## Hồ sơ Instagram riêng tư rò rỉ ảnh

Nhà nghiên cứu bảo mật Jatin Banga gần đây đã chứng minh cách một số hồ sơ Instagram riêng tư rò rỉ liên kết đến ảnh riêng tư từ các tài khoản này - ngay trong thân phản hồi HTML.

Khi được truy cập bởi người dùng chưa xác thực từ một số thiết bị di động, hồ sơ Instagram riêng tư (chẳng hạn như tài khoản do nhà nghiên cứu tạo [_https://instagram.com/jatin.py_](https://www.instagram.com/jatin.py)) hiển thị thông điệp tiêu chuẩn: "Tài khoản này là riêng tư. Hãy theo dõi để xem ảnh và video của họ."

![A sample private Instagram profile when accessed by an unauthenticated user](https://www.bleepstatic.com/images/news/u/1164866/2026/Jan/Instagram-private-profiles-bug/jatin-py-profile.jpeg)

**Ví dụ về hồ sơ Instagram riêng tư khi được truy cập bởi người dùng chưa xác thực**

Tuy nhiên, trong mã nguồn HTML của các hồ sơ bị ảnh hưởng, liên kết đến một số ảnh riêng tư đã được nhúng vào phản hồi trang.

Trong [ví dụ](https://github.com/jatin-dot-py/instagram-private-bypass/blob/main/sample%5Fresponse.html) của Banga, đối tượng JSON _polaris\_timeline\_connection_ được trả về trong HTML chứa các liên kết CDN đã mã hóa đến các bức ảnh đáng lẽ không thể truy cập được.

**Mã nguồn HTML trả về liên kết đến ảnh riêng tư**

Video minh họa (PoC) được Banga chia sẻ và nhúng bên dưới thể hiện lỗ hổng rò rỉ dữ liệu đang hoạt động.

Bằng cách giới hạn kiểm tra chính thức trên các hồ sơ thử nghiệm riêng tư mà Banga đã tạo hoặc được phép sử dụng rõ ràng, ông nhận thấy ít nhất 28% hồ sơ đã trả về liên kết đến ảnh riêng tư:

## Meta âm thầm khắc phục vấn đề sau báo cáo, nhà nghiên cứu cho biết

Nhà nghiên cứu tuyên bố rằng ông đã chia sẻ phát hiện của mình với công ty mẹ của Instagram là Meta từ ngày 12 tháng 10 năm 2025.

Ban đầu Meta phân loại vấn đề là lỗi bộ nhớ đệm CDN, một cách mô tả mà nhà nghiên cứu không đồng ý.

"Đây không phải là vấn đề bộ nhớ đệm CDN - hệ thống phụ trợ của Instagram đã không kiểm tra xác thực trước khi tạo phản hồi," [Banga viết](http://medium.com/@jatin.b.rx3/i-found-a-bug-that-exposed-private-instagram-posts-to-anyone-eebb7923f7e3), mô tả nó như một lỗi xác thực phía máy chủ.

Banga đã tạo báo cáo lỗi thứ hai để làm rõ vấn đề, nhưng không đạt được giải pháp thỏa đáng với Meta dù có cuộc thảo luận kéo dài nhiều ngày.

Theo nhà nghiên cứu, sau nhiều lần trao đổi, trường hợp đã bị đóng với lý do "không áp dụng" nhưng lỗ hổng ngừng hoạt động vào khoảng ngày 16 tháng 10.

"Thời gian công bố phối hợp tiêu chuẩn là 90 ngày. Tôi đã cho Meta 102 ngày và nhiều lần yêu cầu hỗ trợ. Lỗ hổng đã ngừng hoạt động trên tất cả các tài khoản tôi kiểm tra - dù không có phân tích nguyên nhân gốc rễ từ Meta, không có xác nhận rằng vấn đề cơ bản thực sự đã được giải quyết," ông tiếp tục.

Ngoài việc công bố và [kho lưu trữ GitHub](https://github.com/jatin-dot-py/instagram-private-bypass/) ghi lại bằng chứng rộng về lỗ hổng và liên lạc với Meta, Banga đã chia sẻ thêm tài liệu với BleepingComputer để chứng minh sự tồn tại của lỗ hổng.

Chúng tôi đã hỏi Banga tại sao ông không lưu trữ hồ sơ riêng tư thử nghiệm bằng dịch vụ công cộng như Wayback Machine của Internet Archive, vốn có thể giữ lại mã nguồn HTML với các liên kết đến ảnh riêng tư, từ đó xác nhận rõ ràng sự tồn tại của lỗi.

"Wayback Machine không gửi User-Agent và Headers di động cụ thể cần thiết để kích hoạt lỗ rò rỉ phía máy chủ này, vì vậy trình thu thập của họ không thể ghi nhận nó," nhà nghiên cứu giải thích với BleepingComputer.

Trong [thư tín đã công bố](http://github.com/jatin-dot-py/instagram-private-bypass/tree/main/official%5Fcommunication/pdfs), một nhà phân tích sàng lọc lỗ hổng của Meta đã viết:

**Phản hồi của Meta về lỗi rò rỉ hồ sơ riêng tư Instagram** ([Jatin B.](https://github.com/jatin-dot-py/instagram-private-bypass/blob/main/official%5Fcommunication/pdfs/Case%5F1838100803582037.pdf))

Cuối cùng, trong quá trình trò chuyện, nhà phân tích cho biết:

"Việc một vấn đề không thể tái tạo được sửa không thay đổi thực tế là nó không thể tái tạo được vào thời điểm đó. Ngay cả khi vấn đề có thể tái tạo, có thể một thay đổi đã được thực hiện để sửa một vấn đề khác và vấn đề này đã được sửa như một tác dụng phụ ngoài ý muốn."

"Tôi muốn nhấn mạnh rằng tôi không theo đuổi tiền thưởng ở đây. Bằng cách công khai tiết lộ này, tôi đã từ bỏ mọi cơ hội nhận phần thưởng," Banga nói với BleepingComputer qua email.

"Mục tiêu là sự minh bạch. Meta đã vá lỗi rò rỉ quyền riêng tư nghiêm trọng 48-96 giờ sau báo cáo của tôi nhưng từ chối thừa nhận, bác bỏ nó như một 'tác dụng phụ ngoài ý muốn.' Sự cẩu thả và miễn cưỡng điều tra nguyên nhân gốc rễ thực sự - bất chấp việc có nhật ký - mới là vấn đề thực sự."

"Không ai biết lỗ hổng này đã bị khai thác trong bao lâu, vì nó không quá khó để tìm thấy."

BleepingComputer đã liên hệ với Meta để bình luận ba lần riêng biệt trước thời hạn xuất bản nhưng không nhận được phản hồi.