# Cách giảm chi phí bằng khôi phục mật khẩu tự phục vụ

![Specops header](https://www.bleepstatic.com/content/posts/2025/10/20/specops-reset-header.jpg)

Tất cả chúng ta đều cần đặt lại mật khẩu thỉnh thoảng, dù là do quên tạm thời hay vì các mối lo ngại bảo mật rộng hơn. Tuy nhiên, quy trình này có thể tích tụ chi phí đáng ngạc nhiên cho tổ chức. Điều này có nghĩa là [self-service password resets](https://specopssoft.com/product/specops-password-reset/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) (SSPR) không chỉ là một “thứ hay có”, mà là điều thiết yếu.

Tất nhiên, các lần đặt lại mật khẩu là một phần trong công việc của các đội IT, theo Gartner, 40% cuộc gọi đến help desk liên quan đến việc hết hạn, thay đổi và đặt lại mật khẩu. [Với Forrester ước tính rằng một lần đặt lại tốn $70](https://www.forrester.com/report/best-practices-selecting-deploying-and-managing-enterprise-password-managers/RES139333), không khó để thấy chi phí có thể tích tụ nhanh như thế nào.

Đây là lúc SSPR phát huy vai trò. Bởi vì nó cho phép người dùng thay đổi mật khẩu của chính họ một cách an toàn (thay vì gọi helpdesk), có thể có khoản tiết kiệm tài chính đáng kể.

Thật vậy, một [phân tích của Specops](https://specopssoft.com/blog/save-money-self-service-password-resets/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) trên hơn 700 tổ chức trong cơ sở khách hàng của chúng tôi phát hiện rằng trung bình người dùng của giải pháp uReset SSPR đã tiết kiệm khoảng $136 cho mỗi người dùng. Đó không chỉ là một khoản tiết kiệm đáng kể về mặt tài chính, mà còn về thời gian của nhân viên và service desk.

Nói đơn giản, nếu người dùng có thể đặt lại mật khẩu của chính họ, họ sẽ quay lại làm việc sớm hơn và service desk có thể tập trung vào những việc khác.

[![Thống kê](https://www.bleepstatic.com/images/news/security/s/specops/self-service-password-resets/ureset-social-share.jpg)](http://specopssoft.com/blog/save-money-self-service-password-resets/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Nhu cầu về bảo mật

Tuy nhiên, có thể có các thách thức, vì vậy điều quan trọng là đảm bảo bạn [tiếp cận SSPR đúng cách](https://specopssoft.com/blog/sspr-registration-challenges/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article). Cụ thể, công nghệ phải an toàn để đóng cánh cửa với những kẻ gian lận và tội phạm khác. Ví dụ, có nguy cơ tài khoản có thể bị xâm phạm.

Bạn sẽ cần chú ý đến những dấu hiệu tinh vi của vấn đề, chẳng hạn như [hoạt động bạn không nhận ra](https://www.ncsc.gov.uk/collection/using-online-services-safely/recovering-hacked-account-or-service), bao gồm các tin nhắn đặt lại mật khẩu hoặc thay đổi cài đặt bảo mật.

Kẻ xấu có thể theo đuổi lừa đảo chuyển SIM (sim-swapping), nơi họ chuyển số điện thoại của nạn nhân sang một SIM giả để [chặn mã xác thực hai yếu tố SMS](https://specopssoft.com/blog/sim-swap-fraud-prevention-guide-2025/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) và đặt lại mật khẩu của người đó nhằm mục đích riêng, chẳng hạn truy cập hồ sơ mạng xã hội hoặc tài khoản ngân hàng.

Vậy giải pháp là gì? Một hệ thống an toàn và hiệu quả nên được xây dựng theo các tầng được chỉ định, với những người dùng được xếp hạng theo mức độ rủi ro, từ thấp đến cao. Các yếu tố có tính chất quan trọng cao có thể bao gồm thông tin đăng nhập quản trị cho cơ sở dữ liệu chứa dữ liệu cá nhân nhận dạng, [theo National Cyber Security Centre](https://www.ncsc.gov.uk/collection/secure-system-administration/risk-manage-administration-using-tiers) (NCSC).

Các tầng rủi ro thấp hơn, nhưng vẫn quan trọng, có thể bao gồm tài khoản developer cho bảng điều khiển dịch vụ đám mây cho môi trường sandbox phát triển không phải sản xuất, NCSC lưu ý.

Các tùy chọn phục hồi mật khẩu sẽ cần được ghép với tài khoản theo mức độ rủi ro, từ [multi-factor authentication (MFA) tool](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) đến sự can thiệp của service desk. Tương tự, bạn sẽ cần đảm bảo vệ sinh đăng ký đúng cách, bao gồm phát hành mã phục hồi và xác minh lại định kỳ.

Ví dụ, [Specops helps increase defenses](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) chống lại các cuộc tấn công mật khẩu Active Directory với một lớp bảo vệ khác, được xây dựng trên MFA cho Windows Logon, RDP và VPN.

## [**Secure your Active Directory passwords with Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Verizon’s Data Breach Investigation Report phát hiện rằng thông tin đăng nhập bị đánh cắp tham gia vào 44.7% các vụ vi phạm.   
  
Bảo mật Active Directory một cách dễ dàng với các chính sách mật khẩu tuân thủ, chặn hơn 4+ tỷ mật khẩu bị lộ, tăng cường bảo mật và giảm bớt rắc rối hỗ trợ!

[Try it for free](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Phát hiện mối nguy

Có thể áp dụng nhiều cách tiếp cận để tăng cường phát hiện bất kỳ nguy hiểm nào. Ví dụ, giới hạn tần suất (rate limiting) có thể được sử dụng để giới hạn và theo dõi số lượng yêu cầu mà một người dùng cụ thể thực hiện trong một khoảng thời gian xác định.

[Cloud APIs use this approach](https://learn.microsoft.com/en-us/microsoft-cloud/dev/dev-proxy/concepts/what-is-rate-limiting) để đảm bảo rằng dòng yêu cầu không làm quá tải dịch vụ.

Các cách tiếp cận khác bao gồm:

* **Đặt lại ở vị trí bất thường:** Nếu một người dùng dường như đăng nhập từ một vị trí lạ, thậm chí hai vị trí rất xa nhau trong một khoảng thời gian ngắn, điều này có thể báo hiệu tài khoản và mật khẩu bị xâm phạm.
* **Kiểm tra uy tín IP/device:** Đánh giá lịch sử của thiết bị hoặc website có thể giúp bảo vệ hệ thống của bạn khỏi các rủi ro tiềm ẩn. Ví dụ, [External Attack Surface Management](https://specopssoft.com/product/external-attack-surface-management/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) (EASM) từ Specops có thể thực hiện kiểm tra uy tín trên các mail server.

![Outpost24 External Attack Surface Management Dashboard](https://www.bleepstatic.com/images/news/security/s/specops/self-service-password-resets/external-attack-surface-management-dashboard.jpg)

* **Lịch sử kiểm toán (Audit trails):** Bằng cách theo dõi lịch sử của một tài khoản hoặc nền tảng cụ thể, người dùng có thể xác định các vấn đề tiềm ẩn. Điều này có thể dẫn đến một đánh giá SOC.

## Trải nghiệm người dùng

Tất nhiên, điều quan trọng là phải cân nhắc trải nghiệm người dùng. Bằng cách sử dụng progressive profiling, bạn có thể giảm ma sát, khiến việc thu thập dữ liệu và thông tin liên quan trở nên ít khó chịu nhất có thể.

Bạn cũng có thể xây dựng hệ thống thu thập số liệu xung quanh các từ chối sai, đảm bảo rằng bạn biết về bất kỳ trường hợp nào mà người dùng hợp lệ có thể bị từ chối truy cập.

Một kế hoạch thử nghiệm A/B có thể giúp đo lường giảm ticket và các lần đặt lại gian lận, cung cấp bằng chứng rằng bạn thực sự tăng cường bảo mật đồng thời tiết kiệm thời gian cho nhân viên.

## Lợi thế của Specops uReset

Specops uReset được thiết kế để [give users the benefits of SSPR](https://specopssoft.com/product/specops-password-reset/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), loại bỏ sự phiền toái liên quan đến việc đặt lại mật khẩu đồng thời tăng cường bảo mật. Người dùng có thể đặt lại mật khẩu Entra ID hoặc Active Directory một cách an toàn từ bất kỳ vị trí, thiết bị hoặc trình duyệt nào, làm cho nó lý tưởng cho các đội từ xa và hybrid.

Hệ thống được thiết kế để làm cho cuộc sống dễ dàng cho người dùng và đội IT; admins có thể tự động enrol users, trong khi công cụ báo cáo của uReset giữ bạn được cập nhật về quá trình enrolment.

Add-on [First Day Password](https://specopssoft.com/our-resources/first-day-password/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) cũng có nghĩa là nhân viên IT không bao giờ phải chia sẻ mật khẩu ngày đầu tiên với nhân viên mới nữa.

Quan trọng là, công cụ giúp xây dựng bảo mật trên toàn doanh nghiệp, dựa trên MFA và việc sử dụng một bước xác minh end-user ngăn cản nhân viên đặt lại mật khẩu cho đến khi danh tính của họ được xác nhận.

Các lần đặt lại mật khẩu tốn kém, nhưng có lẽ quan trọng hơn, chúng có thể lãng phí thời gian quý giá của nhân viên bạn. Với các công cụ SSPR phù hợp, bạn có thể cung cấp một quy trình mượt mà, an toàn và hiệu quả.

**[Book a uReset demo today](https://specopssoft.com/product/specops-password-reset/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Sponsored and written by [Specops Software](https://specopssoft.com/product/specops-password-reset/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._