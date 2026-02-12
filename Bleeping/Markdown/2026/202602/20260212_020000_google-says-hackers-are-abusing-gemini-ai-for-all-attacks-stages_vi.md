# Google cho biết hacker đang lạm dụng AI Gemini cho tất cả các giai đoạn tấn công

![Google says hackers are abusing Gemini AI for all attacks stages](https://www.bleepstatic.com/content/hl-images/2026/02/11/ai-extract.jpg)

Các hacker được nhà nước hậu thuẫn đang sử dụng mô hình AI Gemini của Google để hỗ trợ mọi giai đoạn tấn công, từ trinh sát đến các hành động sau khi xâm nhập.

Nhóm tác nhân xấu từ Trung Quốc (APT31, Temp.HEX), Iran (APT42), Triều Tiên (UNC2970) và Nga đã sử dụng Gemini để xác định hồ sơ mục tiêu và thu thập thông tin tình báo nguồn mở, tạo ra mồi nhử phishing, dịch văn bản, viết mã, kiểm tra lỗ hổng và khắc phục sự cố.

Tội phạm mạng cũng ngày càng quan tâm đến các công cụ và dịch vụ AI có thể hỗ trợ hoạt động bất hợp pháp, chẳng hạn như các chiến dịch ClickFix trong kỹ thuật xã hội.

[![Wiz](https://www.bleepstatic.com/c/w/GitLab-970x250.png)](https://www.wiz.io/lp/gitlab-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FGitLab-Security-Best-Practices-Cheat-Sheet&sfcid=701Vh00000Wn1rmIAB&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=GitLab-Best-Practices) 

### Hoạt động độc hại được AI tăng cường

Nhóm Google Threat Intelligence (GTIG) lưu ý trong báo cáo hôm nay rằng các đối thủ APT sử dụng Gemini để hỗ trợ chiến dịch của họ "từ trinh sát và tạo mồi nhử phishing đến phát triển điều khiển & kiểm soát (C2) và đánh cắp dữ liệu."

Các tác nhân đe dọa từ Trung Quốc đã sử dụng một nhân vật chuyên gia an ninh mạng giả mạo để yêu cầu Gemini tự động hóa phân tích lỗ hổng và cung cấp các kế hoạch kiểm tra mục tiêu trong bối cảnh kịch bản giả mạo.

"Các tác nhân đe dọa từ Trung Quốc đã tạo ra một kịch bản giả mạo, trong một trường hợp thử nghiệm công cụ Hexstrike MCP, và hướng dẫn mô hình phân tích Remote Code Execution (RCE), kỹ thuật vượt qua WAF, và kết quả kiểm tra SQL injection nhắm vào các mục tiêu cụ thể tại Mỹ," Google cho biết.

Một tác nhân khác từ Trung Quốc thường xuyên sử dụng Gemini để sửa mã, thực hiện nghiên cứu và cung cấp lời khuyên về khả năng kỹ thuật cho các vụ xâm nhập.

Đối thủ Iran APT42 đã tận dụng LLM của Google cho các chiến dịch kỹ thuật xã hội, như một nền tảng phát triển để đẩy nhanh việc tạo ra các công cụ độc hại tùy chỉnh (gỡ lỗi, tạo mã và nghiên cứu kỹ thuật khai thác).

Việc lạm dụng thêm từ các tác nhân đe dọa đã được quan sát thấy trong việc triển khai các khả năng mới vào các họ mã độc hiện có, bao gồm bộ công cụ phishing CoinBait và trình tải xuống/phóng mã độc HonestCue.

GTIG lưu ý rằng chưa có bước đột phá lớn nào xảy ra ở khía cạnh này, mặc dù gã khổng lồ công nghệ dự đoán các nhà điều hành mã độc sẽ tiếp tục tích hợp khả năng AI vào bộ công cụ của họ.

HonestCue là một khuôn khổ mã độc proof-of-concept được quan sát vào cuối năm 2025 sử dụng Gemini API để tạo mã C# cho mã độc giai đoạn hai, sau đó biên dịch và thực thi các payload trong bộ nhớ.

![HonestCue operational overview](https://www.bleepstatic.com/images/news/u/1220909/2026/February/honestcue.jpg)

**HonestCue operational overview**  
_Nguồn: Google_

CoinBait là bộ công cụ phishing được bọc trong React SPA giả dạng như một sàn giao dịch tiền điện tử để thu thập thông tin đăng nhập. Nó chứa các dấu tích cho thấy quá trình phát triển của nó được thúc đẩy bằng các công cụ tạo mã AI.

Một chỉ số về việc sử dụng LLM là các thông báo nhật ký trong mã nguồn mã độc được bắt đầu bằng "Analytics:", có thể giúp nhà bảo vệ theo dõi quá trình đánh cắp dữ liệu.

Dựa trên các mẫu mã độc, các nhà nghiên cứu GTIG tin rằng mã độc được tạo bằng nền tảng Lovable AI, vì nhà phát triển đã sử dụng Lovable Supabase client và lovable.app.

Tội phạm mạng cũng đã sử dụng [dịch vụ AI tạo sinh trong các chiến dịch ClickFix](https://www.bleepingcomputer.com/news/security/google-ads-for-shared-chatgpt-grok-guides-push-macos-infostealer-malware/), phân phối mã độc đánh cắp thông tin AMOS cho macOS. Người dùng bị dụ dỗ thực thi các lệnh độc hại thông qua quảng cáo độc hại được liệt kê trong kết quả tìm kiếm cho các truy vấn về khắc phục sự cố cụ thể.

**AI-powered ClickFix attack**  
_nguồn: Google_

Báo cáo còn lưu ý rằng Gemini đã đối mặt với các nỗ lực trích xuất và chưng cất mô hình AI, với các tổ chức tận dụng quyền truy cập API được ủy quyền để truy vấn có hệ thống và tái tạo các quy trình ra quyết định nhằm sao chép chức năng của nó.

Mặc dù vấn đề này không phải là mối đe dọa trực tiếp đối với người dùng các mô hình này hoặc dữ liệu của họ, nhưng nó tạo thành vấn đề thương mại, cạnh tranh và sở hữu trí tuệ đáng kể cho các nhà tạo mô hình.

Về cơ bản, các tác nhân lấy thông tin thu được từ một mô hình và chuyển thông tin sang mô hình khác bằng kỹ thuật học máy gọi là "chưng cất kiến thức", được sử dụng để đào tạo các mô hình mới từ các mô hình tiên tiến hơn.

"Việc trích xuất mô hình và chưng cất kiến thức sau đó cho phép kẻ tấn công nhanh chóng đẩy nhanh quá trình phát triển mô hình AI với chi phí thấp hơn đáng kể," các nhà nghiên cứu GTIG cho biết.

Google đánh dấu các cuộc tấn công này là mối đe dọa vì chúng cấu thành hành vi trộm cắp trí tuệ, có khả năng mở rộng và làm suy yếu nghiêm trọng mô hình kinh doanh AI-dịch-vụ, vốn có khả năng ảnh hưởng đến người dùng cuối trong thời gian ngắn.

Trong một cuộc tấn công quy mô lớn thuộc loại này, Gemini AI đã bị nhắm mục tiêu bởi 100.000 lời nhắc đặt ra một loạt câu hỏi nhằm tái tạo quá trình lập luận của mô hình trên nhiều nhiệm vụ bằng ngôn ngữ không phải tiếng Anh.

Google đã vô hiệu hóa các tài khoản và cơ sở hạ tầng liên quan đến lạm dụng được ghi nhận và đã triển khai các biện pháp phòng thủ có mục tiêu trong các bộ phân loại của Gemini để làm cho việc lạm dụng khó khăn hơn.

Công ty khẳng định rằng họ "thiết kế hệ thống AI với các biện pháp bảo mật mạnh mẽ và rào chắn an toàn vững chắc" và thường xuyên kiểm tra các mô hình để cải thiện tính bảo mật và an toàn của chúng.