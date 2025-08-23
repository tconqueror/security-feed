# Tin tặc lạm dụng tính năng mạng IPv6 để chiếm đoạt cập nhật phần mềm

![Malware](https://www.bleepstatic.com/content/hl-images/2022/05/05/malware-header.jpg)

Một nhóm mối đe dọa APT liên quan đến Trung Quốc mang tên "TheWizards" đã lạm dụng một tính năng mạng IPv6 để tiến hành các cuộc tấn công adversary-in-the-middle (AitM) nhằm chiếm đoạt cập nhật phần mềm để cài đặt malware Windows.

Theo ESET, nhóm này đã hoạt động ít nhất từ năm 2022, nhắm mục tiêu vào các thực thể tại Philippines, Campuchia, Các Tiểu vương quốc Ả Rập Thống nhất, Trung Quốc và Hong Kong. Nạn nhân bao gồm cá nhân, công ty cá cược và các tổ chức khác.

Các cuộc tấn công sử dụng một công cụ tùy chỉnh gọi là "Spellbinder" do ESET phát triển, lạm dụng tính năng Stateless Address Autoconfiguration (SLAAC) của IPv6 để thực hiện [các cuộc tấn công SLAAC](https://wirewatcher.wordpress.com/2011/04/04/the-slaac-attack-using-ipv6-as-a-weapon-against-ipv4/).

SLAAC là một tính năng của giao thức mạng IPv6 cho phép các thiết bị tự động cấu hình địa chỉ IP và gateway mặc định mà không cần máy chủ DHCP. Thay vào đó, nó sử dụng các tin nhắn Router Advertisement (RA) để nhận địa chỉ IP từ các router hỗ trợ IPv6.

Công cụ Spellbinder của hacker lạm dụng tính năng này bằng cách gửi các tin nhắn RA giả mạo qua mạng, khiến các hệ thống gần đó tự động nhận một địa chỉ IP IPv6 mới, máy chủ DNS mới và một gateway IPv6 ưu tiên mới.

Gateway mặc định này, tuy nhiên, lại là địa chỉ IP của công cụ Spellbinder, cho phép nó chặn các liên lạc và chuyển hướng lưu lượng truy cập qua các máy chủ do kẻ tấn công kiểm soát.

"Spellbinder gửi một gói tin RA multicast mỗi 200 ms đến ff02::1 ("tất cả các nút"); các máy Windows trong mạng với IPv6 được kích hoạt sẽ tự động cấu hình thông qua [stateless address autoconfiguration](https://www.rfc-editor.org/rfc/rfc4862) (SLAAC) sử dụng thông tin được cung cấp trong tin nhắn RA, và bắt đầu gửi lưu lượng IPv6 đến máy đang chạy Spellbinder, nơi các gói tin sẽ bị chặn, phân tích và phản hồi khi cần thiết," ESET giải thích.

![Lạm dụng tính năng IPv6 SLAAC bằng công cụ Spellbinder](https://www.bleepstatic.com/images/news/security/malware/s/spellbinder/figure-4%5B1%5D.png)

**Lạm dụng tính năng IPv6 SLAAC bằng công cụ Spellbinder**  
_Nguồn: ESET_

ESET cho biết các cuộc tấn công triển khai Spellbinder sử dụng một tệp nén có tên AVGApplicationFrameHostS.zip, tách thành một thư mục giả mạo phần mềm hợp pháp: "%PROGRAMFILES%\\AVG Technologies."

Trong thư mục này có các tệp AVGApplicationFrameHost.exe, wsc.dll, log.dat và một bản sao hợp pháp của winpcap.exe. Tệp thực thi WinPcap được sử dụng để tải bên tệp wsc.dll độc hại, cái mà tải Spellbinder vào bộ nhớ.

Khi một thiết bị bị nhiễm, Spellbinder bắt đầu chặn và phân tích lưu lượng mạng cố gắng kết nối với các miền cụ thể, chẳng hạn như các miền liên quan đến máy chủ cập nhật phần mềm Trung Quốc.

ESET tiết lộ rằng malware này theo dõi các miền thuộc về các công ty sau: Tencent, Baidu, Xunlei, Youku, iQIYI, Kingsoft, Mango TV, Funshion, Yuodao, Xiaomi, Xiaomi Miui, PPLive, Meitu, Quihoo 360 và Baofeng.

Công cụ này sau đó chuyển hướng các yêu cầu đó để tải xuống và cài đặt các cập nhật độc hại mà triển khai một backdoor tên là "WizardNet."

Backdoor WizardNet cho phép kẻ tấn công có quyền truy cập liên tục vào thiết bị bị nhiễm và cho phép họ cài đặt thêm malware khi cần thiết.

Để bảo vệ chống lại các loại tấn công này, các tổ chức có thể giám sát lưu lượng IPv6 hoặc tắt giao thức nếu không cần thiết trong môi trường của họ.

Vào tháng Giêng, ESET cũng đã báo cáo về một nhóm hacker khác có tên "Blackwood" [chiếm đoạt tính năng cập nhật phần mềm WPS Office](https://www.bleepingcomputer.com/news/security/blackwood-hackers-hijack-wps-office-update-to-install-malware/) để cài đặt malware.