# Tin tặc tuyên bố tấn công Resecurity, công ty nói đó là một honeypot

![Tin tặc giơ tay lên](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

_Cập nhật: Bài viết đã được cập nhật để phản ánh rằng ShinyHunters nói họ không tham gia hoạt động này. Chúng tôi đã cập nhật câu chuyện và tiêu đề._

Các tác nhân đe doạ liên quan đến "Scattered Lapsus$ Hunters" (SLH) tuyên bố đã xâm phạm các hệ thống của công ty an ninh mạng Resecurity và đánh cắp dữ liệu nội bộ, trong khi Resecurity nói những kẻ tấn công chỉ truy cập vào một honeypot được triển khai cố ý chứa thông tin giả nhằm theo dõi hoạt động của họ.

Hôm nay, các tác nhân đe doạ đã xuất bản ảnh chụp màn hình trên Telegram về vụ xâm phạm bị cáo buộc, tuyên bố họ đã đánh cắp dữ liệu nhân viên, liên lạc nội bộ, báo cáo tình báo về các mối đe doạ và thông tin khách hàng.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

"Chúng tôi muốn thông báo rằng chúng tôi đã có quyền truy cập đầy đủ vào hệ thống REsecurity," nhóm viết trên Telegram, tuyên bố họ đã đánh cắp "tất cả các cuộc trò chuyện và nhật ký nội bộ", "toàn bộ dữ liệu nhân viên", "các báo cáo liên quan đến threat intel", và một "danh sách khách hàng hoàn chỉnh kèm chi tiết."

![Một phần của bài đăng trên Telegram bởi các tác nhân đe doạ](https://www.bleepstatic.com/images/news/security/r/resecurity/partial-post-on-telgram.jpg)

**Một phần của bài đăng trên Telegram bởi các tác nhân đe doạ**  
_Nguồn: BleepingComputer_

Làm bằng chứng cho những tuyên bố của mình, các tác nhân đe doạ đã công bố ảnh chụp màn hình mà họ cho là bị đánh cắp từ Resecurity, bao gồm những gì nhìn có vẻ là một instance hợp tác Mattermost hiển thị các liên lạc giữa nhân viên Resecurity và nhân sự Pastebin liên quan đến nội dung độc hại được lưu trữ trên nền tảng chia sẻ văn bản đó.

Các tác nhân đe doạ, tự gọi mình là "Scattered Lapsus$ Hunters" do sự chồng chéo bị cáo buộc giữa các tác nhân ShinyHunters, Lapsus$, và Scattered Spider, nói rằng cuộc tấn công là trả đũa cho những gì họ cho là các nỗ lực liên tục của Resecurity nhằm xã hội hoá kỹ thuật xã hội nhóm và tìm hiểu thêm về hoạt động của họ.

Các tác nhân đe doạ nói nhân viên Resecurity giả vờ là người mua trong quá trình rao bán một cơ sở dữ liệu hệ thống tài chính bị cáo buộc của Việt Nam, tìm mẫu miễn phí và thông tin bổ sung.

Sau khi xuất bản bài báo này, người phát ngôn của ShinyHunters nói với BleepingComputer rằng họ không tham gia hoạt động này. Mặc dù ShinyHunters luôn tuyên bố là một phần của Scattered Lapsus$ Hunters, họ cho biết họ không liên quan đến cuộc tấn công này.

Chúng tôi đã cập nhật bài viết với thông tin này.

Nếu bạn có thông tin liên quan đến sự cố này hoặc các cuộc tấn công chưa được công bố khác, bạn có thể liên hệ với chúng tôi một cách bảo mật qua Signal tại 646-961-3731 hoặc qua email tips@bleepingcomputer.com.

## Resecurity nói đó là một honeypot

Resecurity phản đối các tuyên bố của tác nhân đe doạ, cho biết các hệ thống bị cáo buộc bị xâm nhập không phải là một phần của hạ tầng sản xuất hợp lệ của họ mà thay vào đó là một honeypot được thiết kế để thu hút và theo dõi các tác nhân đe doạ.

Sau khi BleepingComputer liên hệ với Resecurity về tuyên bố này, họ đã chia sẻ [một báo cáo](https://www.resecurity.com/blog/article/synthetic-data-a-new-frontier-for-cyber-deception-and-honeypots) được xuất bản vào ngày 24 tháng 12, nơi công ty nói họ lần đầu phát hiện một tác nhân đe doạ dò probe các hệ thống được phơi bày công khai vào ngày 21 tháng 11 năm 2025.

Công ty cho biết đội DFIR của họ đã xác định các chỉ số reconnaissance sớm và ghi lại nhiều địa chỉ IP liên quan đến tác nhân, bao gồm các địa chỉ có nguồn gốc từ Egypt và dịch vụ Mullvad VPN.

Resecurity nói họ đã phản ứng bằng cách triển khai một tài khoản "honeypot" trong một môi trường cô lập cho phép tác nhân đe doạ đăng nhập và tương tác với các hệ thống chứa dữ liệu nhân viên, khách hàng và thanh toán giả mạo trong khi được các nhà nghiên cứu giám sát.

Honeypot là một hệ thống hoặc tài khoản được phơi bày và giám sát có chủ ý nhằm dụ kẻ tấn công, cho phép họ bị quan sát và phân tích và thu thập tình báo về hoạt động của họ mà không đặt dữ liệu hoặc hạ tầng thật vào rủi ro.

Công ty cho biết họ đã điền honeypot bằng các bộ dữ liệu tổng hợp được thiết kế để rất giống dữ liệu doanh nghiệp thực tế. Những dữ liệu này bao gồm hơn 28.000 hồ sơ tiêu dùng tổng hợp và hơn 190.000 hồ sơ giao dịch thanh toán tổng hợp, cả hai đều được tạo từ định dạng API chính thức của Stripe.

Theo Resecurity, tác nhân đe doạ bắt đầu cố gắng tự động hóa việc rút dữ liệu vào tháng 12, tạo ra hơn 188.000 yêu cầu giữa ngày 12 tháng 12 và ngày 24 tháng 12 trong khi sử dụng số lượng lớn địa chỉ IP proxy dân cư.

Trong suốt hoạt động này, công ty nói họ đã thu thập được telemetery về thủ đoạn, kỹ thuật và hạ tầng của kẻ tấn công.

**Resecurity giám sát hoạt động trên honeypot**  
_Nguồn: Resecurity_

Resecurity khẳng định rằng kẻ tấn công đã tạm thời phơi bày các địa chỉ IP xác nhận nhiều lần do lỗi kết nối proxy, và thông tin tình báo đó đã được báo cáo cho cơ quan thực thi pháp luật.

Sau khi quan sát thêm hoạt động, Resecurity nói họ đã thêm các bộ dữ liệu giả tiếp theo để nghiên cứu hành vi của kẻ tấn công, điều này dẫn đến thêm các lỗi OPSEC và giúp thu hẹp hạ tầng của tác nhân đe doạ.  
Công ty cho biết sau đó họ đã xác định các máy chủ được sử dụng để tự động hoá cuộc tấn công thông qua proxy dân cư và chia sẻ thông tin tình báo đó với cơ quan thực thi pháp luật.

"Một khi tác nhân được định vị sử dụng tình báo mạng có sẵn và dấu thời gian, một tổ chức thực thi pháp luật nước ngoài, đối tác của Resecurity, đã phát hành một yêu cầu trát đòi liên quan đến tác nhân đe doạ," Resecurity cho biết.

Tại thời điểm viết bài, các tác nhân đe doạ chưa cung cấp thêm bằng chứng nào, chỉ đăng một bài Telegram mới tuyên bố rằng sẽ có thêm thông tin sớm.

"Nice damage control Resecurity. More information coming soon!," đọc một bài đăng trên Telegram.