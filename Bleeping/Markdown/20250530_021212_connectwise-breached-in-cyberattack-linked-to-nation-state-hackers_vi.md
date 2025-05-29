# ConnectWise bị xâm nhập trong cuộc tấn công mạng liên quan đến tin tặc nhà nước

![ConnectWise](https://www.bleepstatic.com/content/hl-images/2025/05/29/connectwise-logo.jpg)

Công ty phần mềm quản lý IT ConnectWise cho biết một cuộc tấn công mạng nghi ngờ được tài trợ bởi nhà nước đã xâm nhập vào môi trường của họ và ảnh hưởng đến một số khách hàng ScreenConnect.

"ConnectWise vừa phát hiện hoạt động đáng ngờ trong môi trường của chúng tôi mà chúng tôi tin rằng liên quan đến một tác nhân nhà nước tinh vi, điều này đã ảnh hưởng đến một số rất ít khách hàng ScreenConnect," ConnectWise chia sẻ trong một [thông báo ngắn](https://www.connectwise.com/company/trust/advisories#:~:text=May%2028%2C%202025%20Security%20Event%20Advisory).

"Chúng tôi đã khởi động một cuộc điều tra với một trong những chuyên gia pháp y hàng đầu, Mandiant. Chúng tôi đã liên lạc với tất cả các khách hàng bị ảnh hưởng và đang phối hợp với lực lượng thực thi pháp luật."

ConnectWise là một công ty phần mềm có trụ sở tại Florida, cung cấp các giải pháp quản lý IT, RMM (giám sát và quản lý từ xa), an ninh mạng và tự động hóa cho các nhà cung cấp dịch vụ quản lý (MSPs) và các phòng IT.

Một trong những sản phẩm của họ là ScreenConnect, một công cụ truy cập và hỗ trợ từ xa cho phép kỹ thuật viên kết nối an toàn với hệ thống của khách hàng để xử lý sự cố, vá lỗi và bảo trì hệ thống.

Như đã được [CRN](https://www.crn.com/news/channel-news/2025/connectwise-confirms-screenconnect-cyberattack-says-systems-now-secure-exclusive?itc=refresh) báo cáo đầu tiên, công ty hiện cho biết họ đã triển khai giám sát tăng cường và cải thiện bảo mật trên mạng của mình.

Họ cũng tuyên bố rằng họ chưa thấy bất kỳ hoạt động đáng ngờ nào khác trong các trường hợp của khách hàng.

ConnectWise không trả lời các câu hỏi của BleepingComputer về số lượng khách hàng bị ảnh hưởng, thời điểm xảy ra sự cố, hoặc liệu có hoạt động độc hại nào được quan sát trong các trường hợp ScreenConnect của khách hàng hay không.

Tuy nhiên, một nguồn tin cho BleepingComputer biết sự cố xảy ra vào tháng 8 năm 2024, với ConnectWise phát hiện hoạt động đáng ngờ vào tháng 5 năm 2025, và rằng nó chỉ ảnh hưởng đến các trường hợp ScreenConnect dựa trên đám mây.

Trong một [thảo luận trên Reddit](https://www.reddit.com/r/msp/comments/1kxpwrn/connectwise%5Fconfirms%5Fscreenconnect%5Fcyberattack/), khách hàng cho biết sự cố này liên quan đến một lỗ hổng ScreenConnect được theo dõi là [CVE-2025-3935](http://www.connectwise.com/company/trust/security-bulletins/screenconnect-security-patch-2025.4), được vá vào ngày 24 tháng 4.

Lỗi CVE-2025-3935 là một lỗi tiêm mã ViewState có độ nghiêm trọng cao do việc deserialization không an toàn của ASP.NET ViewState trong các phiên bản ScreenConnect 25.2.3 và trước đó.

Các tác nhân đe dọa có quyền truy cập hệ thống với quyền hạn có thể đánh cắp các khóa máy bí mật được sử dụng bởi một máy chủ ScreenConnect và sử dụng chúng để tạo ra các tải trọng độc hại kích hoạt thực thi mã từ xa trên máy chủ.

Trong khi ConnectWise không cho biết lỗ hổng này đã bị khai thác vào thời điểm đó, nó đã được đánh dấu là "Cao", cho thấy nó có thể đã bị khai thác hoặc có nguy cơ khai thác đáng kể.

Công ty cũng cho biết rằng lỗi này đã được vá trên các nền tảng ScreenConnect được lưu trữ trên đám mây tại "screenconnect.com" và "hostedrmm.com" trước khi được công bố công khai cho khách hàng.

Vì sự cố chỉ ảnh hưởng đến các trường hợp ScreenConnect được lưu trữ trên đám mây, có thể rằng các tác nhân đe dọa đã xâm nhập vào hệ thống của ConnectWise trước và đánh cắp các khóa máy.

Bằng cách sử dụng các khóa đó, các kẻ tấn công có thể thực hiện thực thi mã từ xa trên các máy chủ ScreenConnect của công ty và có khả năng truy cập vào môi trường của khách hàng.

Tuy nhiên, cần lưu ý rằng ConnectWise chưa xác nhận liệu đây có phải là cách mà các trường hợp của khách hàng bị xâm nhập hay không.

BleepingComputer đã gửi các câu hỏi bổ sung cho ConnectWise nhưng chưa nhận được phản hồi vào thời điểm này.