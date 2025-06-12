# Trend Micro khắc phục các lỗ hổng nghiêm trọng trong nhiều sản phẩm

![Trend Micro khắc phục các lỗ hổng nghiêm trọng trong nhiều sản phẩm](https://www.bleepstatic.com/content/hl-images/2022/04/01/Trend_Micro__headpic.jpg)

Trend Micro đã phát hành các bản cập nhật bảo mật để giải quyết nhiều lỗ hổng nghiêm trọng liên quan đến thực thi mã từ xa và bỏ qua xác thực ảnh hưởng đến các sản phẩm Apex Central và Endpoint Encryption (TMEE) PolicyServer của họ.

Nhà cung cấp bảo mật nhấn mạnh rằng họ chưa thấy bằng chứng về việc khai thác chủ động nào xảy ra trên thực địa cho bất kỳ lỗ hổng nào trong số đó. Tuy nhiên, việc áp dụng ngay lập tức các bản cập nhật bảo mật được khuyến nghị để giải quyết các rủi ro.

Trend Micro Endpoint Encryption PolicyServer là một máy chủ quản lý trung tâm cho Trend Micro Endpoint Encryption (TMEE), cung cấp mã hóa toàn bộ ổ đĩa và mã hóa phương tiện di động cho các điểm cuối dựa trên Windows.

Sản phẩm này được sử dụng trong các môi trường doanh nghiệp trong các ngành được quản lý, nơi việc tuân thủ các tiêu chuẩn bảo vệ dữ liệu là rất quan trọng.

Với cập nhật mới nhất, Trend Micro đã giải quyết các lỗ hổng nghiêm trọng sau:

* [**CVE-2025-49212**](https://www.zerodayinitiative.com/advisories/ZDI-25-369/) **\-** Một lỗ hổng thực thi mã từ xa trước khi xác thực do việc giải mã không an toàn trong lớp PolicyValueTableSerializationBinder. Các kẻ tấn công từ xa có thể khai thác điều này để thực hiện mã tùy ý với tư cách là SYSTEM mà không cần yêu cầu đăng nhập.
* [**CVE-2025-49213**](https://www.zerodayinitiative.com/advisories/ZDI-25-370/)**\-** Một lỗ hổng thực thi mã từ xa trước khi xác thực trong lớp PolicyServerWindowsService, xuất phát từ việc giải mã dữ liệu không đáng tin cậy. Các kẻ tấn công có thể chạy mã tùy ý với tư cách là SYSTEM mà không yêu cầu xác thực.
* **[CVE-2025-49216](https://www.zerodayinitiative.com/advisories/ZDI-25-373/)** **\-** Một lỗ hổng bỏ qua xác thực trong dịch vụ DbAppDomain do việc thực hiện xác thực bị lỗi. Các kẻ tấn công từ xa có thể hoàn toàn bỏ qua đăng nhập và thực hiện các hành động ở cấp độ quản trị mà không cần thông tin xác thực.
* [**CVE-2025-49217**](https://www.zerodayinitiative.com/advisories/ZDI-25-374/) _\-_ Một lỗ hổng RCE trước khi xác thực trong phương thức ValidateToken, được kích hoạt bởi việc giải mã không an toàn. Mặc dù hơi khó khai thác hơn, nhưng vẫn cho phép các kẻ tấn công không xác thực chạy mã với tư cách là SYSTEM.

Cần lưu ý rằng trong khi [thông báo bảo mật](https://success.trendmicro.com/en-US/solution/KA-0019928) của Trend Micro cho Endpoint Encryption PolicyServer liệt kê cả bốn lỗ hổng ở trên là nghiêm trọng, thông báo của ZDI đánh giá CVE-2025-49217 là lỗ hổng có mức độ nghiêm trọng cao.

Các vấn đề bổ sung được giải quyết bởi phiên bản mới nhất của Endpoint Encryption PolicyServer bao gồm bốn lỗ hổng nghiêm trọng khác (ví dụ: lỗ hổng SQL injection và nâng quyền).

Tất cả các lỗ hổng đã được giải quyết trong phiên bản 6.0.0.4013 (Bản sửa lỗi 1 Cập nhật 6). Các lỗ hổng ảnh hưởng đến tất cả các phiên bản cho đến phiên bản mới nhất và không có biện pháp khắc phục hoặc giải pháp nào cho chúng.

---

Một [tập hợp vấn đề thứ hai](https://success.trendmicro.com/en-US/solution/KA-0019926) mà Trend Micro đã giải quyết ảnh hưởng đến Apex Central, một bảng điều khiển quản lý bảo mật tập trung được sử dụng để giám sát, cấu hình và quản lý nhiều sản phẩm và đại lý bảo mật của Trend Micro trong một tổ chức.

Cả hai vấn đề đều là những lỗ hổng nghiêm trọng về thực hiện mã từ xa trước khi xác thực:

* [**CVE-2025-49219**](https://www.zerodayinitiative.com/advisories/ZDI-25-366/) – Một lỗ hổng RCE trước khi xác thực trong phương thức GetReportDetailView của Apex Central do việc giải mã không an toàn. Việc khai thác điều này cho phép các kẻ tấn công không xác thực thực hiện mã trong bối cảnh NETWORK SERVICE. (CVSS 9.8)
* [**CVE-2025-49220**](https://www.zerodayinitiative.com/advisories/ZDI-25-367/) – Một lỗ hổng RCE trước xác thực trong Apex Central trong phương thức ConvertFromJson. Việc xác thực đầu vào không đúng cách trong quá trình giải mã cho phép các kẻ tấn công thực hiện mã tùy ý từ xa mà không cần xác thực. (CVSS 9.8)

Các vấn đề này đã được khắc phục trong Bản sửa lỗi B7007 cho Apex Central 2019 (tại chỗ), trong khi chúng được áp dụng tự động phía sau cho Apex Central dưới dạng dịch vụ.