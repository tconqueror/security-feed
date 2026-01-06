# Các lỗi chèn prompt của Copilot là lỗ hổng hay giới hạn của AI?

![Microsoft Copilot](https://www.bleepstatic.com/content/hl-images/2025/10/06/Microsoft_Copilot.jpg)

Microsoft đã phản bác các khẳng định rằng nhiều vấn đề liên quan đến chèn prompt và sandbox được một kỹ sư an ninh mạng nêu ra trong trợ lý AI Copilot của họ cấu thành các lỗ hổng bảo mật.

Sự việc này làm nổi bật một khoảng cách ngày càng lớn giữa cách các nhà cung cấp và các nhà nghiên cứu định nghĩa rủi ro trong các hệ thống AI sinh sinh.

## Lỗ hổng AI hay các giới hạn đã biết?

"Tháng trước, tôi phát hiện 4 lỗ hổng trong Microsoft Copilot. Họ đã đóng các trường hợp của tôi nói rằng chúng không đủ điều kiện để được xử lý dịch vụ," [đăng trên LinkedIn](https://www.linkedin.com/posts/john-russell-187490b5%5Flast-month-i-discovered-4-vulnerabilities-activity-7412602607325818880-Bon4/) bởi kỹ sư an ninh mạng John Russell.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Cụ thể, các vấn đề được Russell tiết lộ và sau đó bị Microsoft bác bỏ là không đủ điều kiện là lỗ hổng bảo mật bao gồm:

* [Chèn prompt gián tiếp](http://medium.com/@d%5Ff4u1t/indirect-prompt-injection-using-delimiter-and-json-payload-enables-system-prompt-disclosure-in-996a7b15dc01) và [chèn prompt trực tiếp](http://medium.com/@d%5Ff4u1t/direct-prompt-injection-enables-system-prompt-disclosure-in-copilot-feeefddeac97) dẫn đến rò rỉ lời nhắc hệ thống
* Bypass chính sách kiểu tệp khi tải lên của Copilot bằng [mã hóa base64](http://medium.com/@d%5Ff4u1t/base64-file-upload-bypass-in-copilot-allows-restricted-file-type-content-to-enter-session-for-de36e4c3096a)
* Thực thi lệnh trong môi trường Linux _cô lập_ của Copilot ([sandbox escape](http://medium.com/@d%5Ff4u1t/arbitrary-command-execution-within-copilots-isolated-linux-environment-via-python-sandbox-escape-c8ce6d9ac480))

Trong số này, bypass hạn chế tải lên tệp là đáng chú ý. Copilot có thể không cho phép các định dạng tệp "rủi ro" được tải lên. Nhưng người dùng có thể đơn giản mã hóa chúng thành chuỗi văn bản base64 và vượt qua hạn chế.

"Một khi được nộp dưới dạng tệp văn bản thuần, nội dung vượt qua kiểm tra loại tệp ban đầu, có thể được giải mã trong phiên, và tệp được tái tạo sau đó được phân tích — hiệu quả là vượt qua các điều khiển chính sách tải lên," giải thích Russell.

Một cuộc tranh luận nhanh chóng nổ ra trên bài đăng của kỹ sư này với cộng đồng an ninh mạng đưa ra nhiều ý kiến khác nhau.

Raj Marathe, một chuyên gia an ninh mạng dày dặn, cho biết những phát hiện đó là hợp lệ, trích dẫn một vấn đề tương tự mà ông nói [đã quan sát thấy](http://www.linkedin.com/feed/update/urn:li:activity:7412602607325818880?commentUrn=urn%3Ali%3Acomment%3A%28activity%3A7412602607325818880%2C7412746950724304897%29&dashCommentUrn=urn%3Ali%3Afsd%5Fcomment%3A%287412746950724304897%2Curn%3Ali%3Aactivity%3A7412602607325818880%29) trong quá khứ:

"Tôi đã chứng kiến một bản demo năm ngoái nơi chèn prompt được ẩn trong một tài liệu Word và tải lên Copilot. Khi Copilot đọc tài liệu đó, nó hoạt động sai và khóa người dùng. Nó không hiển thị hay gạch trắng mà được ngụy trang khéo léo trong tài liệu. Tôi vẫn chưa nghe ai đó nhận được phản hồi từ Microsoft về phát hiện đó."

Tuy nhiên, [một số khác đặt câu hỏi](https://www.linkedin.com/feed/update/urn:li:activity:7412602607325818880?commentUrn=urn%3Ali%3Acomment%3A%28activity%3A7412602607325818880%2C7412857756153479168%29&dashCommentUrn=urn%3Ali%3Afsd%5Fcomment%3A%287412857756153479168%2Curn%3Ali%3Aactivity%3A7412602607325818880%29) liệu việc tiết lộ lời nhắc hệ thống có nên được coi là một lỗ hổng hay không.

"Vấn đề với những cái này là chúng tương đối đã được biết. Ít nhất là các con đường dẫn tới chúng đã được biết," [tranh luận](https://www.linkedin.com/feed/update/urn:li:activity:7412602607325818880?commentUrn=urn%3Ali%3Acomment%3A%28activity%3A7412602607325818880%2C7412713053244440576%29&dashCommentUrn=urn%3Ali%3Afsd%5Fcomment%3A%287412713053244440576%2Curn%3Ali%3Aactivity%3A7412602607325818880%29) nhà nghiên cứu an ninh Cameron Criswell.

"Sẽ rất khó để loại bỏ mà không làm mất đi tính hữu ích. Tất cả những điều này chỉ cho thấy rằng LLM vẫn không thể [tách biệt] dữ liệu khỏi chỉ dẫn."

Criswell lập luận rằng hành vi như vậy phản ánh một giới hạn rộng hơn của các mô hình ngôn ngữ lớn, vốn có thể gặp khó khăn trong việc phân biệt đáng tin cậy giữa dữ liệu do người dùng cung cấp và lệnh. Trong thực tế, điều này có nghĩa là nếu các chỉ dẫn tiềm ẩn có thể bị chèn vào, chúng có thể dẫn đến các vấn đề như đầu độc dữ liệu hoặc tiết lộ thông tin ngoài ý muốn.

Tuy nhiên, Russell phản biện rằng các trợ lý AI cạnh tranh như Anthropic Claude không gặp vấn đề khi "từ chối tất cả các phương pháp này mà tôi tìm thấy có thể hoạt động trong Copilot," cho rằng nguyên nhân là thiếu kiểm tra đầu vào đủ chặt chẽ.

Một lời nhắc hệ thống (system prompt) đề cập đến các chỉ dẫn ẩn hướng dẫn hành vi của động cơ AI và, nếu được thiết kế không đúng, có thể bao gồm các quy tắc hoặc logic nội bộ có thể hỗ trợ một kẻ tấn công.

Dự án OWASP GenAI [có quan điểm tinh tế hơn](https://genai.owasp.org/llmrisk/llm072025-system-prompt-leakage/), phân loại rò rỉ lời nhắc hệ thống là một rủi ro tiềm tàng chỉ khi các lời nhắc chứa dữ liệu nhạy cảm hoặc được dựa vào như các biện pháp kiểm soát bảo mật, thay vì coi việc tiết lộ lời nhắc tự nó là một lỗ hổng độc lập:

"Ngắn gọn: việc tiết lộ lời nhắc hệ thống tự nó không trình bày rủi ro thực sự — rủi ro bảo mật nằm ở các yếu tố nền tảng, cho dù đó là tiết lộ thông tin nhạy cảm, vượt rào các cơ chế bảo vệ hệ thống, phân tách quyền không đúng, v.v.  
   
Ngay cả khi cách diễn đạt chính xác không được tiết lộ, kẻ tấn công tương tác với hệ thống hầu như chắc chắn sẽ có thể xác định nhiều rào chắn và hạn chế định dạng có trong ngôn ngữ lời nhắc hệ thống trong quá trình sử dụng ứng dụng, gửi các phát ngôn tới mô hình, và quan sát kết quả."

## Quan điểm của Microsoft về lỗ hổng AI

Microsoft đánh giá tất cả các báo cáo liên quan đến lỗi AI theo [bug bar](http://www.microsoft.com/en-us/msrc/aibugbar) công khai của họ.

Một phát ngôn viên của Microsoft nói với BleepingComputer rằng các báo cáo đã được xem xét nhưng không đáp ứng tiêu chí của công ty để được xử lý như lỗ hổng:

"Chúng tôi ghi nhận công việc của cộng đồng an ninh trong việc điều tra và báo cáo các vấn đề tiềm ẩn... Người báo cáo này đã nêu vài trường hợp được đánh giá là ngoài phạm vi theo các tiêu chí đã công bố của chúng tôi.  
  
Có nhiều lý do khiến một trường hợp có thể nằm ngoài phạm vi, bao gồm các trường hợp ranh giới bảo mật không bị vượt qua, tác động chỉ giới hạn trong môi trường thực thi của người dùng yêu cầu, hoặc thông tin có đặc quyền thấp khác được cung cấp mà không được coi là một lỗ hổng."

Cuối cùng, tranh chấp xoay quanh định nghĩa và quan điểm.

Trong khi Russell coi chèn prompt và hành vi sandbox là những rủi ro đáng kể, Microsoft xem chúng như các giới hạn mong đợi trừ khi chúng vượt qua một ranh giới bảo mật rõ ràng, chẳng hạn như cho phép truy cập trái phép hoặc lấy cắp dữ liệu.

Khoảng cách trong cách định nghĩa rủi ro AI này có khả năng tiếp tục là điểm ma sát khi các công cụ này được triển khai rộng rãi trong môi trường doanh nghiệp.