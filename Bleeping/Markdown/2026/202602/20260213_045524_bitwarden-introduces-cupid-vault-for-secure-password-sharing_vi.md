# Bitwarden giới thiệu 'Cupid Vault' để chia sẻ mật khẩu an toàn

![Bitwarden introduces ‘Cupid Vault’ for secure password sharing](https://www.bleepstatic.com/content/hl-images/2024/05/02/bitwarden-vault.jpg)

Bitwarden đã ra mắt một hệ thống mới có tên 'Cupid Vault' cho phép người dùng chia sẻ mật khẩu an toàn với các địa chỉ email đáng tin cậy.

Cupid Vault hoạt động bằng cách cho phép người dùng phiên bản miễn phí của Bitwarden tạo một kho lưu trữ dùng chung cho 2 người gọi là 'Organization'. Các người dùng khác có thể truy cập các thông tin đăng nhập trong không gian Organization bằng chứng chỉ được chủ tài khoản chỉ định.

Việc mời người dùng (đối tác, bạn bè, thành viên gia đình) vào một Organization có thể được thực hiện bằng cách thêm địa chỉ email của họ làm thành viên thứ hai.

[![Wiz](https://www.bleepstatic.com/c/w/GitLab-970x250.png)](https://www.wiz.io/lp/gitlab-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FGitLab-Security-Best-Practices-Cheat-Sheet&sfcid=701Vh00000Wn1rmIAB&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=GitLab-Best-Practices)

Bằng cách này, người dùng Bitwarden có thể [chia sẻ một cách an toàn](https://bitwarden.com/blog/introducing-bitwarden-cupid-vault-to-securely-share-and-unshare-passwords/) các bộ sưu tập cặp đăng nhập cho tài khoản dịch vụ phát trực tuyến truyền thông hoặc các nền tảng trực tuyến khác.

![Creating a new Organization (top), setting a Collection (mid), and inviting a user (bottom)](https://www.bleepstatic.com/images/news/u/1220909/2026/February/1.jpg)

**Tạo Organization mới (trên), thiết lập Collection (giữa), và mời người dùng (dưới)**  
_Nguồn: Bitwarden_

Việc thiết lập Organization và tạo các bộ sưu tập dùng chung có thể thực hiện bằng cách đăng nhập vào kho lưu trữ Bitwarden thông qua giao diện web.

Để ngăn chặn các cuộc tấn công đăng ký adversary-in-the-middle, chủ sở hữu kho lưu trữ có thể xác minh thông qua cụm từ vân tay để đảm bảo thành viên dự định mới có quyền truy cập. Kho dùng chung hoàn toàn tách biệt với kho cá nhân.

**Lời mời tham gia Organization Bitwarden**  
_Nguồn: Bitwarden_

Quyền truy cập vào Organization và các bí mật bên trong có thể bị thu hồi bất cứ lúc nào, và việc chia sẻ có thể được cấu hình theo cả hai hướng.

Bitwarden đã công bố [hướng dẫn chi tiết](https://bitwarden.com/help/getting-started-organizations/) về cách thiết lập và sử dụng Cupid Vault, giải thích rằng quyền sở hữu các mục trong Organization mới không gắn với người tạo ra chúng, vì cả hai thành viên đều có thể thực hiện các thao tác chỉnh sửa hoặc xóa.

_Nguồn: Bitwarden_

Bitwarden là trình quản lý mật khẩu mã nguồn mở phổ biến, cho phép người dùng lưu trữ, tạo và tự động điền mật khẩu cùng các thông tin nhạy cảm khác một cách an toàn.

Nó đa nền tảng, hỗ trợ nhiều trình duyệt, hệ điều hành máy tính để bàn và nền tảng di động, đồng thời bảo vệ dữ liệu được lưu trữ bằng mã hóa end-to-end.

Tính năng Cupid Vault mới ra mắt, được giới thiệu trước Ngày Valentine, có sẵn miễn phí cho tất cả người dùng và có thể thiết lập thông qua gói miễn phí. Tuy nhiên, có giới hạn 2 Collections và 2 người dùng mỗi cái.

Người dùng các gói Family, Teams và Enterprise đã có nhiều người dùng, collections và quyền kiểm soát truy cập dựa trên vai trò chi tiết, vì vậy Cupid Vault là thừa đối với các tầng trả phí và không nên nhầm lẫn với các tính năng chia sẻ bí mật có sẵn cho họ.