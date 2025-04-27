# Công cụ Cookiecrumbler của Brave kêu gọi cộng đồng giúp chặn các thông báo cookie

![Brave](https://www.bleepstatic.com/content/hl-images/2022/06/22/Brave.jpg)

Brave đã phát hành một công cụ nguồn mở mới có tên là "Cookiecrumbler," sử dụng các mô hình ngôn ngữ lớn (LLMs) để phát hiện các thông báo đồng ý cookie và sau đó là các đánh giá từ cộng đồng để chặn những cái không làm hỏng chức năng của trang web.

Trình duyệt Brave đã tự động chặn các banner đồng ý cookie trên tất cả các trang web [kể từ năm 2022](https://www.bleepingcomputer.com/news/security/brave-browser-to-start-blocking-annoying-cookie-consent-banners/) nhưng nhận thấy rằng việc chặn các banner đồng ý có thể gây ra các vấn đề trên trang web làm gián đoạn và làm giảm khả năng sử dụng của trang.

"Việc chặn quá rộng hoặc không chính xác có thể làm hỏng chức năng thiết yếu của trang web, từ quy trình thanh toán đến các vấn đề về bố cục," [giải thích Brave](https://brave.com/privacy-updates/33-cookiecrumbler/).

"Chúng tôi đã gặp nhiều vấn đề (cuộn bị hỏng, trang trắng) khi việc chặn thông báo đồng ý cookie được áp dụng một cách không phân biệt."

Cookiecrumbler sử dụng AI để tìm các trang web sử dụng các nền tảng quản lý đồng ý (CMPs) và báo cáo chúng như là các vấn đề trong dự án GitHub của mình. Các gợi ý của Cookiecrumbler sau đó được xem xét thủ công trước khi áp dụng để tránh làm hỏng chức năng thiết yếu của trang web.

Cách thức hoạt động của công cụ được tóm tắt như sau:

1. Quét các trang web hàng đầu bằng cách sử dụng các proxy khu vực.
2. Tải các trang với Puppeteer để tìm các thông báo cookie tiềm năng.
3. Chuyển chúng cho LLM để phân loại và đưa ra gợi ý sửa chữa.
4. Xuất bản kết quả phát hiện dưới dạng [vấn đề GitHub](https://github.com/brave-experiments/cookiecrumbler-issues/issues) cho cộng đồng phân loại và cải tiến.

Một cách cơ bản, Cookiecrumbler cho phép phát hiện và chặn cookie banner quy mô lớn, nhận thức theo khu vực trong khi giảm thiểu các cảnh báo sai và vấn đề trên trang.

Là một phần mềm tập trung vào quyền riêng tư, thông báo của Brave nêu rõ một số điểm liên quan đến cách thức hoạt động của Cookiecrumbler không làm lộ các chi tiết nhạy cảm.

Trước tiên, đã được làm rõ rằng Cookiecrumbler hoạt động hoàn toàn trên backend của Brave, và không trên trình duyệt của người dùng, nghĩa là không có dữ liệu người dùng nào được sử dụng trong quá trình phát hiện và phân tích của nó.

Thứ hai, công cụ này không tương tác với các phiên người dùng thực tế; thay vào đó, nó sử dụng các proxy và máy quét tự động để mô phỏng việc duyệt web từ các khu vực khác nhau bằng cách sử dụng các danh sách trang công cộng như Tranco.

Cuối cùng, việc bảo vệ quyền riêng tư là lý do chính tại sao Cookiecrumbler hiện không được tích hợp vào trình duyệt Brave mà thay vào đó được sử dụng nội bộ như một công cụ backend cho phân tích.

Brave Software cho biết Cookiecrumbler sẽ được tích hợp vào Brave chỉ sau khi nó đã trải qua một đánh giá toàn diện về quyền riêng tư để đảm bảo cách thức hoạt động của nó tuân thủ quan điểm nghiêm ngặt của phần mềm về quyền riêng tư của người dùng.

Với Cookiecrumbler được phát hành mã nguồn mở và miễn phí [qua GitHub](https://github.com/brave/cookiecrumbler/), nó có thể được sử dụng trực tiếp bởi các nhà phát triển công cụ quyền riêng tư khác, các auditor trang web, những người quản lý danh sách quảng cáo chặn, hoặc ngay cả những người dùng am hiểu công nghệ muốn tạo hoặc cải thiện các quy tắc lọc của riêng họ.