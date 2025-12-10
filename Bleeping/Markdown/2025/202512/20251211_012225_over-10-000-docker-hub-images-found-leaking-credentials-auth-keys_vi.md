# Hơn 10.000 Docker Hub image phát hiện rò rỉ thông tin xác thực, khóa xác thực

![Hơn 10.000 Docker Hub image phát hiện rò rỉ thông tin xác thực, khóa xác thực](https://www.bleepstatic.com/content/hl-images/2022/04/21/Docker.jpg)

Hơn 10.000 Docker Hub container image phơi bày dữ liệu cần được bảo vệ, bao gồm thông tin xác thực trực tiếp tới hệ thống sản xuất, cơ sở dữ liệu CI/CD hoặc khóa mô hình LLM.

Các bí mật ảnh hưởng tới hơn 100 tổ chức, trong đó có một công ty thuộc Fortune 500 và một ngân hàng quốc gia lớn.

Docker Hub là registry container lớn nhất nơi các nhà phát triển tải lên, lưu trữ, chia sẻ và phân phối Docker images sẵn sàng sử dụng có chứa mọi thứ cần thiết để chạy một ứng dụng.

Các nhà phát triển thường sử dụng Docker images để hợp lý hóa toàn bộ vòng đời phát triển và triển khai phần mềm. Tuy nhiên, như [các nghiên cứu trước đây đã cho thấy](https://www.bleepingcomputer.com/news/security/thousands-of-images-on-docker-hub-leak-auth-secrets-private-keys/), sự cẩu thả khi tạo các image này có thể dẫn đến việc phơi bày các bí mật vẫn còn giá trị trong thời gian dài.

Sau khi quét các container image được tải lên Docker Hub vào tháng 11, các nhà nghiên cứu bảo mật tại công ty threat intelligence Flare phát hiện 10.456 image trong số đó đã phơi bày một hoặc nhiều khóa.

Các bí mật thường gặp nhất là access token cho các mô hình AI khác nhau (OpenAI, HuggingFace, Anthropic, Gemini, Groq). Tổng cộng, các nhà nghiên cứu tìm thấy 4.000 khóa như vậy.

Khi kiểm tra các image đã quét, các nhà nghiên cứu phát hiện 42% trong số đó phơi bày ít nhất năm giá trị nhạy cảm.

"Những phơi bày nhiều bí mật này đại diện cho rủi ro nghiêm trọng, vì chúng thường cung cấp quyền truy cập đầy đủ vào môi trường đám mây, kho Git, hệ thống CI/CD, tích hợp thanh toán, và các thành phần hạ tầng cốt lõi khác," Flare ghi nhận trong một [báo cáo](https://flare.io/learn/resources/docker-hub-secrets-exposed/) hôm nay.

![Kích thước của phơi bày bí mật](https://www.bleepstatic.com/images/news/u/1220909/2025/December/size.jpg)

**Kích thước của phơi bày bí mật**  
_Nguồn: Flare_

Phân tích 205 namespace cho phép các nhà nghiên cứu xác định tổng cộng 101 công ty, phần lớn là doanh nghiệp vừa và nhỏ, với một vài tập đoàn lớn xuất hiện trong dataset.

Dựa trên phân tích, hầu hết các tổ chức có bí mật bị phơi bày hoạt động trong lĩnh vực phát triển phần mềm, tiếp theo là các thực thể trong thị trường và công nghiệp, và AI cùng hệ thống thông minh.

Hơn 10 công ty trong ngành tài chính và ngân hàng đã có dữ liệu nhạy cảm bị phơi bày.

![Các loại công ty phơi bày bí mật trên Docker Hub trong tháng 11](https://www.bleepstatic.com/images/news/u/1220909/2025/December/firm-types.jpg)

**Các loại công ty phơi bày bí mật trên Docker Hub trong tháng 11**  
_Nguồn: Flare_

Theo các nhà nghiên cứu, một trong những lỗi thường gặp nhất được quan sát là việc sử dụng .ENV files mà các nhà phát triển dùng để lưu thông tin đăng nhập cơ sở dữ liệu, khóa truy cập đám mây, token và các dữ liệu xác thực khác cho một dự án.

Ngoài ra, họ tìm thấy token API được hardcoded cho dịch vụ AI trong các file ứng dụng Python, config.json files, cấu hình YAML, GitHub tokens, và thông tin đăng nhập cho nhiều môi trường nội bộ.

Một số dữ liệu nhạy cảm xuất hiện trong manifest của Docker images, một file cung cấp chi tiết về image.

Nhiều vụ rò rỉ dường như xuất phát từ các tài khoản được gọi là 'shadow IT', đó là các tài khoản Docker Hub nằm ngoài các cơ chế giám sát nghiêm ngặt của công ty, như tài khoản sử dụng cá nhân hoặc thuộc về nhà thầu.

Flare lưu ý rằng khoảng 25% các nhà phát triển vô tình phơi bày bí mật trên Docker Hub nhận ra sai lầm và xóa bí mật bị rò rỉ khỏi container hoặc file manifest trong vòng 48 giờ.

Tuy nhiên, trong 75% các trường hợp này, khóa bị rò rỉ đã không bị thu hồi, nghĩa là bất kỳ ai đánh cắp nó trong thời gian phơi bày vẫn có thể sử dụng sau này để tiến hành tấn công.

**Sơ đồ khai thác bí mật bị phơi bày**  
_Nguồn: Flare_

Flare gợi ý rằng các nhà phát triển tránh lưu trữ bí mật trong container images, ngừng sử dụng thông tin xác thực tĩnh có thời hạn dài, và tập trung quản lý bí mật của họ bằng cách sử dụng một vault hoặc secrets manager chuyên dụng.

Các tổ chức nên triển khai quét chủ động trên toàn bộ vòng đời phát triển phần mềm và thu hồi bí mật bị phơi bày cũng như vô hiệu hóa các phiên cũ ngay lập tức.