# Lỗ hổng khóa cứng trong Ivanti Workspace Control tiết lộ thông tin xác thực SQL

![Ivanti](https://www.bleepstatic.com/content/hl-images/2024/04/03/Ivanti.jpg)

Ivanti đã phát hành các bản cập nhật bảo mật để khắc phục ba lỗ hổng nghiêm trọng về khóa cứng trong giải pháp Workspace Control (IWC) của công ty.

IWC giúp các quản trị viên doanh nghiệp quản lý máy tính để bàn và ứng dụng, hoạt động như một trung gian giữa hệ điều hành và người dùng, kiểm soát quyền truy cập và cấu hình không gian làm việc.

Nó cung cấp quyền kiểm soát tập trung đối với không gian làm việc của người dùng và cấu hình động máy tính để bàn, ứng dụng và cài đặt người dùng dựa trên chính sách và vai trò người dùng.

Cả ba lỗi bảo mật đều do việc sử dụng một khóa mã hóa đã được thiết lập trước, không thể thay đổi, và chúng có thể dẫn đến việc nâng cao quyền hạn và xâm phạm hệ thống sau khi khai thác thành công, tùy thuộc vào tài khoản bị nhắm mục tiêu trong một cuộc tấn công tiềm tàng.

Hai lỗ hổng bảo mật (CVE-2025-5353 và CVE-2025-22455) cho phép những kẻ tấn công đã xác thực cục bộ giải mã thông tin xác thực SQL được lưu trữ trên các hệ thống chạy IWC phiên bản 10.19.0.0 và các phiên bản trước đó. Lỗ hổng thứ ba được vá hôm nay (CVE-2025-22463) cũng cho phép những kẻ tấn công đã xác thực cục bộ giải mã mật khẩu môi trường được lưu trữ.

"Ivanti đã phát hành các bản cập nhật cho Ivanti Workspace Control để giải quyết ba lỗ hổng nghiêm trọng. Việc khai thác thành công có thể dẫn đến việc tiết lộ thông tin xác thực," công ty [cho biết](http://forums.ivanti.com/s/article/Security-Advisory-Ivanti-Workspace-Control-CVE-2025-5353-CVE-CVE-2025-22463-CVE-2025-22455?language=en%5FUS) hôm nay.

| **Sản phẩm**                    | **Phiên bản bị ảnh hưởng** | **Phiên bản đã giải quyết** | **Bản vá**                                                                                                                                                                   |
| ------------------------------- | -------------------------- | --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ivanti Workspace Control (IWC)  | 10.19.0.0 và trước đó     | 10.19.10.0                  | [Liên kết tải xuống](https://download.ivanti.com/downloads/RES/Ivanti%20Workspace%20Control/Ivanti%5FWorkspace%5FControl%5F10.19.10.0.zip "Ivanti Workspace Control 10.19.10.0") |

## Không có khai thác nào đang hoạt động

May mắn thay, công ty vẫn chưa tìm thấy bằng chứng cho thấy những lỗ hổng này đã được nhằm mục tiêu trong các cuộc tấn công trước khi được công bố.

"Chúng tôi không biết về bất kỳ khách hàng nào bị khai thác bởi những lỗ hổng này trước khi công khai. Những lỗ hổng này đã được công bố thông qua chương trình công bố trách nhiệm của chúng tôi," Ivanti thêm vào.

Ivanti trước đây đã thông báo rằng IWC sẽ [đến thời điểm kết thúc](https://forums.ivanti.com/s/article/Product-Life-Cycle-Policy-for-Ivanti-Workspace-Control-formerly-RES-ONE-Workspace-and-VDX?language=en%5FUS#:~:text=58%3A18%20AM-,Ivanti%20Workspace%20Control%20và%20Ivanti%20Virtual%20Desktop%20Extender,Life%20Date%3A%20ngày%2031%20tháng%2012%2C%202026) vào tháng 12 năm 2026, sau đó các bản vá bảo mật và hỗ trợ kỹ thuật sẽ không còn khả dụng.

Vào tháng 5, công ty cũng đã [khắc phục một lỗ hổng nghiêm trọng về vượt qua xác thực](https://www.bleepingcomputer.com/news/security/ivanti-warns-of-critical-neurons-for-itsm-auth-bypass-flaw/) trong giải pháp quản lý dịch vụ CNTT Neurons cho ITSM và hai lỗ hổng zero-day trong phần mềm Endpoint Manager Mobile (EPMM) [liên quan đến các cuộc tấn công thực thi mã từ xa](https://www.bleepingcomputer.com/news/security/ivanti-fixes-epmm-zero-days-chained-in-code-execution-attacks/).

Một trong các lỗ hổng zero-day (một lỗ hổng thực thi mã từ xa được theo dõi là CVE-2025-4428) [đã bị khai thác bởi tin tặc Trung Quốc](https://www.bleepingcomputer.com/news/security/ivanti-epmm-flaw-exploited-by-chinese-hackers-to-breach-govt-agencies/) để xâm nhập vào các cơ quan Chính phủ và các tổ chức danh tiếng trên toàn thế giới.

Một tháng trước, Ivanti [đã vá một lỗ hổng zero-day Connect Secure nghiêm trọng](https://www.bleepingcomputer.com/news/security/ivanti-patches-connect-secure-zero-day-exploited-since-mid-march/) bị một nhóm gián điệp có liên quan đến Trung Quốc (UNC5221) khai thác trong các cuộc tấn công thực thi mã từ xa để phát tán mã độc kể từ giữa tháng 3 năm 2025.