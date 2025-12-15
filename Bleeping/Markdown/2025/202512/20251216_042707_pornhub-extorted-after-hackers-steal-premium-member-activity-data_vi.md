# PornHub bị tống tiền sau khi hacker đánh cắp dữ liệu hoạt động của thành viên Premium

![PornHub](https://www.bleepstatic.com/content/hl-images/2025/06/05/PornHub.png)

Nền tảng video người lớn PornHub đang bị nhóm tống tiền ShinyHunters tống tiền sau khi lịch sử tìm kiếm và xem của các thành viên Premium được cho là đã bị đánh cắp trong một vụ rò rỉ dữ liệu Mixpanel gần đây.

Tuần trước, PornHub tiết lộ rằng họ đã bị ảnh hưởng bởi một [vi phạm tại nhà cung cấp phân tích Mixpanel](https://www.bleepingcomputer.com/news/security/openai-discloses-api-customer-data-breach-via-mixpanel-vendor-hack/). Mixpanel đã chịu một vụ vi phạm vào ngày 8 tháng 11 năm 2025, sau khi một cuộc tấn công lừa đảo qua SMS (smishing) cho phép các tác nhân đe dọa xâm phạm hệ thống của họ.

"Một sự cố an ninh mạng gần đây liên quan đến Mixpanel, một nhà cung cấp phân tích dữ liệu bên thứ ba, đã ảnh hưởng đến một số người dùng Pornhub Premium," theo một [thông báo bảo mật của PornHub](https://help.pornhub.com/hc/en-us/articles/47334442459283-Important-Message-From-Pornhub) được đăng vào thứ Sáu.

"Cụ thể, tình huống này chỉ ảnh hưởng tới một số người dùng Premium được chọn. Quan trọng là lưu ý đây không phải là một vụ vi phạm hệ thống của Pornhub Premium. Mật khẩu, thông tin thanh toán và thông tin tài chính vẫn an toàn và không bị lộ."

PornHub cho biết họ không hợp tác với Mixpanel từ năm 2021, cho thấy các bản ghi bị đánh cắp là dữ liệu phân tích lịch sử từ năm 2021 hoặc sớm hơn.

Mixpanel [nói rằng vụ vi phạm đã ảnh hưởng](https://mixpanel.com/blog/sms-security-incident/) tới "một số lượng hạn chế" khách hàng, với OpenAI và CoinTracker trước đó đã tiết lộ họ bị ảnh hưởng.

Đây là lần đầu tiên công khai xác nhận rằng ShinyHunters đứng sau vụ vi phạm Mixpanel.

Khi liên hệ với PornHub, công ty đã không cung cấp thêm bình luận cho BleepingComputer ngoài thông báo bảo mật.

## Lịch sử tìm kiếm và xem của PornHub bị lộ

Hôm nay, BleepingComputer được biết rằng ShinyHunters đã bắt đầu tống tiền các khách hàng của Mixpanel vào tuần trước, gửi các email bắt đầu với "We are ShinyHunters" và cảnh báo rằng dữ liệu bị đánh cắp của họ sẽ bị công bố nếu không trả tiền chuộc.

Trong một yêu cầu tống tiền gửi tới PornHub, ShinyHunters tuyên bố họ đã đánh cắp 94GB dữ liệu chứa hơn 200 triệu bản ghi thông tin cá nhân trong vụ vi phạm Mixpanel.

ShinyHunters sau đó xác nhận với BleepingComputer rằng họ đứng sau các email tống tiền, cáo buộc dữ liệu gồm 201,211,943 bản ghi hoạt động tìm kiếm, xem và tải xuống lịch sử của các thành viên Premium của nền tảng.

Một mẫu dữ liệu nhỏ được chia sẻ với BleepingComputer cho thấy các sự kiện phân tích gửi tới Mixpanel chứa một lượng lớn thông tin nhạy cảm mà một thành viên có thể không muốn bị công khai.

Dữ liệu này bao gồm địa chỉ email của một thành viên PornHub Premium, loại hoạt động, vị trí, URL video, tên video, các từ khóa liên quan tới video, và thời gian sự kiện xảy ra.

Các loại hoạt động được BleepingComputer thấy bao gồm việc người đăng ký PornHub đã xem hoặc tải xuống một video hoặc xem một kênh. Tuy nhiên, ShinyHunters cũng nói rằng các sự kiện bao gồm lịch sử tìm kiếm.

Nhóm tống tiền ShinyHunters đã đứng sau một chuỗi vụ rò rỉ dữ liệu trong năm nay bằng cách xâm phạm nhiều công ty tích hợp Salesforce để truy cập vào các instance Salesforce và đánh cắp dữ liệu công ty.

Nhóm đe dọa này có liên quan đến [việc khai thác lỗ hổng zero-day của Oracle E-Business Suite](https://www.bleepingcomputer.com/news/security/oracle-silently-fixes-zero-day-exploit-leaked-by-shinyhunters/) (CVE-2025-61884), cũng như [các cuộc tấn công Salesforce/Drift](https://www.bleepingcomputer.com/news/security/shinyhunters-claims-15-billion-salesforce-records-stolen-in-drift-hacks/) đã ảnh hưởng tới [một số lượng lớn tổ chức](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/) vào đầu năm nay.

Với việc giờ đây được xác nhận ShinyHunters cũng đứng sau vụ vi phạm Mixpanel, các tác nhân đe dọa chịu trách nhiệm cho một số vụ rò rỉ dữ liệu đáng kể nhất trong năm 2025, ảnh hưởng tới hàng trăm công ty.

ShinyHunters cũng đang tạo ra một [ransomware-as-a-service mới có tên ShinySpid3r,](https://www.bleepingcomputer.com/news/security/meet-shinysp1d3r-new-ransomware-as-a-service-created-by-shinyhunters/) đây sẽ là nền tảng cho họ và các tác nhân đe dọa liên quan đến Scattered Spider thực hiện các cuộc tấn công ransomware.