# Notepad++ khắc phục lỗ hổng cho phép kẻ tấn công đẩy tệp cập nhật độc hại

![Notepad++](https://www.bleepstatic.com/content/hl-images/2021/06/07/Notepad++.jpg)

Phiên bản Notepad++ 8.8.9 được phát hành để sửa một lỗ hổng bảo mật trong công cụ cập nhật WinGUp sau khi các nhà nghiên cứu và người dùng báo cáo các sự cố trong đó trình cập nhật tải về các file thực thi độc hại thay vì các gói cập nhật hợp lệ.

Những dấu hiệu đầu tiên của vấn đề này xuất hiện trong một [chủ đề diễn đàn cộng đồng Notepad++](https://community.notepad-plus-plus.org/topic/27212/autoupdater-and-connection-temp-sh/6), nơi một người dùng báo cáo rằng công cụ cập nhật của Notepad++, GUP.exe (WinGUp), đã khởi tạo một file thực thi không rõ tên "%Temp%\\AutoUpdater.exe" mà thực thi các lệnh để thu thập thông tin thiết bị.

Theo người báo cáo, file thực thi độc hại này đã chạy nhiều lệnh thăm dò và lưu đầu ra vào một file có tên 'a.txt.'

```
cmd /c netstat -ano >> a.txt
cmd /c systeminfo >> a.txt
cmd /c tasklist >> a.txt
cmd /c whoami >> a.txt
```

Phần mềm độc hại _autoupdater.exe_ sau đó đã sử dụng lệnh curl.exe để rút trích file a.txt tới một site từ xa tại temp\[.\]sh.

Vì GUP sử dụng thư viện libcurl thay vì lệnh 'curl.exe' thực tế và không thu thập loại thông tin này, các người dùng Notepad++ khác suy đoán rằng người dùng đã cài đặt một phiên bản Notepad++ không chính thức, độc hại hoặc lưu lượng mạng autoupdate đã bị chiếm quyền.

Để giúp giảm thiểu các khả năng chiếm quyền mạng, nhà phát triển Notepad++, Don Ho, đã phát hành phiên bản 8.8.8 vào ngày 18 tháng 11, để các bản cập nhật chỉ có thể được tải xuống từ GitHub.

Như một bản vá mạnh hơn, Notepad 8.8.9 được phát hành vào ngày 9 tháng 12, sẽ ngăn các bản cập nhật không được ký bằng chứng chỉ ký mã của nhà phát triển được cài đặt.

"Bắt đầu từ bản phát hành này, Notepad++ & WinGUp đã được gia cố để xác minh chữ ký & chứng chỉ của các trình cài đặt được tải xuống trong quá trình cập nhật. Nếu việc xác minh thất bại, cập nhật sẽ bị hủy." trích từ [thông báo bảo mật Notepad 8.8.9](https://community.notepad-plus-plus.org/topic/27298/notepad-v8-8-9-vulnerability-fix).

## URL cập nhật bị chiếm quyền

Đầu tháng này, chuyên gia bảo mật Kevin Beaumont cảnh báo rằng ông đã nghe từ ba tổ chức bị ảnh hưởng bởi các sự cố an ninh liên quan tới Notepad++.

"Tôi đã nghe từ 3 tổ chức giờ đã có các sự cố an ninh trên các máy cài Notepad++, nơi có vẻ như các tiến trình Notepad++ đã khởi tạo truy cập ban đầu." [Beaumont giải thích](http://doublepulsar.com/small-numbers-of-notepad-users-reporting-security-woes-371d7a3fd2d9).

"Những việc này đã dẫn tới các tác nhân đe dọa thao tác trực tiếp trên máy."

Nhà nghiên cứu cho biết tất cả các tổ chức ông nói chuyện đều có mối quan hệ với Đông Á và hoạt động có vẻ rất có mục tiêu, với các nạn nhân báo cáo hoạt động thăm dò thủ công sau các sự cố.

Khi Notepad++ kiểm tra cập nhật, nó kết nối tới https://notepad-plus-plus.org/update/getDownloadUrl.php?version=<versionnumber>. Nếu có phiên bản mới hơn, endpoint sẽ trả về dữ liệu XML cung cấp đường dẫn tải xuống tới phiên bản mới nhất:

```
<GUP>
<script/>
<NeedToBeUpdated>yes</NeedToBeUpdated>
<Version>8.8.8</Version>
<Location>https://github.com/notepad-plus-plus/notepad-plus-plus/releases/download/v8.8.8/npp.8.8.8.Installer.exe</Location>
</GUP>
```

Beaumont suy đoán rằng cơ chế autoupdate của Notepad++ có thể đã bị chiếm quyền trong các sự cố này để đẩy các bản cập nhật độc hại cho phép tác nhân đe dọa truy cập từ xa.

"Nếu bạn có thể chặn và thay đổi lưu lượng này, bạn có thể chuyển hướng tải xuống tới bất kỳ vị trí nào bằng cách thay đổi URL trong thuộc tính <Location>," Beaumont giải thích.

"Bởi vì lưu lượng tới notepad-plus-plus.org khá hiếm, có thể ngồi trong chuỗi ISP và chuyển hướng tới một nơi tải khác. Để thực hiện việc này ở quy mô lớn đòi hỏi nhiều nguồn lực," nhà nghiên cứu tiếp tục.

Tuy nhiên, Beaumont lưu ý rằng không hiếm các tác nhân đe dọa sử dụng [malvertising để phân phối các phiên bản Notepad++ độc hại](https://www.bleepingcomputer.com/news/security/malicious-notepad-plus-plus-google-ads-evade-detection-for-months/) cài đặt phần mềm độc hại.

Thông báo bảo mật của Notepad++ chia sẻ cùng sự không chắc chắn, nêu rằng họ vẫn đang điều tra cách lưu lượng bị chiếm quyền.

"Cuộc điều tra đang tiếp tục để xác định phương thức chính xác của việc chiếm quyền lưu lượng. Người dùng sẽ được thông báo một khi có bằng chứng cụ thể về nguyên nhân được thiết lập," trích từ [thông báo bảo mật](http://notepad-plus-plus.org/news/v889-released/).

Nhà phát triển cho biết tất cả người dùng Notepad++ nên nâng cấp lên phiên bản mới nhất, 8.8.9. Họ cũng lưu ý rằng kể từ v8.8.7, tất cả các nhị phân và trình cài chính thức đều được ký bằng chứng chỉ hợp lệ, và người dùng đã cài đặt trước đó một chứng chỉ gốc tùy chỉnh nên gỡ bỏ nó.

BleepingComputer đã liên hệ với nhà phát triển Notepad++ vào ngày 3 tháng 12 với các câu hỏi về các sự cố nhưng không nhận được phản hồi.