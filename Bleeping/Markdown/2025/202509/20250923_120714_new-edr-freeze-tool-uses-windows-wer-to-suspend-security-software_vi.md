# Công cụ mới EDR-Freeze sử dụng Windows WER để tạm dừng phần mềm bảo mật

![Công cụ mới EDR-Freeze sử dụng Windows WER để tạm dừng phần mềm bảo mật](https://www.bleepstatic.com/content/hl-images/2025/08/20/Windows.jpg)

Một phương pháp mới và công cụ proof-of-concept có tên EDR-Freeze chứng minh rằng việc né tránh các giải pháp bảo mật có thể thực hiện được từ chế độ người dùng bằng hệ thống Windows Error Reporting (WER) của Microsoft.

Kỹ thuật này loại bỏ nhu cầu sử dụng một driver dễ khai thác và đặt các tác nhân bảo mật như endpoint detection and response (EDR) vào trạng thái ngủ đông.

Bằng cách sử dụng framework WER cùng với API MiniDumpWriteDump, nhà nghiên cứu bảo mật [TwoSevenOneThree (Zero Salarium)](https://www.zerosalarium.com/2025/09/EDR-Freeze-Puts-EDRs-Antivirus-Into-Coma.html) đã tìm ra cách tạm dừng vô thời hạn hoạt động của các tiến trình EDR và phần mềm diệt virus.

Các phương pháp vô hiệu hóa EDR hiện có hoạt động dựa trên kỹ thuật “Bring Your Own Vulnerable Driver” (BYOVD), trong đó kẻ tấn công sử dụng một kernel driver hợp lệ nhưng dễ bị khai thác và lợi dụng nó để leo thang đặc quyền.

Những hạn chế chính trong các cuộc tấn công BYOVD bao gồm việc phải đưa driver vào hệ thống mục tiêu, vượt qua các cơ chế bảo vệ thực thi, và xóa các dấu vết ở mức kernel có thể lộ hoạt động.

EDR-Freeze được mô tả là một phương pháp kín đáo hơn nhiều, không cần driver kernel, hoạt động hoàn toàn từ chế độ người dùng, và lợi dụng các thành phần Windows hợp pháp có sẵn theo mặc định trong hệ điều hành.

## Cách EDR-Freeze hoạt động

WerFaultSecure là một thành phần của Windows Error Reporting chạy với đặc quyền Protected Process Light (PPL), được thiết kế để thu thập dump khi các tiến trình hệ thống nhạy cảm gặp sự cố để gỡ lỗi và chẩn đoán.

MiniDumpWriteDump là một API trong thư viện DbgHelp tạo một snapshot (“minidump”) của bộ nhớ và trạng thái của tiến trình. Trong quá trình đó, nó tạm dừng tất cả các luồng của tiến trình mục tiêu và tiếp tục chúng sau khi hoàn thành công việc.

EDR-Freeze lợi dụng WerFaultSecure để kích hoạt MiniDumpWriteDump, quá trình này tạm thời tạm dừng tất cả các luồng trong tiến trình mục tiêu trong khi dump được ghi.

Trong khi quá trình này diễn ra, kẻ tấn công tạm dừng chính tiến trình WerFaultSecure, nên trình ghi dump không bao giờ tiếp tục tiến trình mục tiêu, khiến tiến trình AV ở trạng thái “hôn mê”.

Nhà nghiên cứu mô tả đây là một cuộc tấn công cuộc đua (race condition) có thể tái tạo theo bốn bước:

1. Spawn WerFaultSecure as a PPL.  
2. Pass arguments to WerFaultSecure so it calls MiniDumpWriteDump on the target PID.  
3. Poll the target until it becomes suspended by the dump operation.  
4. Immediately open WerFaultSecure (PROCESS\_SUSPEND\_RESUME) and call NtSuspendProcess to freeze the dumper.

Nhà nghiên cứu cũng đã [công bố một công cụ](http://github.com/TwoSevenOneT/EDR-Freeze) thực hiện những hành động này, và đã thử nghiệm trên Windows 11 24H2, thành công trong việc đóng băng tiến trình Windows Defender.

![Setting the parameters (left) and suspending Windows Defender (right)](https://www.bleepstatic.com/images/news/u/1220909/2025/September/target-time.jpg)

**Thiết lập tham số (bên trái) và tạm dừng Windows Defender (bên phải)**  
_Nguồn: Zero Salarium_

Cuộc tấn công mới này kết hợp hành vi dự kiến của cả MiniDumpWriteDump và WerFaultSecure, do đó đây hợp lý hơn là một điểm yếu thiết kế hơn là một lỗ hổng trong Windows.

Việc phòng thủ chống EDR-Freeze có thể thực hiện bằng cách giám sát nếu WER trỏ tới định danh của một tiến trình nhạy cảm như LSASS hoặc các công cụ bảo mật. Vì mục đích này, nhà nghiên cứu bảo mật Steven Lim đã phát triển một công cụ giúp ánh xạ WerFaultSecure tới các tiến trình Microsoft Defender Endpoint.

Tuy nhiên, Microsoft có thể thực hiện các bước để tăng cường bảo mật các thành phần Windows này chống lại lạm dụng, như chặn những lần gọi đáng ngờ, chỉ cho phép với một số PID nhất định, hoặc giới hạn các tham số có thể sử dụng.

BleepingComputer đã liên hệ với Microsoft để xin bình luận về cách phòng chống kỹ thuật như vậy và chúng tôi sẽ cập nhật bài viết này khi có phản hồi.