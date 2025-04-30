# Commvault cho biết sự vi phạm gần đây không ảnh hưởng đến dữ liệu sao lưu của khách hàng

![Data center](https://www.bleepstatic.com/content/hl-images/2024/01/04/Hacker_datacenter.jpg)

Commvault, nhà cung cấp hàng đầu về các giải pháp bảo vệ dữ liệu, cho biết một tác nhân đe dọa đến từ nhà nước đã xâm nhập vào môi trường Azure của họ nhưng không truy cập được dữ liệu sao lưu của khách hàng.

Commvault đã niêm yết trên NASDAQ từ tháng 3 năm 2006, và được đưa vào chỉ số S&P MidCap 400, cung cấp dịch vụ khả năng phục hồi mạng cho hơn 100,000 tổ chức.

Như công ty lần đầu tiên [tiết lộ vào ngày 7 tháng 3](https://www.commvault.com/blogs/security-advisory-march-7-2025), Commvault phát hiện ra sự cố này sau khi được Microsoft thông báo vào ngày 20 tháng 2 về hoạt động đáng ngờ trong môi trường Azure của mình. Một cuộc điều tra tiếp theo vào vụ vi phạm cho thấy sự cố chỉ ảnh hưởng đến một số ít khách hàng của Commvault và không ảnh hưởng đến hoạt động của công ty.

"Quan trọng là, không có truy cập trái phép nào vào dữ liệu sao lưu của khách hàng mà Commvault lưu trữ và bảo vệ, và không có ảnh hưởng đáng kể nào đến hoạt động kinh doanh của chúng tôi hoặc khả năng cung cấp sản phẩm và dịch vụ," Danielle Sheer, Giám đốc Tin Cậy của công ty, [nói trong một bản cập nhật vào thứ Tư](https://www.commvault.com/blogs/notice-security-advisory-update).

"Chúng tôi đang làm việc chặt chẽ với hai công ty an ninh mạng hàng đầu và đang phối hợp với các cơ quan chức năng thích hợp, bao gồm FBI, Cơ quan An ninh mạng và Cơ sở hạ tầng (CISA) và những người khác."

Trong một [tài liệu hỗ trợ](https://kb.commvault.com/article/87661) chứa các chỉ báo của sự thỏa hiệp, Commvault khuyên khách hàng nên áp dụng chính sách Truy cập Có điều kiện cho tất cả các ứng dụng đăng ký App một công thuê Microsoft 365, Dynamics 365 và Azure AD để bảo vệ dữ liệu của họ trước các cố gắng tấn công tương tự.

Công ty cũng khuyến nghị theo dõi thường xuyên hoạt động đăng nhập để phát hiện các cố gắng truy cập từ các địa chỉ IP không nằm trong các khoảng cho phép và nên đổi mới và đồng bộ hóa bí mật khách hàng giữa Commvault và cổng thông tin Azure mỗi 90 ngày.

"Điều này giúp nhanh chóng xác định các vi phạm an ninh tiềm tàng hoặc các tài khoản bị xâm phạm. Nếu phát hiện bất kỳ sự truy cập trái phép nào, hãy ngay lập tức báo cáo sự cố cho Hỗ trợ Commvault để điều tra và khắc phục tiếp theo," công ty cho biết.

Công ty cũng đã lưu ý trong thông báo gốc rằng các tác nhân đe dọa đã khai thác một lỗ hổng zero-day đã được sửa chữa ([CVE-2025-3928](https://documentation.commvault.com/securityadvisories/CV%5F2025%5F03%5F1.html)) trong phần mềm Commvault Web Server mà các tin tặc từ xa với quyền hạn thấp có thể khai thác từ xa để cài đặt webshell trên các máy chủ mục tiêu.

CISA cũng đã [thêm lỗ hổng CVE-2025-3928](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-3928&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=) vào danh mục Lỗ hổng Đã biết bị Khai thác vào thứ Hai, yêu cầu các cơ quan liên bang phải đảm bảo an ninh cho phần mềm Commvault của họ trước ngày 19 tháng 5 năm 2025, theo quy định của Chỉ thị Tác nghiệp Ràng buộc (BOD) 22-01 được phát hành vào tháng 11 năm 2021.

"Các loại lỗ hổng này thường là các vector tấn công cho các đối tượng độc hại và gây ra rủi ro đáng kể cho doanh nghiệp liên bang," [CISA cảnh báo](https://www.cisa.gov/news-events/alerts/2025/04/28/cisa-adds-three-known-exploited-vulnerabilities-catalog).