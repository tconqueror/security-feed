# Tăng mạnh các lần quét nhắm vào cổng đăng nhập Palo Alto Networks

![Tăng mạnh các lần quét nhắm vào cổng đăng nhập Palo Alto Networks](https://www.bleepstatic.com/content/hl-images/2024/10/09/Palo-Alto-Networks.jpg)

Một đợt tăng đột biến các lần quét đáng ngờ nhắm vào cổng đăng nhập Palo Alto Networks cho thấy rõ nỗ lực trinh sát từ các địa chỉ IP đáng ngờ, các nhà nghiên cứu cảnh báo.

Công ty tình báo an ninh mạng GreyNoise báo cáo mức tăng 500% về số lượng địa chỉ IP tập trung vào các profile Palo Alto Networks GlobalProtect và PAN-OS.

Hoạt động đạt đỉnh vào ngày 3 tháng 10 với hơn 1.285 địa chỉ IP riêng biệt tham gia. Thông thường, các lần quét hàng ngày không vượt quá 200 địa chỉ, công ty cho biết.

Phần lớn các IP được quan sát được định vị ở United States, trong khi các cụm nhỏ hơn đặt tại United Kingdom, the Netherlands, Canada, và Russia.

Một cụm hoạt động tập trung lưu lượng vào các mục tiêu ở United States và một cụm khác tập trung vào Pakistan, các nhà nghiên cứu cho biết, lưu ý rằng cả hai có "dấu vân TLS riêng biệt nhưng không hoàn toàn tách biệt."

Theo GreyNoise, 91% địa chỉ IP được phân loại là đáng ngờ. Thêm 7% được gắn nhãn là độc hại.

"Gần như toàn bộ hoạt động được hướng tới các profile Palo Alto mô phỏng của GreyNoise (Palo Alto GlobalProtect, Palo Alto PAN-OS), cho thấy hoạt động mang tính có mục tiêu, có khả năng bắt nguồn từ các lần quét công khai (ví dụ, Shodan, Censys) hoặc các lần quét do kẻ tấn công khởi xướng dùng để nhận diện thiết bị Palo Alto," [giải thích bởi GreyNoise](https://www.greynoise.io/blog/palo-alto-scanning-surges).

![Palo Alto scanning activity](https://www.bleepstatic.com/images/news/u/1220909/2025/October/paloalto.jpg)

**Hoạt động quét Palo Alto**  
_Nguồn: GreyNoise_

GreyNoise [đã cảnh báo trước đó](https://www.bleepingcomputer.com/news/security/spikes-in-malicious-activity-precede-new-cves-in-80-percent-of-cases/) rằng hoạt động quét như vậy thường cho thấy sự chuẩn bị cho các cuộc tấn công sử dụng khai thác mới cho các lỗ hổng zero-day hoặc n-day.

Công ty an ninh mạng gần đây đã phát cảnh báo về các [lần quét mạng tăng cao](https://www.bleepingcomputer.com/news/security/surge-in-networks-scans-targeting-cisco-asa-devices-raise-concerns/) nhắm vào Cisco ASA devices. Hai tuần sau, xuất hiện tin tức về một [lỗ hổng zero-day](https://www.bleepingcomputer.com/news/security/cisco-warns-of-asa-firewall-zero-days-exploited-in-attacks/)[ bị khai thác trong các cuộc tấn công](https://www.bleepingcomputer.com/news/security/cisco-warns-of-asa-firewall-zero-days-exploited-in-attacks/) nhắm vào cùng sản phẩm Cisco.

Tuy nhiên, GreyNoise cho biết mối tương quan quan sát được yếu hơn đối với các lần quét gần đây tập trung vào sản phẩm của Palo Alto Networks.

## Grafana cũng bị nhắm mục tiêu

Các nhà nghiên cứu cũng nhận thấy sự gia tăng trong các nỗ lực khai thác một lỗ hổng path traversal cũ trên Grafana. Vấn đề bảo mật được xác định là CVE-2021-43798 và đã [bị khai thác vào tháng 12 năm 2021](https://www.bleepingcomputer.com/news/security/grafana-fixes-zero-day-vulnerability-after-exploits-spread-over-twitter/) trong các cuộc tấn công zero-day.

[GreyNoise quan sát](https://www.greynoise.io/blog/coordinated-grafana-exploitation-attempts) 110 địa chỉ IP độc hại riêng biệt, phần lớn trong số đó từ Bangladesh, phát động các cuộc tấn công vào ngày 28 tháng 9.

Các mục tiêu chủ yếu đặt tại United States, Slovakia, và Taiwan, với các cuộc tấn công duy trì tỷ lệ đích đến nhất quán tùy theo nguồn gốc cụ thể, điều này thường cho thấy tính tự động hóa.

![Observed activity](https://www.bleepstatic.com/images/news/u/1220909/2025/October/grafana-attacks.jpg)

**Các nỗ lực khai thác được quan sát**  
_Nguồn: GreyNoise_

Greynoise khuyến nghị quản trị viên đảm bảo các instance Grafana của họ đã được vá chống lại CVE-2021-43798 và chặn 110 địa chỉ IP độc hại đã được xác định.

Các nhà nghiên cứu cũng khuyên kiểm tra nhật ký để tìm bằng chứng các yêu cầu path traversal có thể trả về các tệp nhạy cảm.