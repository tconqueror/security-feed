# North Korean Lazarus hackers targeted European defense companies

![North Korean Lazarus hackers targeted European defense companies](https://www.bleepstatic.com/content/hl-images/2024/11/13/Lazarus.jpg)

Nhóm tin tặc North Korean Lazarus đã xâm nhập ba công ty châu Âu trong lĩnh vực quốc phòng thông qua một chiến dịch phối hợp Operation DreamJob lợi dụng chiêu dụ tuyển dụng giả mạo.

Hoạt động của nhóm mối đe dọa này được phát hiện vào cuối tháng Ba và nhắm tới các tổ chức tham gia phát triển công nghệ thiết bị bay không người lái (UAV).

‘Operation DreamJob’ là một chiến dịch kéo dài của Lazarus, trong đó kẻ tấn công, đóng vai một nhà tuyển dụng tại một công ty lớn (thật hoặc giả), tiếp cận nhân viên tại một tổ chức mục tiêu với lời mời làm việc cho một vị trí nổi bật.

Các nạn nhân bị lừa tải về các tập tin độc hại cho phép tin tặc truy cập vào hệ thống của công ty mục tiêu.

Kỹ thuật này từng được sử dụng trước đây chống lại các công ty tiền điện tử và DeFi, các nhà phát triển phần mềm, nhà báo, các nhà nghiên cứu an ninh, và cả các tổ chức trong lĩnh vực phòng thủ, bao gồm ngành hàng không vũ trụ.

Các nhà nghiên cứu tại công ty an ninh mạng ESET cho biết trong phiên bản Operation DreamJob gần đây nhất mà họ phân tích, Lazarus tập trung vào công nghệ liên quan đến UAV, điều này phù hợp với diễn biến địa-chính trị hiện tại và trùng khớp với nỗ lực gia tăng của Bắc Triều Tiên trong việc xây dựng kho vũ khí drone “lấy cảm hứng” từ các thiết kế phương Tây.

### Nhắm đến các nhà sản xuất linh kiện drone

ESET quan sát thấy vào cuối tháng Ba rằng “các cuộc tấn công DreamJob ngoài thực địa đã liên tiếp nhắm tới” một công ty kỹ thuật kim loại ở Tây Nam châu Âu, một nhà sản xuất phụ tùng máy bay, và một công ty quốc phòng, cả hai ở Trung Âu.

Tuy nhiên, công ty an ninh mạng không cung cấp chi tiết về mức độ thành công mà tin tặc đạt được khi nhắm vào ba công ty này.

Cả ba công ty đều sản xuất thiết bị quân sự đang được triển khai ở Ukraine như một phần của hỗ trợ quân sự từ các nước của họ.

Hai trong số đó, tuy nhiên, “rõ ràng tham gia vào phát triển công nghệ UAV, một công ty sản xuất các linh kiện drone quan trọng và công ty còn lại được cho là tham gia thiết kế phần mềm liên quan đến UAV.”

Khi phân tích chuỗi nhiễm, các nhà nghiên cứu phát hiện nó bắt đầu bằng việc nạn nhân khởi chạy một ứng dụng mã nguồn mở hoặc plugin đã bị trojan hóa, chẳng hạn như MuPDF viewer, Notepad++, WinMerge plugins, TightVNC Viewer, libpcre, và DirectX wrappers.

Việc tải DLL trojan hóa hoặc malware dropper được thực hiện thông qua DLL sideloading, một kỹ thuật né tránh dùng phần mềm hợp pháp nhưng có lỗ hổng để tải payload độc hại.

Ở giai đoạn tiếp theo, payload được giải mã và nạp trực tiếp vào bộ nhớ bằng các routines kiểu MemoryModule.

Mã độc giai đoạn cuối là ScoringMathTea RAT (Remote Access Trojan), thiết lập liên lạc với hạ tầng command-and-control (C2) và chờ lệnh.

Trong một chuỗi nhiễm thay thế, một loader mã độc có tên BinMergeLoader (MISTPEN) được sử dụng thay vì RAT, loader này lạm dụng Microsoft Graph API và tokens để tải thêm payload.

![Two attack chains used in the campaign](https://www.bleepstatic.com/images/news/u/1220909/2025/October/infection-chain(1).jpg)

**Hai chuỗi tấn công được sử dụng trong chiến dịch**  
_Nguồn: ESET_

ScoringMathTea RAT, được ghi nhận lần đầu vào năm 2023, hỗ trợ 40 lệnh trong phiên bản mới nhất, cho phép kẻ tấn công có phạm vi hoạt động rộng, từ thực thi lệnh đến thả mã độc mới.

“Chức năng được triển khai là những tính năng thường thấy mà Lazarus yêu cầu: thao tác tập tin và tiến trình, trao đổi cấu hình, thu thập thông tin hệ thống nạn nhân, mở kết nối TCP, và thực thi lệnh cục bộ hoặc payload mới được tải xuống từ server C&C,” ESET giải thích.

ESET nhận xét rằng mặc dù các thủ thuật Operation DreamJob và các chiêu xã hội kỹ thuật lừa đảo đã nhiều lần bị phơi bày qua các báo cáo, nhưng nó vẫn tiếp tục là một modus operandi hiệu quả đối với các tác nhân mối đe dọa từ Bắc Triều Tiên.

Công ty an ninh mạng cung cấp một bộ chỉ số xâm nhập (indicators of compromise) rộng rãi cho các tên miền và công cụ độc hại mà Lazarus đã sử dụng trong chiến dịch DreamJob nhắm vào các tổ chức châu Âu trong lĩnh vực quốc phòng.