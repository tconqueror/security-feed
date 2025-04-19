# Sự khóa tài khoản rộng rãi của Microsoft Entra liên quan đến việc triển khai tính năng bảo mật mới

![Microsoft với nền đỏ](https://www.bleepstatic.com/content/hl-images/2024/01/26/microsoft-red-header.jpg)

Các quản trị viên Windows từ nhiều tổ chức báo cáo về sự khóa tài khoản rộng rãi do các sai sót giả trong việc triển khai ứng dụng phát hiện "thông tin đăng nhập bị rò rỉ" mới của Microsoft Entra ID mang tên MACE.

Những cảnh báo và khóa tài khoản này bắt đầu từ tối qua, với một số quản trị viên tin rằng chúng chỉ là sai sót giả vì các tài khoản đều có mật khẩu duy nhất không được sử dụng trên bất kỳ trang web hoặc ứng dụng nào khác.

Microsoft Entra ID, trước đây là Azure Active Directory, là một dịch vụ quản lý danh tính và truy cập dựa trên đám mây giúp các tổ chức quản lý danh tính người dùng và bảo mật truy cập tới tài nguyên.

Trong một [thảo luận trên Reddit](https://www.reddit.com/r/sysadmin/comments/1k2pmkz/new%5Fentra%5Fleaked%5Fcredentials%5Fno%5Fbreach%5Fon%5Fhibp%5Fetc/) được đăng vào sáng sớm hôm nay, các quản trị viên Windows báo cáo đã nhận được nhiều cảnh báo từ Entra cho biết một số tài khoản người dùng của họ đã được phát hiện có thông tin đăng nhập bị rò rỉ trên dark web hoặc các vị trí khác.

Các tài khoản này đã bị tự động khóa khỏi tổ chức, với nhiều người dùng bị ảnh hưởng trên mỗi tổ chức.

"Chúng tôi cũng vậy... khoảng 1/3 tài khoản của chúng tôi bị khóa cách đây khoảng \~1 giờ. Chúng tôi là MSP nên tôi giả định điều này cũng đang xảy ra với các khách hàng của chúng tôi," một quản trị viên đã đăng trên [Reddit](https://www.reddit.com/r/sysadmin/comments/1k2pmkz/comment/mnvyx3p/).

Các tài khoản bị khóa không cho thấy dấu hiệu nào của việc bị xâm nhập, chẳng hạn như đăng nhập đáng ngờ, và đã được bảo vệ bằng MFA. Hơn nữa, các dịch vụ thông báo vi phạm như Have I Been Pwned (HIBP) không có kết quả nào cho các tài khoản này.

Một báo cáo khác trên Reddit đã xác nhận thêm rằng điều này là phổ biến rộng rãi, với một nhà cung cấp MDR cho biết họ [đã nhận được hơn 20,000 thông báo](https://www.reddit.com/r/sysadmin/comments/1k2pmkz/new%5Fentra%5Fleaked%5Fcredentials%5Fno%5Fbreach%5Fon%5Fhibp%5Fetc/) từ Microsoft trong suốt đêm liên quan đến thông tin đăng nhập bị rò rỉ từ các khách hàng khác nhau.

Mặc dù Microsoft chưa xác nhận công khai nguyên nhân của những khóa tài khoản này, hãng đã nói với một trong những tổ chức bị ảnh hưởng rằng nguyên nhân là do vấn đề trong việc triển khai một ứng dụng Doanh nghiệp mới mang tên "MACE Credential Revocation."

"Vừa mới nói chuyện với kỹ sư. Đây là khóa tổ chức do đợt triển khai MACE ninja mà họ đã thực hiện. không có dấu hiệu nào của việc bị xâm nhập. Anh ấy cần một giờ để chuyển ticket từ xâm nhập sang khóa, nhưng có thể thở phảo nhẹ nhõm. Mã lỗi là: 53003 cho chính sách truy cập có điều kiện," một quản trị viên báo cáo trên Reddit.

Nhiều người đã xác nhận rằng ứng dụng này đã được thêm vào các tổ chức ngay trước khi họ bắt đầu nhận được các cảnh báo.

Ứng dụng MACE Credential Revocation là một [tính năng của Microsoft Entra](https://learn.microsoft.com/en-us/entra/identity/authentication/feature-availability#:~:text=Leaked%20credentials%20%28MACE%29) được sử dụng để phát hiện thông tin đăng nhập bị rò rỉ và khóa các tài khoản có thể bị xâm nhập.

Trong khi tất cả các cảnh báo về thông tin đăng nhập bị rò rỉ đều nên được điều tra để xác nhận rằng một tài khoản không bị xâm nhập, nếu bạn nhận được một loạt cảnh báo đồng thời thì việc triển khai này có thể là nguyên nhân.

BleepingComputer đã liên hệ với Microsoft để hỏi về sự cố này nhưng hiện chưa nhận được phản hồi nào.