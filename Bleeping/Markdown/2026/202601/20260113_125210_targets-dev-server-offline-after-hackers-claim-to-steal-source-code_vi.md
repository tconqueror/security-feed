# Máy chủ phát triển của Target bị ngoại tuyến sau khi tin tặc tuyên bố đánh cắp mã nguồn

![Siêu thị Target](https://www.bleepstatic.com/content/hl-images/2026/01/12/target-header.jpg)

Tin tặc tuyên bố đang rao bán mã nguồn nội bộ thuộc về Target Corporation, sau khi công bố những gì có vẻ là mẫu các kho mã bị đánh cắp trên một nền tảng phát triển phần mềm công khai.

Tuần trước, một tác nhân đe dọa ẩn danh đã tạo nhiều kho trên Gitea có vẻ chứa các phần của mã nội bộ và tài liệu dành cho nhà phát triển của Target. Các kho này được trình bày như một bản xem trước của một tập dữ liệu lớn hơn mà theo lời người này được chào bán cho người mua trên một diễn đàn ngầm hoặc kênh riêng tư.

Sau khi BleepingComputer liên hệ với Target để hỏi về vụ vi phạm được cho là như vậy, các tệp đã bị gỡ xuống và máy chủ Git của nhà bán lẻ, _git.target.com_, trở nên không thể truy cập từ internet.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

## Tin tặc rao bán mã nguồn của Target

Tuần trước, BleepingComputer nhận được một đầu mối rằng một tác nhân đe dọa đang đăng ảnh chụp màn hình trong một cộng đồng hacker riêng tư để chứng minh tuyên bố rằng họ đã truy cập được vào môi trường phát triển nội bộ của Target.

Cùng tác nhân đó cũng đã công bố một số kho trên Gitea, một dịch vụ Git tự lưu trữ tương tự GitHub hoặc GitLab, như một mẫu dữ liệu mà tác nhân này tuyên bố đang được rao bán.

Theo nguồn tin, tin tặc tuyên bố rằng "this is \[the first set of\] data to go to auction."

Mỗi kho chứa một tệp có tên SALE.MD liệt kê hàng chục nghìn tệp và thư mục được cho là có trong tập dữ liệu đầy đủ. Phần danh sách dài hơn 57.000 dòng và quảng cáo tổng kích thước lưu trữ khoảng 860 GB.

![Một trong các tệp SALE.MD với danh sách thư mục](https://www.bleepstatic.com/images/news/u/1164866/2026/Jan/target.com-source-code-sale-claims/sale-md-file.png)

**Các tệp SALE.MD liệt kê nội dung được cho là có trong bản dump đầy đủ đang rao bán**  
(BleepingComputer)

Tên các kho mẫu trên Gitea bao gồm:

* wallet-services-wallet-pentest-collections
* TargetIDM-TAPProvisioingAPI
* Store-Labs-wan-downer
* Secrets-docs
* GiftCardRed-giftcardui

Cần lưu ý rằng metadata commit và tài liệu tham chiếu tên của các máy chủ phát triển nội bộ của Target, và nhiều kỹ sư chủ chốt và kỹ sư cấp cao hiện tại của Target.

**Các kho Gitea được cho là hiển thị một phần mã nguồn và tài liệu nội bộ của Target**  
(BleepingComputer)

## Máy chủ git của Target không còn trực tuyến

BleepingComputer đã chia sẻ các liên kết Gitea với Target vào thứ Năm và yêu cầu bình luận về vụ vi phạm được cho là.

Đến thứ Sáu và thứ Bảy, tất cả các kho đã bị xóa và [bắt đầu trả về lỗi 404](https://gitea.com/tarcom4sell/), phù hợp với một yêu cầu gỡ xuống.

Cùng thời điểm đó, máy chủ Git dành cho nhà phát triển của Target tại _git.target.com_ cũng [trở nên không thể truy cập](http://archive.md/J5d0n) từ internet.

Cho đến thứ Sáu, tên miền phụ này còn có thể truy cập và [chuyển hướng đến một trang đăng nhập](http://archive.md/4IfVZ), yêu cầu nhân viên Target kết nối qua mạng an toàn của công ty hoặc VPN. Tính đến thứ Bảy, trang web không còn tải được từ bên ngoài nữa:

**_git.target.com_ site before it was taken offline** (BleepingComputer)

BleepingComputer cũng quan sát thấy rằng các công cụ tìm kiếm như Google đã lập chỉ mục và lưu cache một số tài nguyên từ _git.target.com_, cho thấy rằng một số nội dung từ tên miền này từng có thể truy cập công khai vào thời điểm nào đó trong quá khứ.

Không rõ khi nào những trang đó bị lập chỉ mục hoặc dưới cấu hình nào, và sự xuất hiện của chúng trong kết quả tìm kiếm không nhất thiết cho thấy các tuyên bố hiện tại có liên quan đến bất kỳ việc lộ thông tin nào của máy chủ, hoặc rằng hạ tầng Git gần đây đã có thể truy cập mà không cần xác thực.

**Tên miền phụ git có thể đã phục vụ tài nguyên công khai vào một thời điểm nào đó**  
(BleepingComputer)

## Bằng chứng cho thấy nguồn gốc nội bộ

Trong khi BleepingComputer chưa xác minh độc lập toàn bộ tập dữ liệu 860 GB hoặc xác nhận rằng một vụ vi phạm đã xảy ra, cấu trúc thư mục, tên kho, và các tham chiếu hệ thống nội bộ trong chỉ mục SALE.MD tương thích với một môi trường Git doanh nghiệp lớn.

Ngoài ra, nội dung không khớp với bất kỳ [dự án mã nguồn mở](http://github.com/target) nào của Target trên GitHub, cho thấy tài liệu, nếu là xác thực, sẽ có nguồn gốc từ hạ tầng phát triển riêng tư thay vì mã được phát hành công khai.

Sự xuất hiện tên của các kỹ sư dẫn đầu và kỹ sư cấp cao hiện tại của Target trong metadata commit và tài liệu, cùng với các liên kết tới các điểm cuối API và nền tảng nội bộ, chẳng hạn như _confluence.target.com_, cũng làm dấy lên nghi vấn về nguồn gốc của các tệp.

Hơn nữa, việc các kho Gitea được dùng để lưu trữ mã nguồn bị cho là bị đánh cắp của Target không còn tồn tại nữa, cũng chỉ ra khả năng đã xảy ra một vụ vi phạm.

Sau khi Target ban đầu yêu cầu các liên kết kho, công ty đã không đưa ra bình luận thêm trước khi bài báo được xuất bản khi được tiếp cận nhiều lần.

Sự cố an ninh công khai đáng kể nhất mà Target đã công bố cho đến nay vẫn là vụ vi phạm năm 2013, trong đó kẻ tấn công đã đánh cắp dữ liệu thẻ thanh toán và các thông tin nhận dạng cá nhân khác của tới 110 triệu khách hàng và chuyển chúng sang cơ sở hạ tầng đặt tại Đông Âu, [theo U.S. Senate](https://www.commerce.senate.gov/services/files/24d3c229-4f2f-405d-b8db-a3a67f183883) và [các nghiên cứu học thuật](https://www.sipa.columbia.edu/sites/default/files/2022-11/Target%20Final.pdf).