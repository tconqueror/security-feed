# Tấn công FileFix mới sử dụng kỹ thuật tuồn vào bộ nhớ đệm để né phần mềm bảo mật

![Tin tặc giơ tay](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

Một biến thể mới của tấn công social engineering FileFix sử dụng kỹ thuật tuồn vào bộ nhớ đệm (cache) để bí mật tải xuống một kho lưu trữ ZIP độc hại lên hệ thống nạn nhân và qua mặt phần mềm bảo mật.

Chiêu phishing và social engineering mới mạo danh "Fortinet VPN Compliance Checker" và được phát hiện lần đầu bởi nhà nghiên cứu an ninh mạng [P4nd3m1cb0y](https://x.com/P4nd3m1cb0y/status/1970796711816605782), người đã chia sẻ thông tin về nó trên X.

Trong một báo cáo mới bởi công ty an ninh mạng [Expel](https://expel.com/blog/cache-smuggling-when-a-picture-isnt-a-thousand-words/), nhà nghiên cứu an ninh mạng Marcus Hutchins chia sẻ thêm chi tiết về cách tấn công này hoạt động.

Đối với những ai chưa quen với các cuộc tấn công [FileFix attacks](https://www.bleepingcomputer.com/news/security/filefix-attack-weaponizes-windows-file-explorer-for-stealthy-powershell-commands/), chúng là một biến thể của cuộc tấn công social engineering [ClickFix social engineering attack](https://www.bleepingcomputer.com/news/security/fake-google-chrome-errors-trick-you-into-running-malicious-powershell-scripts/) do Mr.d0x phát triển. Thay vì lừa người dùng dán các lệnh độc hại vào hộp thoại hệ điều hành, nó sử dụng thanh địa chỉ của Windows File Explorer để thực thi các script PowerShell một cách lén lút.

## FileFix phát triển với kỹ thuật tuồn vào bộ nhớ đệm

Trong cuộc tấn công phishing mới, một trang web hiển thị một hộp thoại mạo danh Fortinet VPN "Compliance Checker", hướng người dùng dán một đường dẫn trông có vẻ hợp lệ tới một chương trình Fortinet trên một network share.

![Mồi FileFix Fortinet VPN Compliance Check](https://www.bleepstatic.com/images/news/security/f/filefix/fortinet-filefix/fortinet-filefix-lure.png)

**Fortinet VPN Compliance Check FileFix lure**  
_Nguồn: Expel_

Trong khi mồi hiển thị đường dẫn " \\\\Public\\Support\\VPN\\ForticlientCompliance.exe," khi được sao chép vào clipboard, thực ra dài hơn nhiều, vì nó được đệm thêm 139 ký tự khoảng trắng để ẩn một lệnh PowerShell độc hại.

Do việc đệm này, khi người truy cập làm theo hướng dẫn để mở File Explorer và dán lệnh vào thanh địa chỉ, chỉ đường dẫn hiển thị, như hình bên dưới.

![Cách một lệnh sao chép xuất hiện trong thanh địa chỉ File Explorer](https://www.bleepstatic.com/images/news/security/f/filefix/fortinet-filefix/filefix-fileexplorer.jpg)

**Cách một lệnh sao chép xuất hiện trong thanh địa chỉ File Explorer**  
_Nguồn: Expel_

Tuy nhiên, khi người dùng nhấn Enter trên bàn phím, Windows chạy lệnh PowerShell ẩn sau thông qua conhost.exe ở chế độ không giao diện (headless), nên người dùng không nhìn thấy.

**Malicious PowerShell command**  
_Nguồn: Expel_

Lệnh PowerShell đầu tiên tạo thư mục %LOCALAPPDATA%\\FortiClient\\compliance, sau đó sao chép các file cache của Chrome từ %LOCALAPPDATA%\\Google\\Chrome\\User Data\\Default\\Cache\\Cache_Data\\ vào thư mục đó.

Script sau đó quét từng file cache bằng biểu thức chính quy để tìm nội dung nằm giữa "bTgQcBpv" và "mX6o0lBw". Nội dung này thực ra là một file zip được lưu trong file hình giả, được trích xuất thành ComplianceChecker.zip và giải nén.

Script sau đó khởi chạy file thực thi FortiClientComplianceChecker.exe từ kho lưu trữ đã giải nén để thực thi mã độc.

Bạn có thể thắc mắc làm thế nào file độc hại lại được lưu trong các file cache của Chrome ngay từ đầu, và đây là nơi kỹ thuật tuồn vào bộ nhớ đệm xuất hiện.

Khi người truy cập truy cập trang phishing chứa mồi FileFix, trang web đã chạy JavaScript yêu cầu trình duyệt lấy về một file hình ảnh.

Vì phản hồi HTTP nói rằng ảnh được lấy có kiểu "image/jpeg", trình duyệt tự động lưu vào cache trên hệ thống file, xử lý nó như một file ảnh hợp lệ, mặc dù thực tế không phải vậy.

Vì việc này được thực hiện trước khi lệnh PowerShell được thực thi thông qua File Explorer, file đã tồn tại trong cache, và file zip có thể được trích xuất từ đó.

"Kỹ thuật này, được gọi là cache smuggling, cho phép phần mềm độc hại né nhiều loại sản phẩm bảo mật khác nhau," giải thích Hutchins.

"Cả trang web lẫn script PowerShell đều không trực tiếp tải xuống bất kỳ file nào. Bằng cách đơn giản để trình duyệt cache 'hình ảnh' giả, phần mềm độc hại có thể đưa cả một file zip lên hệ thống cục bộ mà không cần lệnh PowerShell phải thực hiện bất kỳ yêu cầu web nào."

"Kết quả là, bất kỳ công cụ nào quét các file tải xuống hoặc tìm các script PowerShell thực hiện yêu cầu web sẽ không phát hiện hành vi này."

Các tác nhân đe dọa đã nhanh chóng áp dụng kỹ thuật FileFix mới ngay sau khi nó bị công bố, với các băng nhóm ransomware và các tác nhân đe dọa khác sử dụng nó trong các chiến dịch của họ.

## Bộ tạo ClickFix mở rộng hệ sinh thái

Bên cạnh biến thể FileFix mới tuồn cache, các nhà nghiên cứu tại Palo Alto Unit 42 phát hiện một bộ ClickFix mới có tên "IUAM ClickFix Generator," tự động hóa việc tạo mồi kiểu ClickFix.

Giao diện của ClickFix Generator cho phép kẻ tấn công thiết kế các trang xác thực giả, tùy chỉnh tiêu đề và văn bản trang, chọn bảng màu và cấu hình payload clipboard.

**Giao diện IUAM ClickFix Generator**  
_Nguồn: Unit 42_

Bộ kit cũng hỗ trợ phát hiện hệ điều hành, điều chỉnh các lệnh PowerShell cho Windows hoặc các lệnh shell được mã hóa Base64 cho macOS, trong khi đôi khi phục vụ những mồi vô hại cho các hệ điều hành khác.

Các mồi dường như đều liên quan đến một kiểu CAPTCHA Cloudflare giả, với các nhà nghiên cứu thấy nhiều trang web được tạo sử dụng các mồi được sinh ra này.

Những trang web này tuyên bố có liên kết với Cloudflare, Speedtest, Microsoft Teams, Claude, TradingView, Microsoft và Microsoft 365, trong số những trang khác.

**Microsoft ClickFix lure**  
_Nguồn: BleepingComputer_

Mặc dù mỗi mồi được tùy biến theo chiến dịch của kẻ tấn công, hành vi vẫn giống nhau, hiển thị một CAPTCHA Cloudflare giả yêu cầu người dùng chạy một lệnh ẩn trong Command Prompt, hộp Run, hoặc Terminal.

Trong chiến dịch được Unit 42 quan sát, các cuộc tấn công social engineering này được sử dụng để nhiễm các thiết bị với phần mềm đánh cắp thông tin DeerStealer (Windows) và Odyssey (Mac), cũng như một payload Windows chưa xác định khác.

Vì các loại tấn công social engineering này ngày càng phổ biến trong giới tác nhân đe dọa, điều quan trọng là giáo dục nhân viên về việc không bao giờ sao chép văn bản từ một trang web và chạy nó trong hộp thoại của hệ điều hành.