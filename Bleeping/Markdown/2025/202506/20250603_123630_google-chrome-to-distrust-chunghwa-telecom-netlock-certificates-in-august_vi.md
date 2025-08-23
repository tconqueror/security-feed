# Google Chrome sẽ không còn tin tưởng các chứng chỉ của Chunghwa Telecom, Netlock vào tháng Tám

![Chrome](https://www.bleepstatic.com/content/hl-images/2023/11/28/Google_Chrome.jpg)

Google thông báo rằng họ sẽ không còn tin tưởng các chứng chỉ CA gốc được ký bởi Chunghwa Telecom và Netlock trong Chrome Root Store do một loạt các vi phạm về tuân thủ và không cải thiện.

Sự thay đổi sẽ diễn ra trong phiên bản Google Chrome 139, dự kiến phát hành vào ngày 1 tháng 8 năm 2025.

Ông lớn công nghệ viện dẫn các vi phạm tuân thủ liên tục, cam kết cải thiện không thực hiện và thiếu tiến bộ đo lường là lý do cho hành động này.

"Niềm tin của Chrome vào độ tin cậy của Chunghwa Telecom và Netlock với tư cách là Chủ sở hữu CA có trong Chrome Root Store đã giảm sút do các mẫu hành vi đáng lo ngại được quan sát trong năm qua," [đọc thông báo](https://security.googleblog.com/2025/05/sustaining-digital-certificate-security-chrome-root-store-changes.html).

"Các mẫu này đại diện cho việc mất tính toàn vẹn và không đạt kỳ vọng, làm suy giảm lòng tin vào những Chủ sở hữu CA này như là những nhà phát hành chứng chỉ được tin cậy công khai theo mặc định trong Chrome."

Chunghwa Telecom là nhà cung cấp dịch vụ viễn thông lớn nhất Đài Loan, cung cấp dịch vụ internet, di động và cố định. Nó điều hành một Cơ quan Chứng nhận công cộng (CA) có tên là ePKI và HiPKI, phát hành các chứng chỉ số cho các giao tiếp web an toàn.

Netlock là nhà cung cấp lớn của Hungary về dịch vụ chứng nhận số (chữ ký điện tử, đánh dấu thời gian và chứng chỉ TLS/SSL), nổi bật với CA gốc Arany (Gold Class), rất được sử dụng ở Hungary và các quốc gia châu Âu khác.

Chrome Root Store là danh sách các cơ quan chứng nhận được Google duy trì và được Chrome sử dụng để xác thực các kết nối HTTPS.

Cả hai thực thể đã hoạt động như các Cơ quan Chứng nhận công khai (CAs) trong nhiều năm, với các chứng chỉ của họ có trong Chrome Root Store, có nghĩa là Chrome đã tin tưởng họ theo mặc định.

Bắt đầu từ ngày 1 tháng 8 năm 2025, Google Chrome sẽ hiển thị cảnh báo "Kết nối của bạn không an toàn" khi người dùng truy cập vào các trang web vẫn tiếp tục sử dụng các chứng chỉ được phát hành bởi Chunghwa Telecom hoặc Netlock, vì các CA gốc của họ sẽ không còn được tin tưởng nữa.

![Cảnh báo phát sinh trên các trang sử dụng chứng chỉ không được tin cậy](https://www.bleepstatic.com/images/news/u/1220909/2025/June/warning.jpg)

**Cảnh báo phát sinh trên các trang sử dụng chứng chỉ không được tin cậy**  
_Nguồn: Google_

Mặc dù có thể vượt qua trang đó, nhưng hành động này sẽ làm gián đoạn trải nghiệm duyệt web mượt mà trên các trang bị ảnh hưởng và tạo ra các vấn đề về lòng tin cho khách truy cập.

Vì lý do này, các quản trị viên web bị ảnh hưởng được khuyến nghị hành động ngay bây giờ và chuyển sang một CA được tin cậy càng sớm càng tốt.

Mặc dù các chứng chỉ của Netlock và Chunghwa Telecom được ký cho đến ngày 31 tháng 7 năm 2025 vẫn sẽ được tin tưởng, nhưng nên tránh hoãn việc thay thế không thể tránh khỏi của chúng.

Google lưu ý rằng các doanh nghiệp bị ảnh hưởng có thể ghi đè các thay đổi tin cậy bằng cách cài đặt các gốc bị ảnh hưởng như các gốc được tin cậy cục bộ.

Cần lưu ý rằng thay đổi này sẽ không ảnh hưởng đến Microsoft Edge, Mozilla Firefox hoặc Apple Safari, vì chúng sử dụng các kho tin cậy của trình duyệt khác.

Hành động gần đây này theo sau một hành động tương tự [chống lại Entrust](https://security.googleblog.com/2024/06/sustaining-digital-certificate-security.html), được công bố vào tháng 6 năm 2024 và có hiệu lực vào ngày 12 tháng 11 năm 2024.

Tại thời điểm đó, Google đã biện minh cho quyết định của mình bằng cách lưu ý rằng Entrust đã tham gia vào nhiều sự cố công khai được công bố cho thấy họ đã không đáp ứng các tiêu chuẩn tuân thủ và an ninh trong ngành kể từ năm 2018.

Tương tự, Entrust đã không thực hiện các cam kết cải thiện quy trình hoặc thể hiện tiến bộ có thể đo lường.

Vào tháng 3 năm 2025, Google thông báo về các [yêu cầu an ninh bắt buộc mới cho tất cả các CA](https://security.googleblog.com/2025/03/new-security-requirements-adopted-by.html) phát hành các chứng chỉ HTTPS/TLS công khai được tin tưởng, báo hiệu ý định của họ là thắt chặt các tiêu chuẩn và thúc đẩy các CA nhanh chóng đáp ứng các kỳ vọng tuân thủ đang phát triển.

Các trường hợp của Chunghwa Telecom và Netlock là những ví dụ đầu tiên về việc thực thi những yêu cầu nghiêm ngặt hơn đó, và có khả năng sẽ có nhiều trường hợp tương tự trong tương lai.