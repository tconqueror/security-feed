# Chiến dịch ConsentFix mới chiếm đoạt tài khoản Microsoft qua Azure CLI

![Microsoft](https://www.bleepstatic.com/content/hl-images/2024/01/26/microsoft-red-header.jpg)

Một biến thể mới của cuộc tấn công ClickFix có tên 'ConsentFix' lợi dụng ứng dụng OAuth của Azure CLI để chiếm đoạt tài khoản Microsoft mà không cần mật khẩu hoặc để vượt qua xác thực đa yếu tố (MFA).

Một [ClickFix attack](https://www.bleepingcomputer.com/tag/clickfix/) là một kỹ thuật tấn công xã hội nhằm lừa người dùng chạy các lệnh trên máy tính của họ để cài mã độc hoặc đánh cắp dữ liệu. Chúng thường dùng các hướng dẫn giả mạo tuyên bố sửa lỗi hoặc xác minh rằng người dùng là con người chứ không phải bot.

Biến thể ConsentFix mới này được phát hiện bởi công ty an ninh mạng Push Security, giải thích rằng kỹ thuật ConsentFix đánh cắp mã ủy quyền OAuth 2.0 mà có thể được dùng để lấy access token của Azure CLI.

Azure CLI là một ứng dụng dòng lệnh của Microsoft sử dụng luồng OAuth để cho phép người dùng xác thực và quản lý tài nguyên Azure và Microsoft 365 từ máy cục bộ của họ. Trong chiến dịch này, kẻ tấn công lừa nạn nhân hoàn thành luồng OAuth của Azure CLI và sau đó đánh cắp mã ủy quyền nhận được.

Trong chiến dịch này, kẻ tấn công lừa nạn nhân hoàn thành luồng OAuth của Azure CLI và sau đó đánh cắp mã ủy quyền mà họ đổi để có quyền truy cập toàn bộ tài khoản mà không cần mật khẩu hoặc MFA.

## Cuộc tấn công ConsentFix

Một cuộc tấn công ConsentFix bắt đầu khi nạn nhân truy cập một trang web hợp lệ bị xâm nhập, trang này có thứ hạng cao trên Google Search đối với các cụm từ cụ thể.

Khách truy cập được hiển thị một widget Cloudflare Turnstile CAPTCHA giả mạo yêu cầu một địa chỉ email công ty hợp lệ. Script của kẻ tấn công kiểm tra địa chỉ này so với danh sách mục tiêu dự định, lọc ra bot, nhà phân tích và bất kỳ ai không có trong danh sách mục tiêu.

![Victim prompted to enter their email address](https://www.bleepstatic.com/images/news/u/1220909/2025/December/entermeial.jpg)

**Nạn nhân được yêu cầu nhập địa chỉ email của họ**  
_Nguồn: Push Security_

Người dùng vượt qua kiểm tra này sẽ thấy một trang giống các mẫu tương tác ClickFix, cung cấp hướng dẫn cho nạn nhân để xác minh họ là con người.

Những hướng dẫn này yêu cầu nhấn nút 'Sign in' trên trang, hành động này mở một URL Microsoft hợp lệ trong tab mới.

![The ClickFix-styled page that steals the URL with the code](https://www.bleepstatic.com/images/news/u/1220909/2025/December/verifyurl.jpg)

**Trang theo phong cách ClickFix đánh cắp URL chứa mã**  
_Nguồn: Push Security_

Tuy nhiên, đây không phải là lời nhắc đăng nhập Microsoft thông thường, mà là một trang đăng nhập Azure được sử dụng để tạo mã truy cập OAuth cho Azure CLI.

**Microsoft Azure CLI login page**  
_Nguồn: BleepingComputer_

Nếu người dùng đã đăng nhập vào tài khoản Microsoft, họ chỉ cần chọn tài khoản của mình; nếu không, họ sẽ xác thực bình thường trên trang đăng nhập thực của Microsoft.

Khi điều này xảy ra, Microsoft chuyển hướng họ đến một trang localhost, và thanh địa chỉ trình duyệt bây giờ hiển thị một URL chứa mã ủy quyền OAuth của Azure CLI liên kết với tài khoản người dùng.

Quá trình lừa đảo hoàn tất khi người dùng dán URL vào trang độc hại theo hướng dẫn được cung cấp, trao cho kẻ tấn công quyền truy cập vào tài khoản Microsoft thông qua ứng dụng Azure CLI OAuth.

"Ngay khi các bước hoàn tất, nạn nhân về cơ bản đã cấp cho kẻ tấn công quyền truy cập vào tài khoản Microsoft của họ thông qua Azure CLI," [giải thích Push](http://pushsecurity.com/blog/consentfix).

"Ở thời điểm này, kẻ tấn công kiểm soát hiệu quả tài khoản Microsoft của nạn nhân, nhưng không bao giờ cần lừa lấy mật khẩu hay vượt kiểm tra MFA."

"Thực tế, nếu người dùng đã đăng nhập vào tài khoản Microsoft của họ (tức là họ có phiên hoạt động), hoàn toàn không cần đăng nhập."

Push cho biết tấn công chỉ kích hoạt một lần cho mỗi địa chỉ IP nạn nhân, nên ngay cả khi mục tiêu hợp lệ trở lại cùng trang phishing, họ sẽ không phải trải qua kiểm tra Cloudflare Turnstile nữa.

Các nhà nghiên cứu đề xuất rằng người bảo vệ nên tìm kiếm hoạt động đăng nhập Azure CLI bất thường, chẳng hạn như đăng nhập từ địa chỉ IP mới, và giám sát các legacy Graph scopes, mà kẻ tấn công cố tình lợi dụng để né tránh phát hiện.