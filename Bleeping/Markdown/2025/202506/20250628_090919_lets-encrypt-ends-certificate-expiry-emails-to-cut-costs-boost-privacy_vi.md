# Let's Encrypt ngừng gửi email thông báo hết hạn chứng chỉ để cắt giảm chi phí, tăng cường quyền riêng tư

![Email](https://www.bleepstatic.com/content/hl-images/2024/01/03/email.jpg)

Let's Encrypt đã thông báo rằng họ sẽ không còn thông báo cho người dùng về việc hết hạn chứng chỉ sắp tới qua email do chi phí cao, lo ngại về quyền riêng tư và những phức tạp không cần thiết.

Quyết định ngừng dịch vụ gửi email thông báo hết hạn đã được thực hiện từ ngày 4 tháng 6 năm 2025, nhưng Let's Encrypt đã thông báo điều này qua một bài blog để nâng cao nhận thức và ngăn chặn những gián đoạn không mong muốn.

Let's Encrypt là một Certificate Authority (CA) phi lợi nhuận cung cấp chứng chỉ số miễn phí, tự động và mở để cho phép HTTPS (SSL/TLS) trên các trang web. Về quy mô, họ là một trong những CA lớn nhất thế giới, phát hành hàng trăm triệu chứng chỉ cho hàng tỷ trang web.

Let's Encrypt là một CA minh bạch đã giảm thiểu việc lưu trữ dữ liệu ở mức tối đa có thể. Chứng chỉ gốc của họ được bao gồm trong tất cả các trình duyệt lớn và kho tin cậy của hệ điều hành, trong khi họ nhận được sự hỗ trợ từ các công ty công nghệ nổi tiếng như Google, Cisco, Mozilla, EFF, Facebook và Akamai.

Tổ chức này sử dụng một giao thức tự động gọi là ACME (Automatic Certificate Management Environment), cho phép các trang web và phần mềm máy chủ tự động hóa việc phát hành, cài đặt và gia hạn chứng chỉ với sự can thiệp tối thiểu hoặc không có người can thiệp.

Theo [thông báo mới nhất](https://letsencrypt.org/2025/06/26/expiration-notification-service-has-ended/), sự tồn tại của tự động hóa này là lý do chính khiến dịch vụ thông báo email đang bị ngừng, vì nhu cầu của nó đang giảm.

Việc áp dụng các giải pháp gia hạn tự động đã được tăng cường hơn nữa bởi những thay đổi tiêu chuẩn, chẳng hạn như thông báo gần đây của CA/Browser Forum về việc giảm thời gian sống của chứng chỉ xuống còn 47 ngày vào năm 2029.

Quyết định này đã khiến việc quản lý thủ công trở nên không khả thi, nếu không muốn nói là không thể, mạnh mẽ khuyến khích việc áp dụng tự động hóa để duy trì tuân thủ và tránh gián đoạn.

Một lý do chính khác cho quyết định bỏ dịch vụ email là chi phí duy trì nó, mà Let's Encrypt ước tính lên tới "hàng chục nghìn đô la mỗi năm."

Tổ chức này tin rằng việc phân bổ số tiền này cho các khía cạnh khác của cơ sở hạ tầng sẽ có lợi hơn nhiều, điều này cũng đang bị căng thẳng không cần thiết do việc xử lý các hoạt động phân phối email.

"Cung cấp thông báo hết hạn làm tăng thêm sự phức tạp cho cơ sở hạ tầng của chúng tôi, điều này cần thời gian và sự chú ý để quản lý và làm tăng khả năng xảy ra sai sót," Let's Encrypt giải thích.

"Trong thời gian dài, đặc biệt khi chúng tôi thêm hỗ trợ cho các thành phần dịch vụ mới, chúng tôi cần quản lý sự phức tạp tổng thể bằng cách loại bỏ những thành phần hệ thống mà không còn được biện minh."

Cuối cùng, tổ chức này có những lo ngại về quyền riêng tư của dữ liệu người dùng, vì họ giờ đây phải lưu trữ, quản lý và bảo vệ một cơ sở dữ liệu lớn các địa chỉ email liên kết với hồ sơ phát hành để thông báo các bên liên quan thích hợp.

Điểm mấu chốt cho những người dùng có thể bị ảnh hưởng là nên áp dụng các công cụ hỗ trợ giao thức ACME nếu họ chưa làm như vậy và ngừng phụ thuộc vào email thông báo của Let's Encrypt.

Nếu bạn cần nhận thông báo gia hạn, hãy cân nhắc việc thiết lập một dịch vụ thông báo bên ngoài theo cách khác.