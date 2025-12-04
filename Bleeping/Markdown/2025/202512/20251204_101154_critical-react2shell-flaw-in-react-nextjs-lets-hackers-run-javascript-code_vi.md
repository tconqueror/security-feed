# Lỗ hổng nghiêm trọng trong React, Next.js cho phép kẻ tấn công thực thi mã trên máy chủ

![Lỗ hổng nghiêm trọng trong React, Next.js cho phép kẻ tấn công thực thi mã trên máy chủ](https://www.bleepstatic.com/content/hl-images/2025/12/04/react.jpg)

Một lỗ hổng có mức nghiêm trọng tối đa, được đặt tên là 'React2Shell', trong giao thức 'Flight' của React Server Components (RSC) cho phép thực thi mã từ xa mà không cần xác thực trong các ứng dụng React và Next.js.

Vấn đề bảo mật bắt nguồn từ việc deserialization không an toàn. Nó nhận được điểm nghiêm trọng là 10/10 và đã được gán các định danh CVE-2025-55182 cho React và CVE-2025-66478 (CVE bị từ chối trong National Vulnerability Database) cho Next.js.

Nhà nghiên cứu bảo mật [Lachlan Davidson](https://www.linkedin.com/in/lachlan-s-davidson/) phát hiện lỗ hổng và báo cáo cho React vào ngày November 29\. Ông phát hiện rằng một kẻ tấn công có thể đạt được thực thi mã từ xa (RCE) bằng cách gửi một yêu cầu HTTP được chế tạo đặc biệt tới các endpoint React Server Function.

"Ngay cả khi ứng dụng của bạn không triển khai bất kỳ endpoint React Server Function nào, ứng dụng của bạn vẫn có thể bị tổn thương nếu ứng dụng hỗ trợ React Server Components \[RSC\]," cảnh báo [thông báo bảo mật](https://react.dev/blog/2025/12/03/critical-security-vulnerability-in-react-server-components) từ React.

Các gói sau trong cấu hình mặc định của chúng bị ảnh hưởng:

* react-server-dom-parcel
* react-server-dom-turbopack
* và react-server-dom-webpack

React là một thư viện JavaScript mã nguồn mở để xây dựng giao diện người dùng. Nó được duy trì bởi Meta và được nhiều tổ chức ở mọi quy mô áp dụng cho phát triển front-end.

Next.js, được duy trì bởi [Vercel](https://github.com/vercel/next.js/security/advisories/GHSA-9qr9-h5gf-34mp), là một framework xây dựng trên React bổ sung render phía máy chủ, routing và các endpoint API.

Cả hai giải pháp đều xuất hiện rộng rãi trong môi trường đám mây thông qua các ứng dụng front-end giúp mở rộng và triển khai kiến trúc nhanh hơn và dễ dàng hơn.

Các nhà nghiên cứu tại nền tảng bảo mật đám mây Wiz [cảnh báo](http://www.wiz.io/blog/critical-vulnerability-in-react-cve-2025-55182) rằng lỗ hổng dễ bị khai thác và tồn tại trong cấu hình mặc định của các gói bị ảnh hưởng. 

### Tác động và bản vá

Theo React, lỗ hổng xuất hiện trong các phiên bản 19.0, 19.1.0, 19.1.1, và 19.2.0\. Next.js bị ảnh hưởng trong các phát hành canary thử nghiệm bắt đầu từ 14.3.0-canary.77, và tất cả các phát hành của nhánh 15.x và 16.x thấp hơn các phiên bản đã được vá.

Lỗ hổng tồn tại trong gói 'react-server' được sử dụng bởi React Server Components (RSC), nhưng Next.js kế thừa nó thông qua việc triển khai giao thức RSC "Flight".

Các nhà nghiên cứu của Wiz cho biết 39% tất cả các môi trường đám mây mà họ có khả năng quan sát chứa các trường hợp Next.js hoặc React đang chạy các phiên bản có lỗ hổng CVE-2025-55182, CVE-2025-66478, hoặc cả hai.

Cùng lỗ hổng này có khả năng tồn tại trong các thư viện khác triển khai React Server, bao gồm Vite RSC plugin, Parcel RSC plugin, React Router RSC preview, RedwoodSDK, và Waku.

Công ty bảo mật chuỗi cung ứng phần mềm Endor Labs [giải thích](https://www.endorlabs.com/learn/critical-remote-code-execution-rce-vulnerabilities-in-react-and-next-js) rằng React2Shell "là một lỗ hổng deserialization về mặt logic không an toàn, nơi server không kiểm tra đúng cấu trúc của payload RSC đến."

Có một thất bại xác thực khi nhận dữ liệu bị làm hỏng từ kẻ tấn công, điều này dẫn tới việc thực thi mã JavaScript có đặc quyền trong ngữ cảnh của server.

Davidson tạo một [trang web React2Shell](http://react2shell.com/), nơi ông sẽ công bố chi tiết kỹ thuật. Nhà nghiên cứu cũng cảnh báo rằng có các khai thác proof-of-concept (PoC) không thực sự đáng tin cậy.

Những PoC này gọi các hàm như _vm#runInThisContext_, _child\_process#exec_, và _fs#writeFile,_ nhưng một khai thác thực sự không cần những hàm này, nhà nghiên cứu cho biết.

"Điều này chỉ có thể bị khai thác nếu bạn đã chủ ý cho phép client gọi những hàm này, điều đó sẽ rất nguy hiểm dù trong bất kỳ trường hợp nào," Davidson lưu ý.

Ông giải thích thêm rằng những PoC giả này sẽ không hoạt động với Next.js vì các hàm này không tồn tại do danh sách các hàm server được quản lý tự động.

Các nhà phát triển được khuyến cáo mạnh mẽ áp dụng các bản vá có sẵn trong các phiên bản React 19.0.1, 19.1.2, và 19.2.1, và các phiên bản Next.js 15.0.5, 15.1.9, 15.2.6, 15.3.6, 15.4.8, 15.5.7, và 16.0.7.

Các tổ chức nên kiểm toán môi trường của họ để xác định xem có sử dụng phiên bản dễ bị tổn thương hay không và thực hiện các hành động phù hợp để giảm thiểu rủi ro.

Độ phổ biến của hai giải pháp này được phản ánh trong số lượt tải hàng tuần, khi React có [55.8 million](https://www.npmjs.com/package/react) trên Node Package Manager (NPM), và Next.js có [16.7 million](https://www.npmjs.com/package/next) trên cùng nền tảng.