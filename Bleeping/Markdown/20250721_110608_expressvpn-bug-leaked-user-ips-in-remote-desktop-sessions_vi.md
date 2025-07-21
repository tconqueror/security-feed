# Bug của ExpressVPN đã rò rỉ địa chỉ IP người dùng trong các phiên Remote Desktop

![ExpressVPN](https://www.bleepstatic.com/content/hl-images/2025/07/21/expressvpn-header.jpg)

ExpressVPN đã khắc phục một lỗ hổng trong ứng dụng Windows của mình, khiến lưu lượng Remote Desktop Protocol (RDP) bỏ qua đường hầm mạng riêng ảo (VPN), làm lộ địa chỉ IP thực của người dùng.

Một trong những nguyên tắc chính của VPN là ẩn địa chỉ IP của người dùng, cho phép người dùng duy trì sự ẩn danh trực tuyến và trong một số trường hợp, vượt qua kiểm duyệt. Việc không làm được điều này là một sự cố kỹ thuật nghiêm trọng đối với sản phẩm VPN.

ExpressVPN là nhà cung cấp dịch vụ VPN hàng đầu, thường xuyên được đánh giá là một trong những dịch vụ VPN tốt nhất và được hàng triệu người sử dụng trên toàn thế giới. Nó sử dụng các máy chủ chỉ sử dụng RAM không lưu trữ dữ liệu người dùng và tuân thủ chính sách không ghi nhật ký đã được kiểm toán.

Vào ngày 25 tháng 4 năm 2025, một nghiên cứu viên an ninh có tên "Adam-X" đã báo cáo một lỗ hổng thông qua chương trình thưởng lỗi của ExpressVPN, lộ RDP và các lưu lượng TCP khác được truyền qua cổng 3389.

Sau khi điều tra, nhóm của ExpressVPN phát hiện vấn đề do các dấu vết của mã gỡ lỗi được sử dụng cho thử nghiệm nội bộ một cách vô tình đã được bao gồm trong các bản phát hành sản xuất, cụ thể trong phiên bản từ 12.97 (ra mắt cách đây bốn tháng) đến 12.101.0.2-beta.

“Nếu một người dùng thiết lập kết nối bằng RDP, lưu lượng đó có thể bỏ qua đường hầm VPN,” [ExpressVPN báo cáo trong thông báo](https://www.expressvpn.com/blog/expressvpn-rdp-leak-fixed/).

“Điều này không ảnh hưởng đến việc mã hóa, nhưng có nghĩa là lưu lượng từ các kết nối RDP không được định tuyến qua ExpressVPN như mong đợi.”

“Do đó, một người quan sát, như ISP hoặc ai đó trên cùng một mạng, có thể thấy không chỉ rằng người dùng đã kết nối với ExpressVPN, mà còn rằng họ đang truy cập các máy chủ từ xa cụ thể qua RDP—thông tin mà thường sẽ được bảo vệ.”

Một bản vá đã có sẵn với phiên bản ExpressVPN 12.101.0.45, được phát hành vào ngày 18 tháng 6 năm 2025.

Công ty bảo mật lưu ý rằng sự cố an ninh này không làm ảnh hưởng đến việc mã hóa trên các đường hầm, và các kịch bản rò rỉ chỉ ảnh hưởng đến những người sử dụng Remote Desktop Protocol (RDP), điều mà họ coi là rủi ro thấp đối với khách hàng của mình.

“Như đã đề cập ở trên, trong thực tế, vấn đề này sẽ thường ảnh hưởng đến những người dùng đang sử dụng RDP—một giao thức mà thường không được người tiêu dùng điển hình sử dụng,” đọc thông báo của ExpressVPN.

“Xét rằng cơ sở người dùng của ExpressVPN chủ yếu là người dùng cá nhân hơn là khách hàng doanh nghiệp, số lượng người dùng bị ảnh hưởng có lẽ là nhỏ.”

RDP là một giao thức mạng của Microsoft cho phép người dùng điều khiển từ xa các hệ thống Windows qua mạng, được sử dụng bởi các quản trị viên CNTT, nhân viên làm việc từ xa và các doanh nghiệp.

Tuy nhiên, vẫn được khuyến nghị rằng người dùng nên nâng cấp ứng dụng Windows của họ lên phiên bản 12.101.0.45 để bảo vệ tối ưu.

ExpressVPN cho biết họ sẽ củng cố kiểm tra xây dựng nội bộ của mình để ngăn chặn các lỗi tương tự được giới thiệu trong sản xuất trong tương lai, bao gồm cả việc tự động hóa tăng cường trong kiểm tra phát triển.

Năm ngoái, ExpressVPN đã gặp một vấn đề khác gây ra [rò rỉ yêu cầu DNS](https://www.bleepingcomputer.com/news/security/expressvpn-bug-has-been-leaking-some-dns-requests-for-years/) khi người dùng bật tính năng 'slipt tunneling' trên ứng dụng Windows.

Tính năng này đã bị tạm thời vô hiệu hóa cho đến khi một bản sửa lỗi được thực hiện trong một phiên bản phát hành trong tương lai.