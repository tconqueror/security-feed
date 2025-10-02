# Các email tuyên bố dữ liệu của Oracle bị đánh cắp trong chiến dịch tống tiền mới liên quan đến Clop

![Bàn tay sàng lọc dữ liệu](https://www.bleepstatic.com/content/hl-images/2024/08/16/data-leak.jpg)

Mandiant và Google đang theo dõi một chiến dịch tống tiền mới, trong đó các lãnh đạo tại nhiều công ty nhận được các email tuyên bố rằng dữ liệu nhạy cảm đã bị đánh cắp từ hệ thống Oracle E-Business Suite của họ.

Theo Genevieve Stark, Trưởng Bộ phận Phân tích Tình báo Hoạt động Tội phạm Mạng và Thông tin tại GTIG, chiến dịch bắt đầu vào cuối tháng Chín.

"Hoạt động này bắt đầu vào hoặc trước ngày September 29, 2025, nhưng các chuyên gia của Mandiant vẫn đang ở giai đoạn đầu của nhiều cuộc điều tra, và chưa xác thực được các tuyên bố do nhóm này đưa ra," Stark nói.

Charles Carmakal, CTO của Mandiant – Google Cloud, cho biết các email tống tiền đang được gửi từ một số lượng lớn tài khoản email bị xâm phạm.

"Chúng tôi hiện đang quan sát một chiến dịch email quy mô lớn được khởi động từ hàng trăm tài khoản bị xâm phạm và phân tích ban đầu của chúng tôi xác nhận rằng ít nhất một trong những tài khoản này đã từng liên quan đến hoạt động từ FIN11, một nhóm gây nguy hại có động cơ tài chính hoạt động lâu dài, nổi tiếng với việc triển khai ransomware và tham gia vào tống tiền," Carmakal giải thích.

Mandiant và GTIG báo cáo rằng các email chứa địa chỉ liên hệ được biết là liệt kê trên trang rò rỉ dữ liệu của băng nhóm Clop, cho thấy khả năng có liên hệ đến nhóm tống tiền này.

Tuy nhiên, Carmakal nói rằng mặc dù thủ thuật tương tự với các chiến dịch tống tiền trước đây của Clop và các địa chỉ email cho thấy mối liên hệ tiềm năng, vẫn chưa có đủ bằng chứng để xác định liệu dữ liệu có thực sự bị đánh cắp hay không.

Mandiant và GTIG khuyến nghị các tổ chức nhận được những email này nên điều tra môi trường của họ để tìm các truy cập bất thường hoặc dấu hiệu bị xâm phạm trong các nền tảng Oracle E-Business Suite.

BleepingComputer đã liên hệ với băng nhóm Clop để xác nhận xem họ có đứng sau các email tống tiền này hay không, nhưng hiện tại chưa nhận được phản hồi.

Chúng tôi cũng đã liên hệ với Oracle để xác định xem họ có biết về bất kỳ việc khai thác zero-day gần đây nào có thể dẫn đến việc đánh cắp dữ liệu hay không.

Nếu bạn có bất kỳ thông tin nào liên quan đến sự cố này hoặc bất kỳ cuộc tấn công chưa được công bố nào khác, bạn có thể liên hệ với chúng tôi một cách bảo mật qua Signal tại 646-961-3731 hoặc tại tips@bleepingcomputer.com.

## Nhóm tống tiền Clop là ai?

Hoạt động ransomware Clop, cũng được theo dõi với các tên TA505, Cl0p và FIN11, khởi động vào tháng March 2019 khi bắt đầu nhắm mục tiêu vào mạng doanh nghiệp với một biến thể của ransomware CryptoMix.

Giống như các băng nhóm ransomware khác, các thành viên Clop xâm nhập mạng công ty, đánh cắp dữ liệu, và sau đó triển khai ransomware để mã hóa hệ thống.

Dữ liệu bị đánh cắp và các tệp đã mã hóa sau đó được sử dụng làm đòn bẩy để buộc các công ty trả tiền chuộc để đổi lấy trình giải mã và ngăn chặn việc rò rỉ dữ liệu bị đánh cắp.

Trong khi nhóm này vẫn được biết đến là triển khai ransomware, kể từ năm 2020, họ đã chuyển sang khai thác các lỗ hổng zero-day trong các nền tảng chuyển file an toàn để đánh cắp dữ liệu.

Một số cuộc tấn công đáng chú ý nhất của họ bao gồm:

* **2020:** [Khai thác lỗ hổng zero-day trong Accellion FTA platform](https://www.bleepingcomputer.com/tag/accellion/), ảnh hưởng tới gần 100 tổ chức.
* **2021:** [Khai thác lỗ hổng zero-day trong SolarWinds Serv-U FTP](https://www.bleepingcomputer.com/news/security/clop-gang-exploiting-solarwinds-serv-u-flaw-in-ransomware-attacks/) software.
* **2023:** Khai thác một [zero-day trong GoAnywhere MFT platform](https://www.bleepingcomputer.com/news/security/fortra-shares-findings-on-goanywhere-mft-zero-day-attacks/), xâm phạm hơn 100 công ty.
* **[2023 MOVEit Transfer attack](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-moveit-extortion-attacks/):** Chiến dịch lớn nhất của tác nhân đe dọa đến nay, nơi một khai thác zero-day cho phép [đánh cắp dữ liệu từ 2,773 tổ chức trên toàn thế giới](https://www.emsisoft.com/en/blog/44123/unpacking-the-moveit-breach-statistics-and-analysis/).

Chiến dịch gần đây nhất liên quan đến Clop là vào tháng October 2024, khi các tác nhân đe dọa [khai thác hai zero-day trên nền tảng chuyển file Cleo](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-cleo-data-theft-attacks/) (CVE-2024-50623 và CVE-2024-55956) để đánh cắp dữ liệu và tống tiền các công ty.

Bộ Ngoại giao Hoa Kỳ hiện đang đưa ra một [$10 million reward](https://www.bleepingcomputer.com/news/security/us-govt-offers-10-million-bounty-for-info-on-clop-ransomware/) thông qua chương trình Rewards for Justice cho thông tin liên kết các hoạt động ransomware của Clop với một chính phủ nước ngoài.