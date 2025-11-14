# Kraken ransomware kiểm tra hiệu năng hệ thống để lựa chọn phương pháp mã hóa tối ưu

![Kraken ransomware benchmarks systems for optimal encryption choice](https://www.bleepstatic.com/content/hl-images/2025/02/12/ransomware-3.jpg)

Kraken ransomware, nhằm vào Windows, Linux/VMware ESXi, đang thử nghiệm các máy để kiểm tra tốc độ mà nó có thể mã hóa dữ liệu mà không làm quá tải hệ thống.

Theo các nhà nghiên cứu của Cisco Talos, tính năng của Kraken là một khả năng hiếm gặp sử dụng các tệp tạm thời để lựa chọn giữa mã hóa toàn bộ và mã hóa một phần dữ liệu.

Kraken xuất hiện vào đầu năm như sự tiếp nối của chiến dịch HelloKitty, và tiến hành các cuộc tấn công nhắm vào các mục tiêu lớn (big-game hunting), kèm theo đánh cắp dữ liệu để tống tiền kép.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Trên các trang rò rỉ dữ liệu của băng nhóm có liệt kê các nạn nhân từ Hoa Kỳ, Vương quốc Anh, Canada, Panama, Kuwait và Đan Mạch.

Các nhà nghiên cứu của Cisco lưu ý rằng nhiều đề cập trên trang của Kraken, cũng như sự tương đồng trong thông báo tiền chuộc, cho thấy mối liên hệ với ransomware HelloKitty hiện đã ngưng hoạt động, vốn đã [gained prominence](https://www.bleepingcomputer.com/news/security/hellokitty-ransomware-behind-cd-projekt-red-cyberattack-data-theft/) vào năm 2021 và [attempted a rebranding](https://www.bleepingcomputer.com/news/security/hellokitty-ransomware-rebrands-releases-cd-projekt-and-cisco-data/) sau khi [leak of its source code](https://www.bleepingcomputer.com/news/security/hellokitty-ransomware-source-code-leaked-on-hacking-forum/) xảy ra.

Bên cạnh hoạt động ransomware, Kraken cũng đã ra mắt một diễn đàn tội phạm mạng mới mang tên “The Last Haven Board” để tạo điều kiện cho các giao tiếp và trao đổi được cho là an toàn hơn.

![Kraken's extortion portal on the dark web](https://www.bleepstatic.com/images/news/u/1220909/2025/November/krakenblog(1).jpg)

**Cổng tống tiền của Kraken trên dark web**  
_Nguồn: BleepingComputer_

## Chuỗi tấn công của Kraken

Theo quan sát của Cisco, các cuộc tấn công bằng Kraken thường bắt đầu bằng việc khai thác các lỗ hổng SMB trên các tài sản có kết nối Internet, cung cấp cho tác nhân đe dọa một điểm dừng chân ban đầu.

Tiếp theo, kẻ xâm nhập trích xuất thông tin đăng nhập tài khoản admin và sử dụng chúng để tái xâm nhập môi trường qua Remote Desktop Protocol (RDP) và triển khai các công cụ Cloudflared và SSHFS.

Cloudflared được sử dụng để tạo một đường hầm ngược (reverse tunnel) từ máy nạn nhân về hạ tầng của kẻ tấn công, và SSHFS cho phép trích xuất dữ liệu thông qua các hệ thống tệp từ xa được gắn.

Sử dụng các đường hầm Cloudflared duy trì và RDP, các toán của Kraken dò tìm mạng bị xâm phạm và di chuyển ngang để tới mọi máy có thể truy cập nhằm đánh cắp dữ liệu quan trọng và chuẩn bị cho việc triển khai các nhị phân ransomware.

**Chuỗi lây nhiễm của Kraken**  
_Nguồn: Cisco_

## Thiết lập chế độ mã hóa

Khi lệnh mã hóa được phát ra, Kraken sẽ thực hiện một phép đo hiệu năng trên từng máy, các nhà nghiên cứu [cho biết](https://blog.talosintelligence.com/kraken-ransomware-group/).

Quy trình bao gồm việc tạo một tệp tạm với dữ liệu ngẫu nhiên, mã hóa nó trong một phép đo có thời gian, tính toán kết quả, và sau đó xóa tệp.

Dựa trên kết quả, cơ chế mã hóa quyết định liệu dữ liệu sẽ được mã hóa toàn bộ hay chỉ một phần.

**Hàm tính toán tốc độ**  
_Nguồn: Cisco_

Cisco Talos lưu ý rằng việc đánh giá khả năng của máy có thể giúp tiến nhanh tới giai đoạn cuối của cuộc tấn công và gây thiệt hại tối đa mà không kích hoạt cảnh báo do sử dụng tài nguyên quá mức.

Trước khi kích hoạt việc mã hóa thực tế, Kraken xóa shadow volumes và Recycle Bin và dừng các dịch vụ sao lưu đang chạy trên hệ thống.

Cisco giải thích rằng phiên bản Windows của Kraken có bốn mô-đun mã hóa:

1. **SQL database** – Xác định các instance của Microsoft SQL Server thông qua các khóa registry, tìm đường dẫn thư mục chứa tệp cơ sở dữ liệu của chúng, xác minh các đường dẫn và mã hóa các tệp dữ liệu SQL.
2. **Network share** – Liệt kê các chia sẻ mạng có thể truy cập thông qua WNet APIs, bỏ qua ADMIN$ và IPC$, và mã hóa tệp trên tất cả các chia sẻ khác có thể tiếp cận.
3. **Local drive** – Quét các ký tự ổ đĩa có sẵn, nhắm mục tiêu ổ gắn ngoài, ổ cố định và ổ từ xa, và mã hóa nội dung của chúng bằng các luồng công nhân (worker threads) riêng biệt.
4. **Hyper-V** – Sử dụng các lệnh PowerShell nhúng để liệt kê các VM, lấy đường dẫn ổ đĩa ảo của chúng, buộc dừng các VM đang chạy và mã hóa các tệp đĩa ảo liên quan.

Phiên bản Linux/ESXi liệt kê và buộc chấm dứt các máy ảo đang chạy để mở khóa tệp đĩa của chúng, sau đó thực hiện mã hóa đa luồng toàn bộ hoặc một phần sử dụng cùng logic đánh giá hiệu năng như phiên bản Windows.

Sau khi hoàn tất mã hóa, một script tự động sinh có tên '_bye\_bye.sh_' được thực thi để xóa mọi log, lịch sử shell, nhị phân Kraken, và cuối cùng là chính script đó.

Các tệp bị mã hóa được thêm phần mở rộng '.zpsc', và một ghi chú đòi tiền chuộc ('readme\_you\_ws\_hacked.txt') được thả vào các thư mục bị ảnh hưởng.

**Ghi chú tiền chuộc của Kraken**  
_Nguồn: Cisco_

Cisco lưu ý rằng trong một trường hợp, họ đã quan sát được yêu cầu tiền chuộc lên tới $1 triệu phải trả bằng Bitcoin.

Các chỉ số thoái bộ (IoC) hoàn chỉnh liên quan tới các cuộc tấn công Kraken có sẵn trên kho lưu trữ này: https://github.com/Cisco-Talos/IOCs/blob/main/2025/11/kraken-ransomware-group.txt