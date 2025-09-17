# Cuộc tấn công chuỗi cung ứng tự lây lan ảnh hưởng đến 187 gói npm

![npm](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM.jpg)

Các nhà nghiên cứu bảo mật đã xác định ít nhất 187 gói npm bị xâm phạm trong một cuộc tấn công chuỗi cung ứng đang diễn ra, với payload độc hại tự lây lan để nhiễm các gói khác.

Chiến dịch kiểu sâu (worm) phối hợp có tên 'Shai-Hulud' bắt đầu ngày hôm qua với việc xâm phạm gói _@ctrl/tinycolor_, gói này nhận hơn 2 triệu lượt tải hàng tuần.

Kể từ đó, chiến dịch đã mở rộng đáng kể và hiện bao gồm các gói được xuất bản dưới namespace npm của CrowdStrike.

## Từ _tinycolor_ đến CrowdStrike

Hôm qua, Daniel Pereira, một kỹ sư phần mềm backend cấp cao, đã [cảnh báo](https://www.linkedin.com/posts/daniel-pereira-b17a27160%5Fnpm-profile-activity-7373489836437114880-D9ma?utm%5Fsource=share&utm%5Fmedium=member%5Fdesktop&rcm=ACoAAArUYTQBMx2P2SMFdIx-wUs7H1hfLGpuhVM) cộng đồng về một cuộc tấn công chuỗi cung ứng phần mềm quy mô lớn đang ảnh hưởng tới registry JavaScript lớn nhất thế giới, npmjs.com.

"Có một [sic] malware đang lây lan trên npm khi bạn đang đọc bài này," kỹ sư viết, cảnh báo mọi người không cài đặt các phiên bản mới nhất của dự án _[@ctrl/tinycolor](https://www.npmjs.com/package/@ctrl/tinycolor)_.

![Pereira's LinkedIn post alerting everyone to ongoing npm supply chain attack](https://www.bleepstatic.com/images/news/u/1164866/2025/Sep/npm-supply-chain-attack-crowdstrike/dan-p-post.jpg)

**Pereira cảnh báo mọi người về cuộc tấn công chuỗi cung ứng npm đang diễn ra**

Pereira đã cố gắng [liên hệ](http://linkedin.com/feed/update/urn:li:activity:7373418115398995968/) với GitHub trong 24 giờ qua thông qua các kênh thầm lặng hơn để thảo luận về cuộc tấn công đang diễn ra vì "rất nhiều repo đã bị nhắm tới," và việc công bố công khai có thể đặt mọi người vào rủi ro.

"Nhưng liên hệ với GitHub quá khó. Ví dụ, các bí mật đang bị lộ trong các repo. Việc này rất nghiêm trọng," kỹ sư viết.

Công ty an ninh chuỗi cung ứng phần mềm Socket [bắt đầu điều tra việc xâm phạm](https://socket.dev/blog/tinycolor-supply-chain-attack-affects-40-packages) và xác định ít nhất 40 gói bị xâm phạm trong chiến dịch này. Hôm nay, cả các nhà nghiên cứu của Socket và Aikido đã [xác định thêm các gói](http://www.aikido.dev/blog/s1ngularity-nx-attackers-strike-again#:~:text=publishing%20rights.-,Impacted%20packages,-Package), đưa tổng số lên ít nhất 187.

StepSecurity [cũng đã công bố](https://www.stepsecurity.io/blog/ctrl-tinycolor-and-40-npm-packages-compromised) phân tích kỹ thuật với các đoạn mã đã giải mờ và sơ đồ luồng tấn công, phần lớn xác nhận các phát hiện ban đầu của Socket.

Các gói bị ảnh hưởng bao gồm một số gói được xuất bản bởi tài khoản npmjs của CrowdStrike _[crowdstrike-publisher](https://www.npmjs.com/~crowdstrike-publisher)_.

BleepingComputer đã liên hệ với nhà cung cấp giải pháp an ninh mạng để bình luận:

"Sau khi phát hiện một số gói Node Package Manager (NPM) độc hại trong registry NPM công cộng, một kho mã nguồn mở bên thứ ba, chúng tôi đã nhanh chóng xóa chúng và chủ động xoay vòng các khóa của mình trong các registry công cộng," một phát ngôn viên của CrowdStrike chia sẻ với BleepingComputer.  
  
"Những gói này không được sử dụng trong Falcon sensor, nền tảng không bị ảnh hưởng và khách hàng vẫn được bảo vệ. Chúng tôi đang làm việc với NPM và tiến hành điều tra kỹ lưỡng."

## Sâu tự lây lan sử dụng TruffleHog để đánh cắp bí mật

Các phiên bản bị xâm phạm bao gồm một cơ chế tự lây lan nhằm nhắm mục tiêu các gói khác cùng người duy trì.

Malware tải xuống từng gói theo tên người duy trì, sửa đổi _package.json_, tiêm một script _bundle.js_ (hiển thị bên dưới), đóng gói lại kho lưu trữ, và xuất bản lại nó, do đó "cho phép tự động trojan hóa các gói hạ nguồn," như các nhà nghiên cứu của Socket giải thích.

![bundle.js file uses TruffleHog to exfiltrate secrets ](https://www.bleepstatic.com/images/news/u/1164866/2025/Sep/npm-supply-chain-attack-crowdstrike/socket-bundle_js-file.jpg)

**bundle.js file downloads TruffleHog to exfiltrate secrets** (Socket)

Script _bundle.js_ sử dụng TruffleHog, một công cụ quét bí mật hợp pháp có thể được các nhà phát triển và chuyên gia bảo mật dùng để tìm thông tin nhạy cảm vô tình bị rò rỉ như API key, mật khẩu và token trong repo mã nguồn và các nguồn dữ liệu khác.

Tuy nhiên, script độc hại lợi dụng công cụ này để dò tìm token và thông tin xác thực đám mây trên host.

"Nó xác thực và sử dụng các credential của nhà phát triển và CI, tạo một workflow GitHub Actions bên trong các repository, và gửi trộm kết quả đến một webhook được mã hóa cứng (hxxps://webhook[.]site/bb8ca5f6-4175-45d2-b042-fc9ebb8170b7)," giải thích Socket.

Tên 'Shai-Hulud' xuất phát từ các file workflow _shai-hulud.yaml_ được malware dùng trong các phiên bản bị xâm phạm, và là tham chiếu đến những con sâu cát khổng lồ trong series [_Dune_](https://en.wikipedia.org/wiki/Sandworm%5F%28Dune%29) của Frank Herbert.

"Mặc dù không phải là một tham chiếu độc đáo, sự hiện diện của nó củng cố rằng kẻ tấn công đã cố ý gán tên chiến dịch 'Shai-Hulud,'" các nhà nghiên cứu của Socket Kush Pandya và Peter van der Zee [nêu rõ](https://socket.dev/blog/ongoing-supply-chain-attack-targets-crowdstrike-npm-packages) hôm nay.

Malware được tìm thấy trong các gói bổ sung được xác định hôm nay giống hệt với chuỗi trước đó sử dụng _bundle.js_ để:

* Tải xuống và thực thi công cụ quét bí mật hợp pháp, TruffleHog
* Tìm kiếm trên host các bí mật như token và thông tin xác thực đám mây
* Kiểm tra xem các credential nhà phát triển và CI được phát hiện có hợp lệ hay không
* Tạo các workflow GitHub Actions trái phép trong các repository
* Lấy cắp dữ liệu nhạy cảm và gửi ra tới một endpoint webhook được mã hóa cứng

## Sự cố tiếp nối các cuộc tấn công quy mô lớn đang diễn ra như nx 's1ngularity'

Điều làm cho cuộc tấn công chuỗi cung ứng này nổi bật, ngoài các gói phổ biến mà nó tấn công, là thời điểm xảy ra.

Cuộc tấn công nối tiếp hai vụ tấn công chuỗi cung ứng có tiếng vang cao xảy ra trong cùng tháng.

Tuần đầu tháng Chín, malware sử dụng AI đã [tấn công 2.180 tài khoản GitHub](https://www.bleepingcomputer.com/news/security/ai-powered-malware-hit-2-180-github-accounts-in-s1ngularity-attack/) trong cái gọi là cuộc tấn công 's1ngularity'.

Trong khi nguyên nhân gốc rễ của cuộc tấn công hôm nay vẫn đang được điều tra, các thực hành viên, bao gồm Pereira, giả thuyết rằng cuộc tấn công hôm nay có thể do những kẻ tấn công đứng sau 's1ngularity' điều phối.

Đầu tháng này, các người duy trì của các gói npm phổ biến [chalk and debug](https://www.bleepingcomputer.com/news/security/hackers-hijack-npm-packages-with-2-billion-weekly-downloads-in-supply-chain-attack/) cũng trở thành nạn nhân của phishing trong một vụ tấn công riêng biệt, dẫn đến việc dự án của họ bị xâm phạm.

Hiệu ứng lan tỏa của những cuộc tấn công này kéo sâu vào chuỗi phụ thuộc, có khả năng ảnh hưởng đến các dự án được sử dụng rộng rãi như Google Gemini CLI, mà [đã phát hành một tuyên bố](https://github.com/google-gemini/gemini-cli/discussions/8385) trong cuối tuần:

"Chúng tôi muốn làm rõ: Mã nguồn của Gemini CLI bản thân nó không bị xâm phạm, và máy chủ của chúng tôi vẫn an toàn," Ryan J. Salva, Senior Director of Product Management của Google, viết.

"Tuy nhiên, sự cố này có thể đã ảnh hưởng đến người dùng đã cài đặt hoặc cập nhật Gemini CLI trong cửa sổ tấn công bằng phương pháp cài đặt NPM. Chúng tôi đang cung cấp chi tiết về sự cố, làm rõ ai bị ảnh hưởng, và nêu các bước người dùng nên thực hiện để đảm bảo hệ thống của họ an toàn."

Những cuộc tấn công đang diễn ra này cho thấy sự mong manh của chuỗi cung ứng phần mềm hiện đại, nơi một pull request độc hại hoặc tài khoản người duy trì bị xâm phạm có thể lan rộng đến hàng trăm dự án.

Trong khi các nhà cung cấp như Google và CrowdStrike nhấn mạnh nền tảng cốt lõi của họ vẫn an toàn, sự cố này nhấn mạnh nhu cầu cấp bách cho các nhà phát triển trong việc bảo vệ các bản build phần mềm và pipeline của họ.

Người dùng bị ảnh hưởng nên kiểm tra môi trường và log để tìm dấu hiệu bị xâm phạm, xoay vòng tất cả bí mật và token CI/CD, và xem xét cây phụ thuộc để phát hiện các phiên bản độc hại. Khóa chặt (pin) các phụ thuộc vào các bản phát hành đáng tin cậy và giới hạn phạm vi quyền xuất bản vẫn là các bước quan trọng để giảm rủi ro bị xâm phạm ở cấp gói.