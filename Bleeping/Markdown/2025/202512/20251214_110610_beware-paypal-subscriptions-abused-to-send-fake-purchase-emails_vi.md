# Cảnh báo: PayPal "Subscriptions" bị lạm dụng để gửi email thông báo mua hàng giả

![PayPal](https://www.bleepstatic.com/content/hl-images/2025/12/13/paypal-scam-2025.jpg)

Một chiêu lừa qua email đang lợi dụng tính năng thanh toán "Subscriptions" của PayPal để gửi các email hợp lệ từ PayPal chứa thông báo mua hàng giả được nhúng trong trường Customer service URL.

Trong vài tháng qua, nhiều người đã báo cáo \[[1](https://www.reddit.com/r/Scams/comments/1pa1n19/us%5Fpretty%5Fobvious%5Fscam%5Femail%5Fbut%5Fappears%5Fto%5Fhave/), [2](https://www.bbb.org/scamtracker/lookupscam/1091213)\] nhận được email từ PayPal với nội dung, "Your automatic payment is no longer active."

Email bao gồm một trường customer service URL đã bị chỉnh sửa để chèn một thông điệp nói rằng bạn đã mua một món hàng đắt tiền, chẳng hạn như một thiết bị Sony, MacBook hoặc iPhone.

Văn bản này bao gồm một tên miền, một thông báo nói rằng một khoản thanh toán từ $1,300 đến $1,600 đã được xử lý (số tiền thay đổi theo email), và một số điện thoại để hủy hoặc tranh chấp khoản thanh toán. Văn bản được lấp đầy bằng các ký tự Unicode khiến một số phần trông đậm hoặc có phông chữ khác thường, một thủ thuật dùng để cố gắng né bộ lọc spam và phát hiện từ khóa.

"http://[domain] [domain] A payment of $1346.99 has been successfully processed. For cancel and inquiries, Contact PayPal support at +1-805-500-6377," là nội dung trường customer service URL trong email lừa đảo.

![Email đăng ký PayPal được sử dụng trong vụ lừa đảo](https://www.bleepstatic.com/images/news/security/phishing/p/paypal/subscription-phishing/subscription-phishing-email.jpg)

**Email đăng ký PayPal được sử dụng trong vụ lừa đảo**  
_Nguồn: BleepingComputer_

Mặc dù rõ ràng đây là lừa đảo, các email này được gửi trực tiếp bởi PayPal từ địa chỉ "service@paypal.com," khiến người nhận lo lắng rằng tài khoản của họ có thể đã bị xâm phạm.

Hơn nữa, vì đây là email hợp lệ do PayPal gửi, chúng vượt qua các bộ lọc bảo mật và spam. Ở phần tiếp theo, chúng tôi sẽ giải thích cách những kẻ lừa đảo gửi các email này.

Mục tiêu của các email này là khiến người nhận nghĩ rằng tài khoản của họ đã mua một thiết bị đắt tiền và làm họ hoảng sợ để gọi tới số "Hỗ trợ PayPal" của kẻ lừa đảo.

Các email như vậy từ trước đến nay thường được dùng để thuyết phục nạn nhân gọi tới một số điện thoại để thực hiện gian lận ngân hàng hoặc lừa họ cài đặt phần mềm độc hại lên máy tính của họ.

Do đó, nếu bạn nhận được một email hợp lệ từ PayPal nói rằng khoản thanh toán tự động của bạn không còn hoạt động, và nó chứa một xác nhận mua hàng giả, hãy bỏ qua email đó và không gọi số điện thoại.

Nếu bạn lo ngại rằng tài khoản PayPal của mình bị xâm phạm, hãy đăng nhập vào tài khoản và xác nhận rằng không có khoản phí nào.

## Cách chiêu lừa PayPal hoạt động

BleepingComputer đã được gửi một bản sao của email từ người nhận và nhận thấy kỳ lạ rằng vụ lừa xuất phát từ địa chỉ hợp lệ "service@paypal.com".

Hơn nữa, header email cho thấy các email này là hợp lệ, vượt qua kiểm tra DKIM và SPF, và xuất phát trực tiếp từ máy chủ thư "mx15.slc.paypal.com" của PayPal, như được hiển thị bên dưới.

```
ARC-Authentication-Results: i=1; mx.google.com;
       dkim=pass header.i=@paypal.com header.s=pp-dkim1 header.b="AvY/E1H+";
       spf=pass (google.com: domain of service@paypal.com designates 173.0.84.4 as permitted sender) smtp.mailfrom=service@paypal.com;
       dmarc=pass (p=REJECT sp=REJECT dis=NONE) header.from=paypal.com
Received: from mx15.slc.paypal.com (mx15.slc.paypal.com. [173.0.84.4])
        by mx.google.com with ESMTPS id a92af1059eb24-11dcb045a3csi5930706c88.202.2025.11.28.09.14.49
        for 
        (version=TLS1_3 cipher=TLS_AES_256_GCM_SHA384 bits=256/256);
        Fri, 28 Nov 2025 09:14:49 -0800 (PST)
```

Sau khi thử nghiệm nhiều tính năng thanh toán của PayPal, BleepingComputer đã tái tạo được cùng mẫu email bằng cách sử dụng tính năng "Subscriptions" của PayPal và tạm dừng một subscriber.

Subscriptions của PayPal là tính năng thanh toán cho phép merchant tạo các tùy chọn thanh toán định kỳ để người dùng đăng ký dịch vụ với một số tiền xác định.

Khi một merchant tạm dừng subscription của một subscriber, PayPal sẽ tự động gửi email thông báo cho subscriber rằng khoản thanh toán tự động của họ không còn hoạt động.

Tuy nhiên, khi BleepingComputer cố gắng tái tạo vụ lừa bằng cách thêm văn bản khác ngoài một URL vào Customer Service URL, PayPal đã từ chối thay đổi vì chỉ cho phép URL.

Vì vậy, có vẻ như những kẻ lừa đảo đang lợi dụng một lỗi trong cách PayPal xử lý metadata của subscription hoặc dùng một phương thức, chẳng hạn như API hoặc nền tảng cũ không có ở mọi vùng, cho phép lưu văn bản không hợp lệ trong trường Customer service URL.

Bây giờ chúng ta biết họ tạo email từ PayPal như thế nào, vẫn chưa rõ làm sao email đó được gửi tới những người không đăng ký subscription của PayPal.

Header thư cho thấy PayPal thực tế đang gửi email tới địa chỉ "receipt3@bbcpaglomoonlight.studio," mà chúng tôi tin là địa chỉ email liên kết với một subscriber giả do kẻ lừa đảo tạo.

Tài khoản này có thể là một danh sách gửi thư Google Workspace, tự động chuyển tiếp bất kỳ email nào nó nhận đến tất cả thành viên nhóm khác. Trong trường hợp này, các thành viên chính là những người mà kẻ lừa đảo nhắm tới.

Việc chuyển tiếp này có thể khiến tất cả các kiểm tra SPF và DMARC tiếp theo bị thất bại, vì email đã bị chuyển tiếp bởi một máy chủ không phải người gửi ban đầu.

Khi BleepingComputer liên hệ PayPal để hỏi liệu vấn đề này đã được khắc phục hay chưa, họ từ chối bình luận và thay vào đó chia sẻ tuyên bố sau.

"PayPal does not tolerate fraudulent activity and we work hard to protect our customers from consistently evolving scam tactics," PayPal told BleepingComputer.

"We are aware of this phishing scam and encourage people to always be vigilant online and mindful of unexpected messages. If customers suspect they are a target of a scam, we recommend they contact Customer Support directly through the PayPal app or our Contact page for assistance."