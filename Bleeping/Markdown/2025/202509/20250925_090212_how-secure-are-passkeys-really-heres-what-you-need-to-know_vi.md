# Passkeys an toàn đến mức nào, thực sự? Đây là những gì bạn cần biết

![Một khóa bảo mật](https://www.bleepstatic.com/content/posts/2025/09/23/specops-passkeys.jpg)

Chúng ta đã biết từ lâu rằng mật khẩu có nhiều điểm yếu. Dù là phishing, [tấn công brute force](https://specopssoft.com/blog/brute-force-attack/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), hay [tấn công từ điển](https://specopssoft.com/blog/what-is-password-dictionary-attack/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), xác thực dựa trên mật khẩu vẫn là một trong những mắt xích yếu nhất trong an ninh mạng. Thực tế, [Verizon’s 2025 Data Breach Investigations Report](https://www.verizon.com/business/resources/reports/dbir/) cho thấy 88% các vụ vi phạm có liên quan đến việc sử dụng thông tin đăng nhập bị đánh cắp.

Đó là lý do nhiều tổ chức ngày càng khám phá [xác thực không mật khẩu](https://specopssoft.com/blog/considerations-when-going-passwordless/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), với passkeys nổi lên như một trong những ứng viên hàng đầu thay thế hoàn toàn mật khẩu truyền thống.

[FIDO Alliance](https://fidoalliance.org/celebrating-world-passkey-day-2025-showcase-of-real-world-passkey-deployments/), một nhân tố chính trong phát triển tiêu chuẩn không mật khẩu, báo cáo rằng 54% người dùng cho rằng passkeys tiện lợi hơn mật khẩu, và 53% tin rằng chúng an toàn hơn.

Nhưng passkeys thực sự là gì? Và liệu chúng có thực sự an toàn như lời đồn? Hãy cùng tìm hiểu.

## Passkeys là gì và chúng hoạt động như thế nào?

Passkeys là một dạng xác thực không mật khẩu dựa trên mật mã khóa công khai. Thay vì dựa vào thứ bạn nhớ (ví dụ: mật khẩu), passkeys dựa vào thứ bạn có. Thường là một thiết bị như điện thoại, laptop, hoặc security key.

Dưới đây là cách hoạt động đơn giản của chúng:

* Khi bạn tạo passkey, thiết bị của bạn tạo một cặp khóa: một khóa công khai, một khóa riêng.
* Khóa công khai được lưu bởi dịch vụ bạn đăng nhập.
* Khóa riêng ở lại an toàn trên thiết bị của bạn và không bao giờ rời thiết bị.
* Để đăng nhập, thiết bị của bạn dùng khóa riêng để ký một thử thách, chứng minh danh tính mà không tiết lộ bí mật nào.

## Passkeys thực sự khác mật khẩu đến vậy chứ?

Nói ngắn gọn: có. Khác với mật khẩu, passkeys không thể bị đánh cắp qua các cuộc tấn công lừa đảo (phishing), không thể tái sử dụng trên nhiều trang, và không thể bị đoán qua các phương pháp brute-force. Chúng là duy nhất cho từng trang hoặc ứng dụng, được lưu trữ cục bộ trên thiết bị của bạn, và được bảo vệ bằng xác thực cục bộ (như sinh trắc học hoặc PIN).

Ngay cả khi một kẻ tấn công xâm nhập cơ sở dữ liệu của công ty, họ chỉ tìm thấy khóa công khai, và những khóa này vô dụng khi không có khóa riêng tương ứng trên thiết bị của bạn. Điều này làm cho passkeys an toàn hơn nhiều so với mật khẩu truyền thống.

## [**Secure your Active Directory passwords with Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Verizon’s Data Breach Investigation Report nhận thấy thông tin đăng nhập bị đánh cắp tham gia vào 44.7% các vụ vi phạm.   
  
Bảo mật Active Directory một cách dễ dàng với các chính sách mật khẩu tuân thủ, chặn hơn 4 tỷ mật khẩu bị lộ, tăng cường an ninh, và giảm thiểu phiền toái cho bộ phận hỗ trợ!

[Thử miễn phí](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Các công ty lớn đang áp dụng passkeys

Nhiều tổ chức đã bắt đầu chuyển sang xác thực không mật khẩu bằng passkeys.

* **Microsoft** thực hiện một bước lớn vào tháng 5 năm 2025 bằng cách chuyển sang [“passwordless by default”](https://www.theverge.com/news/659929/microsoft-passwordless-passkeys-by-default) cho tất cả tài khoản mới. Mật khẩu không còn bắt buộc khi đăng ký. Thay vào đó, người dùng xác thực bằng passkeys, thông báo push, hoặc hardware security keys. Microsoft cho biết gần 1 triệu passkeys được đăng ký hàng ngày, với tỷ lệ đăng nhập thành công 98% – so với chỉ 32% đối với mật khẩu.
* **Aflac**, một nhà cung cấp bảo hiểm hàng đầu tại Mỹ, trở thành công ty bảo hiểm lớn đầu tiên áp dụng passkeys theo [FIDO Alliance](https://fidoalliance.org/celebrating-world-passkey-day-2025-showcase-of-real-world-passkey-deployments/). Điều này được cho là đã dẫn đến giảm 32% các yêu cầu khôi phục mật khẩu, và giúp đội hỗ trợ của họ không phải xử lý khoảng 30,000 cuộc gọi liên quan đến danh tính mỗi tháng.

## Điều gì làm passkeys hấp dẫn?

Có một vài lý do khiến các tổ chức — và người dùng — bắt đầu ưu tiên passkeys hơn mật khẩu truyền thống:

* **Bảo mật mạnh hơn theo thiết kế:** Passkeys loại bỏ các vectơ tấn công phổ biến như phishing và credential stuffing. Vì khóa riêng không bao giờ rời thiết bị người dùng và không thể bị đoán, kẻ tấn công gần như không còn gì để khai thác.
* **Trải nghiệm người dùng đơn giản hơn:** Đăng nhập bằng passkey nhanh và dễ, thường chỉ cần vân tay hoặc quét khuôn mặt. Không còn phải nhớ các chuỗi ký tự dài.
* **Giảm chi phí hỗ trợ:** Với ít sự cố liên quan mật khẩu hơn, đội trợ giúp thấy số lượng ticket giảm.
* **Trải nghiệm nhất quán trên nhiều nền tảng:** Passkeys hoạt động trên thiết bị và trình duyệt khác nhau theo tiêu chuẩn được ngành công nhận, cho phép người dùng xác thực an toàn dù đang dùng laptop hay điện thoại.

## Những hạn chế của passkeys

Passkeys hứa hẹn nhiều, nhưng không phải không có thách thức. Theo [nghiên cứu của FIDO Alliance](https://fidoalliance.org/new-fido-alliance-research-shows-87-percent-us-uk-workforces-are-deploying-passkeys-for-employee-sign-ins/), một số rào cản hàng đầu do các tổ chức báo cáo bao gồm độ phức tạp (43%), chi phí (33%), và thiếu rõ ràng (29%).

Với điều đó trong đầu, đây là một số hạn chế cần xem xét:

* **Phụ thuộc vào thiết bị:** Vì passkeys gắn với thiết bị của người dùng, nếu họ mất quyền truy cập vào điện thoại hoặc laptop thì khôi phục tài khoản có thể trở nên phức tạp và tốn thời gian.
* Thiết lập phức tạp: Việc thiết lập hệ thống xác thực tương thích passkey đòi hỏi thay đổi hạ tầng hiện có, có thể rất phức tạp — đặc biệt với các môi trường lớn hoặc cũ.
* **Tương thích hạn chế với hệ thống cũ:** Không phải dịch vụ và nền tảng nào cũng hỗ trợ passkeys. Các tổ chức vẫn dựa vào phần mềm cũ hoặc công cụ bên thứ ba có thể cần chạy mô hình lai trong khi chuyển đổi, điều này thực sự có thể làm cho an ninh trở nên khó khăn hơn.
* **Chi phí ban đầu:** Việc triển khai hỗ trợ passkey, từ thay đổi hạ tầng đến đào tạo người dùng, đòi hỏi đầu tư cả thời gian lẫn tiền bạc, điều này có thể là rào cản quá lớn cho một số tổ chức.
* **Giáo dục và nhận thức người dùng:** Passkeys vẫn còn tương đối mới, nghĩa là nhiều người dùng không quen cách chúng hoạt động. Việc áp dụng có thể chậm và kéo dài, với nhu cầu mạnh mẽ về onboarding và truyền thông.

![Microsoft sign-in page](https://www.bleepstatic.com/images/news/security/s/specops/passkeys/microsoft-sign-in-passkey.jpg)

## Liệu passkeys có thay thế hoàn toàn mật khẩu?

Passkeys đang tiến nhanh tới việc được chấp nhận rộng rãi, đặc biệt cho các môi trường có yêu cầu an ninh cao và ứng dụng ưu tiên di động. Nhưng điều đó không có nghĩa là [mật khẩu sẽ biến mất](https://specopssoft.com/blog/considerations-when-going-passwordless/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) ngay ngày mai.

Vẫn còn nhiều kịch bản trong đó việc áp dụng passkey chưa khả thi — ví dụ, hệ thống legacy không tương thích với công nghệ passkey, hoặc người dùng không có thiết bị tương thích.

Trong giai đoạn chuyển tiếp này, nhiều tổ chức có khả năng sẽ chạy mô hình lai, nơi passkeys được khuyến khích, nhưng mật khẩu vẫn được dùng như dự phòng quan trọng. Đó là lý do vì sao điều quan trọng là tiếp tục [thực thi thói quen mật khẩu mạnh](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) ở bất cứ nơi nào mật khẩu vẫn còn được sử dụng.

## Đừng bỏ qua tầm quan trọng của bảo mật mật khẩu

Ngay cả khi passkeys đang gia tăng, mật khẩu vẫn là một phần của bức tranh xác thực — và chúng cần được bảo vệ đúng cách.

[Specops Password Policy](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) giúp bạn thực thi chính sách mật khẩu mạnh hơn bằng cách chặn các mật khẩu yếu, thường được dùng, và quét liên tục Active Directory của bạn so với cơ sở dữ liệu trực tiếp gồm hơn 4 tỷ mật khẩu bị lộ.

Nếu bạn vẫn đang phụ thuộc vào mật khẩu, ngay cả như một phương án dự phòng, hãy đảm bảo chúng không phải là mắt xích yếu nhất của bạn.

**[Đăng ký dùng thử miễn phí Specops Password Policy ngay hôm nay.](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)**

_Tài trợ và viết bởi [Specops Software](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._