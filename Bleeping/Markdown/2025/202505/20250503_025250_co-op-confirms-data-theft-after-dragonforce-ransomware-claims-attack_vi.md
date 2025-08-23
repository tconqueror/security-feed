# Co-op xác nhận việc đánh cắp dữ liệu sau khi ransomware DragonForce tuyên bố tấn công

![Bảng hiệu Co-op](https://www.bleepstatic.com/content/hl-images/2025/04/30/co-op.jpg)

Cuộc tấn công mạng vào Co-op nghiêm trọng hơn nhiều so với báo cáo ban đầu, khi công ty xác nhận rằng dữ liệu đã bị đánh cắp từ một số lượng đáng kể khách hàng hiện tại và trước đây.

"Do các cuộc điều tra pháp y đang diễn ra, chúng tôi giờ đây biết rằng những kẻ tấn công đã có thể truy cập và trích xuất dữ liệu từ một trong những hệ thống của chúng tôi," Co-op nói với BleepingComputer.

"Dữ liệu đã truy cập bao gồm thông tin liên quan đến nhiều thành viên hiện tại và trước đây của chúng tôi."

"Dữ liệu này bao gồm thông tin cá nhân của các thành viên Co-op Group như tên và thông tin liên lạc, và không bao gồm mật khẩu, thông tin ngân hàng hoặc thẻ tín dụng của các thành viên, giao dịch hoặc thông tin liên quan đến bất kỳ sản phẩm hoặc dịch vụ nào của các thành viên hoặc khách hàng với Co-op Group."

Vào thứ Tư, gã khổng lồ bán lẻ Anh [Co-op đã giảm nhẹ nghiêm trọng cuộc tấn công mạng](https://www.bleepingcomputer.com/news/security/uk-retailer-co-op-shuts-down-some-it-systems-after-hack-attempt/), tuyên bố rằng họ đã tắt một phần hệ thống CNTT của mình sau khi phát hiện một nỗ lực xâm nhập vào mạng của họ.

Tuy nhiên, ngay sau khi tin tức được công bố, BleepingComputer đã biết rằng công ty thực sự đã gặp phải một lỗ hổng sử dụng các chiến thuật liên quan đến Scattered Spider/Octo Temptest, nhưng phòng thủ của họ đã ngăn chặn những kẻ tấn công gây ra thiệt hại đáng kể cho mạng lưới.

Các nguồn tin đã cho BleepingComputer biết rằng cuộc tấn công được cho là đã xảy ra vào ngày 22 tháng 4, với những kẻ tấn công sử dụng các chiến thuật tương tự như cuộc tấn công trước đó vào Marks and Spencer. Các kẻ tấn công reportedly đã thực hiện một cuộc tấn công kỹ thuật xã hội cho phép họ thiết lập lại mật khẩu của một nhân viên, từ đó truy cập vào mạng lưới.

Khi họ có quyền truy cập vào mạng, họ đã đánh cắp tệp Windows NTDS.dit, một cơ sở dữ liệu cho Windows Active Directory Services chứa các giá trị hash mật khẩu cho các tài khoản Windows.

Co-op hiện đang trong quá trình xây dựng lại tất cả các bộ điều khiển miền Windows của mình và tăng cường Entra ID với sự giúp đỡ của Microsoft DART. KPMG đang hỗ trợ với dịch vụ AWS.

Khi chia sẻ những chi tiết này với Co-op vào ngày hôm qua, công ty nói rằng họ không có thông tin gì thêm để chia sẻ và đã gửi cho chúng tôi tuyên bố ban đầu của họ.

## Ransomware DragonForce đứng sau cuộc tấn công

Hôm nay, [BBC đã báo cáo lần đầu tiên](https://www.bbc.com/news/articles/crkx3vy54nzo) rằng các đối tác của hoạt động ransomware DragonForce, cùng những [kẻ tấn công đã xâm phạm M&S](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/), cũng đứng sau cuộc tấn công vào Co-op.

Phóng viên BBC Joe Tidy đã nói chuyện với một điều hành viên của DragonForce, người xác nhận họ là tác giả của cuộc tấn công và đã chia sẻ các mẫu dữ liệu doanh nghiệp và khách hàng bị đánh cắp trong cuộc tấn công. Các kẻ tấn công khẳng định đã có dữ liệu của 20 triệu người đã đăng ký tham gia chương trình thưởng thành viên của Co-op.

Các kẻ tấn công cho biết họ đã liên hệ với người đứng đầu bảo mật mạng của Co-op và các giám đốc khác qua tin nhắn Microsoft Teams, chia sẻ các hình chụp màn hình của các thông điệp tống tiền với BBC.

Sau cuộc tấn công, Co-op đã gửi một email nội bộ tới nhân viên cảnh báo họ cần cảnh giác khi sử dụng Microsoft Teams và không được chia sẻ bất kỳ dữ liệu nhạy cảm nào, có thể là do lo ngại rằng các kẻ tấn công vẫn còn quyền truy cập vào nền tảng này.

Các kẻ tấn công cũng tuyên bố với BBC rằng họ đã đứng sau cuộc tấn công [mạng vào Harrods](https://www.bleepingcomputer.com/news/security/harrods-the-next-uk-retailer-targeted-in-a-cyberattack/).

DragonForce là một hoạt động ransomware-as-a-service mà các tội phạm mạng khác có thể tham gia dưới dạng đối tác để sử dụng các bộ mã hóa ransomware và trang đàm phán của họ. Đổi lại, các điều hành viên DragonForce nhận được 20-30% của bất kỳ khoản tiền chuộc nào được trả bởi các nạn nhân bị tống tiền.

Trong các cuộc tấn công, các đối tác sẽ xâm nhập vào một mạng, đánh cắp dữ liệu, và cuối cùng triển khai phần mềm độc hại mã hóa các tệp trên tất cả các máy chủ và máy trạm. Các kẻ tấn công sau đó yêu cầu thanh toán tiền chuộc để lấy lại trình giải mã và hứa rằng dữ liệu bị đánh cắp sẽ được xóa.

Nếu không thanh toán tiền chuộc, hoạt động ransomware thường công khai dữ liệu bị đánh cắp trên trang web rò rỉ dữ liệu mật của họ trên dark web.

DragonForce là một hoạt động tương đối mới nhưng đang [chuẩn bị trở thành một trong những hoạt động nổi bật hơn](https://www.bleepingcomputer.com/news/security/dragonforce-expands-ransomware-model-with-white-label-branding-scheme/) trong lĩnh vực ransomware.

Họ được cho là đang làm việc với các kẻ tấn công nói tiếng Anh phù hợp với một [chuỗi chiến thuật cụ thể](https://www.bleepingcomputer.com/news/security/fbi-shares-tactics-of-notorious-scattered-spider-hacker-collective/) liên quan đến tên gọi "Scattered Spider" hoặc "[Octo Tempest](https://www.bleepingcomputer.com/news/security/microsoft-octo-tempest-is-one-of-the-most-dangerous-financial-hacking-groups/)."

Các kẻ tấn công này là chuyên gia trong việc sử dụng các cuộc tấn công kỹ thuật xã hội, SIM Swapping, [và các cuộc tấn công mệt mỏi MFA](https://www.bleepingcomputer.com/news/security/mfa-fatigue-hackers-new-favorite-tactic-in-high-profile-breaches/) để xâm nhập vào các mạng và sau đó đánh cắp dữ liệu hoặc triển khai ransomware. Các kẻ tấn công này được biết đến với việc tống tiền nạn nhân một cách quyết liệt.

Cần lưu ý rằng Scatted Spider không phải là một băng nhóm hoặc nhóm có các thành viên cụ thể. Thay vào đó, họ là một cộng đồng linh hoạt gồm các kẻ tấn công có động cơ tài chính tụ tập trên cùng các kênh Telegram, máy chủ Discord và diễn đàn hack.

Do họ "rải rác" trong cảnh quan tội phạm mạng, việc thực thi pháp luật gặp khó khăn hơn trong việc theo dõi những người cụ thể có liên quan đến một cuộc tấn công.

Các kẻ tấn công ban đầu liên quan đến phân loại Scattered Spider đã đứng sau một chuỗi các cuộc tấn công, bao gồm các cuộc tấn công vào [MGM](https://www.bleepingcomputer.com/news/security/mgm-resorts-shuts-down-it-systems-after-cyberattack/) và [Reddit](https://www.bleepingcomputer.com/news/security/reddit-hackers-threaten-to-leak-data-stolen-in-february-breach/). 

Một số, nếu không phải tất cả, các hacker ban đầu này đã bị [Mỹ](https://www.bleepingcomputer.com/news/security/us-arrests-scattered-spider-suspect-linked-to-telecom-hacks/), [Vương quốc Anh](https://www.bleepingcomputer.com/news/security/uk-arrests-suspected-scattered-spider-hacker-linked-to-mgm-attack/), và [Tây Ban Nha](https://www.bleepingcomputer.com/news/legal/alleged-scattered-spider-sim-swapper-arrested-in-spain/) bắt giữ.

Tuy nhiên, các hacker trước đây chưa rõ danh tính hoặc những kẻ bắt chước hiện đang sử dụng cùng một phương pháp để leo thang cuộc tấn công.

Nhà nghiên cứu an ninh mạng Will Thomas đã tổng hợp một [hướng dẫn được khuyến nghị](https://www.sans.org/blog/defending-against-scattered-spider-and-the-com-with-cybercrime-intelligence/) về cách phòng thủ chống lại các cuộc tấn công của Scattered Spider.