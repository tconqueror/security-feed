# Trình quản lý mật khẩu KeePass giả mạo dẫn đến cuộc tấn công ransomware ESXi

![Hacker với logo KeePass](https://www.bleepstatic.com/content/hl-images/2023/10/19/background.jpg)

Các tác nhân đe dọa đã phân phối các phiên bản trojan của trình quản lý mật khẩu KeePass trong ít nhất tám tháng để cài đặt các beacon Cobalt Strike, đánh cắp thông tin xác thực và cuối cùng là triển khai ransomware vào mạng đã bị xâm nhập.

Nhóm Tình báo Đe dọa của WithSecure đã phát hiện ra chiến dịch này sau khi họ được mời để điều tra một cuộc tấn công ransomware. Các nhà nghiên cứu phát hiện rằng cuộc tấn công bắt đầu với một trình cài đặt KeePass độc hại được quảng bá qua các quảng cáo Bing mà quảng bá các trang web phần mềm giả.

Bởi vì KeePass là mã nguồn mở, các tác nhân đe dọa đã thay đổi mã nguồn để xây dựng một phiên bản trojan hóa, được gọi là KeeLoader, chứa tất cả các chức năng quản lý mật khẩu bình thường. Tuy nhiên, nó bao gồm các sửa đổi cài đặt một beacon Cobalt Strike và xuất cơ sở dữ liệu mật khẩu KeePass dưới dạng văn bản rõ, sau đó bị đánh cắp qua beacon.

WithSecure cho biết rằng các watermark Cobalt Strike được sử dụng trong chiến dịch này liên quan đến một broker truy cập ban đầu (IAB) được cho là có liên quan đến các cuộc tấn công ransomware Black Basta trong quá khứ.

Một watermark Cobalt Strike là một định danh duy nhất được nhúng vào một beacon mà được gắn liền với giấy phép được sử dụng để tạo ra payload.

"Watermark này thường được ghi nhận trong bối cảnh của các beacon và miền liên quan đến ransomware Black Basta. Nó có thể được sử dụng bởi các tác nhân đe dọa hoạt động như các Broker Truy cập Ban đầu làm việc chặt chẽ với Black Basta," giải thích [WithSecure](https://labs.withsecure.com/content/dam/labs/docs/W%5FIntel%5FResearch%5FKeePass%5FTrojanised%5FMalware%5FCampaign.pdf).

"Chúng tôi không biết về bất kỳ sự cố nào khác (bao gồm ransomware hoặc không) sử dụng watermark beacon Cobalt Strike này – điều này không có nghĩa là nó chưa từng xảy ra."

Các nhà nghiên cứu đã tìm thấy nhiều biến thể của KeeLoader đã được phát hiện, được ký bằng các chứng chỉ hợp pháp và được phát tán qua các miền typo-squatting như keeppaswrd\[.\]com, keegass\[.\]com và KeePass\[.\]me.

BleepingComputer đã xác nhận rằng trang web keeppaswrd\[.\]com vẫn đang hoạt động và tiếp tục phân phối trình cài đặt KeePass giả mạo \[[VirusTotal](https://www.virustotal.com/gui/file/0000cff6a3c7f7eebc0edc3d1e42e454ebb675e57d6fc1fd968952694b1b44b3)\].

![Trang KeePass giả mạo đẩy trình cài đặt trojan](https://www.bleepstatic.com/images/news/malware/k/keepass/keepass-iab/keepass-malware-site.jpg)

**Trang KeePass giả mạo đẩy trình cài đặt trojan**  
_Nguồn: BleepingComputer_

Ngoài việc thả các beacon Cobalt Strike, chương trình KeePass giả mạo còn bao gồm chức năng đánh cắp mật khẩu cho phép các tác nhân đe dọa đánh cắp bất kỳ thông tin xác thực nào được nhập vào chương trình.

"KeeLoader không chỉ được sửa đổi đến mức có thể hoạt động như một loader phần mềm độc hại. Chức năng của nó đã được mở rộng để hỗ trợ việc exfiltration dữ liệu cơ sở dữ liệu KeePass," đọc báo cáo của WithSecure.

"Khi dữ liệu cơ sở dữ liệu KeePass được mở; thông tin tài khoản, tên đăng nhập, mật khẩu, trang web và bình luận cũng được xuất ra ở định dạng CSV dưới %localappdata% dưới dạng .kp. Giá trị số nguyên ngẫu nhiên này nằm trong khoảng từ 100-999."

![Đánh cắp thông tin đăng nhập KeePass](https://www.bleepstatic.com/images/news/malware/k/keepass/keepass-iab/dumping-keepass-credentials.jpg)

**Đánh cắp thông tin đăng nhập KeePass**  
_Nguồn: WithSecure_

Cuối cùng, cuộc tấn công được điều tra bởi WithSecure đã dẫn đến việc máy chủ VMware ESXi của công ty bị mã hóa bằng ransomware.

Cuộc điều tra sâu hơn về chiến dịch đã phát hiện ra một cơ sở hạ tầng rộng lớn được tạo ra để phân phối các chương trình độc hại ngụy trang thành các công cụ hợp pháp và các trang phishing được thiết kế để đánh cắp thông tin xác thực.

Miền aenys\[.\]com đã được sử dụng để lưu trữ các miền phụ bổ sung giả mạo các công ty và dịch vụ nổi tiếng, chẳng hạn như WinSCP, PumpFun, Phantom Wallet, Sallie Mae, Woodforest Bank và DEX Screener.

Mỗi cái trong số này được sử dụng để phân phối các biến thể phần mềm độc hại khác nhau hoặc đánh cắp thông tin xác thực.

WithSecure gán hoạt động này với độ tin cậy vừa phải cho UNC4696, một nhóm tác nhân đe dọa trước đó liên quan đến các [chiến dịch Nitrogen Loader](https://www.bleepingcomputer.com/news/security/new-nitrogen-malware-pushed-via-google-ads-for-ransomware-attacks/). Các chiến dịch Nitrogen trước đây được liên kết với ransomware BlackCat/ALPHV.

Người dùng luôn được khuyên nên tải phần mềm, đặc biệt là các phần mềm nhạy cảm như trình quản lý mật khẩu, từ các trang web hợp pháp và tránh bất kỳ trang nào có liên kết quảng cáo.

Ngay cả khi một quảng cáo hiển thị URL chính xác cho một dịch vụ phần mềm, nó vẫn nên được tránh, bởi vì [các tác nhân đe dọa đã chứng minh nhiều lần](https://www.bleepingcomputer.com/news/security/convincing-youtube-google-ads-lead-to-windows-support-scams/) rằng họ có thể [vượt qua chính sách quảng cáo](https://www.bleepingcomputer.com/news/security/google-ads-push-fake-google-authenticator-site-installing-malware/) để [hiển thị URL hợp pháp](https://www.bleepingcomputer.com/news/security/arc-browsers-windows-launch-targeted-by-google-ads-malvertising/) trong khi liên kết đến các trang giả mạo.