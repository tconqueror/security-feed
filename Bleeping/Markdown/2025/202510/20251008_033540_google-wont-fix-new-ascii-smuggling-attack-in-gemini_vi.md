# Google sẽ không khắc phục tấn công tuồn ASCII mới trong Gemini

![Google won’t fix new ASCII smuggling attack in Gemini](https://www.bleepstatic.com/content/hl-images/2024/08/13/Gemini.jpg)

Google đã quyết định không khắc phục một tấn công tuồn ASCII mới trong Gemini có thể được sử dụng để lừa trợ lý AI cung cấp cho người dùng thông tin giả, thay đổi hành vi của mô hình và âm thầm đầu độc dữ liệu của nó.

ASCII smuggling là một cuộc tấn công nơi các ký tự đặc biệt từ Tags Unicode block được dùng để chèn các payload vô hình đối với người dùng nhưng vẫn có thể được phát hiện và xử lý bởi các large-language models (LLMs).

Nó tương tự với các tấn công khác mà các nhà nghiên cứu đã trình bày gần đây chống lại Google Gemini, tất cả khai thác khoảng cách giữa những gì người dùng nhìn thấy và những gì máy đọc, như thực hiện điều khiển [CSS manipulation](https://www.bleepingcomputer.com/news/security/google-gemini-flaw-hijacks-email-summaries-for-phishing/) hoặc [exploiting GUI limitations](https://www.bleepingcomputer.com/news/security/google-calendar-invites-let-researchers-hijack-gemini-to-leak-user-data/).

Mặc dù tính dễ bị tấn công của LLMs trước ASCII smuggling không phải là phát hiện mới, vì một số nhà nghiên cứu đã khám phá khả năng này từ khi các công cụ generative AI xuất hiện, mức độ rủi ro giờ đã khác \[[1](http://www.promptfoo.dev/docs/red-team/plugins/ascii-smuggling/), [2](http://embracethered.com/blog/posts/2024/claude-hidden-prompt-injection-ascii-smuggling/), [3](http://reference.garak.ai/en/latest/ascii%5Fsmuggling.html), [4](http://x.com/rez0%5F%5F/status/1745545813512663203)\].

Trước đây, chatbot chỉ có thể bị thao túng ác ý bằng các tấn công như vậy nếu người dùng bị lừa dán các prompt được thiết kế đặc biệt. Với sự trỗi dậy của các công cụ AI có tính tác nhân như Gemini, những công cụ này có quyền truy cập rộng rãi vào dữ liệu nhạy cảm của người dùng và có thể thực hiện các nhiệm vụ một cách tự động, mối đe dọa trở nên nghiêm trọng hơn.

Viktor Markopoulos, một nhà nghiên cứu bảo mật tại công ty FireTail, đã [thử nghiệm ASCII smuggling](http://www.firetail.ai/blog/ghosts-in-the-machine-ascii-smuggling-across-various-llms) trên một số công cụ AI được sử dụng rộng rãi và phát hiện rằng Gemini (Calendar invites or email), DeepSeek (prompts), và Grok (X posts), dễ bị tấn công này.

Claude, ChatGPT, và Microsoft CoPilot được chứng minh là an toàn trước ASCII smuggling, đã thực hiện một số hình thức làm sạch đầu vào, FireTail phát hiện.

![Susceptibility to ASCII smuggling](https://www.bleepstatic.com/images/news/u/1220909/2025/October/table.png)

**Mức độ dễ bị tấn công bởi ASCII smuggling**  
_Source: FireTail_

Về phần Gemini, việc tích hợp với Google Workspace đặt ra rủi ro cao, vì kẻ tấn công có thể sử dụng ASCII smuggling để nhúng văn bản ẩn trong Calendar invites hoặc email.

Markopoulos nhận thấy có thể ẩn các chỉ thị trong tiêu đề lời mời Calendar, ghi đè thông tin tổ chức (mạo danh danh tính), và tuồn các mô tả cuộc họp hoặc liên kết ẩn.

![Calendar entry as the user sees it (left) and Gemini chat with poisoned data (right)](https://www.bleepstatic.com/images/news/u/1220909/2025/October/meeting.png)

**Mục lịch như người dùng nhìn thấy (trái) và chat Gemini với dữ liệu bị đầu độc (phải)**  
_Source: FireTail_

Về rủi ro từ email, nhà nghiên cứu cho biết “for users with LLMs connected to their inboxes, a simple email with hidden commands can instruct the LLM to search the inbox for sensitive items or send contact details, turning a standard phishing attempt into an autonomous data extraction tool.”

LLMs được hướng dẫn duyệt web cũng có thể vô tình tìm thấy các payload ẩn trong mô tả sản phẩm và cung cấp cho chúng các URL độc hại để truyền đạt tới người dùng.

Nhà nghiên cứu đã báo cáo các phát hiện cho Google vào ngày 18 tháng 9 nhưng gã khổng lồ công nghệ đã bác bỏ vấn đề này là không phải lỗi bảo mật và có thể chỉ bị lợi dụng trong bối cảnh các cuộc tấn công xã hội kỹ thuật.

Dù vậy, Markopoulos đã chỉ ra rằng cuộc tấn công có thể lừa Gemini cung cấp thông tin sai cho người dùng. Trong một ví dụ, nhà nghiên cứu đã gửi một chỉ thị vô hình mà Gemini xử lý để trình bày một trang web khả nghi như nơi để mua điện thoại chất lượng tốt với giảm giá.

Các công ty công nghệ khác, tuy nhiên, có quan điểm khác về loại vấn đề này. Ví dụ, Amazon đã xuất bản [hướng dẫn bảo mật chi tiết](https://aws.amazon.com/blogs/security/defending-llm-applications-against-unicode-character-smuggling/) về chủ đề tuồn ký tự Unicode.

BleepingComputer đã liên hệ với Google để làm rõ thêm về lỗi nhưng chúng tôi vẫn chưa nhận được phản hồi.