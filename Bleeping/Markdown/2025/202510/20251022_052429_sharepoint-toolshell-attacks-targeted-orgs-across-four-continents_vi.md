# Sharepoint ToolShell tấn công các tổ chức nhắm vào các tổ chức trên bốn châu lục

![Tin tặc](https://www.bleepstatic.com/content/hl-images/2025/09/09/hacker.jpg)

Các tin tặc được cho là có liên hệ với China đã lợi dụng lỗ hổng ToolShell (CVE-2025-53770) trong Microsoft SharePoint trong các cuộc tấn công nhắm vào các cơ quan chính phủ, các trường đại học, nhà cung cấp dịch vụ viễn thông và các tổ chức tài chính.

Lỗ hổng bảo mật ảnh hưởng các máy chủ SharePoint on-premise và đã được tiết lộ là một [zero-day bị khai thác tích cực](https://www.bleepingcomputer.com/news/microsoft/microsoft-sharepoint-zero-day-exploited-in-rce-attacks-no-patch-available/) vào ngày 20 tháng 7, sau khi nhiều nhóm hacker có liên quan đến China lợi dụng nó trong các cuộc tấn công quy mô rộng. Microsoft đã phát hành [các bản cập nhật khẩn cấp](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-emergency-patches-for-sharepoint-rce-flaws-exploited-in-attacks/) vào ngày hôm sau.

Vấn đề này là một bypass cho CVE-2025-49706 và CVE-2025-49704, hai lỗ hổng mà các nhà nghiên cứu Viettel Cyber Security đã trình diễn tại cuộc thi hack Pwn2Own Berlin vào tháng Năm, và có thể bị lợi dụng từ xa không cần xác thực để thực thi mã và truy cập đầy đủ vào hệ thống file.

Microsoft trước đây cho biết rằng ToolShell đã bị khai thác bởi ba nhóm đe dọa Chinese, Budworm/Linen Typhoon, Sheathminer/Violet Typhoon, và Storm-2603/Warlock ransomware.

Trong một [báo cáo](https://www.security.com/blog-post/toolshell-china-zingdoor) hôm nay, công ty an ninh mạng Symantec, thuộc Broadcom, cho biết ToolShell đã được sử dụng để xâm phạm nhiều tổ chức ở Middle East, South America, the U.S., và Africa, và các chiến dịch đã sử dụng phần mềm độc hại thường liên quan đến Salt Typhoon Chinese hackers:

* Một nhà cung cấp dịch vụ viễn thông ở Middle East
* Hai bộ phận chính phủ ở một quốc gia châu Phi
* Hai cơ quan chính phủ ở South America
* Một trường đại học ở the United States
* Một cơ quan công nghệ bang ở Africa
* Một bộ phận chính phủ ở Middle East
* Một công ty tài chính ở Europe

Hoạt động nhắm vào công ty viễn thông, vốn là trọng tâm của báo cáo của Symantec, bắt đầu vào ngày 21 tháng 7 với việc khai thác CVE-2025-53770 để cấy webshells cho phép truy cập dai dẳng.

Tiếp theo là DLL side-loading một backdoor viết bằng Go có tên Zingdoor, có thể thu thập thông tin hệ thống, thực hiện thao tác trên tập tin, và hỗ trợ thực thi lệnh từ xa.

Sau đó, một bước side-loading khác khởi chạy "có vẻ là Trojan ShadowPad," các nhà nghiên cứu cho biết, và hành động này tiếp theo bằng việc thả công cụ KrustyLoader viết bằng Rust, vốn cuối cùng triển khai framework post-exploitation mã nguồn mở Sliver.

Đáng chú ý, các bước side-loading đã được thực hiện bằng cách sử dụng các file thực thi hợp pháp của Trend Micro và BitDefender. Trong các cuộc tấn công ở South America, các tác nhân đe dọa đã dùng một file giống tên Symantec.

Tiếp theo, kẻ tấn công tiến hành dump thông tin xác thực qua ProcDump, Minidump, và LsassDumper, và lợi dụng PetitPotam (CVE-2021-36942) để chiếm quyền trên domain.

Các nhà nghiên cứu lưu ý rằng danh sách các công cụ công khai sẵn có và living-off-the-land được sử dụng trong các cuộc tấn công bao gồm tiện ích Certutil từ Microsoft, GoGo Scanner (một engine quét của red-team), và tiện ích Revsocks cho phép rút trộm dữ liệu, command-and-control, và duy trì persistence trên thiết bị đã bị xâm phạm.

Symantec cho biết các phát hiện của họ chỉ ra rằng lỗ hổng ToolShell đã bị khai thác bởi một tập hợp các tác nhân đe dọa Chinese lớn hơn so với những gì trước đây được biết.