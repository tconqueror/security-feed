# Hai lỗ hổng mới trong Supermicro BMC cho phép firmware độc hại né tránh bảo mật Root of Trust

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEha20McHRa6QM9%5FcLc5Zt0tgtjRrsac1WMDmrRCwhyphenhyphenZDOgR9xL9btaZ6kzvvX3O1qceOw6fEkSwDCvv-5lhAw7FHGAHgCtFH%5FyMRbmkD6cCiHmTInnVxWNUA2-SmYefabOsra8y%5Fv49M7aDTFMuT52Tt7CWhbFC9wWiYLeQ8fZ-hVYdWCKntdz%5Fvx82qf8U/s728-rw-e365/bmc-exploit.jpg)

Các nhà nghiên cứu an ninh mạng đã tiết lộ chi tiết về hai lỗ hổng ảnh hưởng đến firmware của Supermicro Baseboard Management Controller (BMC) có thể cho phép kẻ tấn công vượt qua các bước xác thực quan trọng và cập nhật hệ thống bằng một ảnh firmware được chế tạo đặc biệt.

Các [lỗ hổng mức độ trung bình](https://www.supermicro.com/en/support/security%5FBMC%5FIPMI%5FSept%5F2025), đều phát sinh từ việc kiểm tra chữ ký mật mã không đúng cách, được liệt kê dưới đây -

* **[CVE-2025-7937](https://nvd.nist.gov/vuln/detail/CVE-2025-7937)** (điểm CVSS: 6.6) - Một ảnh firmware được chế tạo có thể qua mặt logic xác thực firmware của Supermicro BMC trong Root of Trust (RoT) 1.0 để cập nhật firmware hệ thống bằng cách chuyển hướng chương trình đến một bảng "fwmap" giả trong vùng không được ký
* **[CVE-2025-6198](https://nvd.nist.gov/vuln/detail/CVE-2025-6198)** (điểm CVSS: 6.4) - Một ảnh firmware được chế tạo có thể qua mặt logic xác thực firmware của Supermicro BMC trong Signing Table để cập nhật firmware hệ thống bằng cách chuyển hướng chương trình đến một bảng signing table ("sig_table") giả trong vùng không được ký

[](https://thehackernews.uk/exec-guide-d)

Quá trình xác thực ảnh được thực hiện trong quá trình cập nhật firmware diễn ra qua ba bước: Lấy khóa công khai từ chip SPI flash của BMC, xử lý bảng "fwmap" hoặc "sig_table" được nhúng trong ảnh tải lên, và tính toán digest băm mật mã của tất cả các vùng firmware "được ký", rồi xác minh giá trị chữ ký so với digest đã tính.

Công ty an ninh firmware Binarly, đơn vị được ghi nhận đã phát hiện và thông báo hai thiếu sót này, cho biết CVE-2025-7937 là một bypass cho [CVE-2024-10237](https://www.binarly.io/blog/ghost-in-the-controller-abusing-supermicro-bmc-firmware-verification), vốn đã được Supermicro [công bố](https://nvd.nist.gov/vuln/detail/CVE-2024-10237) vào tháng 1 năm 2025. Lỗ hổng này ban đầu được [phát hiện](https://developer.nvidia.com/blog/analyzing-baseboard-management-controllers-to-secure-data-center-infrastructure/) bởi NVIDIA, cùng với CVE-2024-10238 và CVE-2024-10239.

CVE-2024-10237 là một "lỗi logic trong quy trình xác thực của firmware tải lên, điều này cuối cùng có thể dẫn đến việc chip SPI của BMC bị flash lại bằng một ảnh độc hại," nhà nghiên cứu của Binarly, Anton Ivanov, [cho biết](https://www.binarly.io/blog/broken-trust-fixed-supermicro-bmc-bug-gains-a-new-life-in-two-new-vulnerabilities) trong một báo cáo chia sẻ với The Hacker News. "Vấn đề bảo mật này có thể cho phép kẻ tấn công tiềm năng giành quyền kiểm soát hoàn toàn và dai dẳng cả hệ thống BMC lẫn hệ điều hành máy chủ chính."

"Lỗ hổng này cho thấy quy trình xác thực có thể bị thao túng bằng cách thêm các mục tùy chỉnh vào bảng 'fwmap' và di dời nội dung đã được ký ban đầu của ảnh sang vùng firmware không được đặt trước, điều này đảm bảo rằng digest được tính vẫn khớp với giá trị đã ký."

Mặt khác, CVE-2024-10238 và CVE-2024-10239 là hai lỗi tràn ngăn xếp trong hàm xác thực ảnh của firmware, cho phép kẻ tấn công thực thi mã tùy ý trong ngữ cảnh BMC.

Phân tích của Binarly nhận thấy bản sửa cho CVE-2024-10237 là không đủ, xác định một con đường tấn công tiềm năng bằng cách chèn một bảng "fwmap" tùy chỉnh trước bảng gốc, sau đó được sử dụng trong quy trình xác thực. Điều này về cơ bản cho phép tác nhân đe dọa chạy mã tùy chỉnh trong ngữ cảnh hệ thống BMC.

[](https://thehackernews.uk/cis-security-suite)

Điều tra thêm về cách triển khai logic xác thực firmware trên bo mạch chủ X13SEM-F xác định một lỗi trong hàm "auth_bmc_sig" có thể cho phép kẻ tấn công tải một ảnh độc hại mà không sửa đổi giá trị digest băm.

"Một lần nữa, vì tất cả các vùng dùng để tính digest được định nghĩa trong chính ảnh tải lên (trong 'sig_table'), có thể sửa đổi nó, cùng với một số phần khác của ảnh – ví dụ, kernel – và chuyển dữ liệu gốc sang vùng không dùng trong firmware," Ivanov nói. "Điều này có nghĩa là digest của dữ liệu đã được ký vẫn sẽ khớp với giá trị gốc."

Khai thác thành công CVE-2025-6198 không chỉ có thể cập nhật hệ thống BMC bằng một ảnh được chế tạo đặc biệt, mà còn vượt qua tính năng bảo mật BMC RoT.

"Trước đây, chúng tôi đã báo cáo việc phát hiện khóa thử nghiệm trên các thiết bị Supermicro, và PSIRT của họ đã khẳng định rằng phần cứng RoT (Root of Trust) xác thực khóa và điều đó không ảnh hưởng đến phát hiện này," Alex Matrosov, CEO kiêm Trưởng bộ phận REsearch tại Binarly, nói với The Hacker News.

"Tuy nhiên, nghiên cứu mới cho thấy tuyên bố trước đó từ Supermicro không chính xác, và CVE-2025-6198 vượt qua BMC RoT. Trong trường hợp này, bất kỳ rò rỉ nào của khóa ký sẽ ảnh hưởng toàn bộ hệ sinh thái. Tái sử dụng khóa ký không phải là phương pháp tốt nhất, và chúng tôi khuyến nghị ít nhất là xoay vòng các khóa ký theo dòng sản phẩm. Dựa trên các sự cố trước như [PKfail](https://thehackernews.com/2024/08/new-flaws-in-sonos-smart-speakers-allow.html) và việc rò rỉ khóa Intel Boot Guard, việc tái sử dụng các khóa ký mật mã có thể gây ảnh hưởng toàn ngành."