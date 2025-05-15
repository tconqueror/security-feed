# Windows 11 và Red Hat Linux bị tấn công vào ngày đầu tiên của Pwn2Own

![Pwn2Own Berlin](https://www.bleepstatic.com/content/hl-images/2025/05/15/Pwn2Own_Berin.jpg)

Vào ngày đầu tiên của Pwn2Own Berlin 2025, các nhà nghiên cứu an ninh đã nhận được 260.000 đô la sau khi thành công trong việc chứng minh các lỗ hổng zero-day cho Windows 11, Red Hat Linux và Oracle VirtualBox.

Red Hat Enterprise Linux for Workstations là mục tiêu đầu tiên trong danh mục nâng cao quyền hạn cục bộ sau khi nhóm nghiên cứu DEVCORE, Pumpkin, khai thác một lỗ hổng tràn số nguyên để kiếm được 20.000 đô la.

Hyunwoo Kim và Wongi Lee cũng đã có quyền root trên một thiết bị Red Hat Linux bằng cách kết hợp một lỗ hổng use-after-free và một rò rỉ thông tin, nhưng một trong các lỗ hổng đã bị khai thác là một N-day, dẫn đến [sự va chạm của bug](https://x.com/thezdi/status/1922988072142000509).

Tiếp theo, Chen Le Qi của STARLabs SG đã nhận được 30.000 đô la cho một chuỗi khai thác kết hợp giữa use-after-free và tràn số nguyên để nâng cao quyền hạn lên SYSTEM trên hệ thống Windows 11.

Windows 11 đã bị tấn công thêm hai lần nữa để đạt được quyền SYSTEM bởi Marcin Wiązowski, người đã khai thác một lỗ hổng ghi ngoài giới hạn, và Hyeonjin Choi, người đã trình diễn một zero-day loại confusion.

Team Prison Break đã kiếm được 40.000 đô la sau khi trình diễn một chuỗi khai thác sử dụng tràn số nguyên để thoát khỏi Oracle VirtualBox và thực thi mã trên hệ điều hành cơ sở.

Sina Kheirkhah của Team Summoning được trao thêm 35.000 đô la cho một zero-day Chroma và một lỗ hổng đã biết trong Nvidia Triton Inference Server, trong khi Billy và Ramdhan từ STARLabs SG đã kiếm được 60.000 đô la cho việc thoát khỏi Docker Desktop và thực thi mã trên OS cơ sở bằng cách sử dụng một zero-day use-after-free.

![Bảng xếp hạng ngày đầu tiên của Pwn2Own Berlin 2025](https://www.bleepstatic.com/images/news/u/1109292/2025/Pwn2Own%20Berlin%202025%201st%20day%20leaderboard.jpg)

_Bảng xếp hạng ngày đầu tiên của Pwn2Own Berlin 2025 ([Trend Zero Day Initiative](https://x.com/thezdi/status/1923034127759970639))_

​​Cuộc thi hack Pwn2Own Berlin 2025, tập trung vào công nghệ doanh nghiệp và giới thiệu một danh mục AI, diễn ra tại Berlin từ ngày 15 đến ngày 17 tháng 5, trong khuôn khổ hội nghị [OffensiveCon](https://www.offensivecon.org/).

[Vào ngày thứ hai](https://www.zerodayinitiative.com/blog/2025/5/14/pwn2own-berlin-the-full-schedule#day2), các nhà nghiên cứu an ninh sẽ cố gắng khai thác các zero-day trong Microsoft SharePoint, VMware ESXi, Mozilla Firefox, Red Hat Enterprise Linux for Workstations và Oracle VirtualBox.

Sau khi các lỗ hổng zero-day được trình diễn và công bố trong Pwn2Own, các nhà cung cấp có 90 ngày để phát hành các bản sửa lỗi bảo mật cho phần mềm và sản phẩm phần cứng của họ.

Các thí sinh Pwn2Own sẽ nhắm đến các sản phẩm đã được vá hoàn toàn trong các danh mục AI, trình duyệt web, ảo hóa, nâng cao quyền hạn cục bộ, máy chủ, ứng dụng doanh nghiệp, cloud-native/container và ô tô, và sẽ có khả năng kiếm được hơn 1.000.000 đô la tiền mặt và giải thưởng.

Tuy nhiên, trong khi các đơn vị bench-top của Tesla Model 3 2024 và Tesla Model Y 2025 cũng có sẵn làm mục tiêu, không có nỗ lực nào được ghi nhận trước khi cuộc thi bắt đầu.