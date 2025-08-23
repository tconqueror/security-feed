# Gói NPM độc hại sử dụng steganography Unicode để tránh bị phát hiện

![NPM](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_head_pic.jpg)

Một gói độc hại trong chỉ mục Node Package Manager sử dụng các ký tự Unicode vô hình để ẩn mã độc hại và các liên kết Google Calendar để lưu trữ URL cho vị trí command-and-control.

Gói này, có tên _os-info-checker-es6_, xuất hiện như một tiện ích thông tin và đã được tải xuống hơn 1,000 lần kể từ đầu tháng.

Các nhà nghiên cứu tại [Veracode](https://www.veracode.com/resources/sophisticated-npm-attack-leveraging-unicode-steganography-and-google-calendar-c2) phát hiện ra rằng phiên bản đầu tiên của gói đã được thêm vào chỉ mục Node Package Manager (NPM) vào ngày 19 tháng 3 và là gói vô hại, vì nó chỉ thu thập thông tin hệ điều hành từ máy chủ.

Tác giả đã thêm các sửa đổi vài ngày sau đó để bao gồm các nhị phân cụ thể cho nền tảng và các tập lệnh cài đặt đã bị che giấu.

Vào ngày 7 tháng 5, một phiên bản mới của gói đã được công bố, có mã cho "một cơ chế C2 (command-and-control) tinh vi" mà cung cấp payload cuối cùng.

Phiên bản mới nhất của '[os-info-checker-es6](https://www.npmjs.com/package/os-info-checker-es6)' có sẵn trên npm tại thời điểm viết bài là v1.0.8 và nó là độc hại, Veracode cảnh báo.

Hơn nữa, gói này được liệt kê là một phụ thuộc cho bốn gói NPM khác: [skip-tot](https://www.npmjs.com/package/skip-tot), [vue-dev-serverr](https://www.npmjs.com/package/vue-dev-serverr), [vue-dummyy](https://www.npmjs.com/package/vue-dummyy), và '[vue-bit](https://www.npmjs.com/package/vue-bit) - tất cả đều giả vờ là công cụ kỹ thuật nền tảng và truy cập.

Hiện chưa rõ liệu những gói này có được quảng bá bởi kẻ tấn công hay không.

## Steganography Unicode

Trong phiên bản độc hại, kẻ tấn công đã nhúng dữ liệu vào cái mà dường như là một chuỗi '|' . Tuy nhiên, ký tự thẳng đứng này được theo sau bởi một chuỗi dài các ký tự Unicode vô hình từ phạm vi Variation Selectors Supplement (U+E0100 đến U+E01EF).

Những ký tự Unicode này thường là những ký tự sửa đổi, chủ yếu được sử dụng "để cung cấp các biến thể glyph cụ thể trong các kịch bản phức tạp." Trong trường hợp này, vai trò của chúng là để tạo điều kiện cho steganography dựa trên văn bản - che giấu thông tin trong dữ liệu khác.

Veracode đã giải mã và khôi phục chuỗi để tìm payload cho một cơ chế C2 tinh vi phụ thuộc vào một liên kết ngắn Google Calendar để đạt đến vị trí lưu trữ payload cuối cùng.

Nhà nghiên cứu giải thích rằng sau khi lấy liên kết Google Calendar, một tập hợp các chuyển hướng được kiểm tra cho đến khi nhận được phản hồi HTTP 200 OK cho yêu cầu.

Tiếp theo, nó quét một thuộc tính _data-base-title_ từ trang HTML của sự kiện, chứa URL mã hóa base64 trỏ đến payload cuối cùng.

Sử dụng một hàm có tên _ymmogvj,_ URL được giải mã để lấy payload malware. Các nhà nghiên cứu cho biết yêu cầu mong đợi một payload malware giai đoạn-2 mã hóa base trong thân phản hồi, và có thể một vector khởi tạo và một khóa bí mật trong các tiêu đề HTTP - một dấu hiệu cho thấy có thể được mã hóa payload cuối cùng.

Veracode cũng phát hiện rằng payload cũng được thực thi bằng cách sử dụng _eval()._ Kịch bản bao gồm một cơ chế duy trì đơn giản trong thư mục tạm của hệ thống, ngăn nhiều phiên chạy cùng một lúc.

Tại thời điểm phân tích, các nhà nghiên cứu không thể lấy được payload cuối cùng, cho thấy rằng chiến dịch có thể đang dừng lại hoặc vẫn ở giai đoạn đầu.

Mặc dù Veracode đã báo cáo các phát hiện của mình cho NPM, các gói đáng ngờ vẫn còn hiện diện trên nền tảng.