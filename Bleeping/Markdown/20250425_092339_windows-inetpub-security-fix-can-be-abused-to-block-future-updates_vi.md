# Bản sửa lỗi bảo mật "inetpub" của Windows có thể bị lạm dụng để chặn các bản cập nhật trong tương lai

![Microsoft](https://www.bleepstatic.com/content/hl-images/2024/01/26/microsoft-red-header.jpg)

Một bản cập nhật bảo mật Windows gần đây đã tạo một thư mục 'inetpub', đã giới thiệu một điểm yếu mới cho phép kẻ tấn công ngăn chặn việc cài đặt các bản cập nhật trong tương lai.

Sau khi người dùng cài đặt bản cập nhật bảo mật [Microsoft Patch Tuesday](https://www.bleepingcomputer.com/news/microsoft/microsoft-april-2025-patch-tuesday-fixes-exploited-zero-day-134-flaws/) của tháng này, họ [đột nhiên phát hiện ra một thư mục "inetpub"](https://www.bleepingcomputer.com/news/microsoft/windows-11-april-update-unexpectedly-creates-new-inetpub-folder/) thuộc về tài khoản SYSTEM được tạo tại thư mục gốc của ổ hệ thống, thường là ổ C:.

Thật kỳ lạ khi thấy thư mục này được tạo ra vì nó thường được sử dụng để chứa các tệp liên quan đến dịch vụ Web Internet Information của Microsoft, dịch vụ không được cài đặt trên các thiết bị này.

Trong một bản cập nhật của một [thông báo bảo mật](http://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-21204), Microsoft sau đó đã xác nhận rằng thư mục C:\\inetpub là một phần của bản sửa lỗi cho một lỗ hổng nâng cao quyền truy cập của Windows Process Activation được theo dõi với mã CVE-2025-21204, với công ty [cảnh báo không được xóa thư mục](https://www.bleepingcomputer.com/news/security/microsoft-windows-inetpub-folder-created-by-security-fix-dont-delete/).

"Sau khi cài đặt các bản cập nhật được liệt kê trong bảng Bản cập nhật Bảo mật cho hệ điều hành của bạn, một thư mục mới %systemdrive%\\inetpub sẽ được tạo trên thiết bị của bạn," [Microsoft xác nhận](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-21204#exploitability).

"Thư mục này không nên bị xóa cho dù dịch vụ Internet Information (IIS) có hoạt động trên thiết bị mục tiêu hay không. Hành vi này là một phần của các thay đổi nhằm tăng cường bảo vệ và không yêu cầu bất kỳ hành động nào từ quản trị viên CNTT và người dùng cuối."

Tuy nhiên, chuyên gia an ninh mạng Kevin Beaumont đã chứng minh rằng thư mục này có thể bị lạm dụng để ngăn chặn việc cài đặt các bản cập nhật Windows trong tương lai nếu nó được tạo theo một cách nhất định.

"Tôi đã phát hiện ra rằng bản sửa lỗi này giới thiệu một lỗ hổng từ chối dịch vụ trong ngăn xếp bảo trì Windows cho phép người dùng không phải quản trị ngăn chặn tất cả các bản cập nhật bảo mật Windows trong tương lai," Kevin Beaumont cho biết.

Trong một báo cáo mới, [Beaumont cho biết](https://doublepulsar.com/microsofts-patch-for-cve-2025-21204-symlink-vulnerability-introduces-another-symlink-vulnerability-9ea085537741) rằng người dùng Windows, ngay cả những người không có quyền quản trị, có thể tạo một junction giữa C:\\inetpub và một tệp Windows, như C:\\windows\\system32\\notepad.exe bằng cách sử dụng lệnh sau.

```
mklink /j c:\inetpub c:\windows\system32\notepad.exe
```

Junction Windows là một loại thư mục đặc biệt chuyển hướng truy cập tới một thư mục khác trên cùng một hoặc một ổ đĩa khác, khiến nó dường như tồn tại cả hai địa điểm.

Khi được hỏi tại sao junction này ngăn cản việc cài đặt bản cập nhật, Beaumont cho biết ông tin rằng chính vì bản cập nhật mong đợi một thư mục thay vì một tệp.

"Nó có thể hoạt động với cơ bản bất kỳ tệp nào, tôi nghĩ là vì ngăn xếp bảo trì mong đợi c:\\inetpub phải là một thư mục - nhưng mklink cho phép bạn tạo một junction tới một tệp," Beaumont nói với BleepingComputer.

Theo [tài liệu của Microsoft](http://learn.microsoft.com/en-us/windows/win32/fileio/hard-links-and-junctions), junction có nghĩa là các liên kết giữa các thư mục thay vì giữa các tệp. Tuy nhiên, như bạn có thể thấy từ hình ảnh trước đó trong bài viết, vẫn có khả năng tạo một cái như trong hình ảnh dưới đây.

![C:\inetpub junction pointing to C:\Windows\system32\notepad.exe](https://www.bleepstatic.com/images/news/Microsoft/w/inetpub/inetpub-junction.jpg)

**C:\\inetpub junction trỏ đến C:\\Windows\\system32\\notepad.exe**  
_Nguồn: BleepingComputer_

Với junction này được tạo, nếu bạn cố gắng cài đặt bản cập nhật bảo mật tháng 4, nó sẽ không cài đặt đúng cách, tạo ra lỗi [0x800F081F](https://learn.microsoft.com/en-us/troubleshoot/windows-server/installing-updates-features-roles/fix-windows-update-errors). Mã lỗi này liên quan đến lỗi "CBS\_E\_SOURCE\_MISSING," nghĩa là một gói hoặc tệp không được tìm thấy.

![Windows 0x800F081F error after creating junction](https://www.bleepstatic.com/images/news/Microsoft/w/inetpub/windows-update-error.jpg)

**Lỗi Windows 0x800F081F sau khi tạo junction**  
_Nguồn: BleepingComputer:_

Beaumont cho biết ông đã báo cáo lỗi này cho Microsoft, họ đã phân loại nó là một lỗi "Trung bình" và đã đóng trường hợp của ông, cho biết họ sẽ xem xét việc sửa chữa nó trong tương lai.

"Sau khi điều tra kỹ lưỡng, trường hợp này hiện được xếp hạng là một vấn đề mức độ nghiêm trọng Trung bình," [Microsoft đã gửi email cho Beaumont](https://cyberplace.social/@GossiTheDog/114398293866746480).

"Nó không đáp ứng tiêu chuẩn hiện tại của MSRC cho việc bảo trì ngay lập tức khi bản cập nhật không thể áp dụng chỉ khi thư mục 'inetpub' là một junction tới một tệp và thành công khi xóa symlink inetpub và thử lại."

BleepingComputer cũng đã liên hệ với Microsoft về lỗi này vào thứ Tư nhưng vẫn chưa nhận được phản hồi.