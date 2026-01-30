# Microsoft sẽ vô hiệu hóa NTLM mặc định trong các bản phát hành Windows tương lai

![Windows](https://www.bleepstatic.com/content/hl-images/2024/06/12/windows-blue-background.jpg)

Microsoft thông báo rằng họ sẽ vô hiệu hóa giao thức xác thực NTLM đã 30 năm tuổi theo mặc định trong các bản phát hành Windows sắp tới do các lỗ hổng bảo mật khiến các tổ chức phơi nhiễm trước các cuộc tấn công mạng.

NTLM (viết tắt của New Technology LAN Manager) là giao thức xác thực challenge-response được giới thiệu năm 1993 với Windows NT 3.1 và là kế nhiệm của giao thức LAN Manager (LM).

Kerberos đã [thay thế NTLM](https://answers.microsoft.com/en-us/msoffice/forum/all/ntlm-vs-kerberos/d8b139bf-6b5a-4a53-9a00-bb75d4e219eb) và hiện là giao thức mặc định hiện tại cho các thiết bị kết nối miền chạy Windows 2000 trở lên. Mặc dù đã từng là giao thức mặc định trong các phiên bản Windows cũ, NTLM vẫn được sử dụng ngày nay như một phương pháp xác thực dự phòng khi Kerberos không khả dụng, mặc dù nó sử dụng mật mã yếu và dễ bị tấn công.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Kể từ khi phát hành, NTLM đã bị khai thác rộng rãi trong các [cuộc tấn công NTLM relay](https://www.bleepingcomputer.com/tag/ntlm-relay-attack/) (nơi các tác nhân đe dọa buộc các thiết bị mạng bị xâm phạm xác thực với các máy chủ do kẻ tấn công kiểm soát) để leo thang đặc quyền và giành quyền kiểm soát hoàn toàn miền Windows. Bất chấp điều này, NTLM vẫn được sử dụng trên máy chủ Windows, cho phép kẻ tấn công khai thác các lỗ hổng như [PetitPotam](https://www.bleepingcomputer.com/news/security/microsoft-fixes-new-petitpotam-windows-ntlm-relay-attack-vector/), [ShadowCoerce](https://www.bleepingcomputer.com/news/microsoft/microsoft-quietly-fixes-shadowcoerce-windows-ntlm-relay-bug/), [DFSCoerce](https://www.bleepingcomputer.com/news/microsoft/new-dfscoerce-ntlm-relay-attack-allows-windows-domain-takeover/) và [RemotePotato0](https://www.bleepingcomputer.com/news/security/windows-remotepotato0-zero-day-gets-an-unofficial-patch/) để bỏ qua các biện pháp giảm thiểu tấn công NTLM relay.

NTLM cũng đã bị nhắm mục tiêu bởi các [cuộc tấn công pass-the-hash](https://www.bleepingcomputer.com/tag/pass-the-hash/), trong đó tin tặc mạng khai thác lỗ hổng hệ thống hoặc triển khai phần mềm độc hại để đánh cắp các hash NTLM (mật khẩu được băm) từ các hệ thống mục tiêu. Những mật khẩu được băm này được sử dụng để xác thực như người dùng bị xâm phạm, cho phép kẻ tấn công đánh cắp dữ liệu nhạy cảm và lan truyền ngang qua mạng.

## "Bị chặn và không còn được tự động sử dụng"

Vào thứ Năm, như một phần của nỗ lực rộng lớn hơn hướng tới các phương pháp xác thực không dùng mật khẩu và chống lừa đảo, Microsoft đã thông báo rằng NTLM cuối cùng sẽ bị vô hiệu hóa theo mặc định trong bản phát hành chính tiếp theo của Windows Server và các phiên bản máy khách Windows liên quan, đánh dấu sự thay đổi đáng kể từ giao thức cũ sang xác thực dựa trên Kerberos an toàn hơn.

Microsoft cũng đã phác thảo kế hoạch chuyển đổi ba giai đoạn được thiết kế để giảm thiểu rủi ro liên quan đến NTLM đồng thời hạn chế gián đoạn. Trong giai đoạn một, quản trị viên sẽ có thể sử dụng các công cụ kiểm tra nâng cao có sẵn trong Windows 11 24H2 và Windows Server 2025 để xác định nơi NTLM vẫn đang được sử dụng.

Giai đoạn hai, dự kiến vào nửa cuối năm 2026, sẽ giới thiệu các tính năng mới như IAKerb và Local Key Distribution Center để giải quyết các tình huống phổ biến kích hoạt chế độ dự phòng NTLM.

Giai đoạn ba sẽ vô hiệu hóa NTLM mạng theo mặc định trong các bản phát hành tương lai, mặc dù giao thức này vẫn sẽ hiện diện trong hệ điều hành và có thể được kích hoạt lại rõ ràng thông qua các điều khiển chính sách nếu cần.

![NTLM timeline](https://www.bleepstatic.com/images/news/u/1109292/2026/ntlm-timeline.png)

_Dòng thời gian NTLM (Microsoft)_

​"Vô hiệu hóa NTLM theo mặc định không có nghĩa là hoàn toàn loại bỏ NTLM khỏi Windows. Thay vào đó, Windows sẽ được cung cấp ở trạng thái bảo mật mặc định nơi xác thực NTLM mạng bị chặn và không còn được tự động sử dụng", [Microsoft cho biết](https://techcommunity.microsoft.com/blog/windows-itpro-blog/advancing-windows-security-disabling-ntlm-by-default/4489526).

"Hệ điều hành sẽ ưu tiên các giải pháp thay thế hiện đại, an toàn hơn dựa trên Kerberos. Đồng thời, các kịch bản cũ phổ biến sẽ được giải quyết thông qua các khả năng mới sắp tới như Local KDC và IAKerb (bản xem trước)."

Microsoft lần đầu tiên thông báo [kế hoạch loại bỏ giao thức xác thực NTLM](https://www.bleepingcomputer.com/news/security/microsoft-plans-to-kill-off-ntlm-authentication-in-windows-11/) vào tháng 10 năm 2023, lưu ý rằng họ cũng muốn mở rộng các điều khiển quản lý để cung cấp cho quản trị viên sự linh hoạt hơn trong việc giám sát và hạn chế việc sử dụng NTLM trong môi trường của họ.

Họ cũng [chính thức không dùng nữa xác thực NTLM](https://www.bleepingcomputer.com/news/microsoft/microsoft-deprecates-windows-ntlm-authentication-protocol/) trên Windows và máy chủ Windows vào tháng 7 năm 2024, khuyên các nhà phát triển chuyển sang xác thực Kerberos hoặc Negotiation để ngăn ngừa các vấn đề trong tương lai.

Microsoft đã cảnh báo các nhà phát triển ngừng sử dụng NTLM trong ứng dụng của họ [từ năm 2010](https://learn.microsoft.com/en-us/openspecs/windows%5Fprotocols/ms-nlmp/1e846608-4c5f-41f4-8454-1b91af8a755b) và khuyên quản trị viên Windows vô hiệu hóa NTLM hoặc cấu hình máy chủ của họ để chặn các cuộc tấn công NTLM relay bằng Dịch vụ Chứng chỉ Active Directory (AD CS).