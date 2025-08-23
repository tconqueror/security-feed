# Co-op xác nhận dữ liệu của 6.5 triệu thành viên bị đánh cắp trong cuộc tấn công mạng

![Co-op](https://www.bleepstatic.com/content/hl-images/2025/04/30/co-op.jpg)

Nhà bán lẻ Co-op ở Vương quốc Anh đã xác nhận rằng dữ liệu cá nhân của 6.5 triệu thành viên đã bị đánh cắp trong cuộc tấn công mạng lớn vào tháng 4, khiến các hệ thống bị tê liệt và gây ra tình trạng thiếu thực phẩm tại các cửa hàng tạp hóa của họ.

Co-op (viết tắt của Cooperative Group) là một trong những hợp tác xã tiêu dùng lớn nhất tại Vương quốc Anh, hoạt động trong các lĩnh vực cửa hàng thực phẩm, dịch vụ an táng, bảo hiểm và dịch vụ pháp lý. Nó thuộc sở hữu của hàng triệu thành viên, những người nhận được chiết khấu cho các dịch vụ và tham gia vào quản trị công ty.

Giám đốc điều hành của Co-op, Shirine Khoury-Haq, đã xin lỗi hôm nay trên chương trình BBC Breakfast, xác nhận rằng các kẻ tấn công đã thành công trong việc đánh cắp dữ liệu của tất cả 6.5 triệu thành viên.

"Dữ liệu của họ đã bị sao chép, và bọn tội phạm đã có quyền truy cập vào nó như khi họ tấn công các tổ chức khác. Đó thật sự là phần tồi tệ trong việc này, thật không may," Khoury-Haq cho biết.

Mặc dù không có thông tin tài chính hay giao dịch nào bị phơi bày trong cuộc tấn công, nhưng thông tin liên lạc của các thành viên đã bị đánh cắp.

Giám đốc điều hành cho biết sự cố này cảm thấy như một cuộc tấn công cá nhân, không phải nhằm vào bà, mà là nhằm vào các thành viên và nhân viên của Co-op bị ảnh hưởng.

"Và đây không phải về tôi. Đó là các đồng nghiệp của tôi. Nó có ý nghĩa cá nhân với tôi vì điều đó đã làm tổn thương họ. Nó làm tổn thương các thành viên của tôi. Họ đã lấy dữ liệu của họ và điều đó làm tổn thương khách hàng của chúng tôi, và tôi thực sự lấy điều đó một cách cá nhân," bà giải thích trong cuộc phỏng vấn.

[Cuộc tấn công mạng xảy ra vào tháng 4](https://www.bleepingcomputer.com/news/security/uk-retailer-co-op-shuts-down-some-it-systems-after-hack-attempt/), buộc Co-op phải đóng cửa một số hệ thống CNTT để ngăn chặn các tác nhân đe dọa lan rộng đến các thiết bị và cuối cùng triển khai trình mã hóa ransomware DragonForce.

Ban đầu được đánh giá thấp như một cuộc xâm nhập vào mạng của mình, [công ty đã xác nhận sau đó](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/) rằng một lượng "đáng kể" dữ liệu đã được truy cập và đánh cắp trong cuộc tấn công.

Các nguồn tin cho biết với BleepingComputer vào thời điểm đó rằng sự cố này xảy ra ban đầu vào ngày 22 tháng 4, sau khi các tác nhân đe dọa thực hiện một cuộc tấn công kỹ thuật xã hội cho phép họ đặt lại mật khẩu của một nhân viên.

Khi họ có được quyền truy cập vào mạng, họ đã lan rộng đến các thiết bị khác và cuối cùng đã lấy cắp tệp Windows NTDS.dit của miền Windows. Tệp này là cơ sở dữ liệu cho Dịch vụ Active Directory của Windows, chứa các băm mật khẩu cho các tài khoản Windows.

Các tác nhân đe dọa thường đánh cắp tệp này để lấy và bẻ khóa mật khẩu ngoại tuyến, cho phép họ tiếp tục lan rộng đến các thiết bị khác trên mạng.

BleepingComputer được cho biết rằng cuộc tấn công này liên quan đến các tác nhân đe dọa có liên quan đến Scattered Spider, những người đã liên quan đến cuộc tấn công [Marks & Spencer (M&S)](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/) mà ransomware DragonForce đã được triển khai.

BBC báo cáo rằng họ đã nói chuyện với nhà điều hành ransomware DragonForce về Co-op, người đã xác nhận rằng một trong những liên kết của họ đứng sau cuộc tấn công này. Họ cũng đã chia sẻ mẫu dữ liệu với BBC, tuyên bố rằng dữ liệu doanh nghiệp và khách hàng của Co-op đã bị đánh cắp trong cuộc tấn công.

Tuần trước, Cơ quan Tội phạm Quốc gia Vương quốc Anh (NCA) [đã bắt giữ bốn người](https://www.bleepingcomputer.com/news/security/four-arrested-in-uk-over-mands-co-op-harrods-cyberattacks/) nghi ngờ có liên quan đến các cuộc tấn công vào Co-op, M&S, và một cuộc tấn công chưa thành công vào [Harrods](https://www.bleepingcomputer.com/news/security/harrods-the-next-uk-retailer-targeted-in-a-cyberattack/).

Các cá nhân bị bắt giữ là hai nam giới 19 tuổi, một nam thanh niên 17 tuổi và một nữ 20 tuổi, đã bị bắt giữ ở London và West Midlands.

Có [báo cáo](https://krebsonsecurity.com/) rằng một trong những nghi phạm đã bị bắt có liên quan đến một [cuộc tấn công năm 2023 vào MGM Resorts](https://www.bleepingcomputer.com/news/security/mgm-resorts-shuts-down-it-systems-after-cyberattack/) đã dẫn đến [việc mã hóa hơn 100 máy ảo VMware ESXi](https://www.bleepingcomputer.com/news/security/mgm-casinos-esxi-servers-allegedly-encrypted-in-ransomware-attack/).

Cuộc tấn công vào MGM cũng được quy cho Scattered Spider, người đã làm việc với hoạt động ransomware BlackCat vào thời điểm đó.