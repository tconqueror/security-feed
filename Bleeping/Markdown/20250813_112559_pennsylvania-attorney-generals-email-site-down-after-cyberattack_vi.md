# Email của tổng chưởng lý Pennsylvania, trang web ngừng hoạt động sau cuộc tấn công mạng

![Tổng Chưởng lý Pennsylvania Dave Sunday](https://www.bleepstatic.com/content/hl-images/2025/08/13/Pennsylvania_Attorney_General_Dave_Sunday.jpg)

Văn phòng Tổng chưởng lý Pennsylvania đã thông báo rằng một cuộc tấn công mạng gần đây đã làm ngưng hoạt động các hệ thống của họ, bao gồm cả đường dây điện thoại đất và tài khoản email.

Như Tổng chưởng lý Dave Sunday tiết lộ trên mạng xã hội vào thứ Hai, nhân viên văn phòng hiện đang làm việc để khôi phục các dịch vụ bị ảnh hưởng và điều tra sự việc với sự giúp đỡ của các cơ quan thực thi pháp luật.

"Mạng lưới hiện đang lưu trữ hệ thống của Văn phòng Tổng Chưởng lý hiện đang bị ngưng hoạt động, có nghĩa là trang web của văn phòng không online, cũng như các tài khoản email của văn phòng và đường dây điện thoại cố định," [Sunday cho biết](https://www.facebook.com/PaAttorneyGen/posts/1334533431364939).

"Chúng tôi đang thực hiện các bước để xác định nguyên nhân của sự cố mạng, và làm việc để khôi phục các dịch vụ trên tất cả các kênh. Nhân viên Văn phòng Tổng Chưởng lý đang tiếp tục làm việc vì lợi ích của Khối thịnh vượng chung và phối hợp với các giám sát viên để giảm thiểu mọi gián đoạn."

Tổng chưởng lý Pennsylvania vẫn chưa chính thức xác định nhóm nào đứng sau cuộc tấn công. Tuy nhiên, ảnh hưởng rộng rãi và nghiêm trọng của sự cố này mang đầy đủ dấu hiệu của một cuộc tấn công ransomware, mặc dù chưa có hoạt động ransomware nào nhận trách nhiệm cho đến nay.

Trong khi các nhân viên ứng phó sự cố tiếp tục làm việc để khôi phục các hệ thống bị ảnh hưởng, [trang web của Tổng chưởng lý Pennsylvania](https://www.attorneygeneral.gov/) vẫn ngoại tuyến vào thời điểm bài viết này được xuất bản.

![Trang web Tổng chưởng lý Pennsylvania ngừng hoạt động](https://www.bleepstatic.com/images/news/u/1109292/2025/PA%20OAG%20site.png)

_Trang web của văn phòng Tổng chưởng lý Pennsylvania (BleepingComputer)_

Mặc dù vector tấn công vẫn chưa biết, [chuyên gia an ninh mạng Kevin Beaumont đã phát hiện,](https://cyberplace.social/@GossiTheDog/114852498783201767) một tháng trước, rằng một số thiết bị Citrix NetScaler có mặt công cộng trên mạng của AG Pennsylvania bị dễ bị tấn công do khai thác một lỗ hổng nghiêm trọng được theo dõi là CVE-2025-5777 (còn được biết đến là [Citrix Bleed 2](https://www.bleepingcomputer.com/tag/citrixbleed2/)).

Theo các quét Shodan được chia sẻ bởi Beaumont, một trong hai thiết bị [đã ngoại tuyến kể từ ngày 29 tháng 7](https://beta.shodan.io/host/207.218.103.19), trong khi thiết bị còn lại [đã bị ngưng hoạt động vào ngày 7 tháng 8](https://beta.shodan.io/host/207.218.103.174).

Vào thứ Hai, tổ chức phi lợi nhuận về bảo mật internet Shadowserver Foundation [đã báo cáo](https://bsky.app/profile/shadowserver.bsky.social/post/3lw6z7psrbs2u) rằng hơn 3.300 thiết bị Citrix NetScaler vẫn đang dễ bị tấn công bởi lỗ hổng CVE-2025-5777.

Cùng ngày, Trung tâm An ninh mạng Quốc gia Hà Lan (NCSC) [cảnh báo](https://www.bleepingcomputer.com/news/security/netherlands-citrix-netscaler-flaw-cve-2025-6543-exploited-to-breach-orgs/) rằng những kẻ tấn công đã khai thác lỗ hổng này như một lỗ hổng zero-day từ ít nhất đầu tháng 5 để xâm nhập nhiều tổ chức quan trọng trong nước.

Openbaar Ministerie (Dịch vụ Công tố Công cộng Hà Lan), chỉ [gần đây](http://www.om.nl/onderwerpen/inbreuk-om-ict/nieuws/2025/08/04/om-gaat-stapsgewijs-online) đã khôi phục [các máy chủ email](http://www.om.nl/onderwerpen/inbreuk-om-ict/nieuws/2025/08/07/om-is-weer-per-mail-bereikbaar), cũng [công bố một vụ xâm phạm](https://www.om.nl/onderwerpen/inbreuk-om-ict/nieuws/2025/07/18/onderzoek-naar-aanleiding-van-signaal-ncsc) vào ngày 18 tháng 7 dẫn đến [gián đoạn hoạt động đáng kể](http://www.om.nl/onderwerpen/inbreuk-om-ict/nieuws/2025/07/21/werk-om-mogelijk-komende-weken-nog-verstoord).

CISA đã đưa lỗ hổng Citrix CVE-2025-5777 vào danh mục các lỗ hổng đã được khai thác, [ra lệnh cho các cơ quan liên bang vá hệ thống của họ](http://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-5777&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=) chống lại khai thác đang hoạt động trong vòng một ngày.