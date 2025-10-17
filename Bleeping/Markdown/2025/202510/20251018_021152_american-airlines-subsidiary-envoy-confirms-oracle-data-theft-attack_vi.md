# Công ty con Envoy của American Airlines xác nhận cuộc tấn công đánh cắp dữ liệu Oracle

![American Eagle](https://www.bleepstatic.com/content/hl-images/2025/10/17/american-eagle.jpg)

Envoy Air, một hãng hàng không khu vực thuộc sở hữu của American Airlines, xác nhận rằng dữ liệu đã bị xâm phạm từ ứng dụng Oracle E-Business Suite sau khi băng nhóm tống tiền Clop đưa tên American Airlines lên trang rò rỉ dữ liệu của chúng.

"Chúng tôi biết về sự cố liên quan đến ứng dụng Oracle E-Business Suite của Envoy," Envoy Air nói với BleepingComputer.

"Khi biết về vấn đề này, chúng tôi ngay lập tức bắt đầu điều tra và đã liên hệ với cơ quan thực thi pháp luật. Chúng tôi đã tiến hành xem xét kỹ lưỡng dữ liệu liên quan và xác nhận rằng không có dữ liệu nhạy cảm hoặc dữ liệu khách hàng bị ảnh hưởng. Một lượng hạn chế thông tin kinh doanh và chi tiết liên hệ thương mại có thể đã bị xâm phạm."

Envoy Air là một công ty con của American Airlines và điều hành các chuyến bay khu vực theo thương hiệu American Eagle. Mặc dù hoạt động như một công ty riêng biệt, hãng được tích hợp vào mạng lưới của American cho việc bán vé, lập lịch và dịch vụ hành khách.

Băng nhóm tống tiền Clop hiện đang rò rỉ những gì họ tuyên bố là dữ liệu bị đánh cắp từ Envoy trên trang rò rỉ dữ liệu của chúng, tuyên bố, "The company doesn't care about its customers, it ignored their security!!!"

Sự cố an ninh mới này liên quan đến chiến dịch đánh cắp dữ liệu vào tháng 8 do nhóm tống tiền Clop thực hiện, chiến dịch này bắt đầu [emailing extortion demands to companies](https://www.bleepingcomputer.com/news/security/clop-extortion-emails-claim-theft-of-oracle-e-business-suite-data/) vào tháng 9, tuyên bố đã đánh cắp dữ liệu từ các hệ thống Oracle E-Business Suite.

Trong khi Oracle ban đầu tuyên bố rằng các tác nhân đe dọa đang khai thác các lỗ hổng đã được vá vào tháng 7, công ty sau đó tiết lộ rằng băng nhóm tống tiền đã [exploited a zero-day flaw tracked as CVE-2025-61882](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/) trong các cuộc tấn công.

CrowdStrike và Mandiant sau đó tiết lộ rằng [Clop exploited the flaws in early August](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/) để xâm nhập hệ thống và triển khai phần mềm độc hại.

Trong khi Clop không tiết lộ có bao nhiêu công ty bị ảnh hưởng bởi các cuộc tấn công đánh cắp dữ liệu, John Hultquist của Google đã nói với BleepingComputer qua email rằng họ tin rằng hàng chục tổ chức đã bị ảnh hưởng.

Băng nhóm Clop cũng đang [extorting Harvard University](https://www.bleepingcomputer.com/news/security/harvard-investigating-breach-linked-to-oracle-zero-day-exploit/) như một phần của cùng chiến dịch đánh cắp dữ liệu này, với trường đại học xác nhận với BleepingComputer rằng sự cố ảnh hưởng tới "một số hạn chế các bên liên quan đến một đơn vị hành chính nhỏ."

Tuần trước, [Oracle silently patched another E-Business Suite zero-day](https://www.bleepingcomputer.com/news/security/oracle-silently-fixes-zero-day-exploit-leaked-by-shinyhunters/) được theo dõi là CVE-2025-61884 mà không tiết lộ rằng lỗ hổng này đã bị khai thác tích cực vào tháng 7 năm 2025.

Lỗ hổng zero-day này liên quan đến một mã khai thác bị rò rỉ bởi Shiny Lapsus$ Hunters extortion group trên Telegram.

American Airlines trước đó đã trải qua các vụ rò rỉ dữ liệu vào các năm [2022](https://www.bleepingcomputer.com/news/security/american-airlines-learned-it-was-breached-from-phishing-targets/) và [2023](https://www.bleepingcomputer.com/news/security/american-airlines-southwest-airlines-disclose-data-breaches-affecting-pilots/) làm lộ thông tin cá nhân của nhân viên.

## Who is Clop?

Hoạt động ransomware Clop, cũng được theo dõi dưới tên TA505, Cl0p, và FIN11, bắt đầu vào năm 2019 khi nhóm này bắt đầu xâm nhập mạng lưới doanh nghiệp để triển khai biến thể CryptoMix ransomware và đánh cắp dữ liệu.

Kể từ 2020, nhóm tống tiền đã chuyển từ chủ yếu sử dụng ransomware sang khai thác các lỗ hổng zero-day trong các nền tảng chuyển tệp an toàn hoặc lưu trữ dữ liệu để đánh cắp dữ liệu.

Một số cuộc tấn công của họ sử dụng lỗ hổng zero-day bao gồm:

* **2020:** Khai thác một [zero-day in the Accellion FTA platform](https://www.bleepingcomputer.com/tag/accellion/), ảnh hưởng tới gần 100 tổ chức.
* **2021:** Khai thác một [zero-day in SolarWinds Serv-U FTP](https://www.bleepingcomputer.com/news/security/clop-gang-exploiting-solarwinds-serv-u-flaw-in-ransomware-attacks/) software.
* **2023:** Khai thác một [zero-day in the GoAnywhere MFT platform](https://www.bleepingcomputer.com/news/security/fortra-shares-findings-on-goanywhere-mft-zero-day-attacks/), xâm nhập hơn 100 công ty.
* **2023:** Khai thác một [zero-day in MOVEit Transfer](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-moveit-extortion-attacks/) là chiến dịch lớn nhất của Clop cho đến nay, nơi một mã khai thác zero-day cho phép [data theft from 2,773 organizations worldwide](https://www.emsisoft.com/en/blog/44123/unpacking-the-moveit-breach-statistics-and-analysis/).
* **2024:** Khai thác [two Cleo file transfer zero-days (CVE-2024-50623 and CVE-2024-55956)](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-cleo-data-theft-attacks/) để đánh cắp dữ liệu và tống tiền các công ty.

U.S. State Department hiện đang đưa ra một [$10 million reward](https://www.bleepingcomputer.com/news/security/us-govt-offers-10-million-bounty-for-info-on-clop-ransomware/) cho thông tin liên kết hoạt động ransomware của Clop với một chính phủ nước ngoài.