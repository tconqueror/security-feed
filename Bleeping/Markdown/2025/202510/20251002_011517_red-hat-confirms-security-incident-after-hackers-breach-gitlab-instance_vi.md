# Red Hat xác nhận sự cố bảo mật sau khi tin tặc xâm nhập hệ thống GitLab

![Red Hat logo](https://www.bleepstatic.com/content/hl-images/2025/10/02/redhat-header-vign.jpg)

_Chỉnh sửa: Sau khi xuất bản, Red Hat xác nhận rằng đó là một vi phạm tài khoản GitLab, không phải GitHub._

Một nhóm tống tiền tự gọi là Crimson Collective tuyên bố đã xâm nhập các kho tư nhân GitLab của Red Hat, đánh cắp gần 570GB dữ liệu nén trên 28.000 dự án nội bộ.

Dữ liệu này được cho là bao gồm khoảng 800 Báo cáo Tương tác Khách hàng (CERs), có thể chứa thông tin nhạy cảm về mạng và nền tảng của khách hàng.

Một CER là tài liệu tư vấn chuẩn bị cho khách hàng, thường chứa chi tiết hạ tầng, dữ liệu cấu hình, token xác thực, và các thông tin khác có thể bị lợi dụng để xâm nhập mạng của khách hàng.

Red Hat xác nhận rằng họ đã gặp sự cố bảo mật liên quan đến mảng tư vấn của mình, nhưng từ chối xác minh bất kỳ tuyên bố nào của kẻ tấn công về các kho GitLab và các CERs bị đánh cắp.

"Red Hat nắm được các báo cáo liên quan đến một sự cố bảo mật liên quan đến mảng tư vấn của chúng tôi và chúng tôi đã khởi xướng các bước khắc phục cần thiết," Red Hat nói với BleepingComputer.

"Tính bảo mật và toàn vẹn của hệ thống cũng như dữ liệu được giao phó cho chúng tôi là ưu tiên hàng đầu. Tại thời điểm này, chúng tôi không có lý do để tin rằng vấn đề bảo mật ảnh hưởng đến bất kỳ dịch vụ hoặc sản phẩm Red Hat nào khác và rất tự tin về tính toàn vẹn của chuỗi cung ứng phần mềm của chúng tôi."

Trong khi Red Hat không trả lời thêm câu hỏi về vụ vi phạm, các tin tặc nói với BleepingComputer rằng vụ xâm nhập xảy ra khoảng hai tuần trước.

Họ cáo buộc đã tìm thấy token xác thực, URI cơ sở dữ liệu đầy đủ, và các thông tin riêng tư khác trong mã của Red Hat và các CERs, mà họ tuyên bố đã sử dụng để truy cập vào hạ tầng khách hàng downstream.

Nhóm tấn công cũng đã công bố một danh sách thư mục hoàn chỉnh của các kho GitLab bị cho là bị đánh cắp và một danh sách các CERs từ 2020 đến 2025 trên Telegram.

Danh sách thư mục các CERs bao gồm nhiều lĩnh vực và các tổ chức nổi tiếng như Bank of America, T-Mobile, AT&T, Fidelity, Kaiser, Mayo Clinic, Walmart, Costco, U.S. Navy’s Naval Surface Warfare Center, Federal Aviation Administration, House of Representatives, và nhiều tổ chức khác.

Nếu bạn có bất kỳ thông tin nào liên quan đến sự cố này hoặc bất kỳ cuộc tấn công chưa được tiết lộ nào khác, bạn có thể liên hệ với chúng tôi một cách bí mật qua Signal tại 646-961-3731 hoặc tại tips@bleepingcomputer.com.

Các tin tặc cho biết họ đã cố gắng liên hệ với Red Hat để đưa ra yêu cầu tống tiền nhưng chỉ nhận được phản hồi mẫu hướng dẫn họ gửi báo cáo lỗ hổng cho đội bảo mật.

Theo họ, ticket được tạo đã liên tục được chuyển cho thêm nhiều người, bao gồm cả thành viên pháp lý và bảo mật của Red Hat.

BleepingComputer đã gửi thêm câu hỏi cho Red Hat, và chúng tôi sẽ cập nhật câu chuyện này nếu nhận được thêm thông tin.

Cùng nhóm này cũng nhận trách nhiệm về việc tạm thời [defacing Nintendo’s topic page](http://x.com/pirat%5Fnation/status/1970821013559538141) tuần trước để thêm thông tin liên hệ và liên kết đến kênh Telegram của họ.