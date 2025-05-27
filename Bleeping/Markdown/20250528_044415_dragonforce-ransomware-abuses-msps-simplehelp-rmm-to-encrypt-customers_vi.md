# Ransomware DragonForce lợi dụng MSP’s SimpleHelp RMM để mã hóa khách hàng

![Tấn công mạng](https://www.bleepstatic.com/content/hl-images/2022/05/09/world-internet-network.jpg)

Hoạt động ransomware DragonForce đã thành công trong việc xâm nhập vào một nhà cung cấp dịch vụ quản lý và sử dụng nền tảng giám sát và quản lý từ xa (RMM) SimpleHelp của nó để đánh cắp dữ liệu và triển khai phần mềm mã hóa trên hệ thống của các khách hàng hạ nguồn.

Sophos đã được mời vào điều tra vụ tấn công và tin rằng các tác nhân đe dọa đã khai thác một chuỗi lỗ hổng SimpleHelp cũ hơn được theo dõi là CVE-2024-57727, CVE-2024-57728, và CVE-2024-57726 để xâm nhập vào hệ thống.

SimpleHelp là một công cụ hỗ trợ và truy cập từ xa thương mại thường được các MSP sử dụng để quản lý hệ thống và triển khai phần mềm qua các mạng lưới của khách hàng.

Báo cáo của [Sophos](https://news.sophos.com/en-us/2025/05/27/dragonforce-actors-target-simplehelp-vulnerabilities-to-attack-msp-customers/) cho biết các tác nhân đe dọa đã sử dụng SimpleHelp để thực hiện việc tình báo trên hệ thống của khách hàng, chẳng hạn như thu thập thông tin về khách hàng của MSP, bao gồm tên và cấu hình thiết bị, người dùng và kết nối mạng.

Các tác nhân đe dọa sau đó đã cố gắng đánh cắp dữ liệu và triển khai phần mềm giải mã trên các mạng lưới của khách hàng, nhưng đã bị chặn lại trên một trong các mạng, sử dụng bảo vệ đầu cuối Sophos. Tuy nhiên, các khách hàng khác thì không may mắn như vậy, với các thiết bị bị mã hóa và dữ liệu bị đánh cắp cho các cuộc tấn công tống tiền kép.

Sophos đã [chia sẻ các IOC](https://github.com/sophoslabs/IoCs/blob/master/2505%20DragonForce%20targets%20SimpleHelp%20RMM.csv) liên quan đến vụ tấn công này để giúp các tổ chức bảo vệ tốt hơn mạng lưới của họ.

Các MSP từ lâu đã là một [mục tiêu quý giá cho các băng nhóm ransomware](https://www.bleepingcomputer.com/news/security/ransomware-attacks-target-msps-to-mass-infect-customers/), vì một vụ vi phạm duy nhất có thể dẫn đến các cuộc tấn công vào nhiều công ty. Một số chi nhánh ransomware đã chuyên môn hóa vào các công cụ thường được các MSP sử dụng, chẳng hạn như SimpleHelp, ConnectWise ScreenConnect và Kaseya.

Điều này đã dẫn đến các cuộc tấn công tàn khốc, bao gồm [cuộc tấn công ransomware lớn của REvil vào Kaseya](https://www.bleepingcomputer.com/news/security/revil-ransomware-hits-1-000-plus-companies-in-msp-supply-chain-attack/), đã gây ảnh hưởng tới hơn 1.000 công ty.

## DragonForce nổi tiếng sau các cuộc tấn công bán lẻ ở Vương quốc Anh

Băng nhóm ransomware DragonForce gần đây đã trở nên nổi tiếng sau khi được liên kết với một loạt các cuộc xâm nhập bán lẻ nổi bật liên quan đến các tác nhân đe dọa sử dụng [tactics Scattered Spider](https://www.bleepingcomputer.com/news/security/fbi-shares-tactics-of-notorious-scattered-spider-hacker-collective/).

Như được báo cáo lần đầu bởi BleepingComputer, phần mềm ransomware của nhóm này đã được triển khai trong các cuộc tấn công vào nhà bán lẻ Vương quốc Anh [Marks & Spencer](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/). Ngay sau đó, những tác nhân đe dọa tương tự đã xâm nhập một nhà bán lẻ khác ở Vương quốc Anh, [Co-op](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/), nơi xác nhận một lượng lớn dữ liệu khách hàng đã bị đánh cắp.

BleepingComputer [trước đây đã báo cáo](https://www.bleepingcomputer.com/news/security/dragonforce-expands-ransomware-model-with-white-label-branding-scheme/) rằng DragonForce đang cố gắng xây dựng một "cartel" bằng cách cung cấp mô hình ransomware-as-a-service (RaaS) nhãn trắng, cho phép các chi nhánh triển khai các phiên bản thương hiệu lại của phần mềm mã hóa của nó.

Với cách tiếp cận thân thiện với các chi nhánh ngày càng tăng và danh sách nạn nhân đang ngày càng mở rộng, DragonForce đang nhanh chóng trở thành một nhân tố chính trong lĩnh vực ransomware.