# Google liên kết thêm các nhóm tin tặc Trung Quốc với các cuộc tấn công React2Shell

![Tin tặc Trung Quốc](https://www.bleepstatic.com/content/hl-images/2025/12/04/Chinese-hackers.jpg)

Trong suốt cuối tuần, nhóm tình báo mối đe dọa của Google đã liên kết thêm năm nhóm tin tặc Trung Quốc nữa với các cuộc tấn công khai thác lỗ hổng thực thi mã từ xa có mức độ nghiêm trọng tối đa "[React2Shell](https://react2shell.com/)".

Được theo dõi là [CVE-2025-55182](https://www.bleepingcomputer.com/news/security/critical-react2shell-flaw-in-react-nextjs-lets-hackers-run-javascript-code/), lỗ hổng đang bị khai thác tích cực này ảnh hưởng đến thư viện JavaScript mã nguồn mở React và cho phép các kẻ tấn công không cần xác thực thực thi mã tùy ý trong các ứng dụng React và Next.js chỉ với một yêu cầu HTTP.

Mặc dù nhiều package của React (tức là react-server-dom-parcel, react-server-dom-turbopack, và react-server-dom-webpack) dễ bị khai thác trong cấu hình mặc định của chúng, lỗ hổng chỉ ảnh hưởng đến các phiên bản React 19.0, 19.1.0, 19.1.1 và 19.2.0 được phát hành trong năm qua.

Sau khi các cuộc tấn công bắt đầu, Palo Alto Networks [đã báo cáo](https://unit42.paloaltonetworks.com/cve-2025-55182-react-and-cve-2025-66478-next/) rằng hàng chục tổ chức đã bị xâm phạm, bao gồm các sự cố liên quan đến các tác nhân được nhà nước Trung Quốc hỗ trợ. Các kẻ tấn công khai thác lỗ hổng để thực thi lệnh và đánh cắp các tệp cấu hình AWS, thông tin xác thực và các thông tin nhạy cảm khác.

Nhóm bảo mật của Amazon Web Services (AWS) [cũng cảnh báo](https://www.bleepingcomputer.com/news/security/react2shell-critical-flaw-actively-exploited-in-china-linked-attacks/) rằng các tác nhân liên quan đến Trung Quốc Earth Lamia và Jackpot Panda đã bắt đầu khai thác React2Shell chỉ trong vài giờ sau khi lỗ hổng được công bố.

## Năm nhóm tin tặc Trung Quốc nữa bị liên kết với các cuộc tấn công

Vào thứ Bảy, Google Threat Intelligence Group (GTIG) báo cáo phát hiện ít nhất thêm năm nhóm gián điệp mạng Trung Quốc tham gia các cuộc tấn công React2Shell đang diễn ra kể từ khi lỗ hổng được tiết lộ [vào ngày 3 tháng 12](https://www.bleepingcomputer.com/news/security/critical-react2shell-flaw-in-react-nextjs-lets-hackers-run-javascript-code/).

Danh sách các nhóm mối đe dọa có liên kết nhà nước khai thác lỗ hổng hiện bao gồm UNC6600 (đã triển khai phần mềm tunneling MINOCAT), UNC6586 (trình tải SNOWLIGHT), UNC6588 (payload backdoor COMPOOD), UNC6603 (phiên bản cập nhật của backdoor HISONIC), và UNC6595 (ANGRYREBEL.LINUX Remote Access Trojan).

"Do việc sử dụng React Server Components (RSC) trong các framework phổ biến như Next.js, có một số lượng đáng kể hệ thống bị phơi nhiễm dễ bị vấn đề này," [các nhà nghiên cứu GTIG cho biết](http://cloud.google.com/blog/topics/threat-intelligence/threat-actors-exploit-react2shell-cve-2025-55182/).

"GTIG cũng đã quan sát thấy nhiều thảo luận liên quan đến CVE-2025-55182 trên các diễn đàn ngầm, bao gồm các chủ đề mà trong đó các tác nhân mối đe dọa chia sẻ liên kết đến công cụ quét, mã proof-of-concept (PoC), và kinh nghiệm của họ khi sử dụng các công cụ này."

Khi điều tra các cuộc tấn công này, GTIG cũng phát hiện các tác nhân liên quan đến Iran nhắm vào lỗ hổng và các kẻ tấn công vì mục đích tài chính đã triển khai phần mềm đào tiền điện tử XMRig trên các hệ thống chưa được vá.

Tổ chức giám sát Internet Shadowserver [hiện đang theo dõi](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=7&source=http%5Fvulnerable&source=http%5Fvulnerable6&tag=cve-2025-55182%2B&dataset=unique%5Fips&limit=100&group%5Fby=tag&stacking=stacked&auto%5Fupdate=on) hơn 116.000 địa chỉ IP dễ bị tấn công bởi React2Shell, với hơn 80.000 trong số đó ở Hoa Kỳ.

![Thiết bị dễ bị tấn công bởi React2Shell](https://www.bleepstatic.com/images/news/u/1109292/2025/Devices%20vulnerable%20to%20React2Shell%20attacks.jpg)

_Thiết bị dễ bị tấn công bởi React2Shell (Shadowserver)_

GreyNoise cũng đã quan sát [hơn 670 địa chỉ IP](https://viz.greynoise.io/query/tags:%22React%20Server%20Components%20Unsafe%20Deserialization%20CVE-2025-55182%20RCE%20Attempt%22%20last%5Fseen:1d) cố gắng khai thác lỗ hổng thực thi mã từ xa React2Shell trong 24 giờ qua, chủ yếu xuất phát từ Hoa Kỳ, Ấn Độ, Pháp, Đức, Hà Lan, Singapore, Nga, Úc, Vương quốc Anh, và Trung Quốc.

Vào ngày 5 tháng 12, Cloudflare liên kết một sự cố gián đoạn trang web toàn cầu với các [biện pháp giảm thiểu khẩn cấp](https://www.bleepingcomputer.com/news/security/cloudflare-blames-todays-outage-on-emergency-react2shell-patch/) cho lỗ hổng React2Shell.