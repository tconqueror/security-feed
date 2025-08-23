# Đưa Quản lý Expsosure Đúng Hướng: Những Cái Nhìn từ 500 CISOs

![Penter world header](https://www.bleepstatic.com/content/posts/2025/05/28/pentera-header.jpg)

_Các kết quả từ báo cáo [Pentesting](https://pentera.io/resources/reports/global-state-of-pentesting-2025-survey-report/?utm%5Fsource=Article%20&source=Article%20&utm%5Fmedium=Bleeping%20Computer%20&medium=Bleeping%20Computer%20&utm%5Fcampaign=Xposure&campaign=Xposure) lần thứ 4 của Pentera, khảo sát khoảng 500 CISOs toàn cầu, cho thấy trong khi các thực tiễn Quản lý Exposure đang trưởng thành, vẫn còn một số khoảng trống mà thị trường chưa giải quyết._

Bề mặt tấn công hiện đại đang mở rộng, động, phân tán và hết sức mờ mịt. Khi các doanh nghiệp mở rộng vào kiến trúc tự nhiên đám mây hoặc hybrid, triển khai APIs hàng ngàn cái và tích hợp các thiết bị IoT và OT vào hoạt động cốt lõi, diện tích cho các mối đe dọa mạng gia tăng cả về kích thước và độ phức tạp. Ngày nay, trung bình một doanh nghiệp quản lý 75 công cụ bảo mật, và gần một nửa số CISOs báo cáo sự gia tăng liên tục trong các công cụ bảo mật của họ qua từng năm.

Sự phức tạp này không ngăn cản được kẻ tấn công. Nó cho phép họ. Các tác nhân đe dọa hoạt động một cách cơ hội. Không có bề mặt nào là an toàn vì các kẻ tấn công bị thúc đẩy để khai thác bất cứ điều gì được phơi bày; cuối cùng họ được thúc đẩy để nhắm đến các bề mặt tương đối yếu hơn so với bề mặt khác. Đối với các lãnh đạo bảo mật, điều này có nghĩa là không phải là vấn đề làm thế nào để bao phủ nhiều diện tích hơn, mà là đâu để tập trung vào bảo mật tối đa - nơi nào trên bề mặt tấn công có nguy cơ cao nhất?

Báo cáo [2025 State of Pentesting](https://pentera.io/resources/reports/global-state-of-pentesting-2025-survey-report/?utm%5Fsource=Article%20&source=Article%20&utm%5Fmedium=Bleeping%20Computer%20&medium=Bleeping%20Computer%20&utm%5Fcampaign=Xposure&campaign=Xposure) được phát hành gần đây bởi [Pentera](https://pentera.io/?utm%5Fsource=Article%20&source=Article%20&utm%5Fmedium=Bleeping%20Computer%20&medium=Bleeping%20Computer%20&utm%5Fcampaign=Xposure&campaign=Xposure) tiết lộ độ dễ bị tổn thương tương đối của các bề mặt tấn công khác nhau, từ cơ sở hạ tầng đám mây và tài sản web-facing đến APIs, endpoints và thậm chí cả hệ thống IoT. Các CISOs từ 500 doanh nghiệp đã được hỏi nơi nào trên mạng của họ họ cảm thấy có nguy cơ, nơi nỗ lực pentesting được hướng tới và những khu vực nào cuối cùng đã bị xâm phạm.

Các kết quả cung cấp cái nhìn cho các đội bảo mật để làm sắc nét trọng tâm, hướng các chiến lược thử nghiệm của họ và đóng những lỗ hổng nguy hiểm nhanh hơn.

## [Tham dự Xposure! Hội nghị kỹ thuật số Quốc gia về Quản lý Exposure](https://events.pentera.io/xposure2025?utm%5Fsource=Article%20&source=Article%20&utm%5Fmedium=Bleeping%20Computer%20&medium=Bleeping%20Computer%20&utm%5Fcampaign=Xposure&campaign=Xposure)

Đưa ra cách tiếp cận chủ động trong việc quản lý và giảm thiểu rủi ro mạng, nhận thông tin từ các lãnh đạo an ninh mạng về bảo mật mạng toàn doanh nghiệp, và nghe cách các nhân vật hàng đầu trong ngành đang thực hiện các giai đoạn của Quản lý Expsosure Liên tục (CTEM).

Xposure mang lại cách tiếp cận suy nghĩ tiên tiến cho khả năng chống chịu mạng.

[Đăng ký ngay](https://events.pentera.io/xposure2025?utm%5Fsource=Article%20&source=Article%20&utm%5Fmedium=Bleeping%20Computer%20&medium=Bleeping%20Computer%20&utm%5Fcampaign=Xposure&campaign=Xposure)

## Sự Thật Ít Được Nhận Thức về Quản lý Exposure

Ngay cả với các chương trình quản lý exposure tốt nhất, các vụ vi phạm vẫn xảy ra. Nhưng khi làm việc trong các chương trình bảo mật chín muồi hơn, bạn nhận ra **một vụ vi phạm không nhất thiết có nghĩa là sự thỏa hiệp**.

Lấy ví dụ về một tài sản bị phơi bày. Nó có thể bị vi phạm theo nghĩa kỹ thuật—có thể thậm chí với một tác nhân đe dọa thiết lập một bàn đạp trên đó. Nhưng nếu tài sản đó không gắn liền với dữ liệu nhạy cảm, hệ thống sản xuất, hoặc dịch vụ quan trọng, tác động thực tế là không đáng kể.

**Không phải tất cả các vụ vi phạm đều bằng nhau**. Đó là sự thay đổi tư duy cơ sở mà quản lý exposure đưa ra.

Khác với quản lý lỗ hổng truyền thống, nơi các nhóm đang truy tìm CVEs dựa trên điểm số mức độ nghiêm trọng hoặc độ tuổi phiếu, quản lý exposure có tính chiến lược. Nó cân nhắc cả **khả năng khai thác** và **tác động** để xác định những lỗ hổng thực sự quan trọng. Lăng kính đôi này cho phép các nhóm đi qua tiếng ồn và chú trọng vào những lỗ hổng có thể dẫn đến sự thỏa hiệp tồi tệ.

Báo cáo State of Pentesting củng cố sự thật này. Mặc dù gần 67% doanh nghiệp báo cáo có một vụ vi phạm trong 2 năm qua, chỉ có 36% đối mặt với thời gian ngưng hoạt động, 30% gặp phải loạt dữ liệu bị phơi bày, và 28% chịu thiệt hại tài chính. Điều đó có nghĩa là một phần lớn "các vụ vi phạm" đã không hoặc ít có hậu quả vận hành. Mục tiêu không phải là loại bỏ mọi vụ vi phạm - mà chỉ là những vụ vi phạm sẽ làm tổn thương bạn.

![Points scored from CISO insights](https://www.bleepstatic.com/images/news/security/p/pentera/ciso-insights/insights-graph.jpg)

## Tài sản Web-Facing - Vẫn là Liên Kết Yếu Nhất

Nếu quản lý exposure là về việc đồng bộ hóa khắc phục với rủi ro, các tài sản web-facing là ví dụ chính của một câu chuyện cảnh báo.

Theo dữ liệu, các tài sản web-facing đứng đầu cả ba chỉ số: chúng được coi là dễ bị tổn thương nhất (45%), được kiểm tra nhiều nhất (57%), và bị vi phạm nhiều nhất (30%).

Ở một số khía cạnh, điều này là khuyến khích. Nó cho thấy các nhóm bảo mật đang xác định chính xác các tài sản bên ngoài, công nhận chúng là cả mục tiêu có thể tiếp cận và hấp dẫn, và hướng nỗ lực pentesting cho phù hợp.

Nhưng bất chấp tất cả sự chú ý đó, các kẻ tấn công vẫn đang xâm nhập.

Tại sao? Bởi vì chỉ dựa trên việc phơi bày, các tài sản web-facing có nguy cơ. Những hệ thống này - DNS, cổng web, và trang đăng nhập được thiết kế để có thể tiếp cận. Sự mở cửa của chúng làm cho chúng trở thành “quả chín dễ hái”, đặc biệt là khi các cấu hình sai, các dịch vụ bị phơi bày, hoặc các cổng mở không được kiểm tra và không có các biện pháp kiểm soát bổ sung như MFA.

Nhưng điều này không có nghĩa là thất bại.

Nếu các kẻ tấn công xâm phạm một tài sản hướng công cộng và gặp phải một ngõ cụt - không có quyền truy cập vào các hệ thống nhạy cảm, không có dữ liệu giá trị, không có di chuyển bên lề - thì, vậy điều gì? Sự vi phạm không có tác động. Trong quản lý exposure, không chỉ là giảm tỷ lệ vi phạm - mà là giảm tác động của các vụ vi phạm xảy ra.

## Mạng nội bộ, Endpoints và Ứng dụng - Một Mặt Trận Bị Kiểm Soát

Khi nói đến các hệ thống gần gũi với những tài sản quý giá, các tổ chức đang làm đúng. Chúng được kiểm tra rộng rãi (48%) được coi là dễ bị tổn thương (32%), và đang nhìn thấy tỷ lệ vi phạm thấp (16%).

Mạng nội bộ, endpoints, và ứng dụng đều xếp hạng trong nhóm hàng đầu về hoạt động pentesting và cho thấy tỷ lệ vi phạm tương đối thấp, 16% cho mạng nội bộ, 13% cho endpoints, và 15% cho ứng dụng. Tất cả đều cho thấy một khoảnh khắc thành công từ nỗ lực tập trung.

Đây là những hệ thống chứa dữ liệu nhạy cảm, cung cấp hoạt động, và đại diện cho một con đường rõ ràng để di chuyển bên lề hoặc tăng quyền riêng tư. Về mặt quan trọng của chúng, chúng nhận được mức độ chú ý và tập trung lớn hơn, với các kiểm soát an ninh và công cụ lão luyện hơn. Nó cũng phản ánh một cái gì đó sâu sắc hơn: sự trưởng thành trong quản lý exposure. Các tổ chức không chỉ quét các hệ thống này để tìm lỗ hổng, họ kiểm tra chúng trong bối cảnh, ưu tiên dựa trên tác động tiềm năng, và xác thực để đảm bảo rằng các biện pháp phòng thủ giữ vững trước áp lực.

## Rủi ro API - Cho thấy Khoảng cách Giữa Nhận Thức và Thực Tế

APIs nằm ở giao điểm giữa logic kinh doanh và hệ thống backend. Chúng là thiết yếu, được tích hợp sâu sắc, và thường bị bỏ qua, với dữ liệu từ báo cáo khảo sát chỉ ra rằng các APIs có thể dễ bị tổn thương hơn so với những gì các nhóm bảo mật nhận ra.

Trong khi APIs được kiểm tra với tỷ lệ tương tự như mạng nội bộ (48%), chúng cho thấy tỷ lệ vi phạm cao hơn, 21%, so với 16% cho mạng nội bộ. Khoảng cách đó cho thấy một sự ngắt kết nối: hoặc rủi ro được nhận thức của APIs quá thấp, hoặc các phương pháp thử nghiệm hiện tại không tiết lộ bức tranh đầy đủ.

Thách thức là sự phức tạp. APIs là động, khó kiểm kê, và nổi tiếng khó kiểm tra tốt. Bề mặt tấn công của chúng không chỉ là về cổng hoặc endpoints, mà còn về các lỗi logic, xác thực bị hỏng, và các tích hợp bị cấu hình sai, tất cả đều dẫn đến các con đường tấn công không hiển thị trong một quét tiêu chuẩn.

APIs cũng thường cầu nối các hệ thống, cho dù giữa các dịch vụ đám mây, công cụ bên thứ ba, ứng dụng di động, và cơ sở dữ liệu nội bộ. Điều đó làm cho chúng trở thành các mục tiêu quan trọng cho di chuyển bên lề hoặc xuất dữ liệu. Và khoảng cách tầm nhìn của chúng làm cho chúng đặc biệt hấp dẫn đối với những kẻ tấn công hiểu cách di chuyển dưới radar.

Đóng khoảng cách này có nghĩa là nâng cấp kiểm tra, cả về tần suất và độ sâu. Kiểm tra liên tục, mang tính đối kháng của các APIs là cần thiết để phát hiện các lỗi tích hợp mà các phương pháp truyền thống dường như đã bỏ lỡ.

## Quản lý Exposure Cho thấy Những Dấu Hiệu Khuyến Khích của Sự Đồng Bộ

Báo cáo State of Pentesting 2025 xác nhận những gì chúng ta đã biết trong nhiều năm - khoảng cách gần hơn với rủi ro kinh doanh thúc đẩy thực hiện sắc nét hơn.

Có sự đồng bộ ngày càng tăng giữa rủi ro được nhận thức, hoạt động pentesting, và các vụ vi phạm. Đây là một tín hiệu mạnh rằng các thực tiễn quản lý exposure đang trưởng thành, khi các nhóm đang giảm thiểu khoảng cách giữa rủi ro giả định và thực tế.

Mục tiêu của quản lý exposure không phải là ngăn ngừa mọi vụ vi phạm. Mà là để ngăn chặn những vụ vi phạm quan trọng. Bằng cách kết hợp ưu tiên dựa trên dữ liệu với xác thực liên tục, các nhóm bảo mật có thể tập trung vào các lỗ hổng thực sự, không phải là các mối đe dọa lý thuyết. Đảm bảo rằng khi kẻ tấn công gõ cửa, không có gì giá trị ở phía sau cánh cửa đó.

Để tìm hiểu thêm về cách các doanh nghiệp hàng đầu đang triển khai các chương trình Quản lý Exposure của họ, tham gia [Xposure](https://events.pentera.io/xposure2025?utm%5Fsource=Article%20&source=Article%20&utm%5Fmedium=Bleeping%20Computer%20&medium=Bleeping%20Computer%20&utm%5Fcampaign=Xposure&campaign=Xposure), Hội nghị kỹ thuật số Quốc gia về Quản lý Exposure.

**[Đăng ký ngay](https://events.pentera.io/xposure2025?utm%5Fsource=Article%20&source=Article%20&utm%5Fmedium=Bleeping%20Computer%20&medium=Bleeping%20Computer%20&utm%5Fcampaign=Xposure&campaign=Xposure)**

_Được tài trợ và viết bởi [Pentera](https://events.pentera.io/xposure2025?utm%5Fsource=Article%20&source=Article%20&utm%5Fmedium=Bleeping%20Computer%20&medium=Bleeping%20Computer%20&utm%5Fcampaign=Xposure&campaign=Xposure)._