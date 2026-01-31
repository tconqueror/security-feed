# Lừa đảo thanh toán lưu trữ đám mây tràn ngập hộp thư đến với thông báo gia hạn giả mạo

![Cloud storage](https://www.bleepstatic.com/content/hl-images/2024/01/17/cloud.jpg)

Trong vài tháng qua, một chiến dịch lừa đảo đăng ký lưu trữ đám mây quy mô lớn đã nhắm mục tiêu vào người dùng toàn cầu bằng các email liên tục cảnh báo sai rằng ảnh, tệp và tài khoản của họ sắp bị chặn hoặc xóa do một lỗi thanh toán không có thật.

Dựa trên nhiều email mà BleepingComputer ghi nhận, chiến dịch này đã leo thang trong vài tháng qua, khi mọi người nhận được nhiều phiên bản lừa đảo mỗi ngày, tất cả dường như được gửi từ cùng một nhóm lừa đảo.

Dù nội dung email khác nhau, tất cả các thông điệp đều cố gắng tạo ra cảm giác khẩn cấp bằng cách tuyên bố rằng vấn đề thanh toán hoặc lưu trữ phải được giải quyết ngay lập tức, nếu không các tệp của người dùng sẽ bị xóa hoặc chặn.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

## Chiến dịch email lừa đảo lưu trữ đám mây

Các email lừa đảo xuất phát từ nhiều miền khác nhau, hầu hết dường như được tạo ngẫu nhiên cho chiến dịch spam, như được hiển thị trong danh sách mẫu dưới đây.

```
xavpy@njyihuhzhyjumdjenwdsugjsku.us
hxsupportxf@bjmbsjabnjjvdfdlntduihco.com
zwblygwgtrmwag.18445435479309@qqjon7.oleglp.4mzrly.us
[name]-6704@ucv9q.333.sb100014.tour.za.com
```

Bản thân các email sử dụng nhiều dòng tiêu đề khác nhau, tất cả đều được thiết kế để dọa người nhận mở email.

Các dòng tiêu đề ví dụ mà BleepingComputer ghi nhận bao gồm:

* Immediate Action Required. Payment Declined
* Cloud Storage 1TB: Payment overdue
* \[personal name\]¸Your Account Has been Blocked! Your Photos and Videos will be Removed Fri,30 Jan-2026\. take action!!
* We've blocked your account! Your photos and videos will be deleted . Renew your subscription for free now!
* \[personal name\] - Your store is full , click to check and save 80% , ID#88839
* \[personal name\], Your Cloud Account has been locked on Mon,26 Jan-2026\. Your photos and videos will be removed!
* Sorry \[<personal email address>\], We Have To Suspend Your Account Today ! Sat,24 Jan-2026
* \[name\] - Your store is full , click to check and save 80%
* Cloud Storage 1TB: Payment overdue

Nhiều dòng tiêu đề được cá nhân hóa với tên hoặc địa chỉ email của người nhận và bao gồm các ngày cụ thể hoặc định danh để tăng tính khẩn cấp và làm cho thông điệp trông hợp lệ.

Email mà BleepingComputer ghi nhận tuyên bố rằng việc gia hạn đăng ký đám mây không thành công hoặc phương thức thanh toán đã hết hạn, đồng thời cảnh báo người nhận rằng các bản sao lưu có thể ngừng đồng bộ hóa và ảnh, video, tài liệu cùng bản sao lưu thiết bị có thể bị mất nếu sự cố không được giải quyết.

![Một trong nhiều email khóa lưu trữ đám mây đang được gửi trên toàn cầu](https://www.bleepstatic.com/images/news/security/phishing/c/cloud-spam/example-cloud-spam.jpg)

**Một trong nhiều email khóa lưu trữ đám mây đang được gửi trên toàn cầu**  
_Nguồn: BleepingComputer_

Các email mà BleepingComputer ghi nhận tuyên bố rằng việc gia hạn đăng ký đám mây không thành công hoặc phương thức thanh toán đã hết hạn, đồng thời cảnh báo người nhận rằng các bản sao lưu có thể ngừng đồng bộ hóa và ảnh, video, tài liệu cùng bản sao lưu thiết bị có thể bị mất nếu sự cố không được giải quyết.

Các thông điệp thường bao gồm ID tài khoản giả mạo, số đăng ký và ngày hết hạn để tăng tính hợp lệ.

"Đăng ký Đám mây Của Bạn Đang Gặp Rủi Ro. Chúng tôi không thể xử lý khoản thanh toán gần đây nhất của bạn. Nếu không được giải quyết, dung lượng lưu trữ đám mây và các bản sao lưu của bạn có thể bị tạm dừng," một email mà BleepingComputer ghi nhận viết.

"Hành Động Khẩn Cấp Bắt Buộc Vui lòng xác minh hoặc cập nhật phương thức thanh toán của bạn càng sớm càng tốt để tránh mất quyền truy cập vào ảnh, tệp và bản sao lưu thiết bị."

Tất cả email spam trong chiến dịch này đều chứa liên kết đến https://storage.googleapis.com/, một phần của Google Cloud Storage, nơi tin tặc lưu trữ các tệp HTML chuyển hướng tĩnh. Khi người dùng nhấp vào, URL sẽ chuyển hướng họ đến một trang lừa đảo/giả mạo được lưu trữ trên các miền ngẫu nhiên.

Tất cả các liên kết mà BleepingComputer kiểm tra đều dẫn đến cùng một bộ trang lừa đảo.

Các trang lừa đảo mạo danh cổng thông tin dịch vụ đám mây và hiển thị nổi bật thương hiệu liên quan đến đám mây, bao gồm cả logo Google Cloud. Các trang web này tuyên bố rằng bộ nhớ đám mây của người dùng đã đầy và cảnh báo rằng ảnh, video, danh bạ, tệp và dữ liệu cá nhân không còn được sao lưu và sẽ bị xóa.

"Vì bạn đã vượt quá kế hoạch lưu trữ của mình, tài liệu, danh bạ và dữ liệu thiết bị của bạn không còn được sao lưu lên Đám mây và ảnh, video của bạn không tải lên Ảnh Đám mây. Ổ Đám mây và các ứng dụng hỗ trợ Đám mây không cập nhật trên các thiết bị của bạn," trang lừa đảo hiển thị bên dưới viết.

"Dữ liệu của bạn sẽ bị mất mà không có bảo vệ bảo mật nếu không có hành động khẩn cấp."

**Trang lừa đảo cảnh báo bộ nhớ đám mây của bạn đã đầy**  
_Nguồn: BleepingComputer_

Nhấp vào nút "Tiếp tục" đưa mục tiêu đến một bản quét lưu trữ giả luôn báo cáo rằng Ảnh, Ổ Đám mây và Thư đều đã đầy. Các trang sau đó cảnh báo rằng dữ liệu sẽ bị mất trừ khi nâng cấp dung lượng lưu trữ đám mây, tuyên bố rằng người đó đủ điều kiện để nâng cấp "ưu đãi" giới hạn với mức giảm giá 80%.

Tuy nhiên, sau khi nhấp vào nút cập nhật dung lượng lưu trữ, thay vì được chuyển đến một trang dịch vụ đám mây hợp pháp, bạn sẽ được chuyển hướng đến các trang tiếp thị liên kết quảng cáo các sản phẩm không liên quan.

Các sản phẩm được quảng cáo trong chiến dịch lừa đảo này bao gồm dịch vụ VPN, phần mềm bảo mật ít người biết đến và các dịch vụ dựa trên đăng ký khác không liên quan đến lưu trữ đám mây.

Các trang cuối cùng dẫn đến biểu mẫu thanh toán được thiết kế để thu thập chi tiết thẻ tín dụng và tạo doanh thu liên kết cho các tin tặc đứng sau chiến dịch.

Thật không may, nhiều người nhận được những email này có thể không nhận ra chúng là lừa đảo và mua một sản phẩm họ không cần, nghĩ rằng nó sẽ giải quyết các sự cố lưu trữ đám mây giả mạo.

Điều quan trọng là phải hiểu rằng những email và trang đích này không phải là thông báo dịch vụ đám mây hợp pháp. Hơn nữa, các nhà cung cấp đám mây hợp pháp không gửi email dẫn đến quét lưu trữ hoặc sản phẩm bảo mật của bên thứ ba hoặc VPN để giải quyết các vấn đề thanh toán.

Hơn nữa, hầu hết các nhà cung cấp lưu trữ đám mây hợp pháp sẽ chặn quyền truy cập vào dung lượng lưu trữ bổ sung của bạn khi bạn không thanh toán, thay vì xóa các tệp của bạn ngay lập tức.

Ví dụ, [Google cho biết](http://support.google.com/googleone/answer/2736362?hl=en#:~:text=If%20you%20cancel%20your%20storage,deleted%20from%20your%20Google%20account.) rằng nếu một kế hoạch Google Drive bị hủy, bạn sẽ mất quyền truy cập vào dung lượng lưu trữ bổ sung cho đến khi bạn thanh toán lại và các tệp của bạn sẽ chỉ bị xóa sau 2 năm.

Microsoft OneDrive [theo cách tiếp cận tương tự](https://support.microsoft.com/en-gb/office/what-does-it-mean-when-your-onedrive-account-is-frozen-2735f7de-71a3-4745-9a08-7c6799bb89f7) nhưng cho biết họ có thể xóa các tệp sau 6 tháng nếu tài khoản vượt quá dung lượng lưu trữ được phân bổ.

Người dùng nhận được các thư rác này nên xóa chúng mà không nhấp vào bất kỳ liên kết nào và không mua bất cứ thứ gì được quảng cáo qua email.

Vì mục tiêu của chiến dịch là dọa người nhận thực hiện các giao dịch mua không cần thiết, bỏ qua những thông điệp này là hành động tốt nhất.

Bất kỳ lo ngại nào về lưu trữ đám mây hoặc thanh toán nên được kiểm tra thủ công bằng cách truy cập trang web hoặc ứng dụng chính thức của dịch vụ đám mây hợp pháp.