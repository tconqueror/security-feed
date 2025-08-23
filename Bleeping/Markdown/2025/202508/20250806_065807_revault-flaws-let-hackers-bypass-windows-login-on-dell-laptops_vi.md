# Lỗi ReVault cho phép hacker vượt qua đăng nhập Windows trên laptop Dell

![Dell](https://www.bleepstatic.com/content/hl-images/2024/05/09/Dell-headpic.jpg)

Các lỗ hổng firmware ControlVault3 ảnh hưởng đến hơn 100 mẫu laptop Dell có thể cho phép kẻ tấn công vượt qua đăng nhập Windows và cài đặt malware tồn tại ngay cả khi hệ thống được cài đặt lại.

Dell ControlVault là một giải pháp bảo mật dựa trên phần cứng lưu trữ mật khẩu, dữ liệu sinh trắc học và mã bảo mật bên trong firmware trên một bo mạch con chuyên dụng, được gọi là Unified Security Hub (USH).

Năm lỗ hổng, được báo cáo bởi bộ phận bảo mật Talos của Cisco và được đặt tên là "**ReVault**," ảnh hưởng đến cả firmware ControlVault3 và các lập trình giao diện ứng dụng (APIs) Windows của nó trong dòng laptop Latitude và Precision tập trung vào doanh nghiệp của Dell.

Những thiết bị này rất phổ biến trong lĩnh vực an ninh mạng, chính phủ và công nghiệp, nơi mà thẻ thông minh, dấu vân tay và NFC cũng thường được sử dụng cho xác thực.

Danh sách đầy đủ các lỗ hổng ReVault bao gồm các lỗi out-of-bounds (CVE-2025-24311, CVE-2025-25050), một lỗ hổng free tùy ý (CVE-2025-25215), một tràn ngăn xếp (CVE-2025-24922) và một vấn đề deserialization không an toàn (CVE-2025-24919) ảnh hưởng đến các API Windows của ControlVault.

Dell [đã phát hành các bản cập nhật bảo mật](https://www.dell.com/support/kbdoc/en-us/000276106/dsa-2025-053) để khắc phục các lỗ hổng ReVault trong driver và firmware ControlVault3 từ tháng 3 đến tháng 5. Danh sách đầy đủ các mẫu bị ảnh hưởng có sẵn trong [thông báo bảo mật của Dell](https://www.dell.com/support/kbdoc/en-us/000276106/dsa-2025-053).

## Vượt qua đăng nhập Windows và tăng quyền

Kết hợp các lỗ hổng này có thể cho phép kẻ tấn công thực hiện mã tùy ý trên firmware, có khả năng tạo ra các implant tồn tại ngay cả khi Windows được cài đặt lại.

Họ cũng có thể tận dụng quyền truy cập vật lý để vượt qua đăng nhập Windows hoặc nâng cao quyền người dùng cục bộ lên mức quản trị viên.

"Một kẻ tấn công cục bộ với quyền truy cập vật lý vào laptop của người dùng có thể mở nó ra và truy cập trực tiếp vào bo mạch USH qua USB bằng một bộ kết nối tùy chỉnh," [Cisco Talos cho biết](https://blog.talosintelligence.com/revault-when-your-soc-turns-against-you/).

"Từ đó, tất cả các lỗ hổng đã được mô tả trước đó trở thành trong phạm vi cho kẻ tấn công mà không cần phải đăng nhập vào hệ thống hoặc biết mật khẩu mã hóa toàn bộ đĩa."

Việc khai thác thành công cũng có thể cho phép kẻ tấn công thao túng xác thực dấu vân tay, buộc thiết bị mục tiêu [chấp nhận bất kỳ dấu vân tay nào](http://blog.talosintelligence.com/content/media/2025/08/demo%5Ffingerprint2%5Fresized.mp4) thay vì chỉ của những người dùng hợp lệ.

Talos khuyến nghị giữ cho các hệ thống được cập nhật thông qua Windows Update hoặc trang web của Dell, vô hiệu hóa các thiết bị bảo mật không sử dụng như đầu đọc dấu vân tay, đầu đọc thẻ thông minh và đầu đọc NFC, và vô hiệu hóa đăng nhập bằng dấu vân tay trong các tình huống rủi ro cao.

Để giảm thiểu một số tấn công vật lý, các nhà nghiên cứu cũng đề xuất kích hoạt phát hiện xâm nhập khung trong cài đặt BIOS máy tính để đánh dấu các nỗ lực can thiệp vật lý và Bảo mật Đăng nhập Nâng cao (ESS) trong Windows để phát hiện firmware CV không phù hợp.