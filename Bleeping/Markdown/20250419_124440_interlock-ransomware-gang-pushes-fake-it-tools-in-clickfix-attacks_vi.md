# Băng nhóm ransomware Interlock sử dụng công cụ IT giả trong các cuộc tấn công ClickFix

Băng nhóm ransomware Interlock hiện đang sử dụng các cuộc tấn công ClickFix giả danh các công cụ IT để xâm nhập vào các mạng doanh nghiệp và triển khai phần mềm mã hóa tệp trên các thiết bị.

ClickFix là một chiến thuật kỹ thuật xã hội mà trong đó nạn nhân bị lừa thực hiện các lệnh PowerShell nguy hiểm trên hệ thống của họ để giả định khắc phục một lỗi hoặc xác minh bản thân, dẫn đến việc cài đặt malware.

Mặc dù đây không phải là lần đầu tiên ClickFix được liên kết với các cuộc nhiễm ransomware, việc xác nhận về Interlock cho thấy một xu hướng gia tăng trong những loại tác nhân đe dọa này sử dụng chiến thuật.

Interlock là một hoạt động ransomware được ra mắt vào cuối tháng 9 năm 2024, nhắm vào các máy chủ FreeBSD và hệ thống Windows.

Interlock không được cho là hoạt động theo mô hình ransomware-as-a-service. Tuy nhiên, nó duy trì một cổng dữ liệu rò rỉ trên dark web để tăng áp lực lên nạn nhân, yêu cầu thanh toán từ hàng trăm nghìn đô la đến hàng triệu đô la.

## Từ ClickFix đến ransomware

Trong quá khứ, Interlock đã sử dụng các bản cập nhật giả mạo cho trình duyệt và khách hàng VPN để cài đặt malware và xâm nhập vào các mạng.

Theo các nhà nghiên cứu Sekoia, băng nhóm ransomware Interlock đã bắt đầu sử dụng các cuộc tấn công ClickFix vào tháng 1 năm 2025.

Interlock đã sử dụng ít nhất bốn URL để lưu trữ các yêu cầu CAPTCHA giả mạo, thông báo cho người truy cập thực hiện một lệnh trên máy tính của họ để xác minh bản thân và tải về một công cụ được quảng bá.

Các nhà nghiên cứu cho biết họ đã phát hiện CAPTCHA độc hại trên bốn trang web khác nhau, giả mạo các cổng Microsoft hoặc Advanced IP Scanner:

* microsoft-msteams\[.\]com/additional-check.html
* microstteams\[.\]com/additional-check.html
* ecologilives\[.\]com/additional-check.html
* advanceipscaner\[.\]com/additional-check.html

Tuy nhiên, chỉ có trang giả mạo Advanced IP Scanner, một công cụ quét IP phổ biến thường được sử dụng bởi nhân viên IT, dẫn đến việc tải về một trình cài đặt độc hại.

Nhấp vào nút 'Fix it' sẽ sao chép lệnh PowerShell độc hại vào bộ nhớ đệm của nạn nhân. Nếu được thực thi trong dấu nhắc lệnh hoặc hộp thoại Chạy của Windows, nó sẽ tải về một payload PyInstaller có kích thước 36MB.

Trong cùng lúc, trang web hợp pháp của AdvanceIPScanner sẽ mở trong một cửa sổ trình duyệt để giảm nghi ngờ.

Payload độc hại cài đặt một bản sao hợp pháp của phần mềm nó giả vờ làm và đồng thời thực thi một script PowerShell nhúng chạy trong một cửa sổ ẩn.

Script này đăng ký một khóa Run trong Windows Registry để duy trì sự tồn tại và sau đó thu thập và xuất ra thông tin hệ thống bao gồm phiên bản OS, mức độ quyền của người dùng, các quá trình đang chạy và các ổ đĩa có sẵn.

Sekoia đã quan sát thấy command and control (C2) phản hồi với nhiều payload khác nhau, bao gồm LummaStealer, BerserkStealer, keyloggers và Interlock RAT.

Cái sau là một trojan đơn giản có thể được cấu hình động, hỗ trợ xuất file, thực thi lệnh shell và chạy các DLL độc hại.

Sau khi bị xâm phạm ban đầu và triển khai RAT, các điều hành viên Interlock đã sử dụng thông tin đăng nhập bị đánh cắp để di chuyển bên dưới qua RDP, trong khi Sekoia cũng thấy PuTTY, AnyDesk và LogMeIn được sử dụng trong một số cuộc tấn công.

Bước cuối cùng trước khi thực thi ransomware là xuất dữ liệu, với các tệp bị đánh cắp được tải lên Azure Blobs do kẻ tấn công kiểm soát.

Biến thể Windows của Interlock được đặt (thông qua một tác vụ theo lịch) để chạy hàng ngày vào lúc 08:00 PM, nhưng nhờ vào việc lọc dựa trên phần mở rộng file, điều này không gây ra nhiều lớp mã hóa mà chỉ đóng vai trò là một biện pháp dư thừa.

Sekoia cũng báo cáo rằng ghi chú tiền chuộc cũng đã phát triển, với các phiên bản mới nhất tập trung nhiều hơn vào khía cạnh pháp lý của việc vi phạm dữ liệu và hậu quả quy định nếu dữ liệu bị đánh cắp được công khai.

Các cuộc tấn công ClickFix hiện đã được một loạt các tác nhân đe dọa áp dụng, bao gồm các băng nhóm ransomware khác và các hacker Bắc Triều Tiên.

Tháng trước, Sekoia đã phát hiện ra rằng nhóm hacker Bắc Triều Tiên nổi tiếng Lazarus đang sử dụng các cuộc tấn công ClickFix nhằm vào những người tìm việc trong ngành công nghiệp tiền điện tử.