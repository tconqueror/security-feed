# GitLab vá các vấn đề nghiêm trọng về chiếm đoạt tài khoản, thiếu xác thực

![GitLab](https://www.bleepstatic.com/content/hl-images/2024/05/01/GitLab.jpg)

GitLab đã phát hành các bản cập nhật bảo mật để giải quyết nhiều lỗ hổng trong nền tảng DevSecOps của công ty, bao gồm cả những lỗ hổng cho phép kẻ tấn công chiếm đoạt tài khoản và tiêm các công việc độc hại vào các pipeline trong tương lai.

Công ty đã phát hành các phiên bản GitLab Community và Enterprise 18.0.2, 17.11.4, và 17.10.8 để khắc phục các lỗ hổng bảo mật này và đã kêu gọi tất cả các quản trị viên nâng cấp ngay lập tức.

"Những phiên bản này chứa các bản sửa lỗi quan trọng về lỗi và bảo mật, và chúng tôi rất khuyến nghị rằng tất cả các cài đặt GitLab tự quản lý nên được nâng cấp lên một trong những phiên bản này ngay lập tức," công ty [cảnh báo](https://about.gitlab.com/releases/2025/06/11/patch-release-gitlab-18-0-2-released/#cve-2025-5121---missing-authorization-issue-impacts-gitlab-ultimate-ee). "GitLab.com hiện đã chạy phiên bản đã vá. Khách hàng GitLab Dedicated không cần thực hiện hành động gì."

Vào thứ Tư, GitLab đã vá một vấn đề tiêm HTML được theo dõi dưới mã [CVE-2025-4278](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2025-4278) có thể cho phép kẻ tấn công từ xa chiếm đoạt tài khoản bằng cách tiêm mã độc hại vào trang tìm kiếm.

Công ty cũng đã phát hành những bản vá cho một vấn đề thiếu xác thực ([CVE-2025-5121](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2025-5121)) ảnh hưởng đến GitLab Ultimate EE và cho phép các tác nhân mối đe dọa từ xa tiêm các công việc CI/CD độc hại vào bất kỳ pipeline CI/CD tương lai của dự án nào.

Pipeline của GitLab là một tính năng của hệ thống Continuous Integration/Continuous Deployment (CI/CD) cho phép người dùng xây dựng, kiểm tra hoặc triển khai các thay đổi mã theo thứ tự hoặc tự động chạy các quy trình và tác vụ song song.

Tuy nhiên, việc khai thác thành công yêu cầu kẻ tấn công phải có quyền truy cập đã xác thực vào các phiên bản GitLab với giấy phép GitLab Ultimate.

Công ty cũng đã vá một lỗ hổng cross-site scripting ([CVE-2025-2254](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2025-2254)) có thể cho phép các kẻ tấn công thành công hoạt động trong ngữ cảnh của một người dùng hợp pháp và một lỗi từ chối dịch vụ (DoS) ([CVE-2025-0673](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2025-0673)) có thể cho phép các tác nhân độc hại kích hoạt các vòng lặp chuyển hướng vô hạn, gây cạn kiệt bộ nhớ và từ chối quyền truy cập cho người dùng hợp pháp.

Các kho lưu trữ GitLab thường là mục tiêu trong các cuộc tấn công vì thông tin nhạy cảm và dữ liệu mà chúng chứa, như đã được chứng minh bằng các vi phạm gần đây được báo cáo bởi công ty cho thuê xe đa quốc gia [Europcar Mobility Group](https://www.bleepingcomputer.com/news/security/europcar-gitlab-breach-exposes-data-of-up-to-200-000-customers/) và gã khổng lồ giáo dục [Pearson](https://www.bleepingcomputer.com/news/security/education-giant-pearson-hit-by-cyberattack-exposing-customer-data/), những người đã bị xâm phạm kho lưu trữ GitLab kể từ đầu năm.

Nền tảng DevSecOps của GitLab có hơn 30 triệu người dùng đăng ký và được sử dụng bởi hơn 50% các công ty trong danh sách Fortune 100, bao gồm Goldman Sachs, Airbus, T-Mobile, Lockheed Martin, Nvidia, và UBS.