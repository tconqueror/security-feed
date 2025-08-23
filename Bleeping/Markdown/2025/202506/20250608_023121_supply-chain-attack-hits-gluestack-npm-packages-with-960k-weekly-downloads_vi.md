# Cuộc tấn công chuỗi cung ứng ảnh hưởng đến các gói NPM Gluestack với 960K lượt tải hàng tuần

![NPM](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_logo_headpic.jpg)

Một cuộc tấn công chuỗi cung ứng đáng kể đã ảnh hưởng đến NPM sau khi 16 gói Gluestack 'react-native-aria' phổ biến với hơn 950.000 lượt tải hàng tuần bị xâm nhập để chứa mã độc hoạt động như một trojan truy cập từ xa (RAT).

BleepingComputer xác định rằng vụ xâm nhập bắt đầu vào ngày 6 tháng 6 lúc 4:33 PM EST, khi một phiên bản mới của gói react-native-aria/focus được công bố trên NPM. Kể từ đó, 16 trong số 20 gói Gluestack [react-native-aria packages](https://www.npmjs.com/org/react-native-aria) đã bị xâm nhập trên NPM, với các tác nhân đe dọa phát hành một phiên bản mới gần đây nhất chỉ cách đây hai giờ.

![Xâm nhập liên tục của các gói NPM](https://www.bleepstatic.com/images/news/security/g/gluestack/npm-supply-chain-attack/gluestack-2-hours.jpg)

**Xâm nhập liên tục của các gói NPM**  
_Nguồn: BleepingComputer_

Cuộc tấn công chuỗi cung ứng đã được phát hiện bởi công ty an ninh mạng [Aikido Security,](https://www.aikido.dev/) những người đã phát hiện ra mã bị làm mờ được tiêm vào tệp `lib/index.js` cho các gói sau:

| **Tên gói**                   | **Phiên bản** | **Lượt tải hàng tuần** |
| ------------------------------ | ----------- | -------------------- |
| react-native-aria/button       | 0.2.11      | 51.000               |
| react-native-aria/checkbox     | 0.2.11      | 81.000               |
| react-native-aria/combobox     | 0.2.10      | 51.000               |
| react-native-aria/disclosure   | 0.2.9       | 3                    |
| react-native-aria/focus        | 0.2.10      | 100.000              |
| react-native-aria/interactions | 0.2.17      | 125.000              |
| react-native-aria/listbox      | 0.2.10      | 51.000               |
| react-native-aria/menu         | 0.2.16      | 22.000               |
| react-native-aria/overlays     | 0.3.16      | 96.000               |
| react-native-aria/radio        | 0.2.14      | 78.000               |
| react-native-aria/switch       | 0.2.5       | 477                  |
| react-native-aria/toggle       | 0.2.12      | 81.000               |
| react-native-aria/utils        | 0.2.13      | 120.000              |
| gluestack-ui/utils             | 0.1.17      | 55.000               |
| react-native-aria/separator    | 0.2.7       | 65                   |
| react-native-aria/slider       | 0.2.13      | 51.000               |

Những gói này rất phổ biến với khoảng 960.000 lượt tải hàng tuần, biến cuộc tấn công chuỗi cung ứng này thành một vụ việc có hậu quả rộng rãi.

Mã độc đã bị làm mờ một cách nặng nề và được thêm vào dòng cuối cùng của mã nguồn trong tệp, được lót bằng nhiều khoảng trắng, vì vậy nó không dễ bị phát hiện khi sử dụng trình xem mã trên trang NPM.

![Mã độc được thêm vào cuối tệp index.js](https://www.bleepstatic.com/images/news/security/g/gluestack/npm-supply-chain-attack/gluestack-compromise.jpg)

**Mã độc được thêm vào cuối tệp index.js**  
_Nguồn: BleepingComputer_

Aikido đã thông báo với BleepingComputer rằng mã độc gần như giống hệt một trojan truy cập từ xa trong [một vụ xâm nhập NPM khác mà họ phát hiện](https://www.aikido.dev/blog/catching-a-rat-remote-access-trojian-rand-user-agent-supply-chain-compromise) vào tháng trước.

Phân tích của các nhà nghiên cứu về chiến dịch trước đó giải thích rằng trojan truy cập từ xa sẽ kết nối với máy chủ chỉ huy và điều khiển của kẻ tấn công và nhận lệnh để thực thi.

Các lệnh này bao gồm:

* **cd -** Thay đổi thư mục làm việc hiện tại
* **ss\_dir -** Đặt lại thư mục về đường dẫn của tập lệnh
* **ss\_fcd:<path>** \- Buộc thay đổi thư mục đến <path>
* **ss\_upf:f,d -** Tải lên một tệp đơn f đến đích d
* **ss\_upd:d,dest -** Tải lên tất cả các tệp trong thư mục d đến đích dest
* **ss\_stop -** Đặt một cờ dừng để ngắt quy trình tải lên hiện tại
* **Bất kỳ đầu vào nào khác -** Được xử lý như một lệnh shell, thực thi qua child\_process.exec()

Trojan cũng thực hiện việc đánh cắp PATH Windows bằng cách thêm một đường dẫn Python giả (%LOCALAPPDATA%\\Programs\\Python\\Python3127) vào biến môi trường PATH, cho phép mã độc im lặng thay thế các lệnh python hoặc pip hợp pháp để thực thi các tệp nhị phân độc hại.

Nhà nghiên cứu an ninh Aikido, Charlie Eriksen đã cố gắng liên lạc với Gluestack về vụ xâm nhập bằng cách tạo [các vấn đề trên GitHub](https://github.com/gluestack/gluestack-ui/issues/2894) trên mỗi kho dự án, nhưng hiện tại không nhận được phản hồi.

"Không nhận được phản hồi từ những người duy trì gói (hiện là sáng thứ bảy ở Mỹ, có lẽ chính vì lý do này mà nó đang xảy ra)," Arkido nói với BleepingComputer.

"NPM, chúng tôi đã liên lạc và báo cáo mỗi gói, quy trình này thường mất vài ngày để NPM giải quyết."

Aikido cũng quy attribut cuộc tấn công này cho các tác nhân đe dọa tương tự đã xâm nhập vào bốn gói NPM khác vào đầu tuần này mang tên _biatec-avm-gas-station_, _cputil-node_, _lfwfinance/sdk_, và _lfwfinance/sdk-dev_.

BleepingComputer đã liên lạc với Gluestack về các gói bị xâm nhập nhưng hiện tại vẫn chưa nhận được phản hồi.