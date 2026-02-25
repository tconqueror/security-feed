# UnsolicitedBooker nhắm vào các công ty viễn thông Trung Á với các backdoor LuciDoor và MarsSnake

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhSNzH9FCcwXlaHaCt3zQfmpwV3uesrW%5F2ISdcvbuKMl7PIENe9w6dhzBVpj19%5FBmgHKcZIzxBLSBFOmwNx2ahUast29Tk%5FLJoY8qz-SrJziWhHTHURX8HTvJuIVvMJourUJ0Hw8RKnXYUFcz9wsaO7%5FhalOZmw3gof1-N1-jI-MtNsztV5YYP4WvQdPBcY/s1700-e365/TELECOM.jpg)

nhóm hoạt động đe dọa được gọi là **UnsolicitedBooker** đã được quan sát nhắm vào các công ty viễn thông tại Kyrgyzstan và Tajikistan, đánh dấu sự thay đổi từ các cuộc tấn công trước đây nhắm vào các thực thể của Ả Rập Saudi.

Các cuộc tấn công liên quan đến việc triển khai hai backdoor riêng biệt được đặt tên là LuciDoor và MarsSnake, theo một báo cáo được công bố bởi Positive Technologies tuần trước.

"Nhóm đã sử dụng một số công cụ độc nhất và hiếm có nguồn gốc từ Trung Quốc," các nhà nghiên cứu Alexander Badaev và Maxim Shamanov [cho biết](https://ptsecurity.com/research/pt-esc-threat-intelligence/poisonous-mars-or-how-lucidoor-knocks-on-the-doors-of-the-cis/).

UnsolicitedBooker [được ghi nhận lần đầu tiên](https://thehackernews.com/2025/05/chinese-hackers-deploy-marssnake.html) bởi ESET vào tháng 5 năm 2025, quy cho nhóm đe dọa liên kết với Trung Quốc về một cuộc tấn công mạng nhắm vào một tổ chức quốc tế chưa được nêu tên tại Ả Rập Saudi với một backdoor được gọi là MarsSnake. Nhóm này được đánh giá là hoạt động ít nhất từ tháng 3 năm 2023 và có tiền sử nhắm vào các tổ chức ở châu Á, châu Phi và Trung Đông.

Phân tích sâu hơn về nhóm đe dọa đã phát hiện sự trùng lặp chiến thuật với hai nhóm khác, bao gồm Space Pirates và một chiến dịch chưa được quy cho nhóm nào nhắm vào Ả Rập Saudi với một backdoor khác được gọi là Zardoor.

[](https://thehackernews.uk/sse-customer-awards-d)

Bộ các cuộc tấn công mới nhất được ghi nhận bởi nhà cung cấp an ninh mạng của Nga được phát hiện nhắm vào các tổ chức của Kyrgyzstan vào cuối tháng 9 năm 2025 với các email lừa đảo chứa một tài liệu Microsoft Office, khi mở ra, hướng dẫn người nhận "[Kích hoạt nội dung](https://support.microsoft.com/en-us/office/enable-or-disable-macros-in-microsoft-365-files-12b036fd-d140-4e74-b45e-16fed1a7e5c6)" để chạy một macro độc hại.

Trong khi tài liệu hiển thị kế hoạch cước của nhà cung cấp viễn thông cho nạn nhân, macro một cách lén lút thả một trình tải malware C++ được gọi là LuciLoad, sau đó triển khai LuciDoor. Một cuộc tấn công khác được quan sát vào cuối tháng 11 năm 2025 áp dụng cùng một phương thức hoạt động, chỉ lần này nó sử dụng một trình tải khác được gọi là MarsSnakeLoader để triển khai MarsSnake.

Ngay từ tháng 1 năm 2026, UnsolicitedBooker được cho là đã tận dụng các email lừa đảo như một vector để nhắm vào các công ty tại Tajikistan. Mặc dù chuỗi tấn công tổng thể vẫn giữ nguyên, các thông điệp nhúng các liên kết đến các tài liệu mồi nhử thay vì đính kèm trực tiếp chúng.

Được viết bằng C++, LuciDoor thiết lập giao tiếp với một máy chủ điều khiển (C2), thu thập thông tin hệ thống cơ bản, và xuất dữ liệu ra máy chủ dưới định dạng được mã hóa. Sau đó, nó phân tích các phản hồi được gửi bởi máy chủ để chạy các lệnh sử dụng cmd.exe, ghi tệp vào hệ thống, và tải tệp lên.

| [](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiCFTRL30UYyQeCJxw1PnEAwwXgtiSg4D9vCts6Igu19-tATiOvNe8v5ldIZ%5FSntA5dbt%5Fh0C2hB6D0cwjUts-xvb9jSjHrDyGPZKLkm65zkaiF%5FymsiIJyqHmMssx7rRWNtidSejcArb6kWWlG8szP72-IHmHv5s7qudXe5hDPeC20pHObamL2WNl4wFXS/s1700-e365/malware.png) |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Macro trong tài liệu                                                                                                                                                                                                                                                                     |

MarsSnake, tương tự, cho phép kẻ tấn công thu thập siêu dữ liệu hệ thống, thực thi các lệnh tùy ý, và đọc hoặc ghi bất kỳ tệp nào trên đĩa.

Positive Technologies cho biết họ cũng tìm thấy dấu hiệu rằng MarsSnake đã được sử dụng trong các cuộc tấn công nhắm vào Trung Quốc. Điểm khởi đầu là một shortcut của Windows giả mạo một tài liệu Microsoft Word (\*.doc.lnk) kích hoạt việc thực thi một script batch để khởi chạy một Visual Basic Script, sau đó khởi chạy MarsSnake mà không có thành phần trình tải.

Tệp mồi nhử được cho là dựa trên một tệp LNK liên kết với một công cụ pentesting có sẵn công khai được gọi là [FTPlnk\_phishing](https://github.com/Pizz33/FTPlnk%5Fphishing), do các chỉ số thời gian tạo tệp LNK giống hệt nhau và Machine ID. Đáng chú ý là một [tệp LNK tương tự](https://www.darktrace.com/blog/chinese-apt-target-royal-thai-police-in-malware-campaign) đã được nhóm [Mustang Panda](https://thehackernews.com/2025/09/mustang-panda-deploys-snakedisk-usb.html) sử dụng trong các cuộc tấn công nhắm vào Thái Lan vào năm 2022.

"Trong các cuộc tấn công của họ, nhóm đã sử dụng các công cụ hiếm có nguồn gốc từ Trung Quốc," Positive Technologies cho biết. "Điều thú vị là ngay từ đầu, nhóm đã sử dụng một backdoor mà chúng tôi đặt tên là LuciDoor, nhưng sau đó chuyển sang backdoor MarsSnake. Tuy nhiên, vào năm 2026, nhóm đã quay trở lại và tiếp tục sử dụng LuciDoor."

"Hơn nữa, ít nhất trong một trường hợp, chúng tôi quan sát thấy kẻ tấn công sử dụng một router bị hack làm máy chủ C2, và cơ sở hạ tầng của họ mô phỏng cơ sở hạ tầng của Nga trong một số cuộc tấn công."

### PseudoSticky và Cloud Atlas nhắm vào Nga

Thông tin được công bố khi một nhóm đe dọa trước đây chưa được biết đến đang cố ý bắt chước chiến thuật của một nhóm hack ủng hộ Ukraine được gọi là [Sticky Werewolf](https://thehackernews.com/2025/02/sticky-werewolf-uses-undocumented.html) (còn được gọi là Angry Likho, MimiStick, và PhaseShifters) để tấn công các tổ chức Nga trong các lĩnh vực bán lẻ, xây dựng, và nghiên cứu với malware như RemcosRAT và DarkTrack RAT để đánh cắp dữ liệu toàn diện và điều khiển từ xa.

Nhóm mới, được gọi là [PseudoSticky](https://www.f6.ru/blog/pseudo-sticky/), đã hoạt động từ tháng 11 năm 2025\. Các nạn nhân thường bị nhiễm thông qua các email lừa đảo chứa các tệp đính kèm độc hại dẫn đến việc triển khai các trojan. Có dấu hiệu cho thấy nhóm đe dọa đã dựa vào các mô hình ngôn ngữ lớn (LLMs) để [phát triển các chuỗi tấn công](https://www.f6.ru/blog/purecrypter-darktrack-rat/) thả DarkTrack RAT qua PureCrypter.

[](https://thehackernews.uk/ztw-hands-on-d)

"Một phân tích sâu hơn tiết lộ sự khác biệt trong cơ sở hạ tầng, triển khai malware, và các yếu tố chiến thuật riêng lẻ, dẫn chúng tôi nghi ngờ rằng có khả năng không có mối liên kết trực tiếp giữa các nhóm, mà là sự bắt chước có chủ đích," nhà cung cấp bảo mật Nga F6 cho biết.

Các thực thể Nga cũng đã bị nhắm bởi một nhóm hack khác được gọi là [Cloud Atlas](https://thehackernews.com/2025/10/threatsday-bulletin-dns-poisoning-flaw.html#cloud-atlas-revives-old-exploits-to-hit-russian-farms), sử dụng các email lừa đảo mang các tài liệu Word độc hại để phân phối malware tùy chỉnh được gọi là [VBShower và VBCloud](https://thehackernews.com/2024/12/cloud-atlas-deploys-vbcloud-malware.html).

"Khi mở, tài liệu độc hại tải một template từ xa từ C2 được chỉ định trong một trong các luồng của tài liệu," công ty an ninh mạng Solar [cho biết](https://rt-solar.ru/solar-4rays/blog/6397/). "Template này khai thác lỗ hổng CVE-2018-0802. Tiếp theo là tải xuống một tệp độc hại với các luồng thay thế, tức là VBShower."