# Google sẽ gắn cờ các ứng dụng Android tiêu thụ pin quá mức trên Google Play

![Android](https://www.bleepstatic.com/content/hl-images/2024/02/08/Android.jpg)

Google sẽ bắt đầu có hành động đối với các ứng dụng Android trên cửa hàng chính thức Google Play có hoạt động nền cao và gây tiêu hao pin quá mức.

Các ứng dụng vượt qua "ngưỡng hành vi xấu" có thể bị gắn cờ trên Google Play vì ảnh hưởng tiêu cực đến hiệu năng pin và có thể ảnh hưởng đến khả năng hiển thị của chúng trong hệ sinh thái Android.

Các nhà phát triển có thời hạn đến 1 tháng 3 năm 2026 để cập nhật ứng dụng của họ nhằm tuân thủ một chỉ số cốt lõi mới của Android Vitals gọi là "excessive partial wake locks."

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Thuật toán đã ở trạng thái beta kể từ ngày 14 tháng 4, và Google đã phát triển nó hợp tác chặt chẽ với Samsung.

"Đây là chỉ số đầu tiên trong một loạt các chỉ số mới được thiết kế để cung cấp cái nhìn sâu hơn về việc sử dụng tài nguyên của ứng dụng của bạn, cho phép bạn cải thiện trải nghiệm cho người dùng trên toàn bộ hệ sinh thái Android," Google [đã thông báo](http://android-developers.googleblog.com/2025/11/raising-bar-on-battery-performance.html).

Các ứng dụng vượt quá ngưỡng hành vi xấu đối với excessive wake locks có thể bị gắn cờ là những ứng dụng tiêu hao pin trên Google Play và có thể bị loại khỏi "các bề mặt khám phá nổi bật như khuyến nghị."

![Warning displayed on Google Play](https://www.bleepstatic.com/images/news/u/1220909/2025/November/image3_new.jpg)

**Cảnh báo hiển thị trên trang Google Play của ứng dụng vi phạm**  
_Nguồn: Google_

## Google sẽ đo lường những gì

Hệ thống Android vitals của Google Play sẽ theo dõi partial wake locks, tổng thời gian ứng dụng thực hiện công việc nền khi màn hình tắt và ngăn thiết bị vào chế độ ngủ.

Việc đo lường sẽ tính theo phiên người dùng và tổng hợp qua tất cả các phiên trong cửa sổ 28 ngày, chỉ đếm các wake locks không được miễn trừ, nghĩa là các khóa không do hệ thống giữ, không liên quan đến phát âm thanh, hoặc không phải truyền dữ liệu do người dùng khởi xướng.

Hành vi của một ứng dụng sẽ bị coi là quá mức khi một phiên người dùng duy nhất giữ tổng cộng hơn hai giờ các wake locks không được miễn trừ trong vòng 24 giờ.

Google coi ngưỡng hành vi xấu là 5% của các phiên người dùng của ứng dụng trong 28 ngày qua.

Các nhà phát triển có ứng dụng vượt mức này sẽ nhận được cảnh báo trên [trang tổng quan Android vitals](https://play.google.com/console/developers/app/vitals/metrics/overview).

**Cảnh báo tới nhà phát triển của các ứng dụng sử dụng CPU/pin quá mức**  
_Nguồn: Google_

Cuối cùng, thay đổi chính sách này sẽ [gây áp lực](https://developer.android.com/topic/performance/vitals/excessive-wakelock) cho các nhà phát triển nhằm siết chặt hành vi của ứng dụng, giảm bớt hoặc loại bỏ các wake locks không cần thiết, giải phóng chúng càng sớm càng tốt, và chú ý nhiều hơn đến các wake locks do các thư viện bên ngoài và SDK khởi xướng.

Khi được hỏi liệu tính năng này có được sử dụng để phát hiện spyware, adware và malware, vốn thường từ chối ngủ để giữ các kênh mạng mở và rò rỉ dữ liệu hay không, chúng tôi được thông báo rằng đây không phải chức năng dự định của tính năng.

"An ninh ứng dụng là ưu tiên hàng đầu trên Google Play. Tuy nhiên, mục đích chính của chỉ số này là nâng cao hiệu năng pin và chất lượng kỹ thuật để cải thiện trải nghiệm người dùng," Google giải thích.

"Chỉ số này nhắm vào 'hành vi xấu' về việc tiêu thụ tài nguyên quá mức, bất kể ứng dụng có độc hại hay không. Bằng cách thực thi các ngưỡng này, chúng tôi có thể xác định và thực hiện hành động đối với các ứng dụng lạm dụng tài nguyên hệ thống mà không mang lại giá trị cho người dùng – nhưng nó không nhằm mục tiêu chủ yếu vào malware."