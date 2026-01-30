# eScan xác nhận máy chủ cập nhật bị xâm phạm để đẩy bản cập nhật độc hại

![Hacker shhing](https://www.bleepstatic.com/content/hl-images/2021/12/28/hacker.jpg)

MicroWorld Technologies, nhà sản xuất sản phẩm antivirus eScan, đã xác nhận rằng một trong các máy chủ cập nhật của họ bị xâm phạm và được sử dụng để phân phối bản cập nhật trái phép - sau này được phân tích là độc hại - cho một số lượng nhỏ khách hàng vào đầu tháng này.

Tệp này đã được phân phối cho khách hàng đã tải xuống bản cập nhật từ cụm cập nhật khu vực trong khoảng thời gian hai giờ vào ngày 20 tháng 1 năm 2026.

eScan cho biết cơ sở hạ tầng bị ảnh hưởng đã được cách ly và xây dựng lại, thông tin xác thực đã được luân chuyển, đồng thời biện pháp khắc phục đã được cung cấp cho khách hàng bị ảnh hưởng.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Công ty an ninh Morphisec đã công bố riêng một báo cáo kỹ thuật phân tích hoạt động độc hại được quan sát trên các điểm cuối của khách hàng, mà họ liên kết với các bản cập nhật được phân phối từ cơ sở hạ tầng cập nhật của eScan trong cùng khung thời gian.

Morphisec tuyên bố rằng họ đã phát hiện hoạt động độc hại vào ngày 20 tháng 1 năm 2026 và sau đó liên hệ với eScan. MicroWorld Technologies nói với BleepingComputer rằng họ tranh chấp các tuyên bố của Morphisec rằng họ là người đầu tiên phát hiện hoặc báo cáo sự cố.

Theo eScan, công ty đã phát hiện vấn đề nội bộ vào ngày 20 tháng 1 thông qua giám sát và báo cáo của khách hàng, cách ly cơ sở hạ tầng bị ảnh hưởng trong vòng vài giờ và đưa ra thông báo an ninh vào ngày 21 tháng 1. eScan cho biết Morphisec đã liên hệ với công ty sau đó, sau khi công bố các tuyên bố công khai về sự cố.

eScan cũng tranh chấp các tuyên bố rằng khách hàng bị ảnh hưởng không biết về vấn đề, nói rằng họ đã thực hiện thông báo chủ động và tiếp cận trực tiếp với khách hàng bị ảnh hưởng trong khi biện pháp khắc phục đang được hoàn thiện.

## Cơ sở hạ tầng cập nhật bị xâm phạm

Trong thông báo của mình, eScan phân loại sự cố này là sự cố truy cập cơ sở hạ tầng cập nhật, nói rằng việc truy cập trái phép vào cấu hình máy chủ cập nhật khu vực đã cho phép một tệp trái phép được đặt vào đường dẫn phân phối cập nhật.

"Việc truy cập trái phép vào một trong các cấu hình máy chủ cập nhật khu vực của chúng tôi đã dẫn đến việc một tệp không chính xác (tệp nhị phân cấu hình bản vá/bản cập nhật bị hỏng) được đặt vào đường dẫn phân phối cập nhật," trích một thông báo được MicroWorld Technologies chia sẻ với BleepingComputer.

"Tệp này đã được phân phối cho khách hàng tải xuống bản cập nhật từ cụm máy chủ bị ảnh hưởng trong một khung thời gian hạn chế vào ngày 20 tháng 1 năm 2026."

Công ty nhấn mạnh rằng sự cố không liên quan đến lỗ hổng trong chính sản phẩm eScan.

eScan nhấn mạnh rằng chỉ những người có phần mềm được cập nhật từ cụm khu vực cụ thể mới bị ảnh hưởng, trong khi tất cả các khách hàng khác vẫn không bị ảnh hưởng.

Tuy nhiên, eScan cho biết những người đã cài đặt bản cập nhật độc hại có thể thấy hành vi này trên hệ thống của họ:

* Thông báo lỗi dịch vụ cập nhật
* Tệp hosts hệ thống bị sửa đổi ngăn kết nối với máy chủ cập nhật eScan
* Thay đổi tệp cấu hình cập nhật eScan
* Không thể nhận các bản cập nhật định nghĩa bảo mật mới
* Popup không có sẵn cập nhật trên máy khách

BleepingComputer đã liên hệ với eScan để đặt thêm câu hỏi về thời gian hệ thống của họ ban đầu bị xâm phạm và sẽ cập nhật câu chuyện nếu nhận được phản hồi.

## Bản cập nhật được triển khai để đẩy phần mềm độc hại

[Thông báo an ninh](https://www.morphisec.com/blog/critial-escan-threat-bulletin/) của Morphisec cho biết bản cập nhật độc hại đã đẩy xuống một phiên bản sửa đổi của thành phần cập nhật eScan, "Reload.exe".

"Các bản cập nhật độc hại đã được phân phối thông qua cơ sở hạ tầng cập nhật hợp pháp của eScan, dẫn đến việc triển khai phần mềm độc hại nhiều giai đoạn đến các điểm cuối doanh nghiệp và người dùng toàn cầu," theo thông báo của Morphisec.

Mặc dù Reload.exe đã sửa đổi được ký bằng chứng chỉ ký mã dường như của eScan, cả Windows và VirusTotal đều hiển thị chữ ký không hợp lệ.

Theo Morphisec, tệp Reload.exe \[[VirusTotal](https://www.virustotal.com/gui/file/8f2fe9dc184ba209f78d1b81f87f7d39f0d260b8d6dc1f7af9f256071d8c9fe0)\] đã được sử dụng để kích hoạt persistence, thực thi lệnh, sửa đổi tệp HOSTS của Windows để ngăn cập nhật từ xa và kết nối với cơ sở hạ tầng C2 để tải xuống các tải trọng tiếp theo.

Các nhà nghiên cứu cho biết các máy chủ command and control sau đây đã được quan sát:

```
hxxps[://]vhs[.]delrosal[.]net/i
hxxps[://]tumama[.]hns[.]to
hxxps[://]blackice[.]sol-domain[.]org
hxxps[://]codegiant[.]io/dd/dd/dd[.]git/download/main/middleware[.]ts
504e1a42.host.njalla[.]net
185.241.208[.]115

```

Tải trọng cuối cùng được triển khai là một tệp có tên CONSCTLX.exe \[[VirusTotal](https://www.virustotal.com/gui/file/bec369597633eac7cc27a698288e4ae8d12bdd9b01946e73a28e1423b17252b1/content)\], mà Morphisec cho là hoạt động như một backdoor và trình tải xuống liên tục. Morphisec nói rằng các tệp độc hại đã tạo các tác vụ theo lịch trình cho persistence bằng cách sử dụng các tên như "CorelDefrag".

eScan đã tạo một bản cập nhật khắc phục mà khách hàng có thể chạy để thực hiện các hành động sau:

* Tự động xác định và sửa chữa các thay đổi không chính xác
* Kích hoạt lại chức năng cập nhật eScan thích hợp
* Xác minh khôi phục thành công
* Yêu cầu khởi động lại hệ thống tiêu chuẩn

Cả eScan và Morphisec đều khuyến nghị khách hàng chặn các máy chủ command and control ở trên để tăng cường bảo mật.

Vào năm 2024, tin tặc Triều Tiên đã được quan sát [khai thác cơ chế cập nhật](https://www.bleepingcomputer.com/news/security/hackers-hijack-antivirus-updates-to-drop-guptiminer-malware/) của phần mềm antivirus eScan để cài đặt backdoor vào mạng doanh nghiệp.