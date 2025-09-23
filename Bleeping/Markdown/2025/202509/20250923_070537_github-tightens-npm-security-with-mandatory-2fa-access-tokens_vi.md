# GitHub siết chặt bảo mật npm với 2FA bắt buộc, access tokens

![GitHub siết chặt bảo mật npm với 2FA bắt buộc, access tokens](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_headpic.jpg)

GitHub đang triển khai một loạt biện pháp phòng thủ chống lại các cuộc tấn công chuỗi cung ứng trên nền tảng, những cuộc tấn công đã gây ra nhiều sự cố quy mô lớn gần đây.

Các cuộc tấn công mạng đáng chú ý bắt nguồn từ việc xâm phạm các kho lưu trữ trên GitHub rồi lây lan sang NPM bao gồm cuộc tấn công "[s1ngularity](https://www.bleepingcomputer.com/news/security/ai-powered-malware-hit-2-180-github-accounts-in-s1ngularity-attack/)" vào cuối tháng Tám, chiến dịch "[GhostAction](https://www.bleepingcomputer.com/news/security/hackers-steal-3-325-secrets-in-ghostaction-github-supply-chain-attack/)" vào đầu tháng Chín, và chiến dịch theo kiểu sâu máy tính có tên "[Shai-Hulud](https://www.bleepingcomputer.com/news/security/self-propagating-supply-chain-attack-hits-187-npm-packages/)" từ tuần trước.

Các cuộc tấn công đã dẫn tới việc hàng nghìn tài khoản và kho riêng tư bị xâm phạm, dữ liệu nhạy cảm bị đánh cắp, và chi phí khắc phục đáng kể.

Mặc dù GitHub đã phản ứng nhanh để giảm thiểu tác động của những sự cố này, nền tảng dành cho nhà phát triển thừa nhận rằng các biện pháp chủ động mạnh mẽ hơn sẽ hiệu quả hơn.

Để giảm các rủi ro này, [GitHub đã thông báo](https://github.blog/security/supply-chain-security/our-plan-for-a-more-secure-npm-supply-chain/) rằng họ sẽ dần triển khai các biện pháp sau:

* Yêu cầu xác thực hai yếu tố (2FA) cho việc xuất bản cục bộ.
* Thực thi các token chi tiết (granular tokens) với thời hạn 7 ngày.
* Mở rộng và khuyến khích áp dụng xuất bản đáng tin cậy (trusted publishing).
* Loại bỏ token kiểu classic và 2FA TOTP (di chuyển sang 2FA dựa trên FIDO).
* Rút ngắn thời hạn hết hạn của token xuất bản.
* Mặc định quyền xuất bản là cấm token.
* Loại bỏ tùy chọn bỏ qua 2FA cho việc xuất bản cục bộ.

Xuất bản đáng tin cậy, đã được áp dụng trên nhiều hệ sinh thái, được khuyến khích vì nó loại bỏ nhu cầu quản lý token API trong các hệ thống build.

Các người duy trì NPM được khuyên chuyển sang xuất bản đáng tin cậy ngay lập tức, cũng như thực thi 2FA cho việc xuất bản và ghi, và sử dụng WebAuth thay vì mật khẩu dùng một lần theo thời gian (TOTP) cho 2FA.

Nền tảng lưu trữ mã và cộng tác sẽ triển khai các thay đổi này dần dần và cung cấp tài liệu và hướng dẫn di chuyển cần thiết để giảm thiểu gián đoạn cho các luồng công việc hiện có.

Thông báo cũng nhấn mạnh rằng an ninh hệ sinh thái là trách nhiệm chung, và các nhà phát triển được kỳ vọng tự hành động để giảm rủi ro chuỗi cung ứng bằng cách áp dụng các lựa chọn bảo mật tốt hơn có trên nền tảng.

[Ruby Central cũng đã thông báo](https://rubycentral.org/news/strengthening-the-stewardship-of-rubygems-and-bundler/) quản trị chặt chẽ hơn đối với trình quản lý gói RubyGems nhằm cải thiện các biện pháp bảo vệ chuỗi cung ứng.

Hệ sinh thái này cũng đã gặp phải các vấn đề tương tự gần đây, như chiến dịch với [60 malicious Ruby gems](https://www.bleepingcomputer.com/news/security/60-malicious-ruby-gems-downloaded-275-000-times-steal-credentials/) bị tải xuống 275.000 lần, và một chiến dịch khác giả mạo dự án Fastlane để đánh cắp dữ liệu API của Telegram ([typosquatting the Fastlane](https://www.bleepingcomputer.com/news/security/malicious-rubygems-pose-as-fastlane-to-steal-telegram-api-data/)). 

Cho tới khi mô hình quản trị mới và các chính sách nền tảng được hoàn tất, chỉ có nhân viên Ruby Central sẽ giữ quyền admin.

Thông báo hứa hẹn một chuyển đổi sang mô hình minh bạch hơn, hướng tới cộng đồng. Một phiên Hỏi & Đáp dự kiến diễn ra vào cuối ngày hôm nay nhằm giải tỏa các mối quan ngại liên quan đến hành động đột ngột này, mà nhiều thành viên cộng đồng Ruby đã mô tả là một cuộc tiếp quản thô bạo.