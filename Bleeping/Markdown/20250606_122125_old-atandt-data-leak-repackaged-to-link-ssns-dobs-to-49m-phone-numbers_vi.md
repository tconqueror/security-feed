# Rò rỉ dữ liệu cũ của AT&T được đóng gói lại để liên kết SSNs, DOBs với 49 triệu số điện thoại

![AT&T](https://www.bleepstatic.com/content/hl-images/2024/04/03/att-usa.jpg)

Một tác nhân đe dọa đã phát hành lại dữ liệu từ một vụ rò rỉ của AT&T vào năm 2021 ảnh hưởng đến 70 triệu khách hàng, lần này kết hợp các tệp riêng biệt trước đó để liên kết trực tiếp số An sinh xã hội và ngày sinh với từng người dùng.

AT&T đã thông báo với BleepingComputer rằng họ đang điều tra dữ liệu nhưng cũng cho rằng dữ liệu này xuất phát từ vụ rò rỉ đã biết và được đóng gói lại thành một rò rỉ mới.

"Không phải hiếm lạ khi tội phạm mạng đóng gói lại dữ liệu đã được công bố trước đó để kiếm lợi tài chính. Chúng tôi vừa nhận được thông tin về việc dữ liệu AT&T đang được rao bán trên các diễn đàn dark web, và chúng tôi đang tiến hành một cuộc điều tra đầy đủ," AT&T nói với BleepingComputer.

Như lần đầu được phát hiện bởi [HackRead](https://hackread.com/hackers-leak-86m-att-records-with-decrypted-ssns/), dữ liệu AT&T đã được phát hành trên một diễn đàn hack phổ biến nói tiếng Nga, nơi một tác nhân đe dọa tuyên bố rằng nó đã bị đánh cắp trong cuộc [tấn công đánh cắp dữ liệu Snowflake của AT&T vào năm 2024](https://www.bleepingcomputer.com/news/security/massive-atandt-data-breach-exposes-call-logs-of-109-million-customers/), đã tiết lộ nhật ký cuộc gọi của 109 triệu khách hàng.

"Ban đầu có một trong những cơ sở dữ liệu từ vụ rò rỉ Snowflake, đây là bản sao lưu mà tôi đã tạo ra, đã loại bỏ các số giả như 00000 (Tôi nghĩ là của các đặc vụ liên bang...?) và tôi cũng đã giải mã SSNs và DOBs," đọc bài đăng diễn đàn.

![Bài đăng diễn đàn rò rỉ dữ liệu AT&T năm 2021](https://www.bleepstatic.com/images/news/security/d/data-breaches/a/att/2021-re-release/forum-post.jpg)

**Bài đăng diễn đàn rò rỉ dữ liệu AT&T năm 2021**  
_Nguồn: BleepingComputer_

Tuy nhiên, phân tích của BleepingComputer về vụ rò rỉ cho thấy rằng dữ liệu thực tế xuất phát từ một [vụ rò rỉ dữ liệu AT&T vào năm 2021](https://www.bleepingcomputer.com/news/security/atandt-denies-data-breach-after-hacker-auctions-70-million-user-database/) do một tác nhân đe dọa nổi tiếng có tên là ShinyHunters thực hiện, người đã cố gắng bán nó với giá 200,000 đô la.

Ba năm sau, vào tháng 3 năm 2024, một tác nhân đe dọa khác đã [rò rỉ toàn bộ dữ liệu AT&T trên một diễn đàn tội phạm mạng](https://www.bleepingcomputer.com/news/security/att-says-leaked-data-of-70-million-people-is-not-from-its-systems/) miễn phí, tuyên bố rằng nó đến từ vụ rò rỉ AT&T của ShinyHunter năm 2021.

Dữ liệu này bao gồm tên, địa chỉ, số điện thoại di động, ngày sinh được mã hóa, số An sinh xã hội được mã hóa và các thông tin nội bộ khác. Tuy nhiên, trong vụ rò rỉ có các tệp riêng biệt ánh xạ SSNs và DOBs được mã hóa với các chuỗi văn bản rõ ràng chưa mã hóa của chúng.

Vào thời điểm đó, AT&T đã đầu tiên từ chối rằng dữ liệu là của họ nhưng cuối cùng đã [xác nhận rằng dữ liệu đã bị đánh cắp từ hệ thống của họ](https://www.bleepingcomputer.com/news/security/atandt-confirms-data-for-73-million-customers-leaked-on-hacker-forum/) và ảnh hưởng đến 73 triệu khách hàng.

Phân tích của BleepingComputer về vụ rò rỉ hiện tại cho thấy đó là cùng một dữ liệu đã bị rò rỉ vào năm 2024 nhưng đã được làm sạch để loại bỏ dữ liệu nội bộ của AT&T và thêm số An sinh xã hội và ngày sinh chưa mã hóa vào từng hồ sơ khách hàng.

Tổng cộng, có 88,320,017 dòng dữ liệu trong vụ rò rỉ, nhưng khi loại bỏ các bản sao, nó giảm xuống còn 86,017,088 bản ghi duy nhất.

Xử lý thêm dữ liệu cho thấy rằng nó chứa 48,896,044 số điện thoại duy nhất với thông tin khách hàng liên quan.

Sự giảm sút đáng kể này là do nhiều khách hàng có nhiều hồ sơ với cùng một số điện thoại được sử dụng ở các địa chỉ khác nhau.

Để nhấn mạnh, đây không phải là một vụ rò rỉ AT&T mới hay dữ liệu bị đánh cắp từ Snowflake mà thực sự là một phiên bản đóng gói lại của vụ rò rỉ dữ liệu năm 2021.