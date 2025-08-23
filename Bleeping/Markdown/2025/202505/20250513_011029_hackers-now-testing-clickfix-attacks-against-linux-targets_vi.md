# Tin tặc giờ đang thử nghiệm các cuộc tấn công ClickFix nhằm vào các mục tiêu Linux

![Linux](https://www.bleepstatic.com/content/hl-images/2024/05/31/Linux.jpg)

Một chiến dịch mới sử dụng các cuộc tấn công ClickFix đã được phát hiện nhắm vào cả hệ thống Windows và Linux bằng các hướng dẫn cho phép lây nhiễm trên cả hai hệ điều hành.

ClickFix là một [chiến thuật kỹ thuật xã hội](https://www.bleepingcomputer.com/news/security/iclicker-hack-targeted-students-with-malware-via-fake-captcha/) sử dụng các hệ thống xác minh giả hoặc lỗi ứng dụng để lừa đảo người dùng trang web chạy các lệnh console cài đặt phần mềm độc hại.

Những cuộc tấn công này đã truyền thống nhắm vào hệ thống Windows, buộc người dùng thực hiện các kịch bản PowerShell từ lệnh Run của Windows, dẫn đến việc lây nhiễm [phần mềm thông tin](https://www.bleepingcomputer.com/news/security/over-6-000-wordpress-sites-hacked-to-install-plugins-pushing-infostealers/) và [thậm chí ransomware](https://www.bleepingcomputer.com/news/security/interlock-ransomware-gang-pushes-fake-it-tools-in-clickfix-attacks/).

Tuy nhiên, một chiến dịch năm 2024 sử dụng lỗi giả mạo Google Meet cũng [nhắm vào người dùng macOS](https://www.bleepingcomputer.com/news/security/fake-google-meet-conference-errors-push-infostealing-malware/).

## ClickFix nhắm vào người dùng Linux

Một chiến dịch gần đây được phát hiện bởi [các nhà nghiên cứu Hunt.io](https://hunt.io/blog/apt36-clickfix-campaign-indian-ministry-of-defence) vào tuần trước là một trong những chiến dịch đầu tiên áp dụng kỹ thuật kỹ thuật xã hội này cho hệ thống Linux.

Cuộc tấn công, được cho là thuộc về nhóm đe dọa APT36 có liên kết với Pakistan (còn gọi là "Transparent Tribe"), sử dụng một trang web giả mạo Bộ Quốc phòng Ấn Độ với một liên kết đến một thông cáo báo chí được cho là chính thức.

![Trang web độc hại giả mạo Bộ Quốc phòng Ấn Độ](https://www.bleepstatic.com/images/news/u/1220909/2025/May/website.jpg)

**Trang web độc hại giả mạo Bộ Quốc phòng Ấn Độ**  
_Nguồn: Hunt.io_

Khi người dùng nhấp vào liên kết trang web này, họ được phân loại bởi nền tảng để xác định hệ điều hành của mình, và sau đó được chuyển hướng đến quy trình tấn công chính xác.

Trên Windows, nạn nhân sẽ được phục vụ một trang toàn màn hình cảnh báo về quyền sử dụng nội dung hạn chế. Nhấp vào 'Continue' kích hoạt JavaScript sao chép một lệnh MSHTA độc hại vào clipboard của nạn nhân, người này được chỉ dẫn để dán và thực hiện nó trên terminal của Windows.

Điều này khởi động một loader dựa trên .NET kết nối đến địa chỉ của kẻ tấn công, trong khi người dùng thấy một tệp PDF giả mạo để mọi thứ trông hợp pháp và như mong đợi.

Trên Linux, nạn nhân được chuyển hướng đến một trang CAPTCHA mà sao chép một lệnh shell vào clipboard của họ khi nhấp vào nút "I'm not a robot."

Nạn nhân sau đó được hướng dẫn nhấn ALT+F2 để mở hộp thoại chạy của Linux, dán lệnh vào đó, và sau đó nhấn **Enter** để thực thi nó.

![Hướng dẫn cho người dùng Linux](https://www.bleepstatic.com/images/news/u/1220909/2025/May/linux-instructions.jpg)

**Hướng dẫn cho người dùng Linux**  
_Nguồn: Hunt.io_

Lệnh này thả payload 'mapeal.sh' trên hệ thống của mục tiêu, mà theo Hunt.io, không thực hiện bất kỳ hành động độc hại nào trong phiên bản hiện tại, chỉ giới hạn trong việc lấy một hình ảnh JPEG từ máy chủ của kẻ tấn công.

**Kịch bản ClickFix trên Linux**  
_Nguồn: BleepingComputer_

"Script này tải một hình ảnh JPEG từ cùng một thư mục trade4wealth\[.\]in và mở nó ở chế độ nền," Hunt.io giải thích.

"Không có hoạt động nào khác, chẳng hạn như cơ chế duy trì, di chuyển bên hoặc giao tiếp ra ngoài, đã được quan sát trong quá trình thực thi."

Tuy nhiên, có thể APT36 hiện đang thử nghiệm để xác định hiệu quả của chuỗi lây nhiễm Linux, vì họ chỉ cần thay thế hình ảnh bằng một script shell để cài đặt phần mềm độc hại hoặc thực hiện các hoạt động độc hại khác.

Việc thích ứng của ClickFix để thực hiện các cuộc tấn công trên Linux là một minh chứng khác cho hiệu quả của nó, vì loại hình tấn công này hiện đã được sử dụng chống lại cả ba hệ điều hành máy tính để bàn chính.

Theo chính sách chung, người dùng không nên sao chép và dán bất kỳ lệnh nào vào hộp thoại Run mà không biết chính xác lệnh đó làm gì. Làm như vậy chỉ làm tăng nguy cơ lây nhiễm phần mềm độc hại và đánh cắp dữ liệu nhạy cảm.