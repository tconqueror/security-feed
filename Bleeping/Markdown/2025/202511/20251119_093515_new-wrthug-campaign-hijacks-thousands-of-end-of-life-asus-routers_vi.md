# Chiến dịch WrtHug mới chiếm đoạt hàng nghìn bộ định tuyến ASUS hết vòng đời

![Chiến dịch WrtHug mới chiếm đoạt hàng nghìn bộ định tuyến ASUS hết vòng đời](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

Hàng nghìn bộ định tuyến ASUS WRT, chủ yếu là thiết bị đã hết vòng đời hoặc lỗi thời, đã bị chiếm đoạt trong một chiến dịch toàn cầu mang tên Operation WrtHug khai thác sáu lỗ hổng.

Trong sáu tháng qua, các trình quét tìm thiết bị ASUS bị xâm phạm trong Operation WrtHug đã xác định "xấp xỉ 50,000 IP độc nhất" trên toàn cầu.

Phần lớn các thiết bị bị xâm phạm có địa chỉ IP nằm ở Taiwan, trong khi các thiết bị còn lại phân bổ khắp Southeast Asia, Russia, Central Europe và United States.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Đáng chú ý, không có quan sát về nhiễm trong China, điều này có thể chỉ ra một tác nhân đe dọa xuất phát từ quốc gia này, nhưng các nhà nghiên cứu không tìm thấy đủ bằng chứng để khẳng định gán mác với độ tin cậy cao.

Theo các nhà nghiên cứu STRIKE của SecurityScorecard, dựa trên mục tiêu và phương thức tấn công, có thể tồn tại mối liên hệ giữa Operation WrtHug và chiến dịch AyySSHush, được GreyNoise ghi nhận lần đầu vào tháng Năm.

![WrtHug spread](https://www.bleepstatic.com/images/news/u/1220909/2025/November/map(3).jpg)

**WrtHug global spread**  
_Nguồn: SecurityScorecard_

## WrtHug attacks

Các cuộc tấn công bắt đầu bằng việc khai thác lỗ hổng chèn lệnh OS và các lỗ hổng đã biết khác trong bộ định tuyến ASUS WRT, chủ yếu là thiết bị dòng AC-series và AX-series.

Theo các nhà nghiên cứu STRIKE, chiến dịch WrtHug có thể tận dụng các vấn đề bảo mật sau trong các cuộc tấn công:

* **CVE-2023-41345/46/47/48** – OS command injection via token modules
* **CVE-2023-39780** – major command injection flaw (also used in the AyySSHush campaign)
* **CVE-2024-12912** – arbitrary command execution
* **CVE-2025-2492** – improper authentication control that can lead to unauthorized execution of functions

Trong số các lỗ hổng nêu trên, CVE-2025-2492 nổi bật là lỗ hổng duy nhất có điểm mức nghiêm trọng ở mức critical. Một thông báo bảo mật từ ASUS vào tháng Tư đã cảnh báo về mức độ nghiêm trọng của lỗ hổng và rằng nó có thể bị kích hoạt bởi một yêu cầu được tạo đặc biệt trên những bộ định tuyến có tính năng AiCloud được bật.

Trong một báo cáo hôm nay, SecurityScorecard cho biết "các kẻ tấn công dường như lợi dụng dịch vụ ASUS AiCloud trong trường hợp này để triển khai một bộ xâm nhập toàn cầu có mục tiêu."

Một chỉ báo bị xâm phạm cho chiến dịch này là sự hiện diện của một chứng chỉ TLS tự ký trong các dịch vụ AiCloud đã thay thế chứng chỉ chuẩn do ASUS tạo ra trên 99% các thiết bị bị xâm phạm. Chứng chỉ mới gây chú ý vì nó có thời hạn 100 năm, so với chứng chỉ gốc chỉ có hiệu lực 10 năm.

STRIKE sử dụng chứng chỉ độc nhất này để nhận diện 50,000 IP bị nhiễm.

**The malicious certificate**  
_Nguồn: SecurityScorecard_

Giống như trong chiến dịch AyySSHush, các kẻ tấn công không nâng cấp firmware của thiết bị bị xâm phạm, để mở cửa cho việc chiếm đoạt bởi các tác nhân đe dọa khác.

Dựa trên các chỉ báo bị xâm phạm, các nhà nghiên cứu xác định các thiết bị ASUS sau bị Operation WrtHug nhắm tới:

• ASUS Wireless Router 4G-AC55U  
• ASUS Wireless Router 4G-AC860U  
• ASUS Wireless Router DSL-AC68U  
• ASUS Wireless Router GT-AC5300  
• ASUS Wireless Router GT-AX11000  
• ASUS Wireless Router RT-AC1200HP  
• ASUS Wireless Router RT-AC1300GPLUS  
• ASUS Wireless Router RT-AC1300UHP

STRIKE tin rằng các bộ định tuyến bị xâm phạm có thể được sử dụng làm operational relay box (ORB) networks trong các hoạt động hack có nguồn gốc từ China như các nút chuyển tiếp ẩn, proxy và che giấu cơ sở hạ tầng command-and-control. Tuy nhiên, báo cáo không đi sâu vào các hoạt động sau khi xâm phạm và thiếu các chi tiết cụ thể.

ASUS đã phát hành các bản cập nhật bảo mật khắc phục tất cả các lỗ hổng được tận dụng trong các cuộc tấn công WrtHug, vì vậy chủ sở hữu bộ định tuyến nên nâng cấp firmware lên phiên bản mới nhất có sẵn.

Nếu thiết bị không còn được hỗ trợ, người dùng được khuyến nghị thay thế hoặc ít nhất tắt các tính năng truy cập từ xa.

ASUS gần đây cũng đã sửa CVE-2025-59367, một lỗ hổng bypass xác thực ảnh hưởng một số mẫu dòng AC-series, mặc dù chưa bị khai thác nhưng có thể được thêm vào kho vũ khí của các kẻ tấn công trong tương lai.