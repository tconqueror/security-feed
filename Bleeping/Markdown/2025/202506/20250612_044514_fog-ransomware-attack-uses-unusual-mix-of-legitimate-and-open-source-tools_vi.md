# Cuộc tấn công ransomware Fog sử dụng bộ công cụ độc đáo kết hợp giữa công cụ hợp pháp và mã nguồn mở

![Cuộc tấn công ransomware Fog sử dụng bộ công cụ độc đáo kết hợp giữa công cụ hợp pháp và mã nguồn mở](https://www.bleepstatic.com/content/hl-images/2024/06/06/Fog-ransomware.jpg)

Tin tặc ransomware Fog đang sử dụng một bộ công cụ ít phổ biến hơn, bao gồm các tiện ích pentesting mã nguồn mở và một phần mềm giám sát nhân viên hợp pháp có tên Syteca.

Hoạt động ransomware Fog đã được [quan sát lần đầu tiên vào năm ngoái](https://www.bleepingcomputer.com/news/security/new-fog-ransomware-targets-us-education-sector-via-breached-vpns/) vào tháng 5 và sử dụng thông tin đăng nhập VPN bị xâm phạm để truy cập mạng của các nạn nhân.

Sau khi xâm nhập, họ đã sử dụng các cuộc tấn công “pass-the-hash” để giành quyền quản trị, vô hiệu hóa Windows Defender và mã hóa tất cả các tệp, bao gồm cả lưu trữ máy ảo.

Sau đó, nhóm đe dọa này được quan sát đang khai thác các lỗ hổng n-day ảnh hưởng đến các máy chủ [Veeam Backup & Replication](https://www.bleepingcomputer.com/news/security/akira-and-fog-ransomware-now-exploiting-critical-veeam-rce-flaw/) (VBR), cũng như các điểm cuối [SonicWall SSL VPN](https://www.bleepingcomputer.com/news/security/fog-ransomware-targets-sonicwall-vpns-to-breach-corporate-networks/).

## Bộ công cụ tấn công mới

Các nhà nghiên cứu tại Symantec và nhóm Carbon Black Threat Hunter đã phát hiện bộ công cụ tấn công độc đáo này trong một phản ứng sự cố vào tháng trước tại một tổ chức tài chính ở châu Á.

Symantec không thể xác định được vectơ lây nhiễm ban đầu nhưng đã ghi lại việc sử dụng nhiều công cụ mới mà trước đây chưa được thấy trong các cuộc tấn công như vậy.

Công cụ kỳ lạ và thú vị nhất trong số đó là Syteca (trước đây được biết đến với tên Ekran), một phần mềm giám sát nhân viên hợp pháp ghi lại hoạt động màn hình và thao tác nhập liệu.

Các kẻ tấn công có thể sử dụng công cụ này để thu thập thông tin như tài khoản người dùng mà nhân viên nhập mà không hề biết rằng họ đang bị giám sát từ xa.

Syteca đã được chuyển một cách bí mật đến hệ thống bởi Stowaway, một công cụ proxy mã nguồn mở dùng cho giao tiếp và truyền tải tệp bí mật, và được thực thi bởi SMBExec, tương đương với PsExec trong môi trường mã nguồn mở Impacket được sử dụng cho di chuyển ngang.

Cuộc tấn công cũng liên quan đến GC2, một backdoor sau khai thác mã nguồn mở sử dụng Google Sheets hoặc Microsoft SharePoint cho command-and-control (C2) và dữ liệu exfiltration.

GC2 hiếm khi được thấy trong các cuộc tấn công ransomware, và trước đây đã được sử dụng trong các cuộc tấn công được quy cho [nhóm đe dọa APT41 của Trung Quốc](https://www.bleepingcomputer.com/news/security/hackers-abuse-google-command-and-control-red-team-tool-in-attacks/).

Apart from these tools, Symantec also lists the following as part of Fog ransomware’s latest arsenal:

* Adapt2x C2 – open-source alternative to Cobalt Strike supporting post-exploitation actions
* Process Watchdog – system monitoring utility that can restart key processes
* PsExec – Microsoft Sysinternals tool for remote execution across networked machines
* Impacket SMB – Python library with low-level programmatic access to SMB, likely used for deploying the ransomware payload on the victim’s machine.

Để chuẩn bị dữ liệu cho việc exfiltration và gửi nó đến cơ sở hạ tầng của họ, ransomware Fog cũng đã sử dụng các tiện ích 7-Zip, MegaSync, và FreeFileSync.

“Bộ công cụ được triển khai bởi các kẻ tấn công khá không điển hình cho một cuộc tấn công ransomware,” [bình luận của Symantec trong báo cáo](https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/fog-ransomware-attack).

“Phần mềm Syteca và công cụ GC2 không phải là những công cụ mà chúng tôi đã thấy được triển khai trong các cuộc tấn công ransomware trước đây, trong khi công cụ proxy Stowaway và Adap2x C2 Agent Beacon cũng là những công cụ bất thường khi được sử dụng trong cuộc tấn công ransomware,” các nhà nghiên cứu cho biết.

Những bộ công cụ khác thường như bộ công cụ mà Symantec phát hiện trong cuộc tấn công ransomware Fog gần đây có thể giúp các tác nhân đe dọa lẩn tránh sự phát hiện. Báo cáo của các nhà nghiên cứu cung cấp các chỉ số xâm phạm có thể giúp các tổ chức bảo vệ chống lại các sự cố như vậy.