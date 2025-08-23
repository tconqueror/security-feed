# Ransomware DarkBit của MuddyWater đã bị bẻ khóa để khôi phục dữ liệu miễn phí

![Tay cầm một chìa khóa mạng](https://www.bleepstatic.com/content/hl-images/2022/10/09/cyber-key.jpg)

Công ty an ninh mạng Profero đã bẻ khóa mã hóa của nhóm ransomware DarkBit, cho phép họ khôi phục tệp của một nạn nhân miễn phí mà không phải trả tiền chuộc.

Điều này đã xảy ra vào năm 2023 trong một cuộc phản ứng sự cố do các chuyên gia của Profero thực hiện, những người đã được mời để điều tra một cuộc tấn công ransomware vào một trong những khách hàng của họ, vốn đã mã hóa nhiều máy chủ VMware ESXi.

Thời điểm của cuộc tấn công mạng cho thấy nó xảy ra như một hình thức trả thù cho các cuộc tấn công bằng máy bay không người lái vào năm 2023 ở Iran, nhằm vào một nhà máy sản xuất đạn thuộc Bộ Quốc phòng Iran.

Trong cuộc tấn công ransomware, những kẻ đe dọa tự nhận là đến từ DarkBit, trước đây đã đóng giả là những hacker ủng hộ Iran, nhắm mục tiêu vào [các viện giáo dục ở Israel](https://www.bleepingcomputer.com/news/security/ransomware-hits-technion-university-to-protest-tech-layoffs-and-israel/). Những kẻ tấn công đã đưa ra các tuyên bố chống Israel trong các ghi chú đòi tiền chuộc của họ, yêu cầu thanh toán tiền chuộc 80 Bitcoin.

Lực lượng Cyber Command Quốc gia Israel [liên kết các cuộc tấn công DarkBit](https://www.gov.il/he/pages/%5Fmuddywater) với nhóm hacker APT tài trợ từ nhà nước Iran được biết đến với tên [MuddyWater](https://www.microsoft.com/en-us/security/blog/2023/04/07/mercury-and-dev-1084-destructive-attack-on-hybrid-environment/), những người có lịch sử thực hiện các cuộc tấn công gián điệp mạng.

Trong trường hợp được điều tra bởi Profero, những kẻ tấn công đã không tham gia vào việc đàm phán thanh toán tiền chuộc, mà thay vào đó có vẻ như họ quan tâm nhiều hơn đến việc gây gián đoạn hoạt động.

Thay vào đó, các kẻ tấn công đã khởi động một chiến dịch ảnh hưởng nhằm tối đa hóa thiệt hại về danh tiếng đối với nạn nhân, đây là một [chiến thuật liên quan](https://www.bleepingcomputer.com/news/security/russian-sandworm-hackers-pose-as-hacktivists-in-water-utility-breaches/) đến các tác nhân quốc gia đóng giả hacktivists.

## Giải mã DarkBit

Tại thời điểm cuộc tấn công, không có bất kỳ công cụ giải mã nào tồn tại cho ransomware DarkBit, vì vậy các nhà nghiên cứu của Profero đã quyết định phân tích mã độc đó để tìm các điểm yếu tiềm ẩn.

DarkBit sử dụng một khóa AES-128-CBC độc nhất và Initialization Vector (IV) được tạo ra trong thời gian chạy cho mỗi tệp, được mã hóa bằng RSA-2048 và được đính kèm vào tệp đã bị khóa.

![Cấu trúc tệp đã mã hóa cuối cùng](https://www.bleepstatic.com/images/news/u/1220909/2025/August/structure.png)

**Cấu trúc tệp đã mã hóa cuối cùng**  
_Nguồn: Profero_

Profero phát hiện ra rằng phương pháp tạo khóa mà DarkBit sử dụng có độ entropy thấp. Khi kết hợp với thời gian mã hóa, có thể được suy đoán từ thời gian sửa đổi tệp, không gian khóa tổng thể giảm xuống còn vài tỷ khả năng.

Hơn nữa, họ phát hiện ra rằng các tệp Virtual Machine Disk (VMDK) trên máy chủ ESXi có các byte tiêu đề đã biết, vì vậy họ chỉ cần brute force 16 byte đầu tiên để kiểm tra xem tiêu đề có khớp không, thay vì toàn bộ tệp.

Profero đã xây dựng một công cụ để thử tất cả các hạt giống có thể, tạo ra các cặp khóa/IV ứng cử viên và kiểm tra với các tiêu đề VMDK, mà họ chạy trong một môi trường tính toán hiệu suất cao, phục hồi các khóa giải mã hợp lệ.

Song song đó, các nhà nghiên cứu phát hiện ra rằng nhiều nội dung của tệp VMDK không bị ảnh hưởng bởi mã hóa gián đoạn của DarkBit, vì các tệp đó là thưa thớt và nhiều khối mã hóa rơi vào không gian trống.

Điều này cho phép họ phục hồi một lượng lớn dữ liệu giá trị mà không cần phải giải mã chúng bằng phương pháp brute-forcing khóa.

"Khi chúng tôi bắt đầu làm việc để tăng tốc độ brute force, một trong những kỹ sư/thành viên nhóm của chúng tôi đã có một ý tưởng thú vị," Profero giải thích.

"Các tệp VMDK là thưa thớt, có nghĩa là chúng chủ yếu là trống, và do đó, các khối đã mã hóa bởi ransomware trong mỗi tệp cũng chủ yếu là trống. Về mặt thống kê, hầu hết các tệp nằm bên trong các hệ thống tệp VMDK sẽ không bị mã hóa, và hầu hết các tệp trong các hệ thống tệp này thực sự không quan trọng đối với chúng tôi/công việc/chuyên đề điều tra của chúng tôi."

"Vì vậy, chúng tôi nhận ra rằng chúng tôi có thể duyệt qua hệ thống tệp để trích xuất những gì còn lại của các hệ thống tệp VMDK nội bộ... và điều đó hiệu quả! Hầu hết các tệp mà chúng tôi cần đơn giản có thể được khôi phục mà không cần giải mã."

Profero lưu ý rằng các mục tiêu của DarkBit sẽ được phục vụ tốt hơn bằng cách sử dụng một trình xóa dữ liệu hơn là ransomware, và rằng sự từ chối đàm phán của những kẻ tấn công đã khiến họ không còn lựa chọn nào khác ngoài việc phân tách mã hóa của mã độc để tìm kiếm một phương pháp phục hồi.

Trong khi Profero không công khai phát hành trình giải mã DarkBit, họ đã nói với BleepingComputer rằng các nạn nhân trong tương lai có thể liên hệ với họ để nhận trợ giúp.