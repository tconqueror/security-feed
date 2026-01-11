# Instagram phủ nhận có vi phạm giữa các cáo buộc rò rỉ dữ liệu 17 triệu tài khoản

![Instagram](https://www.bleepstatic.com/content/hl-images/2023/12/20/instagram.jpg)

Instagram cho biết họ đã sửa một lỗi cho phép các tác nhân độc hại yêu cầu hàng loạt email đặt lại mật khẩu, giữa lúc có cáo buộc rằng dữ liệu từ hơn 17 triệu tài khoản Instagram đã bị thu thập và rò rỉ trực tuyến.

"We fixed an issue that allowed an external party to request password reset emails for some Instagram users," một phát ngôn viên của Meta told BleepingComputer.

"We want to reassure everyone there was no breach of our systems and people's Instagram accounts remain secure. People can disregard these emails and we apologize for any confusion this may have caused."

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Một làn sóng truyền thông về một vụ rò rỉ dữ liệu Instagram bị cáo buộc bắt đầu sau khi Malwarebytes [warned its customers](https://x.com/Malwarebytes/status/2009664994070184282) rằng tội phạm mạng đã đánh cắp dữ liệu từ 17,5 triệu tài khoản.

Dữ liệu Instagram bị cáo buộc này đã được phát hành miễn phí trên nhiều diễn đàn hacker, với người đăng tuyên bố nó được thu thập thông qua một [unconfirmed 2024 Instagram API leak](https://x.com/darkeye%5Fteam/status/1856158197255680195).

![Bài đăng diễn đàn rò rỉ dữ liệu Instagram bị cáo buộc](https://www.bleepstatic.com/images/news/security/i/instagram/api-scrape-leak/forum-post.jpg)

**Bài đăng trên diễn đàn rò rỉ dữ liệu Instagram bị cáo buộc**

Tổng cộng, dữ liệu được chia sẻ chứa 17,017,213 hồ sơ tài khoản Instagram, bao gồm số điện thoại, tên người dùng, họ tên, địa chỉ nơi ở, địa chỉ email và Instagram IDs.

Không phải tất cả thông tin này đều có ở mỗi bản ghi, một số bản ghi chỉ chứa một Instagram ID và một tên người dùng.

Các nhà nghiên cứu an ninh mạng trên X claim \[[1](https://x.com/IntCyberDigest/status/2010055422523388088), [2](https://x.com/seblatombe/status/2009986151419978085)\] rằng dữ liệu bị cào là từ một sự cố cào API năm 2022, nhưng họ chưa cung cấp bằng chứng rõ ràng để xác nhận điều này.

Hơn nữa, Meta told BleepingComputer rằng họ không biết về bất kỳ sự cố API nào vào năm 2022 hoặc 2024.

Tuy nhiên, Instagram trước đây đã từng chịu các sự cố cào API, chẳng hạn như một [lỗi năm 2017 đã bị lợi dụng](http://arstechnica.com/information-technology/2017/08/celebs-phone-numbers-and-e-mail-addresses-exposed-in-active-instagram-hack/) để cào và bán thông tin cá nhân của khoảng [6 triệu tài khoản bị cáo buộc](http://www.thedailybeast.com/hackers-make-searchable-database-to-dox-instagram-celebs/).

Chưa rõ liệu dữ liệu Instagram mới bị rò rỉ này có phải là tổng hợp từ vụ rò rỉ năm 2017 cộng với thông tin bổ sung trong vài năm gần đây hay không.

BleepingComputer đã liên hệ với người đã rò rỉ thông tin Instagram để xác nhận thời điểm nó bị đánh cắp, nhưng không nhận được phản hồi.

## Instagram phủ nhận có vi phạm

Hiện tại không có bằng chứng cho thấy sự cố này là một vụ rò rỉ dữ liệu Instagram mới. Meta nói họ không biết về bất kỳ sự xâm phạm API nào vào năm 2022 hoặc 2024 và rằng không có vụ vi phạm mới nào.

Hơn nữa, các nhà nghiên cứu chưa cung cấp bằng chứng rằng bộ dữ liệu rò rỉ được thu thập thông qua một lỗ hổng gần đây.

Thay vào đó, thông tin cho thấy dữ liệu có thể là một tổng hợp của các thông tin đã bị cào trước đó từ nhiều nguồn trong vài năm.

Tin tốt là dữ liệu bị rò rỉ này không chứa mật khẩu, vì vậy không cần thiết phải thay đổi mật khẩu.

Tuy nhiên, mọi người cần cảnh giác trước các chiến dịch lừa đảo có mục tiêu, smishing (lừa đảo qua tin nhắn văn bản) và các cuộc tấn công tấn công xã hội lợi dụng thông tin này.

Tội phạm mạng thường sử dụng dữ liệu bị rò rỉ để cố gắng đánh cắp thêm thông tin, chẳng hạn như mật khẩu của người dùng.

Nếu bạn nhận được một email đặt lại mật khẩu Instagram hoặc mã xác thực qua tin nhắn đến số điện thoại của bạn mà bạn không khởi xướng việc khôi phục tài khoản, thì đơn giản là bỏ qua và xóa chúng.

Nếu bạn chưa bật xác thực hai yếu tố trên tài khoản của mình, rất khuyến nghị rằng bạn [turn it on to increase your security](https://help.instagram.com/566810106808145).