# ShinyHunters tuyên bố tấn công Resecurity, công ty nói đó là một honeypot

![Người tấn công giơ tay lên](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

Nhóm tấn công ShinyHunters tuyên bố họ đã xâm nhập hệ thống của công ty an ninh mạng Resecurity và đánh cắp dữ liệu nội bộ, trong khi Resecurity cho biết những kẻ tấn công chỉ truy cập vào một honeypot được triển khai có chủ đích chứa thông tin giả dùng để giám sát hoạt động của chúng.

Hôm nay, các tác nhân đe dọa đã công bố ảnh chụp màn hình trên Telegram về vụ tấn công được cho là, tuyên bố đã đánh cắp dữ liệu nhân viên, thông tin liên lạc nội bộ, báo cáo tình báo mối đe dọa và thông tin khách hàng.

"Chúng tôi muốn thông báo rằng chúng tôi đã có toàn quyền truy cập vào hệ thống REsecurity," nhóm viết trên Telegram, tuyên bố đã đánh cắp "tất cả các cuộc trò chuyện nội bộ và nhật ký", "dữ liệu nhân viên đầy đủ", "các báo cáo liên quan tới threat intel", và một "danh sách khách hàng hoàn chỉnh kèm chi tiết."

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

![Một phần bài đăng trên Telegram của các tác nhân đe dọa](https://www.bleepstatic.com/images/news/security/r/resecurity/partial-post-on-telgram.jpg)

**Một phần bài đăng trên Telegram của các tác nhân đe dọa**  
_Source: BleepingComputer_

Làm bằng chứng cho các tuyên bố của họ, các tác nhân đe dọa đã công bố ảnh chụp màn hình mà họ khẳng định bị đánh cắp từ Resecurity, bao gồm những gì có vẻ là một phiên bản Mattermost cho thấy các trao đổi giữa nhân viên Resecurity và nhân sự Pastebin về nội dung độc hại được lưu trữ trên nền tảng chia sẻ văn bản đó.

Các tác nhân đe dọa, tự gọi mình là "Scattered Lapsus$ Hunters" do sự trùng lặp cáo buộc giữa ShinyHunters, Lapsus$ và Scattered Spider, nói rằng cuộc tấn công là hành động trả đũa cho những gì họ cho là các cố gắng liên tục của Resecurity nhằm thực hiện social engineering với nhóm và tìm hiểu thêm về hoạt động của họ.

ShinyHunters nói rằng nhân viên Resecurity giả vờ là người mua trong quá trình bán một cơ sở dữ liệu hệ thống tài chính của Vietnam, tìm mẫu miễn phí và thêm thông tin.

Nếu bạn có bất kỳ thông tin nào liên quan đến sự cố này hoặc các cuộc tấn công chưa được tiết lộ khác, bạn có thể liên hệ với chúng tôi một cách bảo mật qua Signal tại 646-961-3731 hoặc tại tips@bleepingcomputer.com.

## Resecurity nói đó là một honeypot

Resecurity phản bác các tuyên bố của ShinyHunters, khẳng định rằng hệ thống bị cáo buộc bị xâm nhập không phải là một phần của cơ sở hạ tầng sản xuất hợp pháp của họ mà thay vào đó là một honeypot được thiết kế để thu hút và giám sát các tác nhân đe dọa.

Sau khi BleepingComputer liên hệ với Resecurity về cáo buộc, họ đã chia sẻ [một báo cáo](https://www.resecurity.com/blog/article/synthetic-data-a-new-frontier-for-cyber-deception-and-honeypots) được công bố vào ngày 24 tháng 12, trong đó công ty cho biết họ lần đầu phát hiện một tác nhân đe dọa dò xét các hệ thống công khai của họ vào ngày 21 tháng 11, 2025.

Công ty cho biết đội DFIR của họ đã nhận diện các chỉ báo do thám sớm và ghi lại nhiều địa chỉ IP liên quan đến tác nhân, bao gồm các địa chỉ có nguồn gốc từ Egypt và dịch vụ Mullvad VPN.

Resecurity cho biết họ đã phản ứng bằng cách triển khai một tài khoản "honeypot" trong một môi trường cô lập cho phép tác nhân đe dọa đăng nhập và tương tác với các hệ thống chứa dữ liệu nhân viên, khách hàng và thanh toán giả trong khi đang được các nhà nghiên cứu giám sát.

Honeypot là một hệ thống hoặc tài khoản được phơi bày có chủ đích và được giám sát nhằm dụ dỗ kẻ tấn công, cho phép quan sát và phân tích chúng và thu thập tình báo về hoạt động mà không đặt dữ liệu hoặc cơ sở hạ tầng thực tế vào rủi ro.

Công ty cho biết họ đã điền vào honeypot bằng các bộ dữ liệu tổng hợp được thiết kế để giống với dữ liệu doanh nghiệp thực tế. Những bộ dữ liệu này bao gồm hơn 28.000 hồ sơ người tiêu dùng tổng hợp và hơn 190.000 hồ sơ giao dịch thanh toán tổng hợp, cả hai đều được tạo từ định dạng API chính thức của Stripe.

Theo Resecurity, tác nhân đe dọa bắt đầu cố gắng tự động hóa việc trích xuất dữ liệu vào tháng 12, tạo hơn 188.000 yêu cầu giữa ngày 12 tháng 12 và 24 tháng 12 trong khi sử dụng số lượng lớn các địa chỉ IP proxy residential.

Trong quá trình hoạt động này, công ty cho biết họ đã thu thập được telemetry về chiến thuật, kỹ thuật và cơ sở hạ tầng của kẻ tấn công.

**Hoạt động giám sát của Resecurity trên honeypot**  
_Source: Resecurity_

Resecurity khẳng định rằng kẻ tấn công đã vô tình lộ các địa chỉ IP đã được xác nhận trong thời gian ngắn ở nhiều dịp do lỗi kết nối proxy, và rằng thông tin tình báo đã được báo cáo cho cơ quan thực thi pháp luật.

Sau khi quan sát thêm hoạt động, Resecurity cho biết họ đã thêm các bộ dữ liệu giả khác để nghiên cứu hành vi của kẻ tấn công, điều này dẫn tới thêm các thất bại OPSEC và giúp thu hẹp cơ sở hạ tầng của tác nhân đe dọa.  
Công ty nói rằng họ sau đó đã xác định các máy chủ được sử dụng để tự động hóa cuộc tấn công thông qua các residential proxies và chia sẻ tình báo đó với cơ quan thực thi pháp luật.

"Khi tác nhân được định vị bằng cách sử dụng tình báo mạng có sẵn và các dấu thời gian, một tổ chức thực thi pháp luật nước ngoài, là đối tác của Resecurity, đã phát hành một yêu cầu trát yêu cầu liên quan tới tác nhân đe dọa," Resecurity nói.

Tại thời điểm viết bài, ShinyHunters chưa cung cấp bất kỳ bằng chứng bổ sung nào, chỉ đăng một bài Telegram mới tuyên bố rằng sẽ có thêm thông tin sớm.

"Nice damage control Resecurity. More information coming soon!," các tác nhân đe dọa đăng.