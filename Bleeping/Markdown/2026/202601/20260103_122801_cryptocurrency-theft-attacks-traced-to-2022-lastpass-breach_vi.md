# Các cuộc tấn công trộm tiền điện tử được truy vết đến vụ vi phạm LastPass 2022

![Trộm cắp LastPass](https://www.bleepstatic.com/content/hl-images/2025/12/31/lastpass-empty-vaults.jpg)

Công ty điều tra blockchain TRM Labs cho biết các vụ trộm tiền điện tử đang diễn ra đã được truy vết đến vụ vi phạm LastPass năm 2022, với kẻ tấn công rút sạch ví nhiều năm sau khi các kho mật khẩu được mã hóa bị đánh cắp và rửa tiền thông qua các sàn giao dịch liên quan đến Nga.

Vào năm 2022, [LastPass tiết lộ](https://www.bleepingcomputer.com/news/security/lastpass-developer-systems-hacked-to-steal-source-code/) rằng kẻ tấn công đã xâm nhập hệ thống của họ bằng cách xâm phạm một môi trường phát triển, đánh cắp một phần mã nguồn của công ty và thông tin kỹ thuật độc quyền.

Trong một sự cố an ninh sau đó nhưng có liên quan, những kẻ tấn công đã [xâm nhập công ty lưu trữ đám mây GoTo](https://www.bleepingcomputer.com/news/security/goto-says-hackers-breached-its-dev-environment-cloud-storage/) sử dụng thông tin đăng nhập bị đánh cắp trước đó và [đã lấy cắp các bản sao lưu cơ sở dữ liệu LastPass](https://www.bleepingcomputer.com/news/security/lastpass-says-hackers-accessed-customer-data-in-new-breach/) được lưu trữ trên nền tảng này. Đối với một số khách hàng, các kho mật khẩu được mã hóa này không chỉ chứa thông tin đăng nhập, mà còn [chứa khóa riêng và seed phrase của ví tiền điện tử](https://www.bleepingcomputer.com/news/security/lastpass-breach-linked-to-theft-of-44-million-in-crypto/).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Mặc dù các kho mật khẩu được mã hóa, người dùng có mật khẩu chính yếu hoặc tái sử dụng yếu vẫn dễ bị bẻ khóa ngoại tuyến, điều mà người ta tin là đã diễn ra kể từ khi bị rò rỉ.

"Phụ thuộc vào độ dài và độ phức tạp của mật khẩu chính và cài đặt số lần lặp (iteration count), bạn có thể muốn đặt lại mật khẩu chính của mình," [LastPass cảnh báo](http://support.lastpass.com/s/document-item?language=en%5FUS&bundleId=lastpass&topicId=LastPass/security-bulletin-recommended-actions-free-premium-families.html&%5FLANG=enus) khi họ công bố vụ vi phạm.

Liên kết giữa các vụ vi phạm LastPass và các vụ trộm tiền điện tử còn được củng cố bởi U.S. Secret Service, cơ quan này vào năm 2025 đã [tịch thu hơn $23 triệu tiền điện tử](https://www.bleepingcomputer.com/news/security/us-seizes-23-million-in-crypto-stolen-via-password-manager-breach/) và cho biết kẻ tấn công đã có được khóa riêng của nạn nhân bằng cách giải mã dữ liệu kho mật khẩu bị lấy trong vụ vi phạm trình quản lý mật khẩu.

Trong [hồ sơ tòa](http://legacy.www.documentcloud.org/documents/25555236-merged%5F42402%5F-1-1741359918), các nhân viên điều tra cho biết không có bằng chứng rằng thiết bị của nạn nhân bị xâm nhập qua phishing hoặc mã độc, và họ tin rằng vụ trộm có liên quan đến các kho mật khẩu bị đánh cắp.

## Các vụ trộm tiền điện tử liên quan đến vụ vi phạm LastPass

Trong [một báo cáo](https://www.trmlabs.com/resources/blog/trm-traces-stolen-crypto-from-2022-lastpass-breach-on-chain-indicators-suggest-russian-cybercriminal-involvement) xuất bản tuần trước, TRM cho biết các cuộc tấn công trộm tiền điện tử đang diễn ra đã được truy vết đến việc lạm dụng các kho mật khẩu LastPass được mã hóa bị đánh cắp năm 2022.

Thay vì ví bị rút ngay sau khi bị vi phạm, các vụ trộm xảy ra theo từng đợt trong nhiều tháng hoặc nhiều năm sau, cho thấy kẻ tấn công dần dần giải mã các kho mật khẩu và trích xuất các thông tin đăng nhập được lưu trữ.

Các ví bị ảnh hưởng đã bị rút bằng các phương thức giao dịch tương tự, không có báo cáo về một cuộc tấn công mới, cho thấy kẻ tấn công đã sở hữu khóa riêng trước khi tiến hành trộm.

"Liên kết trong báo cáo không dựa trên việc quy trách nhiệm trực tiếp cho từng tài khoản LastPass, mà dựa trên việc tương quan hoạt động chuỗi xuống (downstream on-chain) với mô hình tác động đã biết của vụ vi phạm năm 2022," TRM nói với BleepingComputer.

"Điều đó đã tạo ra một kịch bản trong đó các vụ rút ví sẽ xảy ra lâu sau vụ vi phạm ban đầu, thay vì ngay lập tức, và theo những đợt riêng biệt."

TRM nói với BleepingComputer rằng cuộc điều tra của họ ban đầu dựa trên một số báo cáo nhỏ, bao gồm các đơn gửi tới Chainabuse, trong đó người dùng xác định vụ vi phạm LastPass là phương pháp mà ví của họ bị đánh cắp.

Các nhà nghiên cứu đã mở rộng cuộc điều tra bằng cách xác định hành vi giao dịch tiền điện tử trên các trường hợp khác, liên kết các vụ trộm với chiến dịch đánh cắp dữ liệu LastPass.

TRM nói với BleepingComputer rằng phần quan trọng nhất trong nghiên cứu của họ là khả năng truy vết số tiền bị đánh cắp ngay cả sau khi chúng được trộn bằng tính năng CoinJoin của Wasabi Wallet.

CoinJoin là một kỹ thuật bảo mật cho Bitcoin kết hợp giao dịch của nhiều người dùng thành một giao dịch duy nhất, khiến việc xác định đầu vào tương ứng với đầu ra trở nên khó khăn hơn.

Wasabi Wallet bao gồm CoinJoin như một tính năng tích hợp, cho phép người dùng tự động trộn Bitcoin của họ với người khác để che dấu giao dịch mà không cần phụ thuộc vào dịch vụ trộn.

Sau khi rút ví, kẻ tấn công chuyển đổi tiền điện tử bị đánh cắp sang Bitcoin, điều hướng chúng qua Wasabi Wallet, và cố gắng che dấu dấu vết bằng các giao dịch CoinJoin.

Tuy nhiên, TRM cho biết họ đã có thể "demix" lượng tiền điện tử được gửi qua các giao dịch CoinJoin bằng cách phân tích các đặc điểm hành vi, chẳng hạn như cấu trúc giao dịch, thời gian và các lựa chọn cấu hình ví.

"Thay vì cố gắng demix từng vụ trộm một cách riêng lẻ, các nhà phân tích của TRM phân tích hoạt động như một chiến dịch có điều phối, xác định các cụm tiền gửi và rút Wasabi theo thời gian. Sử dụng các kỹ thuật demixing độc quyền, các nhà phân tích đã ghép các khoản tiền gửi của hacker với một cụm rút cụ thể có giá trị tổng hợp và thời gian phù hợp chặt chẽ với dòng tiền vào, một sự phù hợp về mặt thống kê khó có thể trùng hợp ngẫu nhiên.

Dấu vân blockchain quan sát trước khi trộn, kết hợp với thông tin tình báo liên quan đến các ví sau quá trình trộn, liên tục chỉ ra sự kiểm soát vận hành có nguồn gốc tại Nga. Sự liên tục giữa các giai đoạn trước-trộn và sau-trộn củng cố niềm tin rằng hoạt động rửa tiền được thực hiện bởi các tác nhân hoạt động trong, hoặc liên kết chặt chẽ với, hệ sinh thái tội phạm mạng của Nga."

❖ TRM Labs

Bằng cách coi các vụ trộm là một chiến dịch phối hợp thay vì các xâm phạm đơn lẻ, TRM đã có thể khớp các nhóm khoản tiền gửi Wasabi với các mẫu rút tiền phù hợp với các cuộc tấn công trộm tiền điện tử thông qua vụ vi phạm LastPass.

Các lần rút tiền sớm sau khi ví bị rút thêm nữa cho thấy cùng những tác nhân đe doạ đã lấy tiền đồng thời là những người thực hiện hoạt động trộn.

Sử dụng kỹ thuật này, TRM ước tính hơn $28 triệu tiền điện tử đã bị đánh cắp và rửa thông qua Wasabi Wallet vào cuối 2024 và đầu 2025. Thêm $7 triệu nữa được liên kết với một làn sóng tấn công sau đó vào tháng 9 năm 2025.

TRM cho biết số tiền này được nhiều lần rút về tiền mặt qua cùng các sàn giao dịch liên kết với Nga, bao gồm Cryptex và Audi6, càng chỉ ra rằng cùng những tác nhân đe doạ đứng sau các vụ vi phạm này.