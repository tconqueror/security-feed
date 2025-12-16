# PornHub bị tống tiền sau khi tin tặc đánh cắp dữ liệu hoạt động của thành viên Premium

![PornHub](https://www.bleepstatic.com/content/hl-images/2025/06/05/PornHub.png)

Nền tảng video người lớn PornHub đang bị nhóm tống tiền ShinyHunters tống tiền sau khi lịch sử tìm kiếm và xem của các thành viên Premium của họ được cho là đã bị đánh cắp trong một vụ rò rỉ dữ liệu của Mixpanel gần đây.

Tuần trước, PornHub tiết lộ rằng họ đã bị ảnh hưởng bởi một [vi phạm gần đây tại nhà cung cấp phân tích Mixpanel](https://www.bleepingcomputer.com/news/security/openai-discloses-api-customer-data-breach-via-mixpanel-vendor-hack/). Mixpanel đã chịu một vụ vi phạm vào ngày 8 tháng 11 năm 2025, sau khi một cuộc tấn công lừa đảo SMS (smishing) cho phép các tác nhân đe dọa xâm phạm hệ thống của họ.

"Một sự cố an ninh mạng gần đây liên quan đến Mixpanel, một nhà cung cấp phân tích dữ liệu bên thứ ba, đã ảnh hưởng đến một số người dùng Pornhub Premium," trích từ [thông báo bảo mật của PornHub](https://help.pornhub.com/hc/en-us/articles/47334442459283-Important-Message-From-Pornhub) được đăng vào thứ Sáu.

"Cụ thể, tình huống này chỉ ảnh hưởng đến một số người dùng Premium được chọn. Cần lưu ý rằng đây không phải là một vụ xâm phạm hệ thống của Pornhub Premium. Mật khẩu, thông tin thanh toán và thông tin tài chính vẫn an toàn và không bị lộ."

PornHub cho biết họ không còn làm việc với Mixpanel kể từ năm 2021, cho thấy các bản ghi bị đánh cắp là dữ liệu phân tích lịch sử từ năm 2021 trở về trước.

Mixpanel [nói rằng vụ vi phạm đã ảnh hưởng](https://mixpanel.com/blog/sms-security-incident/) một "số lượng hạn chế" khách hàng, với OpenAI và CoinTracker trước đó đã tiết lộ họ bị ảnh hưởng.

Đây là lần đầu tiên công khai xác nhận rằng ShinyHunters đứng sau vụ vi phạm Mixpanel.

Khi liên hệ với PornHub, công ty đã không cung cấp thêm bình luận nào cho BleepingComputer ngoài thông báo bảo mật.

Sau khi chúng tôi đăng bài, Mixpanel nói với BleepingComputer rằng họ không tin dữ liệu này có nguồn gốc từ vụ vi phạm tháng 11 gần đây.

"Mixpanel nhận thức được các báo cáo rằng Pornhub đã bị tống tiền với dữ liệu được cho là bị đánh cắp từ chúng tôi," Mixpanel nói với BleepingComputer.

"Chúng tôi không tìm thấy dấu hiệu nào cho thấy dữ liệu này bị đánh cắp từ Mixpanel trong Sự cố an ninh tháng 11 năm 2025 của chúng tôi hoặc theo cách nào khác."

"Dữ liệu cuối cùng được truy cập bởi một tài khoản nhân viên hợp pháp tại công ty mẹ của Pornhub vào năm 2023. Nếu dữ liệu này nằm trong tay một bên không được ủy quyền, chúng tôi không tin rằng đó là kết quả của một sự cố an ninh tại Mixpanel."

## Dữ liệu tìm kiếm và lịch sử xem của PornHub bị lộ

Hôm nay, BleepingComputer biết rằng ShinyHunters bắt đầu tống tiền các khách hàng của Mixpanel vào tuần trước, gửi các email bắt đầu bằng "We are ShinyHunters" và cảnh báo rằng dữ liệu bị đánh cắp sẽ được công bố nếu không nhận được tiền chuộc.

Trong một yêu cầu tống tiền gửi cho PornHub, ShinyHunters tuyên bố họ đã đánh cắp 94GB dữ liệu chứa hơn 200 triệu bản ghi thông tin cá nhân trong vụ vi phạm Mixpanel.

ShinyHunters sau đó xác nhận với BleepingComputer rằng họ đứng sau các email tống tiền, khẳng định dữ liệu bao gồm 201,211,943 bản ghi lịch sử tìm kiếm, xem và tải xuống cho các thành viên Premium của nền tảng.

Một mẫu nhỏ dữ liệu được chia sẻ với BleepingComputer cho thấy các sự kiện phân tích được gửi đến Mixpanel chứa một lượng lớn thông tin nhạy cảm mà một thành viên có lẽ không muốn bị công khai.

Dữ liệu này bao gồm địa chỉ email của thành viên PornHub Premium, loại hoạt động, vị trí, URL video, tên video, từ khóa liên quan đến video, và thời gian sự kiện xảy ra.

Các loại hoạt động được BleepingComputer thấy bao gồm việc thuê bao PornHub đã xem hay tải xuống một video hoặc đã xem một kênh. Tuy nhiên, ShinyHunters cũng cho biết các sự kiện bao gồm lịch sử tìm kiếm.

Nhóm tống tiền ShinyHunters đã đứng sau một loạt các vụ vi phạm dữ liệu trong năm nay bằng cách xâm nhập các công ty tích hợp Salesforce khác nhau để truy cập các instance Salesforce và đánh cắp dữ liệu công ty.

Nhóm đe dọa này có liên quan đến [việc khai thác lỗ hổng zero-day của Oracle E-Business Suite](https://www.bleepingcomputer.com/news/security/oracle-silently-fixes-zero-day-exploit-leaked-by-shinyhunters/) (CVE-2025-61884), cũng như [các cuộc tấn công Salesforce/Drift](https://www.bleepingcomputer.com/news/security/shinyhunters-claims-15-billion-salesforce-records-stolen-in-drift-hacks/) đã ảnh hưởng đến [một số lượng lớn tổ chức](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/) đầu năm nay.

Gần đây hơn ShinyHunters [thực hiện một vụ vi phạm tại GainSight](https://www.bleepingcomputer.com/news/security/salesforce-investigates-customer-data-theft-via-gainsight-breach/) cho phép các tác nhân đe dọa đánh cắp thêm dữ liệu Salesforce từ các tổ chức.

Với việc giờ đây xác nhận rằng ShinyHunters cũng đứng sau vụ vi phạm Mixpanel, các tác nhân đe dọa chịu trách nhiệm cho một số vụ rò rỉ dữ liệu đáng kể nhất trong năm 2025, ảnh hưởng đến hàng trăm công ty.

ShinyHunters cũng đang tạo ra một [ransomware-as-a-service mới có tên ShinySpid3r,](https://www.bleepingcomputer.com/news/security/meet-shinysp1d3r-new-ransomware-as-a-service-created-by-shinyhunters/) vốn sẽ phục vụ như một nền tảng cho họ và các tác nhân đe dọa liên kết với Scattered Spider để thực hiện các cuộc tấn công mã độc tống tiền.