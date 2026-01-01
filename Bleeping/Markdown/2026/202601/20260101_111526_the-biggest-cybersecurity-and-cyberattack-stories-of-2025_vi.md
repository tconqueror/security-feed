# Những câu chuyện lớn nhất về an ninh mạng và các cuộc tấn công mạng năm 2025

![2025](https://www.bleepstatic.com/content/hl-images/2025/12/30/2025.jpg)

Năm 2025 là một năm lớn đối với an ninh mạng, với các cuộc tấn công mạng lớn, rò rỉ dữ liệu, các nhóm mối đe dọa trở nên nổi tiếng hơn, và, tất nhiên, các lỗ hổng zero-day bị khai thác trong các sự cố.

Tuy nhiên, một số câu chuyện có tác động hoặc được độc giả quan tâm nhiều hơn những câu khác.

Dưới đây là mười lăm chủ đề mà BleepingComputer cho là có ảnh hưởng lớn nhất trong lĩnh vực an ninh mạng năm 2025, kèm tóm tắt cho từng chủ đề. Các câu chuyện này không theo thứ tự ưu tiên nào.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

### 15. [Vụ rò rỉ dữ liệu PornHub](https://www.bleepingcomputer.com/news/security/pornhub-extorted-after-hackers-steal-premium-member-activity-data/)

Nhóm tống tiền ShinyHunters đang tống tiền PornHub sau khi [đánh cắp dữ liệu hoạt động thành viên Premium của công ty](https://www.bleepingcomputer.com/news/security/pornhub-extorted-after-hackers-steal-premium-member-activity-data/) từ nhà cung cấp phân tích bên thứ ba Mixpanel.

Kẻ tấn công tuyên bố đã đánh cắp khoảng 94 GB dữ liệu chứa hơn 200 triệu bản ghi về hoạt động xem, tìm kiếm và tải xuống của người đăng ký. Họ đe dọa sẽ công bố dữ liệu trừ khi yêu cầu tống tiền được đáp ứng.

Mặc dù vụ rò rỉ không bao gồm thông tin tài chính, việc công khai chi tiết về hoạt động xem nội dung người lớn có thể gây hậu quả lớn về mặt cá nhân và uy tín cho người dùng bị ảnh hưởng.

Những tiết lộ tương tự trong các sự cố trước đây liên quan dữ liệu nhạy cảm về mối quan hệ, chẳng hạn như [vụ rò rỉ Ashley Madison](https://www.wired.com/2015/08/happened-hackers-posted-stolen-ashley-madison-data/), đã [được liên hệ với các tác hại ngoài đời thực](https://www.bbc.com/news/technology-34044506).

### 14. [Các cuộc tấn công Social Engineering kiểu ClickFix](https://www.bleepingcomputer.com/tag/clickfix/)

Năm 2025, các cuộc tấn công ClickFix được nhiều tác nhân đe dọa áp dụng rộng rãi, bao gồm cả [nhóm tin tặc được nhà nước hậu thuẫn](https://www.bleepingcomputer.com/news/security/state-sponsored-hackers-embrace-clickfix-social-engineering-tactic/) và [băng đảng ransomware](https://www.bleepingcomputer.com/news/security/interlock-ransomware-gang-pushes-fake-it-tools-in-clickfix-attacks/). Bắt đầu như một chiến dịch malware trên Windows, nhanh chóng mở rộng sang macOS và Linux, với các cuộc tấn công cài đặt infostealer, RAT và các malware khác.

Các cuộc tấn công ClickFix là các trang web xã hội kỹ thuật được thiết kế để hiển thị một lỗi hoặc sự cố rồi đưa ra "sửa lỗi" để khắc phục. Những lỗi này có thể là thông báo lỗi giả, cảnh báo bảo mật, thử thách CAPTCHA, hoặc thông báo cập nhật hướng dẫn người truy cập chạy PowerShell hoặc lệnh shell để khắc phục.

Nạn nhân tự lây nhiễm cho máy của mình bằng cách chạy các lệnh PowerShell hoặc shell độc hại theo hướng dẫn của kẻ tấn công.

Chiến dịch ClickFix sử dụng nhiều chiêu dụ, bao gồm [màn hình Windows Update giả](https://www.bleepingcomputer.com/news/security/clickfix-attack-uses-fake-windows-update-screen-to-push-malware/), [video kích hoạt phần mềm giả trên TikTok](https://www.bleepingcomputer.com/news/security/tiktok-videos-now-push-infostealer-malware-in-clickfix-attacks/), và các thử thách [CAPTCHA giả có hướng dẫn bằng video](https://www.bleepingcomputer.com/news/security/clickfix-malware-attacks-evolve-with-multi-os-support-video-tutorials/) chỉ dẫn nạn nhân sao chép và dán các lệnh để tải về và thực thi malware.

![ClickFix attack showing a fake Windows Update screen](https://www.bleepstatic.com/images/news/u/1100723/ClickFix_attack.png)

**ClickFix attack showing a fake Windows Update screen**

Các nhà nghiên cứu quan sát [biến thể ClickFix nhắm mục tiêu macOS](https://www.bleepingcomputer.com/news/security/fake-mac-fixes-trick-users-into-installing-new-shamos-infostealer/) lừa nạn nhân chạy lệnh shell độc hại trong Terminal để cài đặt infostealer. Người dùng Linux cũng không tránh khỏi, với một [chiến dịch APT36 phishing](https://www.bleepingcomputer.com/news/security/hackers-now-testing-clickfix-attacks-against-linux-targets/) nhắm thẳng vào họ.

Các cuộc tấn công ClickFix tiếp tục phát triển trong suốt năm, với các nhà nghiên cứu và tác nhân đe dọa tạo ra các biến thể mới của chiêu xã hội kỹ thuật này.

Một biến thể mới được phát hiện có tên ConsentFix [hijacks Microsoft accounts bằng cách lợi dụng Azure CLI OAuth flow](https://www.bleepingcomputer.com/news/security/new-consentfix-attack-hijacks-microsoft-accounts-via-azure-cli/), lừa nạn nhân hoàn tất quy trình chấp thuận OAuth để thu được access token. Một biến thể khác là FileFix [lợi dụng thanh địa chỉ Windows File Explorer để lừa người dùng thực thi lệnh PowerShell độc hại](https://www.bleepingcomputer.com/news/security/filefix-attack-weaponizes-windows-file-explorer-for-stealthy-powershell-commands/).

Trong tháng này, các cuộc tấn công ClickFix còn được thương mại hóa hơn nữa với một [nền tảng 'ErrTraffic' trả phí mới](https://www.bleepingcomputer.com/news/security/new-errtraffic-service-enables-clickfix-attacks-via-fake-browser-glitches/) giúp tự động hóa việc phát tán các cuộc tấn công malware dựa trên ClickFix.

### 13. [Vụ trộm tiền điện tử $1,5 tỷ ở ByBit](https://www.bleepingcomputer.com/news/security/hacker-steals-record-146-billion-from-bybit-eth-cold-wallet/)

Trong một trong những vụ trộm tiền điện tử lớn nhất từng được ghi nhận, [kẻ tấn công đã lấy khoảng $1,5 tỷ bằng Ethereum](https://www.bleepingcomputer.com/news/security/hacker-steals-record-146-billion-from-bybit-eth-cold-wallet/) từ cold wallet của ByBit vào tháng Hai.

Một cuộc điều tra [liên kết vụ trộm với nhóm Lazarus của Bắc Triều Tiên](https://www.bleepingcomputer.com/news/security/north-korean-hackers-linked-to-15-billion-bybit-crypto-heist/), và [FBI sau đó xác nhận](https://www.bleepingcomputer.com/news/security/fbi-confirms-lazarus-hackers-were-behind-15b-bybit-crypto-heist/) nhóm chịu trách nhiệm vụ tấn công. Các nhà nghiên cứu xác định rằng vụ xâm nhập được thực hiện thông qua một [máy tính của nhà phát triển bị xâm nhập](https://www.bleepingcomputer.com/news/security/lazarus-hacked-bybit-via-breached-safe-wallet-developer-machine/) thuộc về một nhà phát triển Safe{Wallet}, vốn được sử dụng trong hoạt động ví của Bybit.

Kẻ tấn công dùng quyền truy cập vào thiết bị nhà phát triển để thao túng phê duyệt giao dịch, cho phép họ rút sạch cold wallet.

Ngoài Bybit, các vụ trộm tiền điện tử khác nhằm vào sàn giao dịch và ví gồm một vụ [$85 triệu ở Phemex](https://www.bleepingcomputer.com/news/security/hackers-steal-85-million-worth-of-cryptocurrency-from-phemex/), vụ [$223 triệu ở Cetus Protocol](https://www.bleepingcomputer.com/news/security/hacker-steals-223-million-in-cetus-protocol-cryptocurrency-heist/), vụ [$27 triệu ở BigONE](https://www.bleepingcomputer.com/news/security/hacker-steals-27-million-in-bigone-exchange-crypto-breach/), và một cuộc tấn công [$7 triệu ảnh hưởng đến hàng nghìn người dùng Trust Wallet](https://www.bleepingcomputer.com/news/security/trust-wallet-says-7-million-crypto-theft-attack-drained-2-596-wallets/).

Trong một sự cố nổi bật khác, [các hacker ủng hộ Israel đã xâm nhập sàn Nobitex của Iran](https://www.bleepingcomputer.com/news/security/pro-israel-hackers-hit-irans-nobitex-exchange-burn-90m-in-crypto/) và "đốt" khoảng $90 triệu tiền điện tử.

### 12. [Các cuộc tấn công đánh cắp dữ liệu Oracle](https://www.bleepingcomputer.com/news/security/clop-extortion-emails-claim-theft-of-oracle-e-business-suite-data/)

Oracle bị nhắm mục tiêu trong một [chiến dịch đánh cắp dữ liệu lớn](https://www.bleepingcomputer.com/news/security/clop-extortion-emails-claim-theft-of-oracle-e-business-suite-data/) sau khi nhóm tống tiền Clop [khai thác nhiều lỗ hổng zero-day](https://www.bleepingcomputer.com/news/security/oracle-silently-fixes-zero-day-exploit-leaked-by-shinyhunters/) trong Oracle E-Business Suite (EBS).

Clop khai thác một lỗ hổng zero-day chưa được vá trong Oracle E-Business Suite, được theo dõi là CVE-2025-61882, để xâm nhập máy chủ và đánh cắp dữ liệu. Theo CrowdStrike và Mandiant, việc khai thác bắt đầu sớm nhất từ tháng Bảy, với hành vi đánh cắp dữ liệu lên đỉnh điểm vào tháng Tám.

Vào tháng Mười, nhóm tống tiền Clop bắt đầu gửi email cho các doanh nghiệp bị ảnh hưởng, cảnh báo rằng dữ liệu sẽ bị rò rỉ nếu không trả tiền chuộc.

**Clop extortion email sent to Oracle E-Business Suite customers**

Một lỗ hổng zero-day Oracle thứ hai được theo dõi là CVE-2025-61884 đã được tiết lộ sau khi nhóm ShinyHunters rò rỉ PoC exploit trên Telegram. Oracle [lặng lẽ sửa lỗi này](https://www.bleepingcomputer.com/news/security/oracle-silently-fixes-zero-day-exploit-leaked-by-shinyhunters/), nhưng vẫn chưa rõ liệu ShinyHunters có dùng thành công lỗ hổng này để đánh cắp dữ liệu hay không.

Các tổ chức công bố các cuộc tấn công Oracle liên quan Clop bao gồm [Harvard University](https://www.bleepingcomputer.com/news/security/harvard-investigating-breach-linked-to-oracle-zero-day-exploit/), [Dartmouth College](https://www.bleepingcomputer.com/news/security/dartmouth-college-confirms-data-breach-after-clop-extortion-attack/), [University of Pennsylvania](https://www.bleepingcomputer.com/news/security/university-of-pennsylvania-confirms-data-theft-after-oracle-ebs-hack/), [University of Phoenix](https://www.bleepingcomputer.com/news/security/university-of-phoenix-data-breach-impacts-nearly-35-million-individuals/), [Logitech](https://www.bleepingcomputer.com/news/security/logitech-confirms-data-breach-after-clop-extortion-attack/), [GlobalLogic](https://www.bleepingcomputer.com/news/security/globallogic-warns-10-000-employees-of-data-theft-after-oracle-breach/), [Korean Air](https://www.bleepingcomputer.com/news/security/korean-air-data-breach-exposes-data-of-thousands-of-employees/), và [Envoy](https://www.bleepingcomputer.com/news/security/american-airlines-subsidiary-envoy-confirms-oracle-data-theft-attack/).

### 11. [Sức mạnh của các cuộc tấn công DDoS tăng lên](https://www.bleepingcomputer.com/news/security/aisuru-botnet-behind-new-record-breaking-297-tbps-ddos-attack/)

Năm 2025 chứng kiến các cuộc tấn công từ chối dịch vụ phân tán (DDoS) phá kỷ lục nhắm vào các tổ chức trên toàn cầu.

Nhiều sự cố được Cloudflare giảm nhẹ cho thấy sức mạnh ngày càng tăng của các nền tảng DDoS, với các cuộc tấn công đạt đỉnh ở [5.6 Tbps](https://www.bleepingcomputer.com/news/security/cloudflare-mitigated-a-record-breaking-56-tbps-ddos-attack/), [7.3 Tbps](https://www.bleepingcomputer.com/news/security/cloudflare-blocks-record-73-tbps-ddos-attack-against-hosting-provider/), [11.5 Tbps](https://www.bleepingcomputer.com/news/security/cloudflare-blocks-record-breaking-115-tbps-ddos-attack/), và sau đó là [22.2 Tbps](https://www.bleepingcomputer.com/news/security/cloudflare-mitigates-new-record-breaking-222-tbps-ddos-attack/).

Sự gia tăng này phần lớn được [quy cho botnet Aisuru](https://www.bleepingcomputer.com/news/security/aisuru-botnet-behind-new-record-breaking-297-tbps-ddos-attack/), vốn nổi lên như một lực lượng đáng kể đứng sau một số cuộc tấn công DDoS lớn nhất từng được ghi nhận.

Microsoft báo cáo rằng Aisuru đã lợi dụng hơn 500.000 địa chỉ IP trong một cuộc tấn công 15 Tbps nhắm vào Azure, với Cloudflare sau đó báo cáo botnet này chịu trách nhiệm cho một cuộc tấn công DDoS lớn hơn 29.7 Tbps.

**Graph from the record-breaking Aisuru attack**  
_Source: Cloudflare_

Trong vài năm gần đây, các hoạt động DDoS đã trở thành mục tiêu của các cơ quan thực thi pháp luật toàn cầu. Năm 2025, cơ quan chức năng đã tiến hành [triệt phá nhiều dịch vụ DDoS-for-hire](https://www.bleepingcomputer.com/news/security/police-takes-down-six-ddos-for-hire-services-arrests-admins/), bắt giữ các quản trị viên điều hành các nền tảng này.

Europol cũng thông báo [phá vỡ nhóm hacktivist ủng hộ Nga NoName057(16)](https://www.bleepingcomputer.com/news/security/europol-disrupts-pro-russian-noname05716-ddos-hacktivist-group/), nhóm từng liên quan đến các chiến dịch DDoS trước đây.

### 10. [Tăng cường tấn công chuỗi cung ứng hướng tới nhà phát triển](https://www.bleepingcomputer.com/news/security/shai-hulud-20-npm-malware-attack-exposed-up-to-400-000-dev-secrets/)

Tội phạm mạng ngày càng nhắm vào nhà phát triển bằng cách lạm dụng các kho gói mã nguồn mở và kho extension, biến chúng thành nơi phân phối malware.

Trên npm, kẻ tấn công nhiều lần cho thấy nền tảng có thể bị lạm dụng để đẩy các gói độc hại.

Chiến dịch [IndonesianFoods](https://www.bleepingcomputer.com/news/security/new-indonesianfoods-spammer-floods-npm-with-150-000-packages/) đã tràn ngập npm với hàng trăm nghìn gói spam và độc hại. Các cuộc tấn công chuỗi cung ứng nhắm mục tiêu hơn đã chiếm quyền các gói hợp pháp có [hàng triệu lượt tải hàng tuần](https://www.bleepingcomputer.com/news/security/hackers-hijack-npm-packages-with-2-billion-weekly-downloads-in-supply-chain-attack/).

Một trong những nỗ lực gây hại nhất là chiến dịch malware [Shai-Hulud](https://www.bleepingcomputer.com/news/security/shai-hulud-20-npm-malware-attack-exposed-up-to-400-000-dev-secrets/), đã nhiễm hàng trăm gói npm và được dùng để đánh cắp bí mật của nhà phát triển và API key.

**GitHub repositories with secrets stolen in the new Shai-Hulud campaign**

Kẻ tấn công cũng nhiều lần nhắm vào chợ extension cho IDE, như [VSCode Marketplace của Microsoft](https://www.bleepingcomputer.com/news/security/malicious-vscode-extensions-on-microsofts-registry-drop-infostealers/) và [OpenVSX](https://www.bleepingcomputer.com/news/security/malicious-crypto-stealing-vscode-extensions-resurface-on-openvsx/).

Một chiến dịch gọi là [Glassworm](https://www.bleepingcomputer.com/news/security/glassworm-malware-returns-on-openvsx-with-3-new-vscode-extensions/) tái xuất nhiều lần, sử dụng extension VSCode để phát tán malware, đánh cắp tiền điện tử, cài cryptominer và tải xuống các payload bổ sung, bao gồm ransomware giai đoạn sớm.

Python Package Index (PyPi) cũng bị nhắm mục tiêu, với các [gói PyPi độc hại](https://www.bleepingcomputer.com/news/security/pypi-invalidates-tokens-stolen-in-ghostaction-supply-chain-attack/) và các [chiến dịch phishing](https://www.bleepingcomputer.com/news/security/hackers-target-python-devs-in-phishing-attacks-using-fake-pypi-site/) đánh cắp thông tin đăng nhập đám mây hoặc cắm backdoor vào hệ thống nhà phát triển. Điều này buộc PyPI phải giới thiệu [các biện pháp kiểm soát mới để hạn chế cập nhật độc hại](https://www.bleepingcomputer.com/news/security/pypi-adds-project-archiving-system-to-stop-malicious-updates/).

### 9. [Công nhân IT Triều Tiên](https://www.bleepingcomputer.com/news/security/north-korea-lures-engineers-to-rent-identities-in-fake-it-worker-scheme/)

Năm 2025, việc công nhân IT Triều Tiên xâm nhập các công ty phương Tây trở thành một mối đe dọa danh tính lớn đối với các tổ chức.

Chính phủ Hoa Kỳ cho biết những công nhân này chuyển thu nhập của họ về chế độ DPRK để tài trợ cho chương trình vũ khí và các sáng kiến khác.

Thay vì lợi dụng lỗ hổng phần mềm, các đối tượng Triều Tiên ngày càng sử dụng danh tính giả, trung gian và việc làm hợp pháp để tiếp cận các công ty phương Tây, thường không bị phát hiện trong thời gian dài.

Các cơ quan Hoa Kỳ [phát hiện các hoạt động "laptop farm"](https://www.bleepingcomputer.com/news/security/us-disrupts-north-korean-it-worker-laptop-farm-scheme-in-16-states/) trên ít nhất 16 bang, nơi người giúp đỡ địa phương nhận laptop do công ty cấp thay cho công nhân Triều Tiên và cho phép truy cập từ xa vào môi trường doanh nghiệp từ Triều Tiên.

Điều tra cũng tiết lộ các chiến dịch [tuyển dụng kỹ sư để cho thuê hoặc bán danh tính](https://www.bleepingcomputer.com/news/security/north-korea-lures-engineers-to-rent-identities-in-fake-it-worker-scheme/), cho phép đặc vụ vượt qua kiểm tra lý lịch, nhận việc và truy cập hệ thống nội bộ dưới danh tính giả. Năm cá nhân [sau đó nhận tội](https://www.bleepingcomputer.com/news/security/five-plead-guilty-to-helping-north-koreans-infiltrate-us-firms/) vì giúp tạo điều kiện cho các kế hoạch này.

Bộ Tài chính Hoa Kỳ đã ban hành nhiều [lệnh trừng phạt](https://www.bleepingcomputer.com/news/security/us-treasury-sanctions-north-korean-bankers-linked-to-cybercrime-it-worker-fraud/) vào năm 2025 nhắm vào [cá nhân Triều Tiên](https://www.bleepingcomputer.com/news/legal/treasury-sanctions-north-korean-over-it-worker-malware-scheme/), [công ty bình phong](https://www.bleepingcomputer.com/news/security/us-sanctions-north-korean-firm-nationals-behind-it-worker-schemes/), và [ngân hàng] liên quan đến các kế hoạch công nhân IT.

Mặc dù không trực tiếp liên quan đến kế hoạch công nhân IT Triều Tiên, năm 2025 cũng chứng kiến gia tăng các chiến dịch "Contagious Interview" lạm dụng quy trình tuyển dụng và phỏng vấn làm cơ chế phân phối malware.

Trong một chiến dịch, hacker Triều Tiên dùng [deepfake Zoom giả mạo giám đốc điều hành công ty](https://www.bleepingcomputer.com/news/security/north-korean-hackers-deepfake-execs-in-zoom-call-to-spread-mac-malware/) để lừa mục tiêu cài macOS malware. Trong một vụ khác, kẻ tấn công lạm dụng phỏng vấn kỹ thuật giả để phát tán malware thông qua các [gói npm độc hại được nhà phát triển cài đặt](https://www.bleepingcomputer.com/news/security/new-wave-of-fake-interviews-use-35-npm-packages-to-spread-malware/) như một phần của "bài kiểm tra".

### 8. [Các cuộc tấn công Salt Typhoon nhắm vào viễn thông tiếp tục](https://www.bleepingcomputer.com/tag/salt-typhoon/)

Lần đầu [bị công bố vào năm 2024](https://www.bleepingcomputer.com/news/security/us-says-chinese-hackers-breached-multiple-telecom-providers/), các cuộc tấn công Salt Typhoon tiếp tục kéo dài trong năm 2025, trở thành một trong những chiến dịch gián điệp mạng gây thiệt hại lớn nhất nhắm vào hạ tầng viễn thông toàn cầu.

Các cuộc tấn công được liên kết với các tác nhân thân Nhà nước Trung Quốc được gọi là [Salt Typhoon](https://www.bleepingcomputer.com/tag/salt-typhoon/), họ tập trung vào quyền truy cập lâu dài và bền bỉ vào mạng viễn thông.

Trong suốt năm, các xâm nhập bổ sung được quy cho chiến dịch này trên nhiều nhà cung cấp lớn tại [Hoa Kỳ](https://www.bleepingcomputer.com/news/security/charter-and-windstream-among-nine-us-telecoms-hacked-by-china/), [Canada](https://www.bleepingcomputer.com/news/security/canada-says-salt-typhoon-hacked-telecom-firm-via-cisco-flaw/), và các khu vực khác.

Các tác nhân đe dọa [khai thác thiết bị mạng Cisco chưa được vá](https://www.bleepingcomputer.com/news/security/chinese-hackers-breach-more-us-telecoms-via-unpatched-cisco-routers/), lạm dụng quyền hạn, và [triển khai malware tùy chỉnh](https://www.bleepingcomputer.com/news/security/chinese-hackers-use-custom-malware-to-spy-on-us-telecom-networks/) thiết kế cho môi trường viễn thông để thu thập cấu hình mạng, giám sát lưu lượng và có khả năng chặn các liên lạc.

Các tác nhân này thậm chí bị liên kết với các vi phạm mạng quân sự, [bao gồm U.S. National Guard](https://www.bleepingcomputer.com/news/security/chinese-hackers-breached-national-guard-to-steal-network-configurations/), vốn bị sử dụng để đánh cắp chi tiết mạng, file cấu hình và thông tin đăng nhập quản trị. Những thông tin này có thể đã được dùng để xâm nhập các mạng nhạy cảm khác.

Các chính phủ và cơ quan an ninh công khai quy những vi phạm Salt Typhoon này cho [ba công ty công nghệ có trụ sở tại Trung Quốc](https://www.bleepingcomputer.com/news/security/global-salt-typhoon-hacking-campaigns-linked-to-chinese-tech-firms/).

Federal Communications Commission đã [ban hành](https://www.bleepingcomputer.com/news/security/fcc-orders-telecoms-to-secure-their-networks-after-salt-tyhpoon-hacks/) cảnh báo và khuyến nghị cho các nhà mạng về việc tăng cường bảo vệ mạng và giám sát xâm nhập. Dù có rủi ro do hack được nhà nước hậu thuẫn, FCC sau đó [rút lại các quy tắc an ninh mạng được đề xuất](https://www.bleepingcomputer.com/news/security/fcc-rolls-back-cybersecurity-rules-for-telcos-despite-state-hacking-risks/).

### 7. [Các cuộc tấn công chèn prompt vào AI (Prompt-injection)](https://maccarita.com/posts/idesaster/)

Khi các hệ thống AI được tích hợp vào hầu hết công cụ năng suất, trình duyệt và môi trường phát triển vào năm 2025, các nhà nghiên cứu đã xác định một lớp lỗ hổng mới được gọi là tấn công prompt injection.

Khác với các lỗ hổng phần mềm truyền thống, prompt injection lợi dụng cách các mô hình AI hiểu chỉ dẫn, cho phép kẻ tấn công thao túng hành vi AI bằng cách cung cấp các đầu vào được chế tạo đặc biệt hoặc ẩn để ghi đè hoặc vượt qua hướng dẫn và biện pháp an toàn ban đầu.

Các cuộc tấn công prompt injection lừa hệ thống AI coi nội dung không đáng tin là hướng dẫn, khiến mô hình rò rỉ dữ liệu nhạy cảm, tạo ra nội dung độc hại, hoặc thực hiện các hành động không mong muốn mà không cần khai thác lỗi trong mã nguồn.

Một số sự cố nổi bật minh họa những tấn công mới này:

* Các nhà nghiên cứu phát hiện [rò rỉ dữ liệu zero-click trong Microsoft 365 Copilot](https://www.bleepingcomputer.com/news/security/zero-click-ai-data-leak-flaw-uncovered-in-microsoft-365-copilot/), nơi email được chế tạo đặc biệt với prompt injection ẩn làm lộ thông tin nhạy cảm mà không cần tương tác của người dùng.
* Google Gemini được xác định có thể bị prompt injection thông qua [tóm tắt email](https://www.bleepingcomputer.com/news/security/google-gemini-flaw-hijacks-email-summaries-for-phishing/) và [lời mời lịch](https://www.bleepingcomputer.com/news/security/google-calendar-invites-let-researchers-hijack-gemini-to-leak-user-data/), cho phép phishing và rò rỉ dữ liệu.
* Trợ lý mã hóa AI và công cụ IDE bị [thao túng qua các prompt bị chèn](https://maccarita.com/posts/idesaster/) để thực hiện hoặc gợi ý mã độc hại.
* Một cuộc tấn công "[CometJacking](https://www.bleepingcomputer.com/news/security/commetjacking-attack-tricks-comet-browser-into-stealing-emails/)" lợi dụng prompt injection trong trình duyệt Comet AI của Perplexity để lừa hệ thống truy cập dữ liệu nhạy cảm từ các dịch vụ liên kết như email và lịch.

Các tấn công prompt injection khác dùng chỉ dẫn ẩn [nhúng trong hình ảnh giảm kích thước](https://www.bleepingcomputer.com/news/security/new-ai-attack-hides-data-theft-prompts-in-downscaled-images/) mà con người không thể nhìn thấy nhưng hệ thống AI có thể đọc được.

### 6. [Nhắm mục tiêu bộ phận help desk trong các cuộc tấn công xã hội kỹ thuật](https://www.bleepingcomputer.com/news/security/hackers-fooled-cognizant-help-desk-says-clorox-in-380m-cyberattack-lawsuit/)

Năm 2025, các tác nhân đe dọa tập trung mạnh vào các chiến dịch xã hội kỹ thuật nhằm vào nhà cung cấp dịch vụ gia công quy trình kinh doanh (BPO) và bộ phận help desk IT để xâm nhập mạng nội bộ công ty.

Thay vì dựa vào lỗi phần mềm hay malware, kẻ tấn công lừa bộ phận help desk bỏ qua các kiểm soát an ninh và cấp quyền truy cập vào tài khoản nhân viên.

Hackers liên quan đến Scattered Spider được cho là đã giả danh một nhân viên và [lừa bộ phận help desk của Cognizant](https://www.bleepingcomputer.com/news/security/hackers-fooled-cognizant-help-desk-says-clorox-in-380m-cyberattack-lawsuit/) để cấp quyền truy cập vào tài khoản. Cuộc tấn công xã hội kỹ thuật này trở thành tâm điểm của vụ kiện trị giá $380 triệu chống lại Cognizant.

**Transcript of call between hacker and service desk**  
_Source: Clorox complaint against Cognizant_

Các tác nhân đe dọa khác cũng dùng loại tấn công này, với một nhóm gọi là "Luna Moth," còn gọi là Silent Ransom Group, [mạo danh bộ phận hỗ trợ IT để xâm nhập nhiều công ty Mỹ](https://www.bleepingcomputer.com/news/security/luna-moth-extortion-hackers-pose-as-it-help-desks-to-breach-us-firms/).

Google báo cáo rằng [Scattered Spider nhắm mục tiêu các công ty bảo hiểm tại Mỹ](https://www.bleepingcomputer.com/news/security/google-warns-scattered-spider-hackers-now-target-us-insurance-companies/) bằng cách lợi dụng các bộ phận hỗ trợ thuê ngoài để lấy quyền truy cập vào hệ thống nội bộ.

Các công ty bán lẻ cũng thừa nhận rằng các cuộc tấn công xã hội kỹ thuật nhắm vào help desk đã trực tiếp tạo điều kiện cho nhiều vụ ransomware và đánh cắp dữ liệu quy mô lớn.

Marks & Spencer (M&S) [xác nhận kẻ tấn công dùng social engineering](https://www.bleepingcomputer.com/news/security/mands-confirms-social-engineering-led-to-massive-ransomware-attack/) để xâm nhập mạng và thực hiện một cuộc tấn công ransomware. [Co-op cũng công bố rò rỉ dữ liệu](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/) sau một sự cố ransomware lạm dụng nhân sự hỗ trợ.

Để đối phó với các cuộc tấn công vào M&S và Co-op, [chính phủ Vương quốc Anh đưa ra hướng dẫn](https://www.bleepingcomputer.com/news/security/uk-shares-security-tips-after-major-retail-cyberattacks/) về chống social engineering nhắm vào help desk và BPO.

### 5. [Nội gián (Insider Threats)](https://www.bleepingcomputer.com/news/security/crowdstrike-catches-insider-feeding-information-to-hackers/)

Các mối đe dọa từ nội gián có tác động lớn trong năm 2025, với nhiều sự cố nổi bật cho thấy nhân viên hoặc tư vấn viên có quyền truy cập tin cậy, dù cố ý lạm dụng hay không bị thu hồi quyền sau khi thôi việc, dẫn đến thiệt hại quy mô lớn.

Coinbase [công bố một vụ rò rỉ dữ liệu](https://www.bleepingcomputer.com/news/security/coinbase-says-recent-data-breach-impacts-69-461-customers/) ảnh hưởng 69.461 khách hàng, sau đó dẫn đến [bắt giữ một cựu nhân viên hỗ trợ Coinbase](https://www.bleepingcomputer.com/news/security/former-coinbase-support-agent-arrested-for-helping-hackers/) bị cáo buộc giúp hacker truy cập hệ thống của họ.

CrowdStrike tiết lộ rằng họ phát hiện một [nội gián cung cấp thông tin cho hacker](https://www.bleepingcomputer.com/news/security/crowdstrike-catches-insider-feeding-information-to-hackers/), bao gồm ảnh chụp màn hình hệ thống nội bộ. Nội gián được cho là đã nhận $25.000 từ một nhóm tự xưng “Scattered Lapsus$ Hunters,” ám chỉ các tác nhân có liên hệ chồng chéo với Scattered Spider, Lapsus$, và ShinyHunters.

BleepingComputer được biết hoạt động này đã bị phát hiện trước khi nội gián có thể cung cấp quyền truy cập vào mạng của CrowdStrike.

Hoạt động nội gián cũng ảnh hưởng đến tổ chức tài chính, khi FinWise Bank [công bố một vụ vi phạm liên quan nội gián](https://www.bleepingcomputer.com/news/security/finwise-insider-breach-impacts-689k-american-first-finance-customers/) ảnh hưởng khoảng 689.000 khách hàng American First Finance. Trong một vụ khác, một nhân viên ngân hàng [bán thông tin đăng nhập chỉ với $920,](https://www.bleepingcomputer.com/news/security/employee-gets-920-for-credentials-used-in-140-million-bank-heist/) sau đó được dùng trong vụ cướp ngân hàng $140 triệu tại Ngân hàng Trung ương Brazil.

Nhiều sự cố khác cho thấy nguy cơ từ nhân viên bất mãn hoặc cựu nhân viên.

Một [developer nhận án bốn năm tù](https://www.bleepingcomputer.com/news/security/developer-guilty-of-using-kill-switch-to-sabotage-employers-systems/) vì tạo “kill switch” nhằm phá hoại hệ thống tại công ty cũ. Một vụ rò rỉ khác tại Coupang [được truy nguồn tới cựu nhân viên giữ quyền truy cập hệ thống](https://www.bleepingcomputer.com/news/security/coupang-data-breach-traced-to-ex-employee-who-retained-system-access/) sau khi rời công ty.

Cuối cùng, một băng đảng ransomware đã cố gắng [tuyển một nhà báo BBC](https://www.bleepingcomputer.com/news/security/ransomware-gang-sought-bbc-reporters-help-in-hacking-media-giant/) để giúp xâm phạm tổ chức truyền thông này.

### 4. [Sự cố gián đoạn CNTT quy mô lớn](https://www.bleepingcomputer.com/news/technology/cloudflare-hit-by-outage-affecting-global-network-services/)

Năm 2025, một loạt sự cố gián đoạn CNTT quy mô lớn làm gián đoạn dịch vụ và nền tảng trên toàn cầu, cho thấy mức độ phụ thuộc của thương mại toàn cầu vào hạ tầng đám mây.

Mặc dù không vụ nào trong số này do vi phạm an ninh mạng gây ra, nhưng tác động của chúng lớn đến mức cần được đề cập trong danh sách các câu chuyện hàng đầu của năm.

**BleepingComputer cũng bị ảnh hưởng bởi sự cố Cloudflare**

Một số sự cố gián đoạn đáng chú ý nhất năm 2025 gồm:

* Một [sự cố toàn cầu của Heroku](https://www.bleepingcomputer.com/news/technology/massive-heroku-outage-impacts-web-platforms-worldwide/) làm hàng trăm ứng dụng web ngừng hoạt động, ảnh hưởng cả trang web lẫn công cụ nội bộ.
* Một [sự cố DNS của Microsoft](https://www.bleepingcomputer.com/news/microsoft/microsoft-dns-outage-impacts-azure-and-microsoft-365-services/) làm gián đoạn Microsoft 365, dịch vụ Azure và ứng dụng cho nhiều tổ chức.
* Google cho biết một trong những gián đoạn nền tảng đám mây lớn nhất trong năm là do vấn đề quản lý API, gây ra [hàng loạt thất bại trên các dịch vụ](https://www.bleepingcomputer.com/news/google/google-links-massive-cloud-outage-to-api-management-issue/) dựa vào hạ tầng đám mây của họ.
* Một [sự cố AWS](https://www.bleepingcomputer.com/news/technology/aws-outage-crashes-amazon-prime-video-fortnite-perplexity-and-more/) làm Amazon Prime Video, Fortnite, Perplexity và nhiều dịch vụ khác ngừng hoạt động.
* Cloudflare [gặp nhiều sự cố](https://www.bleepingcomputer.com/news/technology/cloudflare-hit-by-outage-affecting-global-network-services/), trong đó có một sự cố được truy nguyên tới [việc triển khai bản vá khẩn cấp cho lỗ hổng React2Shell đang bị khai thác](https://www.bleepingcomputer.com/news/security/cloudflare-blames-todays-outage-on-emergency-react2shell-patch/), tạm thời làm gián đoạn dịch vụ mạng toàn cầu của họ.

### 3. [Các cuộc tấn công đánh cắp dữ liệu Salesforce](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/)

Năm 2025, Salesforce trở thành [mục tiêu thường xuyên của các chiến dịch đánh cắp dữ liệu và tống tiền quy mô lớn](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/), khi các tác nhân đe dọa ngày càng nhắm vào nền tảng và các dịch vụ bên thứ ba liên quan.

Mặc dù Salesforce tự nó không bị xâm nhập, kẻ tấn công nhiều lần truy cập được dữ liệu khách hàng thông qua tài khoản bị xâm nhập, OAuth token, và các dịch vụ bên thứ ba, dẫn đến một loạt các vụ rò rỉ dữ liệu có hồ sơ cao.

Những cuộc tấn công này chủ yếu [được liên kết với nhóm tống tiền ShinyHunters](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/) và ảnh hưởng đến các công ty trong nhiều ngành, bao gồm công nghệ, hàng không, an ninh mạng, bảo hiểm, bán lẻ và hàng xa xỉ.

Các công ty bị ảnh hưởng bởi các cuộc tấn công đánh cắp dữ liệu Salesforce gồm [Google](https://www.bleepingcomputer.com/news/security/google-confirms-data-breach-exposed-potential-google-ads-customers-info/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), [Chanel](https://www.bleepingcomputer.com/news/security/fashion-giant-chanel-hit-in-wave-of-salesforce-data-theft-attacks/), [Pandora](https://www.bleepingcomputer.com/news/security/pandora-confirms-data-breach-amid-ongoing-salesforce-data-theft-attacks/), [Allianz Life](https://www.bleepingcomputer.com/news/security/massive-allianz-life-data-breach-impacts-11-million-people/), [Farmers Insurance](https://www.bleepingcomputer.com/news/security/farmers-insurance-data-breach-impacts-11m-people-after-salesforce-attack/), [Workday](https://www.bleepingcomputer.com/news/security/hr-giant-workday-discloses-data-breach-amid-salesforce-attacks/), và nhiều tổ chức khác.

Nhóm tống tiền ShinyHunters cuối cùng [thiết lập một trang rò rỉ dữ liệu](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/) để tống tiền các công ty bị ảnh hưởng.

**ShinyHunters Salesforce leaks site**

Một thành phần quan trọng của các cuộc tấn công này là xâm nhập các nền tảng SaaS bên thứ ba kết nối trực tiếp với Salesforce.

Kẻ tấn công đã xâm nhập các dịch vụ như [Salesloft Drift](https://www.bleepingcomputer.com/news/security/salesloft-breached-to-steal-oauth-tokens-for-salesforce-data-theft-attacks/), đánh cắp OAuth token và thông tin đăng nhập cho phép truy cập vào các instance Salesforce được kết nối.

Những cuộc tấn công chuỗi cung ứng này ảnh hưởng đến nhiều công ty khác nhau, bao gồm [Google](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/), [Cloudflare](https://www.bleepingcomputer.com/news/security/cloudflare-hit-by-data-breach-in-salesloft-drift-supply-chain-attack/), [Zscaler](https://www.bleepingcomputer.com/news/security/zscaler-data-breach-exposes-customer-info-after-salesloft-drift-compromise/), [Tenable](https://www.tenable.com/blog/tenable-response-to-salesforce-and-salesloft-drift-incident), [CyberArk](https://www.cyberark.com/resources/blog/salesloft-drift-incident-overview-and-cyberarks-response), [Elastic](https://www.elastic.co/blog/elastic-update-salesloft-drift-security-incident), [BeyondTrust](https://www.beyondtrust.com/trust-center/security-advisories/salesforce-salesloft-drift-security-incident-response), [Proofpoint](https://www.proofpoint.com/us/blog/corporate-news/salesloft-drift-supply-chain-incident-response), [JFrog](https://jfrog.com/help/r/salesforce-data-incident-identified-linked-to-third-party-salesloft-drift/salesforce-data-incident-identified-linked-to-third-party-salesloft-drift), [Nutanix](https://www.nutanix.com/blog/third-party-salesloft-drift-application-incident-response-our-impact-and-action), [Qualys](https://blog.qualys.com/misc/2025/09/06/salesloft-drift-supply-chain-incident), [Rubrik](https://www.rubrik.com/blog/company/25/salesforce-connected-third-party-drift-application-supply-chain-incident-response), [Cato Networks](https://www.catonetworks.com/blog/cato-networks-statement-on-salesforce-salesloft-drift-incident/), [Palo Alto Networks](https://www.bleepingcomputer.com/news/security/palo-alto-networks-data-breach-exposes-customer-info-support-cases/), và [nhiều công ty khác](https://www.driftbreach.com/).

Salesforce cũng điều tra việc đánh cắp dữ liệu khách hàng [liên quan đến một vi phạm tại Gainsight](https://www.bleepingcomputer.com/news/security/salesforce-investigates-customer-data-theft-via-gainsight-breach/), sử dụng OAuth token bị đánh cắp trong các cuộc tấn công Salesloft Drift.

### 2. [Các cuộc tấn công zero-day](https://www.bleepingcomputer.com/tag/zero-day/)

Năm 2025, các lỗ hổng zero-day vẫn là phương thức được sử dụng rộng rãi để xâm nhập mạng doanh nghiệp nhằm đánh cắp dữ liệu, gián điệp mạng và tấn công ransomware.

Các thiết bị ở rìa mạng và dịch vụ phơi bày trên Internet là mục tiêu chính vì chúng nằm giữa Internet và mạng nội bộ.

Các lỗ hổng zero-day trong Cisco ([firewall ASA](https://www.bleepingcomputer.com/news/security/cisco-warns-of-asa-firewall-zero-days-exploited-in-attacks/), [IOS](https://www.bleepingcomputer.com/news/security/cisco-warns-of-ios-zero-day-vulnerability-exploited-in-attacks/), [AsyncOS](https://www.bleepingcomputer.com/news/security/cisco-warns-of-unpatched-asyncos-zero-day-exploited-in-attacks/), [ISE](https://www.bleepingcomputer.com/news/security/hackers-exploited-citrix-cisco-ise-flaws-in-zero-day-attacks/)), Fortinet ([FortiWeb](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-new-fortiweb-zero-day-exploited-in-attacks/), [FortiVoice](https://www.bleepingcomputer.com/news/security/fortinet-fixes-critical-zero-day-exploited-in-fortivoice-attacks/)), [Citrix NetScaler](https://www.bleepingcomputer.com/news/security/citrix-fixes-critical-netscaler-rce-flaw-exploited-in-zero-day-attacks/), [Ivanti Connect Secure](https://www.bleepingcomputer.com/news/security/ivanti-patches-connect-secure-zero-day-exploited-since-mid-march/), [SonicWall](https://www.bleepingcomputer.com/news/security/sonicwall-warns-of-new-sma1000-zero-day-exploited-in-attacks/), [FreePBX](https://www.bleepingcomputer.com/news/security/freepbx-servers-hacked-via-zero-day-emergency-fix-released/), và [CrushFTP](https://www.bleepingcomputer.com/news/security/new-crushftp-zero-day-exploited-in-attacks-to-hijack-servers/) bị khai thác tích cực ngoài đời thực.

Microsoft SharePoint là một trong những mục tiêu zero-day lớn của năm, với lỗ hổng [ToolShell](https://www.bleepingcomputer.com/news/microsoft/microsoft-sharepoint-zero-day-exploited-in-rce-attacks-no-patch-available/) được liên kết với [tác nhân Trung Quốc](https://www.bleepingcomputer.com/news/security/microsoft-sharepoint-toolshell-attacks-linked-to-chinese-hackers/), và sau đó là [các băng đảng ransomware](https://www.bleepingcomputer.com/news/security/ransomware-gangs-join-attacks-targeting-microsoft-sharepoint-servers/). Những lỗ hổng này được dùng để triển khai web shell, đánh cắp dữ liệu nhạy cảm và duy trì tính bền bỉ trong mạng doanh nghiệp.

Các lỗ hổng Windows cũng liên tục bị lợi dụng, bao gồm lỗi trong [xử lý shortcut](https://www.bleepingcomputer.com/news/microsoft/microsoft-mitigates-windows-lnk-flaw-exploited-as-zero-day/) và [dịch vụ logging](https://www.bleepingcomputer.com/news/security/play-ransomware-exploited-windows-logging-flaw-in-zero-day-attacks/).

Phần mềm khách hàng và doanh nghiệp cũng đóng vai trò, với các lỗ hổng zero-day trong [7-Zip](https://www.bleepingcomputer.com/news/security/7-zip-motw-bypass-exploited-in-zero-day-attacks-against-ukraine/) và [WinRAR](https://www.bleepingcomputer.com/news/security/winrar-zero-day-flaw-exploited-by-romcom-hackers-in-phishing-attacks/) bị khai thác trong các chiến dịch phishing để vượt qua biện pháp bảo vệ và cài malware.

**Sample phishing email exploiting 7-zip zero-day**  
_Source: Trend Micro_

Một số sự cố [liên quan đến](https://www.bleepingcomputer.com/news/security/italian-spyware-vendor-linked-to-chrome-zero-day-attacks/) [phần mềm gián điệp thương mại](https://www.bleepingcomputer.com/news/security/new-landfall-spyware-exploited-samsung-zero-day-via-whatsapp-messages/) và cơ quan thực thi pháp luật [sử dụng các lỗ hổng chưa được công bố để mở khóa thiết bị di động](https://www.bleepingcomputer.com/news/security/serbian-police-used-cellebrite-zero-day-hack-to-unlock-android-phones/).

### 1. [Các cuộc tấn công được hỗ trợ bởi AI](https://www.bleepingcomputer.com/news/security/internet-archive-hacked-data-breach-impacts-31-million-users/)

AI trở thành một công cụ hữu ích cho kẻ tấn công trong năm nay, khi họ dựa vào các large language models (LLMs) trong các cuộc xâm nhập, và để viết và triển khai malware.

Các nhà nghiên cứu an ninh và nhà cung cấp báo cáo số lượng đang tăng của các cuộc tấn công dùng AI để khai thác nhanh hơn, malware thích ứng, và tăng khối lượng cuộc tấn công.

Google [cảnh báo về các họ malware được hỗ trợ bởi AI mới](https://www.bleepingcomputer.com/news/security/google-warns-of-new-ai-powered-malware-families-deployed-in-the-wild/) được quan sát ngoài đời thực, một số trong đó điều chỉnh hành vi động theo môi trường nạn nhân.

Cuộc tấn công [S1ngularity](https://www.bleepingcomputer.com/news/security/ai-powered-malware-hit-2-180-github-accounts-in-s1ngularity-attack/), ảnh hưởng hàng nghìn tài khoản GitHub, làm nổi bật cách các công cụ AI bị lạm dụng để tự động hóa trinh sát và đánh cắp thông tin đăng nhập.

Các mẫu malware proof-of-concept, như [PromptLock ransomware](https://www.bleepingcomputer.com/news/security/experimental-promptlock-ransomware-uses-ai-to-encrypt-steal-data/), dùng LLMs để hỗ trợ mã hóa, đánh cắp dữ liệu và tấn công.

Bên cạnh malware, AI hiện được dùng để đẩy nhanh các nỗ lực khai thác. Các công cụ như [HexStrike](https://www.bleepingcomputer.com/news/security/hackers-use-new-hexstrike-ai-tool-to-rapidly-exploit-n-day-flaws/) được sử dụng để phân tích và khai thác lỗ hổng N-day một cách nhanh chóng, giảm thời gian và kỹ năng cần thiết để khai thác các flaw đã biết.

Các tác nhân đe dọa cũng phát hành các LLMs như [WormGPT 4 và KawaiiGPT](https://www.bleepingcomputer.com/news/security/malicious-llms-empower-inexperienced-hackers-with-advanced-tools/), cho phép tội phạm mạng tạo malware được hỗ trợ bởi AI mà không có các hạn chế hay biện pháp an toàn.

Đến cuối năm, AI không còn là thí nghiệm đối với kẻ tấn công nữa và đã trở thành một công cụ khác giúp tăng tốc phát triển, tự động hóa tấn công và hạ thấp rào cản để tiến hành chúng.