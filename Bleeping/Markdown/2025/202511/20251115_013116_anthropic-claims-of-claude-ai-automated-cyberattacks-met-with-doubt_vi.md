# Anthropic tuyên bố các cuộc tấn công mạng tự động hóa bằng Claude AI gây hoài nghi

![Trí tuệ nhân tạo độc hại](https://www.bleepstatic.com/content/hl-images/2022/05/12/evil-hacker-ai.jpg)

Anthropic báo cáo rằng một nhóm đe dọa được nhà nước Trung Quốc tài trợ, được theo dõi dưới tên GTG-1002, đã tiến hành một chiến dịch gián điệp mạng chủ yếu được tự động hóa thông qua lạm dụng mô hình Claude Code của công ty.

Tuy nhiên, các tuyên bố của Anthropic lập tức gây ra sự hoài nghi rộng rãi, với các nhà nghiên cứu bảo mật và chuyên gia AI gọi báo cáo này là "[bịa đặt](https://x.com/%5Falialkhatib/status/1989346279588348121)" và buộc tội công ty phóng đại sự cố.

Những người khác cho rằng báo cáo đã phóng đại những gì các hệ thống AI hiện tại có thể thực sự thực hiện.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

"Việc Anthropic làm là quảng cáo sáo rỗng. AI là một cú hích lớn nhưng nó không phải skynet, nó không suy nghĩ, nó thực sự không phải là trí tuệ nhân tạo (đó là một điều tiếp thị mà người ta nghĩ ra)," đăng bởi nhà nghiên cứu an ninh mạng [Daniel Card](http://x.com/UK%5FDaniel%5FCard/status/1989322655846072680).

Phần lớn sự hoài nghi xuất phát từ việc Anthropic không cung cấp chỉ số xâm phạm (IOCs) cho chiến dịch. Hơn nữa, các yêu cầu của BleepingComputer về thông tin kỹ thuật về các cuộc tấn công đã không được trả lời.

## Tuyên bố các cuộc tấn công được tự động hóa 80-90% bởi AI

Bất chấp chỉ trích, Anthropic tuyên bố rằng sự cố này đại diện cho trường hợp đầu tiên được ghi nhận công khai về hoạt động xâm nhập tự trị quy mô lớn do một mô hình AI điều phối.

Cuộc tấn công, mà [Anthropic nói](http://www.anthropic.com/news/disrupting-AI-espionage) họ đã gián đoạn vào giữa tháng 9 năm 2025, đã sử dụng mô hình Claude Code để nhắm mục tiêu 30 thực thể, bao gồm các công ty công nghệ lớn, tổ chức tài chính, nhà sản xuất hóa chất và cơ quan chính phủ.

Mặc dù công ty cho biết chỉ một số ít vụ xâm nhập thành công, họ nhấn mạnh chiến dịch này là trường hợp đầu tiên có quy mô như vậy, với AI được cho là tự động thực hiện hầu hết các giai đoạn của quy trình gián điệp mạng.

"Nhóm tác nhân đã đạt được điều mà chúng tôi tin là trường hợp được ghi nhận đầu tiên của một cuộc tấn công mạng phần lớn được thực hiện mà không có can thiệp của con người ở quy mô lớn—AI tự động phát hiện lỗ hổng… khai thác chúng trong các hoạt động trực tiếp, sau đó thực hiện nhiều hoạt động hậu khai thác," Anthropic giải thích trong [báo cáo](http://assets.anthropic.com/m/ec212e6566a0d47/original/Disrupting-the-first-reported-AI-orchestrated-cyber-espionage-campaign.pdf).

"Quan trọng nhất, đây đánh dấu trường hợp được ghi nhận đầu tiên của AI có tính tác nhân thành công trong việc thu được quyền truy cập vào các mục tiêu giá trị cao đã được xác nhận để thu thập tình báo, bao gồm các tập đoàn công nghệ lớn và các cơ quan chính phủ."

![Kiến trúc tấn công](https://www.bleepstatic.com/images/news/u/1220909/2025/November/attack(1).jpg)

**Kiến trúc tấn công**  
_Nguồn: Anthropic_

Anthropic báo cáo rằng các hacker Trung Quốc đã xây dựng một khuôn khổ thao túng Claude để hành động như một tác nhân xâm nhập mạng tự chủ, thay vì chỉ nhận lời khuyên hoặc sử dụng công cụ để tạo các mảnh khung tấn công như đã thấy trong [các sự cố trước đây](https://www.bleepingcomputer.com/news/security/malware-devs-abuse-anthropics-claude-ai-to-build-ransomware/).

Hệ thống sử dụng Claude kết hợp với các tiện ích kiểm thử xâm nhập tiêu chuẩn và một cơ sở hạ tầng dựa trên Model Context Protocol (MCP) để quét, khai thác và trích xuất thông tin mà không có giám sát trực tiếp của con người đối với hầu hết các nhiệm vụ.

Các điều hành viên con người chỉ can thiệp ở những thời điểm quan trọng, chẳng hạn như phê duyệt nâng quyền hoặc xem xét dữ liệu để trích xuất, mà Anthropic ước tính chỉ chiếm 10-20% khối lượng công việc vận hành.

Cuộc tấn công được thực hiện theo sáu giai đoạn riêng biệt, tóm tắt như sau:

* **Giai đoạn 1** – Các điều hành viên con người lựa chọn mục tiêu giá trị cao và sử dụng chiến thuật đóng vai để lừa Claude tin rằng nó đang thực hiện các nhiệm vụ an ninh mạng được ủy quyền, vượt qua các hạn chế an toàn tích hợp của nó.
* **Giai đoạn 2** – Claude tự động quét hạ tầng mạng của nhiều mục tiêu, phát hiện dịch vụ, phân tích cơ chế xác thực và xác định các điểm cuối dễ bị tấn công. Nó duy trì các ngữ cảnh hoạt động riêng biệt, cho phép các cuộc tấn công song song mà không cần giám sát của con người.
* **Giai đoạn 3** – AI tạo ra payloads được tùy chỉnh, tiến hành kiểm thử từ xa và xác thực lỗ hổng. Nó tạo các báo cáo chi tiết để con người xem xét, với con người chỉ can thiệp để phê duyệt việc nâng cấp lên khai thác chủ động.
* **Giai đoạn 4** – Claude trích xuất dữ liệu xác thực từ cấu hình hệ thống, kiểm tra truy cập bằng thông tin đăng nhập và lập bản đồ hệ thống nội bộ. Nó tự điều hướng trong các mạng nội bộ, truy cập API, cơ sở dữ liệu và dịch vụ, trong khi con người chỉ cho phép các xâm nhập nhạy cảm nhất.
* **Giai đoạn 5** – Claude sử dụng quyền truy cập của nó để truy vấn cơ sở dữ liệu, trích xuất dữ liệu nhạy cảm và xác định giá trị tình báo. Nó phân loại các phát hiện, tạo cửa hậu dai dẳng và tạo báo cáo tóm tắt, chỉ yêu cầu phê duyệt của con người cho việc trích xuất dữ liệu cuối cùng.
* **Giai đoạn 6** – Trong suốt chiến dịch, Claude ghi chép mỗi bước theo định dạng có cấu trúc, bao gồm các tài sản phát hiện được, thông tin đăng nhập, phương pháp khai thác và dữ liệu đã trích xuất. Điều này cho phép chuyển giao liền mạch giữa các nhóm tác nhân đe dọa và hỗ trợ khả năng tồn tại lâu dài trong các môi trường đã bị xâm phạm.

**Các giai đoạn của cuộc tấn công**  
_Nguồn: Anthropic_

Anthropic giải thích thêm rằng chiến dịch dựa nhiều hơn vào công cụ nguồn mở thay vì phần mềm độc hại tùy chỉnh, chứng tỏ rằng AI có thể tận dụng các công cụ có sẵn để thực hiện các cuộc tấn công hiệu quả.

Tuy nhiên, Claude không hoàn hảo, vì trong một số trường hợp, nó tạo ra các “ảo tưởng” không mong muốn, kết quả bịa đặt và phóng đại các phát hiện.

Đáp lại việc lạm dụng này, Anthropic đã cấm các tài khoản vi phạm, tăng cường khả năng phát hiện và chia sẻ tình báo với các đối tác để giúp phát triển các phương pháp phát hiện mới cho các xâm nhập do AI điều khiển.