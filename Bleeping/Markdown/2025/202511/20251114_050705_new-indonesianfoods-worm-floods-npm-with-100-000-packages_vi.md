# Con sâu ‘IndonesianFoods’ mới tràn ngập npm với 100,000 gói

![Con sâu ‘IndonesianFoods’ mới tràn ngập npm với 100,000 gói](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_head_pic.jpg)

Một gói tự lây lan được xuất bản trên npm spam registry bằng cách sinh ra các gói mới mỗi bảy giây, tạo ra khối lượng lớn rác.

Con sâu, được gọi là ‘IndonesianFoods’ do cách đặt tên gói đặc trưng lấy ngẫu nhiên tên Indonesia và các thuật ngữ về thực phẩm, đã xuất bản hơn 100,000 gói theo báo cáo của Sonatype, và con số này đang tăng theo cấp số nhân.

Mặc dù các gói không có thành phần độc hại nhắm vào nhà phát triển (ví dụ, đánh cắp dữ liệu, backdoor máy chủ), điều này có thể thay đổi nếu có một bản cập nhật giới thiệu payload nguy hiểm.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Mức độ tự động hóa và quy mô lớn của cuộc tấn công tạo ra khả năng ảnh hưởng tới chuỗi cung ứng phần mềm trên diện rộng.

Nhà nghiên cứu an ninh Paul McCarty, người [đã báo cáo lần đầu](https://sourcecodered.com/indonesianfoods-npm-worm/) chiến dịch spam này, đã [tạo một trang](https://github.com/6mile/Indonesian-Foods-Worm) để theo dõi các nhà xuất bản npm vi phạm và số lượng gói họ đã phát hành trên nền tảng.

Sonatype [báo cáo](https://www.sonatype.com/blog/unprecedented-automation-indonesianfoods-pits-open-source-against-itself) rằng cùng nhóm tác nhân đã thực hiện một nỗ lực khác vào ngày 10 tháng 9, với một gói tên ‘fajar-donat9-breki.’ Mặc dù gói đó chứa cùng logic sao chép, nó đã không lây lan được.

“Cuộc tấn công này đã làm quá tải nhiều hệ thống dữ liệu bảo mật, thể hiện quy mô chưa từng có,” Garret Calpouzos, nhà nghiên cứu chính về an ninh của Sonatype, nói với BleepingComputer.

“Amazon Inspector đang gắn cờ những gói này thông qua các thông báo OSV, kích hoạt một làn sóng lớn các báo cáo lỗ hổng. Chỉ riêng cơ sở dữ liệu của Sonatype đã thấy 72,000 thông báo mới trong một ngày.”

Nhà nghiên cứu nhận xét rằng IndonesianFoods dường như không tập trung xâm nhập máy của nhà phát triển, mà nhằm gây áp lực cho hệ sinh thái và làm gián đoạn chuỗi cung ứng phần mềm lớn nhất thế giới.

“Động cơ không rõ ràng, nhưng hệ quả thì nổi bật,” Calpouzos lưu ý.

Một [báo cáo từ Endor Labs](https://www.endorlabs.com/learn/the-great-indonesian-tea-theft-analyzing-a-npm-spam-campaign) về chiến dịch IndonesianFoods đề cập rằng một số gói dường như lạm dụng TEA Protocol, một hệ thống blockchain thưởng cho đóng góp OSS bằng TEA tokens, chứa các tệp _tea.yaml_ liệt kê tài khoản TEA và địa chỉ ví.

Bằng cách xuất bản hàng nghìn gói liên kết với nhau, kẻ tấn công đã phình to điểm tác động của họ để kiếm nhiều token hơn, cho thấy có động cơ tài chính đằng sau cuộc tấn công.

![Chức năng tự xuất bản](https://www.bleepstatic.com/images/news/u/1220909/2025/November/name-publish.jpg)

**Chức năng tự xuất bản**  
_Nguồn: Endor Labs_

Ngoài ra, Endor Labs báo cáo rằng chiến dịch spam thực tế đã bắt đầu cách đây hai năm, với 43,000 gói được thêm vào năm 2023, việc kiếm tiền bằng TEA được triển khai vào năm 2024, và vòng lặp sao chép giống sâu được giới thiệu vào năm 2025.

Chiến dịch IndonesianFoods xuất hiện trong bối cảnh một số cuộc tấn công chuỗi cung ứng dựa trên tự động hóa tương tự trên các hệ sinh thái mã nguồn mở, bao gồm cuộc tấn công GlassWorm trên OpenVSX, con sâu Shai-Hulud sử dụng lây lan thông qua dependency confusion, và việc chiếm đoạt các gói được sử dụng rộng rãi như chalk và debug.

Từng sự cố riêng lẻ đã gây [thiệt hại hạn chế](https://www.bleepingcomputer.com/news/security/hackers-left-empty-handed-after-massive-npm-supply-chain-attack/), nhưng chúng nhấn mạnh xu hướng mới nơi kẻ tấn công ngày càng khai thác tự động hóa và quy mô để làm cho các hệ sinh thái mã nguồn mở bị quá tải.

Sonatype cũng cảnh báo rằng những hoạt động đơn giản nhưng có tác động lớn này tạo điều kiện lý tưởng cho các tác nhân đe dọa lẻn vào các hệ sinh thái mã nguồn mở các phần mềm độc hại nghiêm trọng hơn.

Khi cuộc tấn công tiếp tục diễn ra, các nhà phát triển phần mềm được khuyên khoá phiên bản phụ thuộc, giám sát các mẫu xuất bản bất thường, và thực hiện các chính sách xác thực chữ ký số nghiêm ngặt.