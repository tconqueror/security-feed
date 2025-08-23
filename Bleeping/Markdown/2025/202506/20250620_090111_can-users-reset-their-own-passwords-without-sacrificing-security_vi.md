# Người dùng có thể tự đặt lại mật khẩu của họ mà không làm mất an ninh không?

![Specops password reset](https://www.bleepstatic.com/content/posts/2025/06/19/users-reset-their-own-passwords.png)

Dù thích hay không, mật khẩu sẽ không biến mất trong thời gian sắp tới. Trong khi nhiều tổ chức đang [khám phá xác thực không có mật khẩu](https://specopssoft.com/blog/considerations-when-going-passwordless/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), mật khẩu vẫn giữ vai trò là hàng rào chính bảo vệ cho hầu hết các dịch vụ trực tuyến đối mặt với công chúng.

Điều này nói lên rằng, chúng đi kèm với một gánh nặng quản lý lớn. Gartner ước tính rằng [40% tất cả các cuộc gọi đến dịch vụ khách hàng](https://www.intelligentciso.com/2019/01/29/yubico-research-reveals-69-of-employees-share-passwords-with-colleagues/) gắn liền với các vấn đề về mật khẩu như hết hạn, thay đổi và đặt lại. Một số vấn đề này (như mật khẩu đã quên, hết hạn định kỳ, hoặc cập nhật theo yêu cầu bảo mật) là không thể tránh khỏi, nhưng chúng vẫn tiêu tốn thời gian và nguồn lực quý giá.

Forrester ước tính [chi phí cho mỗi lần đặt lại khoảng 70 đô la](https://securityboulevard.com/2022/10/the-cost-of-password-lockouts/), và điều này có thể nhanh chóng cộng dồn lại. Dựa vào những con số này, trường hợp cho một [giải pháp đặt lại mật khẩu tự phục vụ](https://specopssoft.com/product/specops-password-reset/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) là cực kỳ thuyết phục: bằng cách cho phép người dùng tự xử lý việc đặt lại, các tổ chức có thể giảm tải cho bộ phận hỗ trợ kỹ thuật và cắt giảm chi phí - mà không làm mất an ninh.

## Về việc đặt lại mật khẩu tự phục vụ

Đặt lại mật khẩu tự phục vụ (SSPRs) cho phép người dùng tự bảo mật đặt lại mật khẩu của họ mà không cần đến sự hỗ trợ của IT. Bằng cách cho phép người dùng tự xử lý những nhiệm vụ thường lệ nhưng cần thiết này, SSPRs giảm đáng kể số lượng vé hỗ trợ, giảm chi phí, và nâng cao hiệu suất bằng cách trao quyền cho người dùng lấy lại quyền truy cập nhanh chóng hoặc thực hiện việc làm mới mật khẩu thường xuyên.

Với SSPR, tất cả điều này có thể xảy ra mà không cần đến sự can thiệp của nhân viên IT. Và lợi ích là có thể đo đếm được, đến từng đồng tiết kiệm: vào năm 2022, một [tổ chức trung bình tiết kiệm được 65.000 đô la](https://specopssoft.com/blog/save-money-self-service-password-resets/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) khi sử dụng các giải pháp đặt lại mật khẩu tự phục vụ.

![Une image contenant Bleu électrique, Azure, bleu vert, TurquoiseLe contenu généré par l’IA peut être incorrect.](https://www.bleepstatic.com/images/news/security/s/specops/self-service-password-reset/uReset-Header-GIF.gif)

## Các yếu tố bảo mật chính

Về căn bản, SSPR chuyển trách nhiệm khôi phục mật khẩu từ IT sang người dùng cuối. Vì lý do này, các nhóm bảo mật nên ưu tiên các yếu tố bảo mật đúng đắn khi triển khai giải pháp SSPR, chẳng hạn như bao gồm các biện pháp xác minh danh tính mạnh mẽ.

Nếu không có các biện pháp bảo vệ thích hợp, SSPR có thể trở thành mục tiêu hấp dẫn cho các kẻ tấn công muốn khai thác các quá trình đặt lại yếu và chiếm quyền truy cập trái phép vào các tài khoản người dùng.

Một quá trình SSPR an toàn phải dựa vào các phương pháp xác minh danh tính có khả năng chống lại các vectơ tấn công phổ biến như phishing và [prompt bombing](https://specopssoft.com/blog/mfa-prompt-bombing-how-it-works-and-how-to-stop-it/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

Ví dụ, việc sử dụng ứng dụng xác thực hoặc token phần cứng cung cấp mức độ đảm bảo cao hơn nhiều so với các phương pháp truyền thống như tin nhắn SMS hoặc câu hỏi bảo mật, thường dễ bị chặn hoặc đoán.

Các tổ chức nên ưu tiên xác thực đa yếu tố (MFA) [bao gồm công nghệ chống phishing](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) để xác minh người dùng trước khi cho phép bất kỳ hành động đặt lại mật khẩu nào.

Bằng cách gia cố quá trình xác minh, các tổ chức có thể nhận được lợi ích từ SSPR mà không tạo ra những lỗ hổng mới cho khung bảo mật của họ.

## [**Bảo vệ mật khẩu Active Directory của bạn với Chính sách Mật khẩu Specops**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Báo cáo Điều Tra Vi Phạm Dữ Liệu của Verizon cho thấy thông tin đăng nhập bị đánh cắp tham gia vào 44.7% vụ vi phạm.   
  
Dễ dàng bảo mật Active Directory với các chính sách mật khẩu tuân thủ luật pháp, chặn hơn 4 tỷ mật khẩu bị xâm phạm, nâng cao bảo mật và giảm bớt phiền phức hỗ trợ!

[Thử miễn phí](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## SSPR cho người dùng truy cập từ xa

Hỗ trợ người dùng truy cập từ xa và không sử dụng VPN là một khía cạnh quan trọng trong bất kỳ giải pháp SSPR hiệu quả nào. Khi người dùng ở bên ngoài mạng doanh nghiệp (như làm việc tại nhà, đi công tác, hoặc sử dụng thiết bị cá nhân), họ vẫn phải có khả năng khôi phục quyền truy cập vào tài khoản của họ mà không cần dựa vào sự can thiệp của bộ phận hỗ trợ.

Điều này khiến một cổng SSPR dựa trên web trở nên thiết yếu để hỗ trợ người dùng truy cập từ xa.

Khác với các giải pháp truyền thống chỉ hoạt động tại chỗ, một cổng có thể truy cập đám mây đảm bảo rằng người dùng có thể khởi xướng các cuộc đặt lại mật khẩu từ bất kỳ đâu, bất kể vị trí vật lý của họ và nơi họ khởi xướng [kết nối với VPN của tổ chức](https://specopssoft.com/2fa-vpn/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

Để duy trì cả khả năng truy cập và bảo mật, cổng SSPR nên yêu cầu xác minh danh tính thông qua các phương pháp MFA đã đăng ký trước. Những phương pháp này có thể bao gồm các ứng dụng xác thực, khóa phần cứng, hoặc [tùy chọn sinh trắc học](https://specopssoft.com/blog/behavioral-biometrics-authentication-passwords/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), cung cấp bảo vệ mạnh mẽ hơn so với các phương pháp không an toàn như SMS hoặc liên kết email.

Bằng cách đảm bảo người dùng có thể xác thực và đặt lại mật khẩu của họ một cách an toàn từ bất kỳ vị trí nào, các tổ chức không chỉ giảm bớt chi phí hỗ trợ, mà còn nâng cao tính liên tục trong kinh doanh bằng cách giữ cho nhân viên làm việc hiệu quả và an toàn, bất kể nơi họ làm việc.

## Giảm thiểu rủi ro kỹ thuật xã hội

Các nhóm bảo mật đang có kế hoạch thực hiện giải pháp SSPR nên có các bước chủ động để giảm thiểu rủi ro từ các cuộc tấn công kỹ thuật xã hội. Ví dụ, các câu hỏi thách thức-trả lời truyền thống (ví dụ: "Tên thời con gái của mẹ bạn là gì?") dễ dàng bị vượt qua thông qua phishing hoặc dữ liệu có sẵn công khai.

Thay vào đó, các tổ chức nên triển khai các cơ chế thách thức-trả lời động tham chiếu đến hoạt động người dùng gần đây hoặc dữ liệu ngữ cảnh, chẳng hạn như tệp cuối cùng đã được truy cập, lịch sử đăng nhập gần đây hoặc các mẫu sử dụng đã biết.

Các lời nhắc nhận thức ngữ cảnh này khiến việc giả mạo người dùng hợp pháp trở nên khó khăn hơn rất nhiều, vì thông tin yêu cầu là cả nhạy cảm về thời gian và cá nhân hóa.

Ngoài việc sử dụng các lời nhắc thách thức-trả lời thông minh hơn, các nhóm bảo mật có thể tích hợp xác thực dựa trên rủi ro vào quy trình SSPR để phát hiện và chặn hành vi nghi ngờ. Các kỹ thuật như phân tích vị trí địa lý, dấu vân tay thiết bị và kiểm tra tốc độ đăng nhập có thể đánh dấu các nỗ lực đặt lại bất thường xuất phát từ các vị trí hoặc thiết bị không quen thuộc.

Nếu một yêu cầu đặt lại đến từ một quốc gia mà người dùng chưa bao giờ đăng nhập trước đó, hoặc từ một trình duyệt mới không liên kết với hồ sơ của họ, hệ thống có thể yêu cầu xác minh bổ sung hoặc từ chối yêu cầu hoàn toàn.

Bằng cách xếp chồng thông tin phát hiện thông minh với xác thực bối cảnh, các tổ chức có thể giảm rủi ro từ các cuộc tấn công kỹ thuật xã hội mà không làm mất đi tính tiện lợi của SSPR.

## Các thực hành tốt nhất khi áp dụng SSPR

* Khi triển khai các SSPR, các nhóm bảo mật cũng nên ưu tiên trải nghiệm của người dùng, vì mức độ cản trở cao có thể làm suy yếu việc áp dụng thành công giải pháp SSPR và nhận ra giá trị lâu dài của nó. Một quy trình đặt lại nặng nề hoặc khó hiểu có thể gây khó chịu cho người dùng, dẫn đến việc lặp lại yêu cầu hỗ trợ - cuối cùng làm suy yếu mục đích của tự phục vụ.
* Để khuyến khích việc áp dụng và giảm thiểu việc bỏ cuộc, các tổ chức nên thiết kế quy trình đặt lại với sự rõ ràng và đơn giản trong tâm trí. Điều này bao gồm việc sử dụng các hướng dẫn từng bước, mẹo nội tuyến và các công cụ hỗ trợ trực quan (ví dụ: thang đo sức mạnh mật khẩu) để hướng dẫn người dùng một cách tự tin và chính xác qua quy trình.
* Giảm mức cản trở trong trải nghiệm đặt lại cũng giúp giảm tỷ lệ lỗi và đảm bảo rằng người dùng hoàn thành quy trình trong lần thử đầu tiên. Ví dụ, cung cấp phản hồi theo thời gian thực về các yêu cầu mật khẩu hoặc đánh dấu các lỗi phổ biến có thể ngăn chặn việc gửi không thành công và các vấn đề nhập lại. Càng nhiều trải nghiệm của SSPR dễ hiểu và hỗ trợ, người dùng càng có khả năng áp dụng nó.

Tóm lại, các giải pháp SSPR giảm bớt gánh nặng cho các nhóm IT và cải thiện tình trạng bảo mật trên toàn tổ chức, nhưng hiệu quả của chúng phụ thuộc vào nhiều yếu tố hơn là chỉ chức năng cốt lõi. Một trải nghiệm người dùng mượt mà, dễ hiểu là rất quan trọng để áp dụng và thành công lâu dài.

Các giải pháp như [Specops uReset](https://specopssoft.com/product/specops-password-reset/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) được xây dựng với điều này trong tâm trí, tích hợp liền mạch với Active Directory và hỗ trợ các quy trình xác minh tùy chỉnh. Specops uReset đảm bảo thông tin đăng nhập được lưu cache được cập nhật và cung cấp nhật ký kiểm tra chi tiết, tất cả mà không cần một VPN.

### **[Đặt lịch demo trực tiếp hôm nay.](https://specopssoft.com/product/specops-password-reset/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article/#tryfree)** 

_Được tài trợ và viết bởi [Specops Software](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._