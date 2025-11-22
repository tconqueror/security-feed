# Lỗ hổng API của WhatsApp cho phép các nhà nghiên cứu thu thập 3,5 tỷ tài khoản

![WhatsApp](https://www.bleepstatic.com/content/hl-images/2022/05/31/WhatsApp.jpg)

Các nhà nghiên cứu đã biên soạn một danh sách gồm 3,5 tỷ số điện thoại di động WhatsApp và thông tin cá nhân liên quan bằng cách lạm dụng một contact-discovery API thiếu cơ chế giới hạn tốc độ.

Nhóm đã báo cáo vấn đề cho WhatsApp, và công ty kể từ đó đã bổ sung các cơ chế giới hạn tốc độ để ngăn chặn lạm dụng tương tự.

Mặc dù nghiên cứu này được tiến hành bởi các nhà nghiên cứu không công bố dữ liệu, nó minh họa một chiến thuật phổ biến mà các tác nhân đe dọa sử dụng để thu thập thông tin người dùng từ các API bị công khai và không được bảo vệ.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

## Lạm dụng API của WhatsApp

Các nhà nghiên cứu từ University of Vienna và SBA Research đã sử dụng tính năng khám phá liên hệ của WhatsApp, cho phép bạn gửi một số điện thoại tới endpoint `GetDeviceList` của API nền tảng để xác định xem một số điện thoại có liên kết với tài khoản hay các thiết bị đã được sử dụng.

Nếu không có cơ chế giới hạn tốc độ chặt chẽ, các API như vậy có thể bị lạm dụng để thực hiện việc liệt kê quy mô lớn trên một nền tảng.

Nhóm nghiên cứu nhận thấy điều này đúng với WhatsApp, khi họ có thể gửi khối lượng lớn các truy vấn trực tiếp tới máy chủ của WhatsApp, kiểm tra hơn 100 triệu số mỗi giờ.

Họ vận hành toàn bộ hoạt động từ một máy chủ đại học duy nhất chỉ dùng năm phiên đã xác thực, ban đầu dự đoán sẽ bị WhatsApp phát hiện. Tuy nhiên, nền tảng không bao giờ chặn các tài khoản, không bao giờ hạn chế lưu lượng của họ, không bao giờ chặn địa chỉ IP và không hề liên hệ mặc dù toàn bộ hoạt động lạm dụng xuất phát từ một thiết bị.

Nhóm nghiên cứu sau đó sinh ra một tập hợp toàn cầu gồm 63 tỷ số di động khả dĩ và kiểm tra tất cả chúng với API. Các truy vấn của họ trả về 3,5 tỷ tài khoản WhatsApp hoạt động.

Kết quả cũng cung cấp một ảnh chụp nhanh chưa từng biết trước về cách WhatsApp được sử dụng trên toàn cầu, cho thấy nơi nền tảng được sử dụng nhiều nhất:

* **India:** 749 million
* **Indonesia:** 235 million
* **Brazil:** 206 million
* **United States:** 138 million
* **Russia:** 133 million
* **Mexico:** 128 million

Hàng triệu tài khoản hoạt động cũng được xác định bên trong các quốc gia nơi WhatsApp bị cấm vào thời điểm đó, bao gồm China, Iran, North Korea và Myanmar. Ở Iran, mức sử dụng tiếp tục tăng khi lệnh cấm được gỡ vào tháng 12 năm 2024.

Ngoài việc xác nhận xem một số điện thoại có được sử dụng trên WhatsApp hay không, các nhà nghiên cứu đã sử dụng các endpoint API khác để liệt kê thêm thông tin về người dùng, bao gồm `[GetUserInfo](https://pkg.go.dev/go.mau.fi/whatsmeow)`, `GetPrekeys`, và `FetchPicture`.

Sử dụng các API bổ sung này, các nhà nghiên cứu đã có thể thu thập ảnh hồ sơ, văn bản "about", và thông tin về các thiết bị khác liên kết với một số điện thoại WhatsApp.

Một thử nghiệm với các số của US đã tải về 77 triệu ảnh hồ sơ mà không có bất kỳ giới hạn tốc độ nào, với nhiều ảnh hiển thị khuôn mặt có thể nhận diện. Nếu văn bản "about" công khai có sẵn, nó cũng tiết lộ chi tiết cá nhân và các liên kết tới các tài khoản xã hội khác.

Cuối cùng, khi các nhà nghiên cứu so sánh phát hiện của họ với vụ rò rỉ số điện thoại Facebook năm 2021, họ nhận thấy rằng 58% số bị rò rỉ từ Facebook vẫn còn hoạt động trên WhatsApp vào năm 2025. Các nhà nghiên cứu giải thích rằng các vụ rò rỉ số điện thoại quy mô lớn gây hại vì chúng có thể hữu dụng cho các hành vi độc hại khác trong nhiều năm.

"With 3.5 B records (i.e., active accounts), we analyze a dataset that would, to our knowledge, classify as the largest data leak in history, had it not been collated as part of a responsibly-conducted research study," giải thích bài báo "[Hey there! You are using WhatsApp: Enumerating Three Billion Accounts for Security and Privacy](https://github.com/sbaresearch/whatsapp-census/blob/main/Hey%5Fthere%5FYou%5Fare%5Fusing%5FWhatsApp.pdf)".

"The dataset contains phone numbers, timestamps, about text, profile pictures, and public keys for E2EE encryption, and its release would entail adverse implications to the included users." — đoạn trích trên nhấn mạnh rằng việc phát hành sẽ gây hậu quả bất lợi cho những người dùng có trong tập dữ liệu.

## Các trường hợp lạm dụng API độc hại khác

Việc thiếu giới hạn tốc độ cho các API của WhatsApp minh họa cho một vấn đề phổ biến trên các nền tảng trực tuyến, nơi các API được thiết kế để dễ chia sẻ thông tin và thực hiện tác vụ, nhưng đồng thời cũng trở thành kênh cho việc thu thập dữ liệu quy mô lớn.

Năm 2021, các tác nhân đe dọa đã lợi dụng một lỗi trong tính năng "Add Friend" của Facebook cho phép họ tải lên danh sách liên hệ từ điện thoại và kiểm tra xem các liên hệ đó có trên nền tảng hay không. Tuy nhiên, API này cũng không giới hạn đúng mức các yêu cầu, cho phép các tác nhân tạo hồ sơ cho 533 triệu người dùng bao gồm số điện thoại, Facebook IDs, tên và giới tính.

Meta sau đó đã xác nhận rằng dữ liệu xuất phát từ việc thu thập tự động một API thiếu biện pháp bảo vệ thích hợp, với Irish Data Protection Commission (DPC) phạt Meta €265 million về vụ rò rỉ.

Twitter gặp vấn đề tương tự khi kẻ tấn công khai thác một lỗ hổng API để đối chiếu số điện thoại và địa chỉ email với 54 triệu tài khoản.

Dell cũng tiết lộ rằng 49 triệu hồ sơ khách hàng bị thu thập sau khi kẻ tấn công lạm dụng một endpoint API không được bảo vệ.

Tất cả những sự cố này, bao gồm vụ của WhatsApp, đều do các API thực hiện tra cứu tài khoản hoặc dữ liệu mà không có giới hạn tốc độ thích hợp, khiến chúng trở thành mục tiêu dễ bị liệt kê quy mô lớn.