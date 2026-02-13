# Chuyển đổi Cảnh báo IBM QRadar thành Hành động với Criminal IP

![Tích hợp Criminal IP + IBM QRadar](https://www.bleepstatic.com/content/posts/2026/02/11/criminal-ip-ibm.jpg)

Criminal IP (criminalip.io), nền tảng thông tin đe dọa và thông tin bề mặt tấn công được hỗ trợ bởi AI, hiện đã được tích hợp với IBM QRadar SIEM và QRadar SOAR.

Việc tích hợp mang thông tin đe dọa dựa trên IP bên ngoài trực tiếp vào các luồng công việc phát hiện, điều tra và phản hồi của IBM QRadar, cho phép các nhóm bảo mật xác định hoạt động độc hại nhanh hơn và ưu tiên các hành động phản hồi hiệu quả hơn trên các hoạt động SOC.

IBM QRadar được các tổ chức doanh nghiệp và khu vực công áp dụng rộng rãi như một nền tảng trung tâm cho giám sát bảo mật, tự động hóa và phản hồi sự cố.

Bằng cách nhúng thông tin tình báo Criminal IP vào QRadar SIEM và mở rộng nó vào các luồng công việc SOAR, các tổ chức có thể áp dụng ngữ cảnh đe dọa bên ngoài trong suốt vòng đời sự cố mà không cần rời khỏi môi trường QRadar.

## Tầm nhìn về Mối đe dọa Thời gian thực từ Nhật ký Lưu lượng Tường lửa

Với việc tích hợp Criminal IP QRadar SIEM, các nhóm bảo mật có thể phân tích nhật ký lưu lượng tường lửa và tự động đánh giá rủi ro liên quan đến các địa chỉ IP liên lạc.

Dữ liệu lưu lượng được chuyển tiếp vào IBM QRadar SIEM được phân tích thông qua API Criminal IP và phản ánh trực tiếp trong giao diện SIEM.

Các địa chỉ IP được quan sát được tự động phân loại thành các mức độ rủi ro Cao, Trung bình hoặc Thấp từ quan điểm thông tin đe dọa.

Điều này cho phép các nhóm SOC nhanh chóng xác định các IP có rủi ro cao, giám sát lưu lượng vào và ra, và ưu tiên các hành động phản hồi như chặn truy cập hoặc thăng cấp trong luồng công việc QRadar SIEM quen thuộc.

## [Thử Criminal IP để phát hiện và phản hồi các mối đe dọa mới nổi](https://www.criminalip.io/contact-us)

Truy cập Thông tin đe dọa Criminal IP cần thiết để chủ động xác định, phân tích và phản hồi các mối đe dọa mới nổi.

Được hỗ trợ bởi AI và OSINT, nó cung cấp điểm đe dọa, dữ liệu danh tiếng, và phát hiện thời gian thực của một loạt các chỉ số độc hại, từ máy chủ C2 và IOCs đến các dịch vụ ẩn danh như VPN, proxy, và VPN ẩn danh, trên các IP, miền và URL. Kiến trúc hướng API của nó đảm bảo tích hợp liền mạch vào các luồng công việc bảo mật để tăng cường khả năng hiển thị, tự động hóa và phản hồi.

[Yêu cầu Demo của bạn](https://www.criminalip.io/contact-us)

## Điều tra Tương tác mà Không Cần Rời khỏi QRadar

![Việc tra cứu Criminal IP tích hợp trong IBM QRadar SIEM cho phép các nhà phân tích điều tra các IP đáng ngờ trực tiếp từ nhật ký lưu lượng.](https://www.bleepstatic.com/images/news/security/c/criminal-ip/ibm-qradar/criminal-ip-integrated-ibm-qradar.jpg)

**Việc tra cứu Criminal IP tích hợp trong IBM QRadar SIEM cho phép các nhà phân tích điều tra các IP đáng ngờ trực tiếp từ nhật ký lưu lượng.**

Ngoài khả năng hiển thị cấp cao, việc tích hợp hỗ trợ điều tra nhanh chóng trong ngữ cảnh. Các nhà phân tích có thể nhấp chuột phải vào các địa chỉ IP hiển thị trong QRadar Log Activity để mở báo cáo IP chi tiết của Criminal IP.

Các báo cáo này cung cấp ngữ cảnh bổ sung, bao gồm các chỉ số đe dọa, hành vi lịch sử, và tín hiệu phơi bày bên ngoài, cho phép các nhà phân tích xác minh rủi ro và ý định mà không cần chuyển đổi công cụ. Luồng công việc được hợp lý hóa này hỗ trợ ra quyết định nhanh hơn trong quá trình điều tra nhạy cảm về thời gian.

## Mở rộng Thông tin tình báo vào Các Luồng công việc QRadar SOAR

Criminal IP cũng được tích hợp với IBM QRadar SOAR để hỗ trợ bổ sung mối đe dọa tự động trong quá trình phản hồi sự cố. Sử dụng các playbook được xây dựng sẵn, thông tin tình báo Criminal IP có thể được áp dụng cho các hiện vật địa chỉ IP và URL, với kết quả bổ sung được trả về trực tiếp vào các trường hợp SOAR dưới dạng hiện vật trúng hoặc ghi chú sự cố.

Việc tích hợp này bao gồm hai playbook:

* **Criminal IP: IP Threat Service** – Bổ sung các hiện vật địa chỉ IP với ngữ cảnh đe dọa Criminal IP.
* **Criminal IP: URL Threat Service** – Thực hiện quét URL nhẹ hoặc đầy đủ và trả về kết quả dưới dạng hiện vật trúng hoặc ghi chú sự cố.

Bằng cách nhúng thông tin tình báo đe dọa Criminal IP trực tiếp vào các luồng công việc SOAR, các nhà phân tích có thể giảm tra cứu thủ công và phản hồi các sự cố hiệu quả hơn.

## Nâng cao Khả năng Phát hiện và Phản hồi Dựa trên Thông tin tình báo

Bằng cách tích hợp Criminal IP với IBM QRadar SIEM và SOAR, các tổ chức có thể kết hợp khả năng tương quan, điều tra và phản hồi của QRadar với thông tin tình báo đe dọa bên ngoài giàu ngữ cảnh được rút ra từ phơi bày internet thực tế.

Cách tiếp cận này cải thiện độ chính xác phát hiện, rút ngắn chu kỳ điều tra, và tăng cường ưu tiên phản hồi trên các hoạt động SOC.

Khi khối lượng cảnh báo tiếp tục tăng, Criminal IP giúp người dùng QRadar đưa ra quyết định nhanh hơn và sáng suốt hơn bằng cách mang ngữ cảnh đe dọa bên ngoài trực tiếp vào các luồng công việc SIEM và SOAR mà không thêm phức tạp vận hành.

Giám đốc điều hành AI SPERA Byungtak Kang nhận xét rằng việc tích hợp nhấn mạnh tầm quan trọng ngày càng tăng của thông tin tình báo phơi bày thời gian thực trong môi trường SOC hiện đại và nhấn mạnh trọng tâm của Criminal IP vào việc cải thiện độ tin cậy phát hiện và hiệu quả vận hành thông qua các tích hợp dựa trên thông tin tình báo thực tế.

## Về Criminal IP

[Criminal IP](https://www.criminalip.io/ko?mtm%5Fcampaign=PaloAlto%20Integration&mtm%5Fkwd=PaloAlto&mtm%5Fsource=bleepingcomputer%20%2F%20cybernewswire&mtm%5Fmedium=press) là nền tảng thông tin tình báo mối đe dọa mạng hàng đầu được phát triển bởi AI SPERA và được sử dụng tại hơn 150 quốc gia trên toàn thế giới. Nó trang bị cho các nhóm bảo mật Thông tin đe dọa có thể hành động cần thiết để chủ động xác định, phân tích và phản hồi các mối đe dọa mới nổi.

Được hỗ trợ bởi AI và OSINT, nó cung cấp điểm đe dọa, dữ liệu danh tiếng, và phát hiện thời gian thực của một loạt các chỉ số độc hại, từ máy chủ C2 và IOCs đến các dịch vụ ẩn danh như VPN, proxy, và VPN ẩn danh, trên các IP, miền và URL.

Kiến trúc hướng API của nó đảm bảo tích hợp liền mạch vào các luồng công việc bảo mật để tăng cường khả năng hiển thị, tự động hóa và phản hồi.

_Được tài trợ và viết bởi [Criminal IP](https://www.criminalip.io/ko?mtm%5Fcampaign=PaloAlto%20Integration&mtm%5Fkwd=PaloAlto&mtm%5Fsource=bleepingcomputer%20%2F%20cybernewswire&mtm%5Fmedium=press)._