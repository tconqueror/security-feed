# Coinbase sửa lỗi nhật ký 2FA khiến mọi người nghĩ rằng họ bị hack

![Coinbase](https://www.bleepstatic.com/content/hl-images/2021/08/31/Coinbase.jpg)

Coinbase đã khắc phục một lỗi gây nhầm lẫn trong nhật ký hoạt động tài khoản của mình, khiến người dùng nghĩ rằng thông tin xác thực của họ bị xâm phạm.

Như [BleepingComputer đã báo cáo lần đầu tiên](https://www.bleepingcomputer.com/news/security/coinbase-to-fix-2fa-account-activity-entry-freaking-out-users/) vào đầu tháng này, Coinbase đã nhầm lẫn gán các nỗ lực đăng nhập không thành công với mật khẩu sai thành các lỗi xác thực hai yếu tố trong nhật ký Hoạt động Tài khoản.

Khi một tác nhân đe dọa cố gắng truy cập vào tài khoản của ai đó và sử dụng mật khẩu sai, các thông báo lỗi như "second_factor_failure" hoặc "2-step verification failed" sẽ được hiển thị thay vì.

Những mục nhập này ngụ ý rằng một tên người dùng và mật khẩu hợp lệ đã được nhập, nhưng việc đăng nhập đã bị chặn bởi xác thực hai yếu tố, chẳng hạn như việc nhập mã xác thực một lần sai từ ứng dụng xác thực.

Nhiều người dùng Coinbase đã liên hệ với BleepingComputer với lo ngại rằng Coinbase đã bị xâm phạm vì mật khẩu của họ là duy nhất cho trang web, không có dấu hiệu nhiễm phần mềm độc hại và không có tài khoản nào khác bị ảnh hưởng.

![Thông báo lỗi 2FA không chính xác trong nhật ký Hoạt động Tài khoản Coinbase](https://www.bleepstatic.com/images/news/cryptocurrency/2fa/incorrect-2fa-error-message/coinbase-account-activity-message.jpg)

**Thông báo lỗi 2FA không chính xác trong nhật ký Hoạt động Tài khoản Coinbase**

Tuy nhiên, Coinbase đã xác nhận với BleepingComputer rằng hệ thống nhật ký của họ đã phân loại không chính xác các nỗ lực đăng nhập với mật khẩu sai là "lỗi 2FA", mặc dù các kẻ tấn công chưa thành công đến giai đoạn 2FA.

Coinbase hiện đã phát hành một bản cập nhật để sửa chữa việc gán nhãn không chính xác này để các nhật ký "Mật khẩu cố gắng không thành công" được hiển thị trong Hoạt động Tài khoản thay thế.

Các lỗi như thế này rất quan trọng để sửa chữa vì chúng gây ra sự hoảng loạn không cần thiết, với người dùng cho biết với BleepingComputer rằng họ đã đặt lại tất cả mật khẩu của mình và dành hàng giờ để cố gắng xác định xem thiết bị của họ có bị xâm phạm hay không do lỗi này.

Những mục nhập bị gán nhãn sai có thể cũng đã được sử dụng trong các cuộc tấn công kỹ thuật xã hội để thuyết phục người dùng rằng thông tin xác thực tài khoản của họ đã bị xâm phạm, có khả năng cho phép các tác nhân đe dọa thu thập thông tin nhạy cảm.

Các tác nhân đe dọa thường [nhắm mục tiêu khách hàng của Coinbase trong các cuộc tấn công kỹ thuật xã hội](https://krebsonsecurity.com/2021/10/how-coinbase-phishers-steal-one-time-passwords/) để truy cập vào tài khoản của họ và rút tiền cryptocurrency đã lưu trữ.

BleepingComputer đã được thông báo rằng các tác nhân đe dọa đã sử dụng những thông báo lỗi bị gán nhãn sai này như một phần của các cuộc tấn công như vậy nhưng không thể xác minh độc lập nếu điều đó là đúng.

Tuy nhiên, các chiến dịch đang diễn ra sử dụng các cuộc tấn công lừa đảo qua SMS tự động (smishing) và các cuộc gọi thoại để giả mạo Coinbase và cố gắng đánh cắp các mã 2FA hoặc thông tin xác thực, vì vậy tất cả người dùng đều nên cẩn thận.

Coinbase đã [nói trong quá khứ](https://www.bleepingcomputer.com/news/security/coinbase-to-fix-2fa-account-activity-entry-freaking-out-users/) rằng họ sẽ không bao giờ gọi điện cho khách hàng hoặc gửi tin nhắn văn bản yêu cầu họ thay đổi mật khẩu hoặc đặt lại xác thực hai yếu tố và rằng khách hàng nên coi tất cả các tin nhắn như vậy là lừa đảo.