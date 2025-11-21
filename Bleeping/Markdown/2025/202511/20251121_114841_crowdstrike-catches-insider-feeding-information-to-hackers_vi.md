# CrowdStrike bắt quả tang nhân viên nội bộ chia sẻ thông tin cho hacker

![CrowdStrike](https://www.bleepstatic.com/content/hl-images/2024/07/21/crowdstrike-header-logo.jpg)

Công ty an ninh mạng Mỹ CrowdStrike đã xác nhận rằng một nhân viên nội bộ đã chia sẻ các ảnh chụp màn hình được chụp trên hệ thống nội bộ với các tác nhân đe dọa không nêu tên.

Tuy nhiên, công ty lưu ý rằng hệ thống của họ không bị xâm phạm do sự cố này và dữ liệu của khách hàng không bị lộ.

"Chúng tôi đã xác định và sa thải một nhân viên nội bộ khả nghi vào tháng trước sau một cuộc điều tra nội bộ xác định anh ta đã chia sẻ các bức ảnh màn hình máy tính của mình ra bên ngoài," một phát ngôn viên của CrowdStrike nói với BleepingComputer hôm nay.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Hệ thống của chúng tôi chưa bao giờ bị xâm phạm và khách hàng vẫn được bảo vệ suốt thời gian. Chúng tôi đã chuyển vụ việc cho các cơ quan thực thi pháp luật có thẩm quyền."

CrowdStrike không nêu cụ thể nhóm đe dọa chịu trách nhiệm cho sự cố này hoặc động cơ của nhân viên ác ý đã chia sẻ ảnh chụp màn hình.

Tuy nhiên, tuyên bố này được đưa ra để trả lời các câu hỏi từ BleepingComputer liên quan đến các ảnh chụp màn hình của hệ thống CrowdStrike gần đây đã được đăng trên Telegram bởi các thành viên của các nhóm đe dọa ShinyHunters, Scattered Spider, và Lapsus$.

## Tập hợp tội phạm mạng Scattered Lapsus$ Hunters

Các nhóm này hiện tự gọi mình là "Scattered Lapsus$ Hunters" và trước đó đã khởi chạy một trang rò rỉ dữ liệu để tống tiền hàng chục công ty bị ảnh hưởng bởi một [làn sóng lớn các vi phạm Salesforce](https://www.bleepingcomputer.com/tag/salesforce/).

Scattered Lapsus$ Hunters đã [nhắm mục tiêu khách hàng Salesforce](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/) bằng các cuộc tấn công lừa đảo qua điện thoại [kể từ đầu năm](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/), xâm phạm các công ty như [Google](http://ogle-suffers-data-breach-in-ongoing-salesforce-data-theft-attacks/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/), [Farmers Insurance](https://www.bleepingcomputer.com/news/security/farmers-insurance-data-breach-impacts-11m-people-after-salesforce-attack/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), ​​​​​​[Workday](https://www.bleepingcomputer.com/news/security/hr-giant-workday-discloses-data-breach-amid-salesforce-attacks/), cũng như các công ty con của LVMH, bao gồm [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), và [Tiffany & Co](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/).

Các công ty họ cố gắng tống tiền bao gồm các thương hiệu và tổ chức nổi tiếng như Google, Cisco, Toyota, Instacart, Cartier, Adidas, Sake Fifth Avenue, Air France & KLM, FedEx, Disney/Hulu, Home Depot, Marriott, Gap, McDonald's, Walgreens, Transunion, HBO MAX, UPS, Chanel, và IKEA.

Scattered Lapsus$ Hunters cũng nhận trách nhiệm cho vụ [xâm phạm Jaguar Land Rover (JLR)](https://www.bleepingcomputer.com/news/security/jaguar-land-rover-says-cyberattack-severely-disrupted-production/), [đã đánh cắp dữ liệu nhạy cảm](https://www.bleepingcomputer.com/news/security/jaguar-land-rover-jlr-confirms-data-theft-after-recent-cyberattack/) và gây [gián đoạn đáng kể hoạt động](https://www.bleepingcomputer.com/news/security/jaguar-land-rover-extends-shutdown-after-cyberattack-by-another-week/), dẫn đến [thiệt hại hơn £196 million ($220 million)](https://www.bleepingcomputer.com/news/security/jaguar-land-rover-cyberattack-cost-the-company-over-220-million/) trong quý vừa qua.

Như BleepingComputer đã báo cáo tuần này, các nhóm tống tiền ShinyHunters và Scattered Spider đang chuyển sang nền tảng ransomware-as-a-service mới có tên [ShinySp1d3r](https://www.bleepingcomputer.com/news/security/meet-shinysp1d3r-new-ransomware-as-a-service-created-by-shinyhunters/), sau khi trước đó sử dụng bộ mã hóa của các băng nhóm ransomware khác trong các cuộc tấn công, bao gồm [ALPHV/BlackCat](https://www.bleepingcomputer.com/news/security/mgm-casinos-esxi-servers-allegedly-encrypted-in-ransomware-attack/), [RansomHub](https://reliaquest.com/blog/scattered-spider-x-ransomhub-a-new-partnership/), [Qilin](https://www.bleepingcomputer.com/news/security/microsoft-links-scattered-spider-hackers-to-qilin-ransomware-attacks/), và [DragonForce](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/).