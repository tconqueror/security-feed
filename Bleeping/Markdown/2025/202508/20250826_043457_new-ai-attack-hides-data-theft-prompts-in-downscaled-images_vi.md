# Cuộc tấn công AI mới ẩn các prompt đánh cắp dữ liệu trong hình ảnh đã được thu nhỏ

![Cuộc tấn công AI mới ẩn các prompt đánh cắp dữ liệu trong hình ảnh đã được thu nhỏ](https://www.bleepstatic.com/content/hl-images/2022/05/12/ai-cybersecurity-hacker.jpg)

Các nhà nghiên cứu đã phát triển một cuộc tấn công mới nhằm đánh cắp dữ liệu người dùng bằng cách tiêm các prompt độc hại vào hình ảnh được xử lý bởi các hệ thống AI trước khi gửi chúng đến một mô hình ngôn ngữ lớn.

Phương pháp này dựa vào các hình ảnh độ phân giải cao mang theo các hướng dẫn vô hình với mắt người nhưng trở nên rõ ràng hơn khi chất lượng hình ảnh bị giảm xuống thông qua các thuật toán resampling.

Được phát triển bởi [các nhà nghiên cứu Trail of Bits](https://blog.trailofbits.com/2025/08/21/weaponizing-image-scaling-against-production-ai-systems/) Kikimora Morozova và Suha Sabi Hussain, cuộc tấn công này xây dựng trên một lý thuyết được trình bày trong một [bài viết USENIX năm 2020](https://www.usenix.org/conference/usenixsecurity20/presentation/quiring) của một trường đại học Đức (TU Braunschweig) khám phá khả năng của một cuộc tấn công thu nhỏ hình ảnh trong học máy.

## Cách thức hoạt động của cuộc tấn công

Khi người dùng tải lên hình ảnh lên các hệ thống AI, chúng sẽ được tự động thu nhỏ xuống chất lượng thấp hơn nhằm hiệu suất và hiệu quả chi phí.

Tùy thuộc vào hệ thống, các thuật toán resampling hình ảnh có thể làm cho hình ảnh nhẹ hơn bằng cách sử dụng nearest neighbor, bilinear hoặc bicubic interpolation.

Tất cả các phương pháp này đều tạo ra các hiện tượng aliasing cho phép các mẫu ẩn xuất hiện trên hình ảnh đã được thu nhỏ nếu nguồn được thiết kế đặc biệt cho mục đích này.

Trong ví dụ của Trail of Bits, các vùng tối cụ thể của một hình ảnh độc hại chuyển sang màu đỏ, cho phép văn bản ẩn xuất hiện màu đen khi thu nhỏ bằng phương pháp bicubic.

![Ví dụ về một thông điệp ẩn xuất hiện trên hình ảnh thu nhỏ](https://www.bleepstatic.com/images/news/u/1220909/2025/August/example.jpg)

**Ví dụ về một thông điệp ẩn xuất hiện trên hình ảnh thu nhỏ**  
_Nguồn: Zscaler_

Mô hình AI diễn giải văn bản này như một phần của hướng dẫn của người dùng và tự động kết hợp nó với đầu vào hợp pháp.

Từ góc độ của người dùng, không có gì có vẻ khác thường, nhưng trên thực tế, mô hình đã thực thi các hướng dẫn ẩn có thể dẫn đến rò rỉ dữ liệu hoặc các hành động rủi ro khác.

Trong một ví dụ liên quan đến [Gemini CLI](https://www.bleepingcomputer.com/news/security/flaw-in-gemini-cli-ai-coding-assistant-allowed-stealthy-code-execution/), các nhà nghiên cứu đã có thể lấy cắp dữ liệu Google Calendar đến một địa chỉ email tùy ý trong khi sử dụng Zapier MCP với 'trust=True' để phê duyệt các cuộc gọi công cụ mà không cần xác nhận của người dùng.

Trail of Bits giải thích rằng cuộc tấn công cần phải được điều chỉnh cho từng mô hình AI theo thuật toán thu nhỏ được sử dụng trong việc xử lý hình ảnh. Tuy nhiên, các nhà nghiên cứu xác nhận rằng phương pháp của họ khả thi đối với các hệ thống AI sau:

* Google Gemini CLI
* Vertex AI Studio (với backend Gemini)
* Giao diện web của Gemini
* API của Gemini qua llm CLI
* Google Assistant trên điện thoại Android
* Genspark

Với việc vector tấn công rộng rãi, nó có thể mở rộng xa hơn các công cụ đã được kiểm tra. Hơn nữa, để chứng minh phát hiện của họ, các nhà nghiên cứu cũng đã tạo ra và công bố [Anamorpher](https://github.com/trailofbits/anamorpher) (hiện đang trong giai đoạn beta), một công cụ mã nguồn mở có thể tạo ra hình ảnh cho từng phương pháp thu nhỏ đã đề cập.

Các nhà nghiên cứu lập luận rằng 

Để giảm thiểu và phòng thủ, các nhà nghiên cứu Trail of Bits khuyến nghị rằng các hệ thống AI áp dụng hạn chế kích thước khi người dùng tải lên một hình ảnh. Nếu việc thu nhỏ là cần thiết, họ khuyên nên cung cấp cho người dùng một cái nhìn trước về kết quả được gửi đến mô hình ngôn ngữ lớn (LLM).

Họ cũng lập luận rằng nên yêu cầu xác nhận rõ ràng từ người dùng cho các cuộc gọi công cụ nhạy cảm, đặc biệt khi có văn bản được phát hiện trong hình ảnh.

"Tuy nhiên, biện pháp phòng ngừa mạnh nhất là thực hiện các mẫu thiết kế an toàn và các biện pháp phòng thủ có hệ thống để giảm thiểu việc tiêm prompt có tác động lớn hơn cả tiêm prompt đa phương thức," các nhà nghiên cứu cho biết, đề cập đến một [bài báo được công bố vào tháng Sáu](https://arxiv.org/pdf/2506.08837) về các mẫu thiết kế để xây dựng các LLM có thể chống lại các cuộc tấn công tiêm prompt.