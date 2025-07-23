# npm 'vô tình' gỡ bỏ gói Stylus, làm hỏng các bản build và pipeline

![npm](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_logo_headpic.jpg)

npm đã gỡ bỏ tất cả các phiên bản của thư viện Stylus chính thức và thay thế chúng bằng một trang "đang giữ an ninh", làm hỏng các pipeline và build trên toàn thế giới phụ thuộc vào gói này.

Một trang web giữ an ninh thường được hiển thị khi các gói và thư viện độc hại bị gỡ bỏ bởi các quản trị viên của npmjs.com, kho phần mềm lớn nhất thế giới chủ yếu được sử dụng cho phát triển JavaScript và Node.js.

Nhưng điều đó không hoàn toàn đúng với Stylus: một thư viện hợp pháp "cách mạng" nhận được 3 triệu lượt tải hàng tuần và cung cấp một cách diễn đạt cho các nhà phát triển tạo ra CSS.

## Stylus 'bị cấm vô tình bởi npmjs'

Tính đến vài giờ trước, npmjs đã gỡ bỏ tất cả các phiên bản của gói Stylus và công bố một trang "gói giữ an ninh" thay vào đó.

![tất cả các phiên bản của gói npm 'stylus' bị gỡ bỏ và thay thế bằng trang 'giữ an ninh'](https://www.bleepstatic.com/images/news/u/1164866/2025/Jul/npm-stylus-ban/placeholder-stylus.jpg)

**Tất cả các phiên bản của 'stylus' bị gỡ bỏ và thay thế bằng trang 'giữ an ninh'**  
(npmjs.com)

"Stylus đã bị cấm vô tình bởi npmjs," [cho biết](https://github.com/stylus/stylus/issues/2938) nhà phát triển Stylus Lei Chen trong một vấn đề GitHub. Người duy trì dự án hiện đang "chờ npmjs khôi phục quyền truy cập vào Stylus."

"Tôi là người duy trì hiện tại của Stylus. Thư viện Stylus đã bị đánh dấu là độc hại..., điều này đã khiến nhiều \[thư viện\] và framework phụ thuộc vào Stylus không thể cài đặt," cũng [đã đăng](https://x.com/chenleidev/status/1947878300086624601) Chen trên X (trước đây là Twitter). "Xin hãy giúp tôi retweet tin nhắn này với hy vọng rằng đội ngũ chính thức của npmjs sẽ chú ý đến vấn đề này."

Trang npmjs ban đầu của Stylus (được hiển thị dưới đây) chỉ ra rằng thư viện hợp pháp này là một "ngôn ngữ mới cách mạng" cho phát triển CSS và thu về gần 3 triệu lượt tải hàng tuần.

![Gói Stylus trên npm nhận hàng triệu lượt tải](https://www.bleepstatic.com/images/news/u/1164866/2025/Jul/npm-stylus-ban/stylus-npm.jpg)

**Gói Stylus trên npm nhận hàng triệu lượt tải** (BleepingComputer)

Chắc chắn rồi, các nhà phát triển của các dự án khác phụ thuộc vào Stylus đã lên tiếng:

"Các bản build của tôi đang thất bại nên các bản cập nhật phần mềm của tôi không được công bố vì lỗi hành chính này," [đã đăng](https://x.com/i%5Fw%5Fh%5Fo/status/1947939151841538404) một nhà phát triển.

Các gói như [typescript-plugin-css-modules](https://www.npmjs.com/package/typescript-plugin-css-modules) (được tải lên tới 500.000 lần hàng tuần) cũng phụ thuộc vào Stylus, [đã lưu ý](http://x.com/Seniya%5FS/status/1947926005328347377) nhà phát triển full-stack Chanuka Asanka:

"Các pipeline đang thất bại. Có ai biết liệu npm/yarn có cung cấp thông báo sớm khi họ sắp làm điều gì đó như vậy không?"

**Stylus được phụ thuộc bởi các dự án lớn** (BleepingComputer)

"Tôi đã triển khai Frappe/ERPNext như tôi thường làm với pipeline CI/CD và nó đột ngột thất bại," [đã viết](https://discuss.frappe.io/t/stylus-malicious-npm-package-removed-but-present-in-frappe-fails-to-build-docker/150549) một nhà phát triển Docker trong một chủ đề diễn đàn Frappe.

## Thực sự đã _xảy ra cái gì_?

Thường thì, các gói bị gỡ bỏ trên npm vì vi phạm một hoặc nhiều [điều khoản dịch vụ mã nguồn mở](https://docs.npmjs.com/policies/open-source-terms) của họ, và tương đối thường xuyên vì chứa mã độc hại. Nhưng điều đó không đúng với Stylus - tất cả các phiên bản của nó có vẻ sạch sẽ và hoạt động tốt.

Tom Abai, một nhà nghiên cứu bảo mật tại công ty bảo mật chuỗi cung ứng Mend.io, đã tìm ra nguyên nhân.

Trong khi điều tra sự phát triển, Abai [đã xác nhận](https://x.com/abai%5Ftom/status/1947933649577341062) rằng ít nhất phiên bản gần nhất (0.64.0) của Stylus là "sạch", nhưng có điều gì đó kỳ lạ xuất hiện liên quan đến gói:

**Nhà nghiên cứu Mend.io làm sáng tỏ sự phát triển** (Tom Abai qua X)

"...một điều kỳ lạ đã xảy ra trong cuộc điều tra của chúng tôi, và chủ sở hữu này _panyakor_..., người có vẻ như đã là một phần của những người sở hữu gói stylus npm, đã phát hành 3 gói độc hại tuần trước..." viết Abai.

npmjs.com, giống như nhiều nền tảng phát triển mã nguồn mở khác, cho phép nhiều người duy trì được liệt kê cho và đóng góp vào một gói. Trong khi Chen có thể là nhà phát triển chính của Stylus, có nhiều tài khoản npm khác được liệt kê dưới danh sách người duy trì.

"Panya, là một trong những người duy trì gói stylus, đã phát hành chúng, và vì điều đó, tài khoản của anh ta đã bị cấm, và tất cả các gói kết nối với anh ta đã bị rút lại, bao gồm cả gói Stylus. Đó là câu chuyện ở đây. Một báo động sai lớn từ NPM," phát biểu Abai.

BleepingComputer cũng đã xác nhận rằng tài khoản npm '[panya](https://www.npmjs.com/~panya)' thực sự đã được liệt kê trong danh sách người duy trì trên npmjs.com cho cả Stylus và 3 gói được liệt kê trong bài viết của Abai, mà không có liên quan gì đến Stylus.

Các gói bị đánh dấu bởi Abai: _@pwa-ib/eslint-plugin-compat_, _@blocks-shared/desktop-title_, _@tui-react-internal/select-account-icon_, được phát hành bởi 'panya', hiện yêu cầu xác thực để truy cập trên kho npmjs.com và do đó bị hạn chế khỏi tầm nhìn công cộng.

Tuy nhiên, BleepingComputer đã có thể thu thập và xem xét các gói này, và chúng tôi có thể xác nhận những phát hiện của Abai.

Ví dụ, tệp "extract.js" trong @blocks-shared/desktop-title chứa một mã kiểu [dependency confusion](https://www.bleepingcomputer.com/tag/dependency-confusion/) thử nghiệm mà ngành công nghiệp đã thấy nhiều lần cho đến bây giờ:

**Mã PoC về sự nhầm lẫn phụ thuộc được thấy trong một gói được phát hành bởi một người đồng duy trì Stylus**  
(Bleeping Computer)

[Theo](https://socket.dev/npm/user/panya) công ty bảo mật chuỗi cung ứng Socket, tài khoản npm 'panya' đã là một người duy trì (và/hoặc phát hành) ít nhất 12 gói trong quá khứ:

**tài khoản npm panya đã liên kết với 12 gói** (Socket.dev)

Tại thời điểm viết, tuy nhiên, tài khoản không có gói nào được liệt kê dưới nó, cho thấy rằng kho có thể đã xóa tất cả các lỗ hổng PoC của nó và gỡ bỏ Stylus trong quá trình này, một cách vô tình.

BleepingComputer đã tiếp cận kho npm và tổ chức mẹ của nó, GitHub, để bình luận về vấn đề này trước khi xuất bản.

## Bạn có thể làm gì?

May mắn thay, nhà phát triển Stylus và các thành viên cộng đồng mã nguồn mở đã [chia sẻ các mẹo chi tiết trong thời gian này](https://github.com/stylus/stylus/issues/2938) cho các nhà phát triển npm và yarn phụ thuộc vào Stylus để duy trì quyền truy cập vào thư viện và khôi phục các bản build của họ.

Các nhà phát triển npm có thể chọn tham chiếu gói stylus "một cách động bằng cách chỉ định một nhánh, tag hoặc commit trong phần `dependencies` của `package.json`," cho biết Chen, chẳng hạn như:

```json
{
  "dependencies": {
    "stylus": "github:stylus/stylus#version-you-need"
  }
}
```

Sử dụng overrides là một tùy chọn khác cho các nhà phát triển npm:

"Bạn có thể ghi đè phiên bản gói `stylus` được sử dụng bởi các phụ thuộc khác bằng cách chỉ định nó trong phần `overrides` (được hỗ trợ trong npm v8.3.0 và mới hơn)"

```json
{
  "overrides": {
    "stylus": "github:stylus/stylus#version-you-need"
  }
}
```

**"Lưu ý**: Đảm bảo tag, nhánh hoặc commit được chỉ định (ví dụ: `0.54.4`) tồn tại trong kho `stylus/stylus`. Xóa cache npm (`npm cache clean --force`) nếu bạn gặp sự cố với các phụ thuộc cũ."

Tóm lại, Chen nhấn mạnh:

"Stylus không chứa mã độc hại; điều này đã được xác nhận. _npmmirror.com_ (một gương phi lợi nhuận được tài trợ bởi Alibaba) đã phục hồi quyền truy cập \[đến thư viện\]," [đã viết](https://github.com/stylus/stylus/issues/2938#issue-3254793141) Lei Chen.  
  
Không rõ điều này có phải là trùng hợp hay không, nhưng một công cụ có tên là thành phần Stylus Tools đã được [báo cáo có một CVE](https://nvd.nist.gov/vuln/detail/CVE-2025-6044).  
  
_Panya_ (người duy trì trước đây của Stylus) đã sử dụng tài khoản của chính họ để phát hành một gói chứa mã độc hại (cho mục đích nghiên cứu bảo mật? Tôi không chắc), nhưng không phát hành một phiên bản mới của Stylus chứa mã độc hại.  
  
Chúng tôi đang chờ hành động chính thức từ npmjs. Vâng, chúng tôi đang chờ họ xử lý.  
  
Một biện pháp thay thế đã được cung cấp trong các bình luận. Xin hãy áp dụng nếu cần thiết."

Trong quá khứ, các nhà phát triển mã nguồn mở đã gây chú ý bởi việc làm hỏng các bản build bằng cách [kéo gói của họ](https://qz.com/646467/how-one-programmer-broke-the-internet-by-deleting-a-tiny-piece-of-code) khỏi các kho vì bất đồng hoặc thậm chí [làm hỏng mã của họ để phản đối](https://www.bleepingcomputer.com/news/security/dev-corrupts-npm-libs-colors-and-faker-breaking-thousands-of-apps/).

Sự cố này đánh dấu trường hợp đầu tiên đáng chú ý về việc một kho đã gỡ bỏ một dự án hợp pháp hoàn toàn, trong những gì dường như là một lỗi hành chính.