# Bài thử nghiệm ransomware AI-Slop lén vào VS Code marketplace

![Bài thử nghiệm ransomware AI-Slop lén vào VS Code marketplace](https://www.bleepstatic.com/content/hl-images/2025/03/13/VSCode.jpg)

Một tiện ích mở rộng độc hại với các khả năng ransomware cơ bản có vẻ được tạo ra với sự trợ giúp của AI, đã được xuất bản trên VS Code marketplace chính thức của Microsoft.

Được đặt tên là _susvsex_ và xuất bản bởi ‘_suspublisher18_,' chức năng độc hại của tiện ích này được quảng cáo công khai trong phần mô tả của nó.

Nhà nghiên cứu của Secure Annex, John Tuckner, đã phát hiện _susvsex_ và nói rằng nó là sản phẩm của “vibe coding” và còn xa mới tinh vi.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Mặc dù đã báo cáo tiện ích mở rộng và mô tả rõ ràng của nó, mô tả tiết lộ việc đánh cắp tập tin tới một máy chủ từ xa và mã hóa tất cả các tập tin bằng AES-256-CBC, Microsoft đã phớt lờ báo cáo của Tuckner và không gỡ bỏ nó khỏi registry của VS Code.

[![Tweet](https://www.bleepstatic.com/images/news/u/1220909/2025/November/tweet.jpg)](https://x.com/tuckner/status/1986232371650183204)

### Cách hoạt động của tiện ích mở rộng ransomware

Tiện ích mở rộng kích hoạt trên bất kỳ sự kiện nào, bao gồm khi cài đặt hoặc khi khởi chạy VS Code, khởi tạo file ‘extension.js’ chứa các biến được hardcoded (IP, khóa mã hóa, địa chỉ command-and-control).

“Nhiều giá trị này có chú thích cho thấy rằng mã không được viết trực tiếp bởi nhà xuất bản và rất có thể được sinh thông qua AI,” [nói](https://secureannex.com/blog/ransomvibe) Tuckner.

Khi kích hoạt, tiện ích gọi một hàm có tên _zipUploadAndEncrypt_ kiểm tra sự tồn tại của một file marker văn bản, và bắt đầu quy trình mã hóa.

Nó tạo một kho .ZIP các file trong thư mục mục tiêu được định nghĩa và gửi chúng ra địa chỉ C2 được hardcoded. Tất cả các file sau đó được thay thế bằng phiên bản đã được mã hóa.

**Quy trình đánh cắp dữ liệu**  
_Nguồn: Secure Annex_

Tucker phát hiện rằng tiện ích mở rộng liên tục kiểm tra một repository riêng tư trên GitHub để lấy lệnh, định kỳ kiểm tra file ‘index.html’ sử dụng token PAT để xác thực, và cố gắng thực thi bất kỳ lệnh nào ở đó.

Bằng cách lợi dụng PAT được hardcoded, nhà nghiên cứu có thể truy cập thông tin máy chủ và phát hiện chủ sở hữu repository có khả năng đặt tại Azerbaijan.

Vì tiện ích mở rộng là một mối đe dọa công khai, nó có thể là kết quả của một thí nghiệm để kiểm tra quy trình kiểm duyệt của Microsoft.

**Tiện ích ransomware trên VS Code marketplace**  
_Nguồn: BleepingComputer_

Secure Annex gọi _susvsex_ là một ‘AI slop’ với các hành động độc hại được tiết lộ trong file README, nhưng lưu ý rằng một vài tinh chỉnh sẽ khiến nó nguy hiểm hơn nhiều.

BleepingComputer đã liên hệ với Microsoft về vấn đề này, và chúng tôi đang chờ phản hồi từ họ. Trong khi _susvsex_ còn tồn tại vào thời điểm bài viết này được viết, nó không còn có sẵn vào thời điểm xuất bản.