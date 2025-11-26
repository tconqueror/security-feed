# Thư viện Forge phổ biến được vá lỗ hổng bỏ qua xác minh chữ ký

![Thư viện Forge phổ biến được vá lỗ hổng bỏ qua xác minh chữ ký](https://www.bleepstatic.com/content/hl-images/2025/11/26/Cryptography.jpg)

Một lỗ hổng trong gói ‘node-forge’, một thư viện mật mã JavaScript phổ biến, có thể bị khai thác để bỏ qua việc xác minh chữ ký bằng cách tạo dữ liệu trông hợp lệ.

Lỗi được theo dõi dưới mã CVE-2025-12816 và được đánh giá mức nghiêm trọng cao. Nó phát sinh từ cơ chế xác thực ASN.1 của thư viện, cho phép dữ liệu bị hỏng vượt qua các kiểm tra ngay cả khi nó về mặt mật mã là không hợp lệ.

“An interpretation-conflict vulnerability in node-forge versions 1.3.1 and earlier enables unauthenticated attackers to craft ASN.1 structures to desynchronize schema validations, yielding a semantic divergence that may bypass downstream cryptographic verifications and security decisions,” reads the flaw's [mô tả](https://nvd.nist.gov/vuln/detail/CVE-2025-12816) in the National Vulnerabilities Database (NVD).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Hunter Wodzenski của Palo Alto Networks đã phát hiện lỗ hổng và báo cáo một cách có trách nhiệm cho các nhà phát triển của node-forge.

Nhà nghiên cứu cảnh báo rằng các ứng dụng dựa vào node-forge để cưỡng chế cấu trúc và tính toàn vẹn của các giao thức mật mã bắt nguồn từ ASN.1 có thể bị lừa xác thực dữ liệu bị hỏng, và đã cung cấp một proof-of-concept cho thấy cách một payload bị giả mạo có thể đánh lừa cơ chế xác minh.

Một thông báo bảo mật từ Carnegie Mellon CERT-CC giải thích rằng tác động khác nhau tùy theo ứng dụng, và có thể bao gồm lách xác thực, sửa đổi dữ liệu đã ký, và sử dụng sai các chức năng liên quan đến chứng chỉ.

“In environments where cryptographic verification plays a central role in trust decisions, the potential impact can be significant,” [CERT-CC cảnh báo](https://kb.cert.org/vuls/id/521113).

Tác động có thể lớn khi xét rằng node-forge cực kỳ phổ biến với gần [26 million weekly downloads](https://www.npmjs.com/package/node-forge) trên registry Node Package Manager (NPM).

Thư viện được sử dụng bởi các dự án cần chức năng mật mã và hạ tầng khóa công khai (PKI) trong các môi trường JavaScript.

Một bản vá đã được phát hành hôm nay trong phiên bản 1.3.2. Các nhà phát triển sử dụng node-forge được khuyên chuyển sang biến thể mới nhất càng sớm càng tốt.

Các lỗi trong các dự án mã nguồn mở được sử dụng rộng rãi [có thể tồn tại trong thời gian dài](https://www.bleepingcomputer.com/news/security/over-30-percent-of-log4j-apps-use-a-vulnerable-version-of-the-library/) sau khi được công bố công khai và khi đã có bản vá. Điều này có thể xảy ra vì nhiều lý do khác nhau, trong đó sự phức tạp của môi trường và nhu cầu kiểm thử mã mới là một vài nguyên nhân.