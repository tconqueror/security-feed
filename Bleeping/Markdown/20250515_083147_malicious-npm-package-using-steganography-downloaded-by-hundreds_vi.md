# Gói npm độc hại sử dụng steganography đã được tải về hàng trăm lần

![NPM](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_head_pic.jpg)

Một gói độc hại trong chỉ mục Node Package Manager sử dụng các ký tự Unicode không thể nhìn thấy để ẩn mã độc và các liên kết Google Calendar để lưu trữ URL cho vị trí command-and-control.

Gói này, có tên _os-info-checker-es6_, xuất hiện như một tiện ích thông tin và đã được tải về hơn 1,000 lần kể từ đầu tháng.

Các nhà nghiên cứu tại [Veracode](https://www.veracode.com/resources/sophisticated-npm-attack-leveraging-unicode-steganography-and-google-calendar-c2), một công ty đánh giá an ninh mã, phát hiện rằng phiên bản đầu tiên của gói đã được thêm vào chỉ mục Node Package Manager (NPM) vào ngày 19 tháng 3 và không có độc hại, vì nó chỉ thu thập thông tin về hệ điều hành từ máy chủ.

Tác giả đã thêm các sửa đổi vài ngày sau để bao gồm các nhị phân cụ thể cho từng nền tảng và các tập lệnh cài đặt bị biến đổi.

Vào ngày 7 tháng 5, một phiên bản mới của gói đã được phát hành, tính năng mã cho "một cơ chế C2 (command-and-control) phức tạp" cung cấp payload cuối cùng.

Phiên bản mới nhất của '[os-info-checker-es6](https://www.npmjs.com/package/os-info-checker-es6)' có sẵn trên npm tại thời điểm viết bài là v1.0.8 và nó độc hại, Veracode cảnh báo.

Hơn nữa, gói này được liệt kê là phụ thuộc cho bốn gói NPM khác: [skip-tot](https://www.npmjs.com/package/skip-tot), [vue-dev-serverr](https://www.npmjs.com/package/vue-dev-serverr), [vue-dummyy](https://www.npmjs.com/package/vue-dummyy), và '[vue-bit](https://www.npmjs.com/package/vue-bit) \- tất cả đều đóng vai trò như các công cụ tiếp cận và phát triển nền tảng kỹ thuật.

Chưa rõ liệu các gói này có được quảng bá bởi tác nhân đe dọa hay không.

## Steganography Unicode

Trong phiên bản độc hại, kẻ tấn công đã nhúng dữ liệu trong những gì xuất hiện như một chuỗi '|'. Tuy nhiên, dấu gạch đứng này được theo sau bởi một chuỗi dài các ký tự Unicode không thể nhìn thấy từ phạm vi Variation Selectors Supplement (U+E0100 đến U+E01EF).

Những ký tự Unicode này thường là các ký tự điều chỉnh, thường được sử dụng "để cung cấp các biến thể glyph cụ thể trong các skrip phức tạp." Trong trường hợp này, vai trò của chúng là để hỗ trợ steganography dựa trên văn bản - ẩn thông tin trong dữ liệu khác.

Veracode đã giải mã và giải thích chuỗi để tìm ra một payload cho một cơ chế C2 phức tạp dựa vào một liên kết ngắn Google Calendar để đến vị trí lưu trữ payload cuối cùng.

Nhà nghiên cứu giải thích rằng sau khi lấy được liên kết Google Calendar, một tập hợp các chuyển hướng được kiểm tra cho đến khi nhận được phản hồi HTTP 200 OK cho yêu cầu.

Sau đó, nó đã lấy thuộc tính _data-base-title_ từ trang HTML của sự kiện, có chứa một URL mã hóa base64 chỉ đến payload cuối cùng.

Sử dụng một hàm gọi là _ymmogvj,_ URL này được giải mã để lấy payload mã độc. Các nhà nghiên cứu cho biết rằng yêu cầu mong đợi một payload mã độc giai đoạn 2 mã hóa base trong thân phản hồi, và có thể là một vector khởi tạo và một khóa bí mật trong tiêu đề HTTP - một dấu hiệu có thể là việc mã hóa của payload cuối cùng.

Veracode cũng phát hiện rằng payload này cũng được thực thi bằng cách sử dụng _eval()._ Tập lệnh bao gồm một cơ chế bảo trì đơn giản trong thư mục tạm thời của hệ thống, ngăn chặn nhiều phiên bản chạy cùng một lúc.

Tại thời điểm phân tích, các nhà nghiên cứu không thể lấy được payload cuối cùng, cho thấy rằng chiến dịch có thể đang tạm dừng hoặc vẫn trong giai đoạn đầu.

Mặc dù Veracode đã báo cáo những phát hiện của mình cho NPM, nhưng các gói nghi vấn vẫn còn hiện diện trên nền tảng.