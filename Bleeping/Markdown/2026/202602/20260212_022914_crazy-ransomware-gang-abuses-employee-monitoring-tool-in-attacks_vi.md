# Băng nhóm mã độc tống tiền Crazy lợi dụng công cụ giám sát nhân viên trong các cuộc tấn công

![Hacker giám sát nhân viên](https://www.bleepstatic.com/content/hl-images/2026/02/11/hacker-employee-monitoring.jpg)

Một thành viên của băng nhóm mã độc tống tiền Crazy đang lạm dụng phần mềm giám sát nhân viên hợp pháp và công cụ hỗ trợ từ xa SimpleHelp để duy trì sự tồn tại trong mạng lưới doanh nghiệp, né tránh phát hiện và chuẩn bị triển khai mã độc tống tiền.

Các vi phạm bảo mật này được ghi nhận bởi các nhà nghiên cứu tại [Huntress](https://www.huntress.com/blog/employee-monitoring-simplehelp-abused-in-ransomware-operations), họ đã điều tra nhiều sự cố nơi tin tặc triển khai Net Monitor for Employees Professional cùng với SimpleHelp để truy cập từ xa vào mạng bị xâm phạm, đồng thời hòa trộn với hoạt động quản trị thông thường.

Trong một vụ xâm nhập, kẻ tấn công đã cài đặt Net Monitor for Employees Professional bằng tiện ích Windows Installer, msiexec.exe, cho phép chúng triển khai agent giám sát trên các hệ thống bị xâm phạm trực tiếp từ trang web của nhà phát triển.

[![Wiz](https://www.bleepstatic.com/c/w/GitLab-970x250.png)](https://www.wiz.io/lp/gitlab-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FGitLab-Security-Best-Practices-Cheat-Sheet&sfcid=701Vh00000Wn1rmIAB&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=GitLab-Best-Practices) 

Sau khi cài đặt, công cụ này cho phép kẻ tấn công xem máy tính để bàn của nạn nhân từ xa, chuyển tập tin và thực thi lệnh, cung cấp hiệu quả quyền truy cập tương tác đầy đủ vào các hệ thống bị xâm phạm.

Kẻ tấn công cũng cố gắng kích hoạt tài khoản quản trị viên cục bộ bằng lệnh này:

```
net user administrator /active:yes
```

Để duy trì sự tồn tại dự phòng, kẻ tấn công đã tải xuống và cài đặt máy khách truy cập từ xa SimpleHelp thông qua các lệnh PowerShell, sử dụng tên tập tin tương tự như tập tin Visual Studio vshost.exe hợp pháp.

Tải trọng sau đó được thực thi, cho phép kẻ tấn công duy trì quyền truy cập từ xa ngay cả khi công cụ giám sát nhân viên bị gỡ bỏ.

Tệp thực thi SimpleHelp đôi khi được ngụy trang bằng cách sử dụng các tên tập tin giả mạo liên quan đến OneDrive:

```
C:\ProgramData\OneDriveSvc\OneDriveSvc.exe
```

Kẻ tấn công đã sử dụng phần mềm giám sát để thực thi lệnh từ xa, chuyển tập tin và theo dõi hoạt động hệ thống trong thời gian thực.

Các nhà nghiên cứu cũng ghi nhận kẻ tấn công vô hiệu hóa Windows Defender bằng cách cố gắng dừng và xóa các dịch vụ liên quan.

![Vô hiệu hóa Windows Defender](https://www.bleepstatic.com/images/news/security/n/netmonitor-abuse-crazy-ransomware/disabling-defender.jpg)

**Vô hiệu hóa Windows Defender**  
_Nguồn: Huntress_

Trong một sự cố, tin tặc đã định cấu hình các quy tắc giám sát trong SimpleHelp để cảnh báo chúng khi các thiết bị truy cập vào ví tiền điện tử hoặc đang sử dụng các công cụ quản lý từ xa khi chúng chuẩn bị triển khai mã độc tống tiền và đánh cắp tiền điện tử tiềm năng.

"Nhật ký cho thấy agent liên tục lặp lại các sự kiện kích hoạt và đặt lại liên quan đến từ khóa về tiền điện tử, bao gồm dịch vụ ví (metamask, exodus, wallet, blockchain), sàn giao dịch (binance, bybit, kucoin, bitrue, poloniex, bc.game, noones), trình khám phá blockchain (etherscan, bscscan) và nền tảng thanh toán payoneer", Huntress giải thích.

"Cùng với những từ khóa này, agent cũng giám sát các từ khóa liên quan đến công cụ truy cập từ xa bao gồm RDP, anydesk, ultraview, teamview và VNC, có thể để phát hiện xem có ai đang kết nối trực tiếp với máy hay không."

**Từ khóa được giám sát bởi agent SimpleHelp**  
_Nguồn: Huntress_

Việc sử dụng nhiều công cụ truy cập từ xa cung cấp tính dự phòng cho kẻ tấn công, đảm bảo chúng duy trì quyền truy cập ngay cả khi một công cụ bị phát hiện hoặc gỡ bỏ.

Mặc dù chỉ một sự cố dẫn đến việc triển khai mã độc tống tiền Crazy, Huntress tin rằng cùng một tin tặc đứng sau cả hai sự cố.

"Tên tập tin giống nhau (vhost.exe) và cơ sở hạ tầng C2 chồng chéo được tái sử dụng trên cả hai trường hợp, cho thấy mạnh mẽ rằng một cá nhân hoặc nhóm đứng sau cả hai vụ xâm nhập", Huntress giải thích.

Việc sử dụng các công cụ quản lý từ xa và giám sát hợp pháp ngày càng [phổ biến trong các vụ xâm nhập mã độc tống tiền](https://www.bleepingcomputer.com/news/security/dragonforce-ransomware-abuses-simplehelp-in-msp-supply-chain-attack/), vì những công cụ này cho phép kẻ tấn công hòa trộn với lưu lượng mạng hợp pháp.

Huntress cảnh báo rằng các tổ chức nên theo dõi chặt chẽ việc cài đặt trái phép các công cụ giám sát và hỗ trợ từ xa.

Hơn nữa, vì cả hai vụ vi phạm đều được kích hoạt thông qua thông tin xác thực SSL VPN bị xâm phạm, các tổ chức cần áp dụng xác thực đa yếu tố (MFA) trên tất cả các dịch vụ truy cập từ xa được sử dụng để truy cập mạng.