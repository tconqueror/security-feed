# Băng nhóm ransomware lợi dụng máy ảo ISPsystem để che giấu việc phân phối payload

![Ransomware gang uses ISPsystem VMs for stealthy payload delivery](https://www.bleepstatic.com/content/hl-images/2025/02/12/ransomware-3.jpg)

Các nhóm vận hành ransomware đang lưu trữ và phân phối payload độc hại hàng loạt bằng cách lạm dụng các máy ảo (VM) được cung cấp bởi ISPsystem, một nhà cung cấp quản lý hạ tầng ảo hợp pháp.

Các nhà nghiên cứu tại công ty an ninh mạng Sophos đã quan sát thấy chiến thuật này khi điều tra các sự cố ransomware 'WantToCry' gần đây. Họ phát hiện ra rằng kẻ tấn công sử dụng các máy ảo Windows có hostname giống nhau, cho thấy các mẫu (template) mặc định được tạo bởi VMmanager của ISPsystem.

Đào sâu hơn, các nhà nghiên cứu phát hiện ra rằng các hostname giống nhau cũng xuất hiện trong hạ tầng của nhiều nhóm vận hành ransomware, bao gồm LockBit, Qilin, Conti, BlackCat/ALPHV và Ursnif, cũng như các chiến dịch phần mềm độc hại liên quan đến RedLine và Lummar info-stealers.

[![Wiz](https://www.bleepstatic.com/c/w/GitLab-970x250.png)](https://www.wiz.io/lp/gitlab-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FGitLab-Security-Best-Practices-Cheat-Sheet&sfcid=701Vh00000Wn1rmIAB&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=GitLab-Best-Practices)

![Vị trí của các thiết bị sử dụng cùng hostname](https://www.bleepstatic.com/images/news/u/1220909/2026/February/vm-infrastructure-202602-fig1.jpg)

**Vị trí của các thiết bị sử dụng cùng hostname**  
_Nguồn: Sophos_

ISPsystem là một công ty phần mềm hợp pháp phát triển bảng điều khiển cho các nhà cung cấp dịch vụ lưu trữ, được sử dụng để quản lý máy chủ ảo, bảo trì hệ điều hành, v.v. VMmanager là nền tảng quản lý ảo hóa của công ty dùng để tạo ra các máy ảo Windows hoặc Linux cho khách hàng.

[Sophos phát hiện](https://www.sophos.com/en-gb/blog/malicious-use-of-virtual-machine-infrastructure) rằng các mẫu Windows mặc định của VMmanager tái sử dụng cùng hostname và các định danh hệ thống mỗi khi được triển khai.

Các nhà cung cấp dịch vụ lưu trữ "bulletproof" (chống đạn) cố tình hỗ trợ các hoạt động tội phạm mạng và bỏ qua yêu cầu gỡ bỏ đã lợi dụng điểm yếu thiết kế này. Chúng cho phép tin tặc tạo máy ảo qua VMmanager để sử dụng làm hạ tầng điều khiển và kiểm soát (C2) cũng như phân phối payload.

Về cơ bản, điều này giúp che giấu các hệ thống độc hại giữa hàng nghìn hệ thống vô hại, làm phức tạp việc truy vết và khiến việc gỡ bỏ nhanh chóng trở nên khó khăn.

Phần lớn các máy ảo độc hại được lưu trữ bởi một nhóm nhỏ các nhà cung cấp có danh tiếng xấu hoặc bị trừng phạt, bao gồm Stark Industries Solutions Ltd., Zomro B.V., First Server Limited, Partner Hosting LTD và JSC IOT.

Sophos cũng phát hiện một nhà cung cấp có quyền kiểm soát trực tiếp hạ tầng vật lý tên là MasterRDP, sử dụng VMmanager để trốn tránh và cung cấp các dịch vụ VPS và RDP không tuân thủ yêu cầu pháp lý.

Theo Sophos, bốn hostname ISPsystem phổ biến nhất "chiếm hơn 95% tổng số máy ảo ISPsystem tiếp xúc internet:"

* WIN-LIVFRVQFMKO
* WIN-LIVFRVQFMKO
* WIN-344VU98D3RU
* WIN-J9D866ESIJ2

Tất cả chúng đều xuất hiện trong dữ liệu phát hiện khách hàng hoặc dữ liệu telemetry liên quan đến hoạt động tội phạm mạng.

Các nhà nghiên cứu lưu ý rằng mặc dù ISPsystem VMmanager là nền tảng hợp pháp để quản lý ảo hóa, nhưng nó cũng hấp dẫn tội phạm mạng vì "chi phí thấp, rào cản gia nhập thấp và khả năng triển khai nhanh chóng."

BleepingComputer đã liên hệ với ISPsystem để hỏi liệu họ có biết về việc lạm dụng hàng loạt các mẫu VM và kế hoạch giải quyết vấn đề hay không, nhưng chưa nhận được tuyên bố nào trước thời điểm xuất bản.