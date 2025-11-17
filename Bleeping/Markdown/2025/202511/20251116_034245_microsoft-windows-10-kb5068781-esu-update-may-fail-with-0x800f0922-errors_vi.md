# Microsoft: Windows 10 KB5068781 ESU cập nhật có thể thất bại với lỗi 0x800f0922

![Windows 10](https://www.bleepstatic.com/content/hl-images/2021/04/17/windows-10-sapphire.jpg)

Microsoft đã xác nhận họ đang điều tra một lỗi khiến bản cập nhật bảo mật mở rộng Windows 10 KB5068781 không thể cài đặt và gặp lỗi 0x800f0922 trên các thiết bị có giấy phép doanh nghiệp.

KB5068781 là [bản cập nhật bảo mật mở rộng Windows 10 đầu tiên](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-kb5068781-the-first-windows-10-extended-security-update/) và được phát hành vào ngày 11 tháng 11 như một phần của [Patch Tuesday](https://www.bleepingcomputer.com/news/microsoft/microsoft-november-2025-patch-tuesday-fixes-1-zero-day-63-flaws/).

Kể từ đó, một số người dùng Windows 10 doanh nghiệp đã báo cáo rằng bản cập nhật KB5068781 không thể cài đặt trên một số thiết bị.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

“Hiện chúng tôi đang gặp cùng vấn đề với KB5068781 trên các thiết bị Win10 được quản lý, mặc dù đã mua và áp dụng giấy phép ESU (MAK key) cho tất cả thiết bị,” một độc giả của BleepingComputer viết.

“Bản cập nhật có vẻ cài đặt thành công, nhưng sau khi khởi động lại, nó không thể áp dụng và quay về với lỗi phổ biến 0x800f0922.”

Microsoft hiện đã xác nhận rằng họ biết và đang điều tra vấn đề này, cho biết nó chỉ ảnh hưởng đến Windows subscription activation thông qua Microsoft 365 Admin Center.

“Some Windows 10 devices enrolled in Extended Security Updates (ESU) might fail to install the November 2025 security update (the Originating KBs listed above) with error 0x800f0922 (CBS\_E\_INSTALLERS\_FAILED),” explains Microsoft.

“Vấn đề này chỉ giới hạn ở các thiết bị được kích hoạt thông qua [Windows subscription activation](https://learn.microsoft.com/windows/deployment/windows-subscription-activation?pivots=windows-10) qua Microsoft 365 Admin Center.”

Rất tiếc, chưa có thời gian ước tính khi nào bản sửa lỗi sẽ có và Microsoft chưa cung cấp bất kỳ giải pháp tạm thời nào để khắc phục những lỗi này.

Ngoài lỗi khi cài đặt, các quản trị viên Windows trong môi trường doanh nghiệp đã báo cáo \[[1](https://www.reddit.com/r/SCCM/comments/1ovetfu/kb5068781%5Fsupersedes%5Flast%5Fpatch%5Fof%5Fw10/), [2](https://www.reddit.com/r/sysadmin/comments/1owu7t9/purchased%5Fand%5Finstalled%5Fesu%5Fproduct%5Fkey%5Ffor%5F1/)\] rằng không phải tất cả thiết bị Windows 10 của họ đều hiển thị cần bản cập nhật KB5068781 ESU mới, ngay cả khi chúng đã được cấp phép phù hợp để nhận nó.

Để giúp các tổ chức cải thiện quy trình vá lỗi và giảm rủi ro các sự cố như thế này, BleepingComputer sẽ tổ chức một webinar vào ngày 2 tháng 12 cùng Action1 về quản lý bản vá hiện đại.