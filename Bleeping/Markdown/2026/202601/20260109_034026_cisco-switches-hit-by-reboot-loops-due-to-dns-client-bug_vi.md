# Các switch Cisco gặp vòng lặp khởi động lại do lỗi DNS client

![Cisco](https://www.bleepstatic.com/content/hl-images/2024/07/18/Cisco.jpg)

Theo các báo cáo do BleepingComputer thu thập, nhiều mẫu switch Cisco đột ngột gặp vòng lặp khởi động lại sau khi ghi nhận lỗi nghiêm trọng từ DNS client.

Bắt đầu khoảng 2 giờ sáng, một lỗi firmware trong dịch vụ DNS client nội bộ của các switch đã coi các lỗi tra cứu DNS là lỗi nghiêm trọng, khiến các thiết bị bị ảnh hưởng khởi động lại liên tục.

Các switch bị ảnh hưởng ghi nhận các lỗi nghiêm trọng tương tự như sau trước khi khởi động lại:

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

```
DNS_CLIENT - SRCADDRFAIL - Result is 2. Failed to identify address for specified name 'www.cisco.com.', requested addr type 2.    ***** FATAL ERROR *****   Reporting Task: DNSC. [debug data] ***** END OF FATAL ERROR *****   

```

Dựa trên các báo cáo từ quản trị viên đã liên hệ với BleepingComputer, các thảo luận trên Reddit và các bài đăng trên diễn đàn Cisco Community \[[1](https://community.cisco.com/t5/switches-small-business/cisco-cbs250-and-c1200-dns-crash/td-p/5359999), [2](https://community.cisco.com/t5/switches-small-business/got-fatal-error-cbs350-24t-4g/td-p/5359883?utm%5Fsource=chatgpt.com)\] , các lỗi nghiêm trọng bắt nguồn từ tác vụ DNSC (DNS Client) và xảy ra khi các switch cố gắng phân giải "www.cisco.com" và các máy chủ thời gian NTP.

Các quản trị viên báo cáo vòng lặp khởi động lặp lại mỗi vài phút, gây gián đoạn nghiêm trọng hoạt động mạng.

“Chu kỳ lặp lại mỗi vài phút. Điều này rõ ràng gây gián đoạn nghiêm trọng và tôi sẽ không thể duy trì hoạt động như thế này trong thời gian dài,” một khách hàng Cisco viết trên [Reddit](https://www.reddit.com/r/Cisco/comments/1q7h9kc/sg550x%5Fseries%5Fswitches%5Fnew%5Ffatal%5Ferrors/).

Theo các báo cáo, lỗi dường như ảnh hưởng tới nhiều mẫu switch Cisco, bao gồm:

* Cisco CBS250 series
* Cisco CBS350 series (including the CBS350-24P-4G)
* Cisco Catalyst C1200 series
* Cisco SG350
* Cisco SG350X
* Cisco SG550X series

Một số quản trị viên báo cáo rằng các lỗi bắt đầu vào cùng thời điểm trên các mạng khác nhau, gợi ý rằng sự cố được kích hoạt toàn cầu hoặc liên quan đến điều kiện dựa trên thời gian.

Mặc dù Cisco chưa công bố nguyên nhân gốc rễ, BleepingComputer được biết bộ phận hỗ trợ của Cisco đã thừa nhận sự cố với ít nhất một khách hàng, cho biết vấn đề ảnh hưởng tới các switch CBS, SG và Catalyst 1200/1300.

Hiện tại, các quản trị viên đã tìm được các biện pháp khắc phục tạm thời để dừng vòng lặp khởi động, bao gồm vô hiệu hóa phân giải DNS, vô hiệu hóa SNTP hoặc đồng bộ thời gian, và chặn truy cập internet đi ra từ các giao diện quản lý switch.

Nhiều người dùng báo cáo rằng vô hiệu hóa cấu hình DNS đã dừng vòng lặp khởi động, ngay cả khi các máy chủ DNS có thể truy cập và hoạt động bình thường. Trong các bài đăng trên diễn đàn Cisco Community, người dùng cũng xác nhận rằng loại bỏ việc phân giải DNS đã giải quyết vòng lặp khởi động.

BleepingComputer đã liên hệ với Cisco để yêu cầu bình luận và sẽ cập nhật bài viết này khi có thêm thông tin.