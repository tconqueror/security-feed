# Microsoft hạn chế quyền truy cập IE mode trong Edge sau các cuộc tấn công zero-day

![Microsoft hạn chế quyền truy cập IE mode trong Edge sau các cuộc tấn công zero-day](https://www.bleepstatic.com/content/hl-images/2021/06/01/Microsoft-Edge.jpg)

Microsoft đang hạn chế quyền truy cập vào Internet Explorer mode trong trình duyệt Edge sau khi phát hiện rằng tin tặc đang lợi dụng các khai thác zero-day trong Chakra JavaScript engine để truy cập vào các thiết bị mục tiêu.

Gã khổng lồ công nghệ không chia sẻ nhiều chi tiết kỹ thuật nhưng cho biết tác nhân đe dọa đã kết hợp kỹ thuật lừa đảo xã hội với một khai thác trong Chakra để đạt được thực thi mã từ xa.

“The \[Edge security\] team recently received intelligence indicating that threat actors were abusing Internet Explorer (IE) mode within Edge to gain access to unsuspecting users’ devices,” [cho biết](https://microsoftedge.github.io/edgevr/posts/Changes-to-Internet-Explorer-Mode-in-Microsoft-Edge/) Gareth Evans, Microsoft Edge Security Team Lead.

Mặc dù việc hỗ trợ Internet Explorer đã kết thúc vào ngày 15 tháng 6 năm 2022, Microsoft Edge có một IE mode để tương thích với các công nghệ cũ hơn (ActiveX và Flash) vẫn còn được sử dụng trong một số ít ứng dụng doanh nghiệp và cổng thông tin chính phủ.

Vào tháng Tám, nhóm bảo mật Edge biết rằng các tác nhân đe dọa đã hướng mục tiêu tới "một trang web giả mạo trông chính thức" và yêu cầu người dùng, thông qua một phần tử giao diện, tải trang bằng IE mode.

Sau khi khai thác lỗ hổng zero-day trong Chakra, kẻ tấn công đã lợi dụng một lỗ hổng thứ hai để tăng quyền và thoát khỏi trình duyệt, từ đó chiếm quyền điều khiển hoàn toàn thiết bị.

Evans không cung cấp các định danh cho các lỗ hổng đã bị khai thác và nói rằng lỗi trong Chakra vẫn chưa được sửa.

Để giảm thiểu rủi ro, Microsoft đã loại bỏ các phương thức cho phép kích hoạt IE mode trong Edge thông qua các cách dễ dàng, như nút thanh công cụ chuyên dụng, menu ngữ cảnh, và các mục trong hamburger menu.

Người dùng muốn IE mode hoạt động giờ đây phải điều hướng tới Settings > Default Browser > Allow và xác định các trang nên được tải bằng Internet Explorer.

![Edge setting for IE mode](https://www.bleepstatic.com/images/news/u/1220909/2025/October/edge.jpg)

**Edge setting for IE mode**  
_Source: BleepingComputer_

Các hạn chế mới nhằm khiến việc kích hoạt IE mode trở thành một hành động có chủ ý của người dùng. Hơn nữa, danh sách các trang web được phê duyệt để tải trong IE mode sẽ làm cho kẻ tấn công rất khó thành công trong các nỗ lực xâm nhập.

Những thay đổi này không áp dụng cho người dùng thương mại, những người sẽ tiếp tục sử dụng IE mode như được cấu hình thông qua chính sách doanh nghiệp.

Tuy nhiên, Microsoft nhắc nhở người dùng rằng họ nên di chuyển khỏi công nghệ web kế thừa trong Internet Explorer sang các sản phẩm hiện đại hơn, cung cấp bảo mật tốt hơn, đáng tin cậy hơn và có hiệu năng được cải thiện.