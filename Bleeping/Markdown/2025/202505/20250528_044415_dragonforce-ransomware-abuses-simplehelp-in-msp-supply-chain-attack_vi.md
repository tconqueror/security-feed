# Ransomware DragonForce lợi dụng SimpleHelp trong cuộc tấn công chuỗi cung ứng MSP

![Các cuộc tấn công mạng](https://www.bleepstatic.com/content/hl-images/2022/05/09/world-internet-network.jpg)

Hoạt động ransomware DragonForce đã thành công trong việc xâm nhập một nhà cung cấp dịch vụ được quản lý (MSP) và sử dụng nền tảng giám sát và quản lý từ xa (RMM) SimpleHelp của nó để đánh cắp dữ liệu và triển khai các trình mã hóa trên hệ thống của khách hàng hạ lưu.

Sophos đã được mời điều tra cuộc tấn công và tin rằng các diễn viên đe dọa đã khai thác một chuỗi các lỗ hổng cũ của SimpleHelp được theo dõi là CVE-2024-57727, CVE-2024-57728 và CVE-2024-57726 để xâm nhập hệ thống.

SimpleHelp là một công cụ hỗ trợ và truy cập từ xa thương mại thường được MSP sử dụng để quản lý hệ thống và triển khai phần mềm trên mạng của khách hàng.

Báo cáo của [Sophos](https://news.sophos.com/en-us/2025/05/27/dragonforce-actors-target-simplehelp-vulnerabilities-to-attack-msp-customers/) cho biết các diễn viên đe dọa đã đầu tiên sử dụng SimpleHelp để thực hiện sự điều tra trên các hệ thống của khách hàng, chẳng hạn như thu thập thông tin về khách hàng của MSP, bao gồm tên thiết bị và cấu hình, người dùng và kết nối mạng.

Các diễn viên đe dọa sau đó đã cố gắng đánh cắp dữ liệu và triển khai các trình mã hóa trên mạng của khách hàng, điều này đã bị chặn trên một trong những mạng bằng cách sử dụng bảo vệ đầu cuối Sophos. Tuy nhiên, các khách hàng khác không may mắn như vậy, các thiết bị đã bị mã hóa và dữ liệu bị đánh cắp để thực hiện các cuộc tấn công tống tiền gấp đôi.

Sophos đã [chia sẻ IOC](https://github.com/sophoslabs/IoCs/blob/master/2505%20DragonForce%20targets%20SimpleHelp%20RMM.csv) liên quan đến cuộc tấn công này nhằm giúp các tổ chức bảo vệ tốt hơn mạng lưới của họ.

MSP từ lâu đã là một [mục tiêu quý giá cho các băng nhóm ransomware](https://www.bleepingcomputer.com/news/security/ransomware-attacks-target-msps-to-mass-infect-customers/), vì một sự xâm nhập duy nhất có thể dẫn đến các cuộc tấn công vào nhiều công ty. Một số đối tác ransomware đã chuyên biệt hóa vào những công cụ thường được các MSP sử dụng, chẳng hạn như SimpleHelp, ConnectWise ScreenConnect và Kaseya.

Điều này đã dẫn đến các cuộc tấn công tàn khốc, bao gồm [cuộc tấn công ransomware khổng lồ của REvil vào Kaseya](https://www.bleepingcomputer.com/news/security/revil-ransomware-hits-1-000-plus-companies-in-msp-supply-chain-attack/), đã tác động đến hơn 1.000 công ty.

## DragonForce nổi tiếng sau các cuộc tấn công vào bán lẻ tại Vương quốc Anh

Băng nhóm ransomware DragonForce gần đây đã gia tăng độ nổi tiếng sau khi được liên kết với một làn sóng các cuộc xâm nhập bán lẻ nổi bật liên quan đến các diễn viên đe dọa sử dụng [chiến thuật Scattered Spider](https://www.bleepingcomputer.com/news/security/fbi-shares-tactics-of-notorious-scattered-spider-hacker-collective/).

Như được BleepingComputer báo cáo đầu tiên, ransomware của nhóm đã được triển khai trong các cuộc tấn công vào nhà bán lẻ Vương quốc Anh [Marks & Spencer](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/). Ngay sau đó, các diễn viên đe dọa tương tự đã xâm nhập vào một nhà bán lẻ khác của Vương quốc Anh, [Co-op](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/), nơi đã xác nhận một số lượng lớn dữ liệu khách hàng đã bị đánh cắp.

BleepingComputer [trước đó đã báo cáo](https://www.bleepingcomputer.com/news/security/dragonforce-expands-ransomware-model-with-white-label-branding-scheme/) rằng DragonForce đang cố gắng xây dựng một "-cartel" bằng cách cung cấp mô hình ransomware-as-a-service (RaaS) nhãn trắng, cho phép các đối tác triển khai các phiên bản đã được thương hiệu lại của trình mã hóa của nó.

Với cách tiếp cận ngày càng thân thiện với các đối tác và danh sách nạn nhân đang gia tăng, DragonForce đang nhanh chóng trở thành một nhân tố lớn trong cảnh quan ransomware.