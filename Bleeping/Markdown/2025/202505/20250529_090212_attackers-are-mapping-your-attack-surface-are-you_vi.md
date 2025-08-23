# Kẻ tấn công đang lập bản đồ bề mặt tấn công của bạn—bạn thì sao?

![Hình ảnh tiêu đề Sprocket](https://www.bleepstatic.com/content/posts/2025/05/28/sprocket-header-image.png)

Trong bối cảnh mối đe dọa ngày nay, bề mặt tấn công đang mở rộng nhanh hơn hầu hết các nhóm an ninh có thể theo dõi. Mỗi tài sản đám mây mới, API bị lộ, tên miền không còn được sử dụng, hoặc dịch vụ cấu hình sai đều trở thành cơ hội cho kẻ tấn công khai thác.

Các tác nhân đe dọa hiện đại đang tận dụng [Quản lý Bề mặt Tấn công](https://www.sprocketsecurity.com/blog/what-is-attack-surface-management?utm%5Fcampaign=Attack%20Surface%20Management%20Launch%203%2F24&utm%5Fsource=BleepingComputer%20Article&utm%5Fmedium=BleepingComputer&utm%5Fterm=Sponsored%20article&utm%5Fcontent=How%20Attackers%20Use%20ASM%20Tactics%20and%20How%20You%20Can%20Beat%20Them%20to%20It) (ASM) để lập bản đồ về dấu chân kỹ thuật số của bạn trước khi bạn nhận ra những gì bị lộ. Thông qua việc thu thập thông tin tự động, công cụ khám phá tài sản và thông tin nguồn mở, họ đang suy nghĩ như các nhóm đỏ, hành động như những thợ săn lỗi, và khai thác các lỗ hổng theo thời gian thực.

Tin tốt là bạn có thể đánh bại họ ở chính trò chơi của họ.

Bài viết này khám phá cách [Công cụ Quản lý Bề mặt Tấn công Sprocket](https://www.sprocketsecurity.com/solutions/attack-surface-management?utm%5Fcampaign=Attack%20Surface%20Management%20Launch%203%2F24&utm%5Fsource=BleepingComputer%20Article&utm%5Fmedium=BleepingComputer&utm%5Fterm=Sponsored%20article&utm%5Fcontent=How%20Attackers%20Use%20ASM%20Tactics%20and%20How%20You%20Can%20Beat%20Them%20to%20It) được xây dựng để hiểu quyển sách hướng dẫn của kẻ tấn công và lấy lại khả năng nhìn thấy và kiểm soát bề mặt tấn công đang mở rộng của bạn.

Giám đốc điều hành Sprocket Security, Casey Cammilleri, chia sẻ rằng sự khác biệt giữa Sprocket ASM và các công cụ khác là “Nhìn từ góc độ của tin tặc và rất mạnh trong việc phát hiện thay đổi. Điều gì đã thay đổi từ ngày hôm qua và nó có ảnh hưởng đến an ninh của tôi không? Đó là cách chúng tôi đã suy nghĩ về việc xây dựng \[Sprocket\] ASM.”

## Quan điểm của kẻ tấn công: Lập bản đồ bề mặt tấn công của bạn

Quan điểm của kẻ tấn công về ASM phản ánh quan điểm của một chuyên gia an ninh hợp pháp, với việc thu thập thông tin hoặc khám phá. Nhờ vào công cụ công khai và tự động hóa, việc tìm kiếm các tài sản bị lộ, các điểm cuối bị bỏ quên và IT bóng là dễ dàng hơn bao giờ hết đối với kẻ tấn công. Kẻ thù có thể nhanh chóng lập một bản đồ chi tiết về hạ tầng hướng ra bên ngoài của bạn.

![Hình ảnh đầu lâu và xương chéo trên bề mặt tấn công](https://www.bleepstatic.com/images/news/security/s/sprocket-security/mapping-attack-surface/skull-crossbones.jpg)

Theo kinh nghiệm của các đội đỏ từ Sprocket Security, hầu hết các tổ chức vô ý phơi bày nhiều hơn họ nhận ra. Các môi trường phát triển cũ, tên miền bị bỏ quên, hoặc các tích hợp SaaS không được chú ý đều là những trái cây dễ hái mà kẻ tấn công yêu thích. Họ có thể xây dựng quy trình làm việc ASM của riêng họ bằng cách sử dụng sự kết hợp của các công cụ mã nguồn mở, như Amass, và các kịch bản tùy chỉnh để tự động hóa những phát hiện này trên quy mô lớn.

Nếu kẻ tấn công có một bản đồ về hạ tầng của bạn mới hơn hoặc chính xác hơn so với của bạn, đó mới chính là nguy hiểm thực sự.

### Trường hợp sử dụng: Các lỗ hổng khai thác VMware ESXi của Broadcom (2023-2024)

Các tác nhân đe dọa đã phát động các chiến dịch khai thác hàng loạt nhằm vào hàng nghìn máy chủ VMware ESXi được kết nối internet bằng cách sử dụng các lỗ hổng đã biết.

Những [lỗ hổng này đã được khai thác](https://www.bleepingcomputer.com/news/security/over-37-000-vmware-esxi-servers-vulnerable-to-ongoing-attacks/) trên thực địa, cho phép kẻ tấn công trên một máy ảo với quyền quản trị thoát khỏi sandbox và thực thi mã trên hệ thống máy chủ. Mặc dù có các bản vá có sẵn, hơn 37,000 máy chủ VMware ESXi bị phơi bày trên internet vẫn còn dễ bị tấn công, điều này làm nổi bật rủi ro của các tài sản công khai chưa được vá.

“Nếu nó bị phơi bày trên internet, bạn càng nên coi nó như thể nó đã bị tấn công. Liên tục quét bề mặt tấn công bên ngoài của bạn như thể bạn là kẻ tấn công. Đánh dấu bất kỳ tài sản có giá trị cao nào và sau đó vá, cách ly, hoặc loại bỏ chúng. Đừng chờ đợi đến khi có tin tức. Hãy hành động ngay khi một lỗ hổng được công bố trước khi nó bị khai thác.” - Michael Belton, Trưởng phòng Dịch vụ Tại Sprocket Security.

## [Khám phá bề mặt tấn công của bạn như một kẻ tấn công](https://portal.sprocketsecurity.com/users/sign%5Fup?utm%5Fcampaign=Attack%20Surface%20Management%20Launch%203%2F24&utm%5Fsource=BleepingComputer%20Article&utm%5Fmedium=BleepingComputer&utm%5Fterm=Sponsored%20article&utm%5Fcontent=How%20Attackers%20Use%20ASM%20Tactics%20and%20How%20You%20Can%20Beat%20Them%20to%20It)

Bạn đã sẵn sàng để xem những gì một hacker sẽ thấy nếu họ được tự do trên bề mặt tấn công của bạn chưa?

Hãy bước tiếp theo trong việc trở nên an toàn hơn bằng cách tạo một tài khoản với Sprocket ASM.

[Tạo tài khoản miễn phí](https://portal.sprocketsecurity.com/users/sign%5Fup?utm%5Fcampaign=Attack%20Surface%20Management%20Launch%203%2F24&utm%5Fsource=BleepingComputer%20Article&utm%5Fmedium=BleepingComputer&utm%5Fterm=Sponsored%20article&utm%5Fcontent=How%20Attackers%20Use%20ASM%20Tactics%20and%20How%20You%20Can%20Beat%20Them%20to%20It)

## Sprocket ASM: Biến Recon thành Phòng ngừa

Nếu kẻ tấn công có thể lập bản đồ hạ tầng của bạn, thì bạn cũng phải làm như vậy, nhưng nhanh hơn, sâu hơn và liên tục. Công cụ Sprocket ASM được thiết kế để cung cấp cho bạn khả năng thu thập thông tin giống như kẻ tấn công tin tưởng, nhưng với bối cảnh, xác thực và giám sát liên tục. Thay vì phải chuyển qua các danh sách tài sản một cách thủ công hoặc phản ứng với các cảnh báo sau khi sự việc xảy ra, bạn có thể sử dụng Sprocket ASM để xem những gì kẻ tấn công thấy theo thời gian thực.

Những hiểu biết của Cammilleri là “Nếu bạn có ASM, bạn có thể dành ít thời gian hơn ở các giai đoạn khám phá và chuyển thẳng vào các giai đoạn kiểm tra và xác thực. Bạn sẽ hiệu quả hơn và có thể mở rộng hơn trong việc kiểm tra tấn công của bạn.”

ASM thành công không chỉ nằm ở khả năng nhìn thấy. Nó còn liên quan đến những hiểu biết hành động. Nhiều tổ chức [bỏ lỡ các điểm phơi bày quan trọng](https://www.sprocketsecurity.com/blog/attack-surface-management-asm-what-youre-missing-and-why-it-matters) vì họ dựa quá nhiều vào các CMDB nội bộ hoặc các danh sách tài sản cũ. Khi các hệ thống đó bắt kịp, kẻ tấn công có thể đã khai thác một phiên bản phát triển bị bỏ quên hoặc một thùng S3 không còn được nhớ đến.

Chìa khóa để biến recon thành phòng ngừa? Tổ chức hóa ASM. Tích hợp nó vào các quy trình làm việc hàng ngày, kết nối nó với quản lý lỗ hổng, và đảm bảo rằng nhóm của bạn hành động đối với những phơi bày với sự khẩn trương mà một kẻ tấn công đã phát hiện chúng.

Nếu bạn không giám sát hạ tầng kỹ thuật số của mình từ bên ngoài vào, ai đó sẽ làm điều đó.

## Làm thế nào để bắt đầu: Đánh bại bọn xấu trước các điểm mù của bạn

Công cụ Sprocket ASM được tạo ra bởi các người thử nghiệm xung quyện hiểu rõ hành vi của kẻ tấn công. Các nhà phòng thủ cần cùng một góc nhìn và tốc độ như đối thủ để giữ an toàn. Công cụ không có phí này cung cấp khả năng nhìn thấy vô song về bề mặt tấn công của bạn và cung cấp cái nhìn sâu sắc vào môi trường đang phát triển.

Bằng cách tiết lộ những gì kẻ tấn công có thể khai thác, công cụ của chúng tôi cho phép nhóm của bạn hành động một cách chủ động và giảm thiểu rủi ro trước khi chúng phát triển.

“Đó là cùng một động cơ mà đội đỏ và các người thử nghiệm của chúng tôi sử dụng trong thực hành pentesting liên tục của họ. Bạn sẽ nhận được thông báo về những phát hiện và thay đổi mới,” Cammilleri chia sẻ, “Nhưng sau đó bạn có thể bổ sung ASM với các tài sản bổ sung mà bạn sở hữu và quản lý.

Nếu có điều gì đó mà kẻ tấn công sẽ hoàn toàn mù quáng về trên Internet, bạn vẫn có thể cung cấp thông tin đó vào ASM và bắt đầu theo dõi nó cho các thay đổi và các vấn đề an ninh.”

![Bảng điều khiển Sprocket Security](https://www.bleepstatic.com/images/news/security/s/sprocket-security/mapping-attack-surface/sprocket-dashboard.jpg)

Sau khi tạo tài khoản miễn phí của bạn, bạn có thể:

✓ **Khám phá tất cả các tài sản bị lộ của bạn** — tên miền, địa chỉ IP, dịch vụ và nhiều hơn nữa — tự động.

✓ **Cắt xuyên qua sự ồn ào** và tập trung vào những gì quan trọng nhất với các ưu tiên rủi ro rõ ràng, có thể hành động.

✓ **Giành quyền kiểm soát** tư thế an ninh của bạn với khám phá tài sản chủ động và quản lý hiệu quả.

Xem [video demo công cụ ASM](https://youtu.be/pKo3ToLzZqY?utm%5Fcampaign=Attack%20Surface%20Management%20Launch%203%2F24&utm%5Fsource=BleepingComputer%20Article&utm%5Fmedium=BleepingComputer&utm%5Fterm=Sponsored%20Article&utm%5Fcontent=How%20Attackers%20Use%20ASM%20Tactics%20and%20How%20You%20Can%20Beat%20Them%20to%20It) toàn diện của chúng tôi để phát hiện thêm nhiều lợi ích khi sử dụng Sprocket ASM.

## Hãy tấn công: Đóng các khoảng trống của bạn

Kẻ tấn công không chờ đợi phép. Họ đã quét, lập bản đồ và khai thác các tài sản bị lộ. Nếu bạn không nhìn vào bề mặt tấn công của mình như cách mà một kẻ tấn công sẽ làm, bạn đã ở thế bất lợi. Bạn không thể bảo đảm những gì bạn không biết là tồn tại.

Các tài sản không biết, IT bóng và các dịch vụ cấu hình sai là những liên kết yếu mà kẻ tấn công thích tìm thấy, và các công cụ an ninh truyền thống thường bỏ qua.

Đó là lý do tại sao khả năng nhìn thấy là cơ sở. Sử dụng khả năng nhìn thấy để củng cố, không gây hại, bằng cách liên tục phát hiện bề mặt tấn công bên ngoài của bạn, ưu tiên phơi bày theo rủi ro thực tế, và đóng các khoảng trống trước khi kẻ thù khai thác chúng.

Với các giải pháp như Sprocket ASM, bạn có thể ngừng chơi trò bắt kịp và bắt đầu nhìn thấy hạ tầng của mình như cách mà kẻ tấn công làm, và đó là cách bạn có thể đánh bại họ.

_Được tài trợ và viết bởi [Sprocket Security](https://www.sprocketsecurity.com/solutions/attack-surface-management?utm%5Fcampaign=Attack%20Surface%20Management%20Launch%203%2F24&utm%5Fsource=BleepingComputer%20Article&utm%5Fmedium=BleepingComputer&utm%5Fterm=Sponsored%20article&utm%5Fcontent=How%20Attackers%20Use%20ASM%20Tactics%20and%20How%20You%20Can%20Beat%20Them%20to%20It)_