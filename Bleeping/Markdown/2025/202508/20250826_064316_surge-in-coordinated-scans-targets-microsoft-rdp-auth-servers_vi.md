# Tăng cường quét có phối hợp nhắm vào máy chủ xác thực Microsoft RDP

![Quét mạng](https://www.bleepstatic.com/content/hl-images/2022/08/17/global-pew-pew.jpg)

Công ty thông tin Internet GreyNoise báo cáo rằng họ đã ghi nhận một đợt tăng đột biến đáng kể trong hoạt động quét bao gồm gần 1,971 địa chỉ IP đang dò tìm Microsoft Remote Desktop Web Access và các cổng xác thực RDP Web Client một cách đồng thời, cho thấy đây là một chiến dịch trinh sát có phối hợp.

Các nhà nghiên cứu cho biết đây là một thay đổi lớn trong hoạt động, với công ty thường chỉ thấy 3–5 địa chỉ IP mỗi ngày thực hiện loại quét này.

GreyNoise cho biết rằng làn sóng quét này đang thử các lỗi về thời gian có thể được sử dụng để xác minh tên người dùng, chuẩn bị cho các cuộc tấn công dựa trên thông tin xác thực trong tương lai, chẳng hạn như tấn công brute force hoặc tấn công password-spray.

Các lỗi về thời gian xảy ra khi thời gian phản hồi của một hệ thống hoặc yêu cầu vô tình tiết lộ thông tin nhạy cảm. Trong trường hợp này, một sự khác biệt nhỏ về thời gian trong cách mà RDP phản hồi với các nỗ lực đăng nhập hợp lệ so với không hợp lệ có thể cho phép kẻ tấn công suy luận xem tên người dùng có đúng không.

GreyNoise cũng cho biết rằng 1,851 địa chỉ đã chia sẻ cùng một chữ ký khách hàng, và trong số đó, khoảng 92% đã bị đánh dấu là độc hại. Các địa chỉ IP chủ yếu có nguồn gốc từ Brazil và nhắm vào các địa chỉ IP ở Hoa Kỳ, cho thấy có thể đây là một botnet hoặc bộ công cụ duy nhất đang thực hiện các cuộc quét.

![Các địa chỉ IP duy nhất thực hiện kiểm tra đăng nhập Microsoft RDP web client](https://www.bleepstatic.com/images/news/security/g/greynoise/rdp-scanning/greynoise-unique-ips.jpg)

**Các địa chỉ IP duy nhất thực hiện kiểm tra đăng nhập Microsoft RDP web client**  
_Nguồn: GreyNoise_

Các nhà nghiên cứu cho rằng thời gian của cuộc tấn công trùng khớp với mùa trở lại trường của Hoa Kỳ, khi các trường học và đại học có thể đang đưa các hệ thống RDP của họ trở lại hoạt động.

"Thời gian có thể không phải là ngẫu nhiên. Ngày 21 tháng 8 nằm trọn trong khoảng thời gian trở lại trường tại Hoa Kỳ, khi các trường đại học và K-12 đưa các phòng thí nghiệm hỗ trợ RDP và quyền truy cập từ xa trực tuyến và onboard hàng nghìn tài khoản mới," [giải thích Noah Stone của GreyNoise](https://www.greynoise.io/blog/surge-malicious-ips-probe-microsoft-remote-desktop).

"Các môi trường này thường sử dụng các định dạng tên người dùng có thể đoán trước (ID sinh viên, firstname.lastname), làm cho việc xác minh trở nên hiệu quả hơn. Kết hợp với các hạn chế ngân sách và ưu tiên về khả năng truy cập trong thời gian tuyển sinh, số lượng có thể tăng vọt."

Tuy nhiên, sự gia tăng trong các lần quét cũng có thể cho thấy rằng một lỗ hổng mới có thể đã được phát hiện, vì GreyNoise trước đây đã phát hiện rằng các đợt tăng cường lưu lượng độc hại [thường xảy ra trước khi công bố các lỗ hổng mới](https://www.bleepingcomputer.com/news/security/spikes-in-malicious-activity-precede-new-cves-in-80-percent-of-cases/).

Quản trị viên Windows quản lý các cổng RDP và thiết bị bị lộ nên đảm bảo rằng các tài khoản của họ được bảo mật đúng cách bằng phương pháp xác thực đa yếu tố và nếu có thể, đặt chúng sau VPN.