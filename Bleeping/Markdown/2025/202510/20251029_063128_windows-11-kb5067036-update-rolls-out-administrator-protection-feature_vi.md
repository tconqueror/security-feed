# Windows 11 KB5067036 cập nhật triển khai tính năng Administrator Protection

![Windows 11](https://www.bleepstatic.com/content/hl-images/2024/07/18/Windows-11.jpg)

Microsoft đã phát hành bản cập nhật tích lũy xem trước KB5067036 cho Windows 11 24H2 và 25H2, bắt đầu triển khai tính năng bảo mật Administrator Protection và một Start Menu được cập nhật.

Bản cập nhật [KB5067036](https://support.microsoft.com/en-us/topic/october-28-2025-kb5067036-os-builds-26200-7019-and-26100-7019-preview-ec3da7dc-63ba-4b1d-ac41-cf2494d2123a#id0ebdj=gradual%5Frollout) là một phần trong lịch cập nhật xem trước không bảo mật tùy chọn của công ty, phát hành các bản cập nhật vào cuối mỗi tháng để thử nghiệm các sửa lỗi và tính năng mới sẽ đến trong Patch Tuesday của tháng tiếp theo.

Khác với các bản cập nhật tích lũy vào Patch Tuesday thông thường, các bản cập nhật xem trước hàng tháng không bao gồm bản vá bảo mật và là tùy chọn.

Bạn có thể cài đặt bản cập nhật KB5067036 bằng cách mở **Settings**, nhấp vào **Windows Update**, rồi chọn **"Check for Updates"**.

Vì đây là một bản cập nhật tùy chọn, bạn sẽ được hỏi có muốn cài đặt hay không bằng cách nhấp vào liên kết "Download and install" trừ khi bạn đã bật tùy chọn "Get the latest updates as soon as they're available", điều này sẽ khiến bản cập nhật tự động cài đặt.

![KB5067036 preview update](https://www.bleepstatic.com/images/news/Microsoft/windows-11/KB5064081.jpg)

_KB5067036 preview update_  
_Nguồn: BleepingComputer_

Bạn cũng có thể tải xuống và cài đặt thủ công bản cập nhật KB5067036 xem trước từ Microsoft Update Catalog.

## Điểm nổi bật của Windows 11 KB5067036

Sau khi cài đặt, bản phát hành tích lũy tùy chọn này sẽ cập nhật hệ thống Windows 11 24H2 lên build 26100.5074 và Windows 11 25H2 lên 26100.7019.

Bản cập nhật xem trước tháng Mười 2025 có nhiều bổ sung mới, bao gồm sửa lỗi cho các vấn đề đã làm [Media Creation Tool](https://www.bleepingcomputer.com/news/microsoft/microsoft-windows-11-media-creation-tool-broken-on-windows-10-pcs/) bị hỏng và gây [vấn đề khi thiết lập kết nối HTTP/2](https://www.bleepingcomputer.com/news/microsoft/windows-11-updates-break-localhost-127001-http-2-connections/) tới các dịch vụ web chạy trên localhost.

Một trong những tính năng đang được triển khai dần cho người dùng là Start Menu được thiết kế lại, bao gồm các hạng mục và chế độ lưới mới, bố cục đáp ứng và phần "All" có thể cuộn, giúp bạn dễ dàng tìm ứng dụng hơn.

Một tính năng được mong đợi khác là việc triển khai tính năng mới [Administrator Protection feature](https://www.bleepingcomputer.com/news/microsoft/microsoft-shares-more-details-on-windows-11-admin-protection/), giảm rủi ro chương trình độc hại chạy lệnh hoặc thực hiện hành động yêu cầu quyền quản trị.

"Administrator protection requires that a user verify their identity with Windows Hello integrated authentication before allowing any action that requires administrator privileges," giải thích Microsoft.

"Những hành động này bao gồm cài đặt phần mềm, thay đổi cài đặt hệ thống như thời gian hoặc registry, và truy cập dữ liệu nhạy cảm. Administrator protection giảm thiểu rủi ro người dùng vô tình thực hiện thay đổi ở mức hệ thống, và quan trọng hơn, giúp ngăn chặn phần mềm độc hại thay đổi hệ thống một cách thầm lặng mà người dùng không biết."

![Administrator Protection feature](https://www.bleepstatic.com/images/news/Microsoft/a/administrator-protection/administrator-protection.png)

**Administrator Protection feature**  
_Nguồn: Microsoft_

Các tính năng sau đây đang được triển khai ngay lập tức cho tất cả người dùng Windows 11:

* **[Authentication]**  
   * Sửa: Một vấn đề gây ra lỗi ACCESS_DENIED khi người dùng cố gắng thay đổi mật khẩu từ xa trên member servers hoặc thiết bị workgroup, ngay cả khi họ có quyền cần thiết.  
   * Sửa: Bản cập nhật này giải quyết một vấn đề ảnh hưởng đến dịch vụ Kerberos Key Distribution Center (KDC) trên domain controller của server. Khi dịch vụ KDC bị dừng thủ công, server không thể lấy vé Kerberos.  
   * Sau khi cài đặt bản cập nhật bảo mật tháng Chín 2025 cho Windows Server 2022 ([KB5065432](https://support.microsoft.com/en-us/topic/september-9-2025-kb5065432-os-build-20348-4171-78d6c76c-f2cc-40d5-bb3a-290abf4a0321)), bạn có thể gặp vấn đề xác thực lặp lại với Active Directory Federation Services (AD FS).
* **[Display]** Sửa: Sau các bản cập nhật gần đây, văn bản có thể không hiển thị đúng khi chỉnh sửa nội dung trong hộp văn bản nhiều dòng trong một số ứng dụng.
* **[Installation (known issue)]** Sửa: Media Creation Tool (version 26100.6584), phát hành ngày 29 tháng Chín, 2025, có thể không hoạt động như mong đợi trên các thiết bị Arm64. Người dùng có thể gặp thông báo lỗi như: “We’re not sure what happened, but we're unable to run this tool on your PC." Đây là một vấn đề đã biết cho Windows 11, phiên bản 25H2.
* **[Media (known issue)]** Sửa: Bản cập nhật này giải quyết một vấn đề trong đó phát lại nội dung được bảo vệ thất bại trên một số máy sau khi cài đặt [KB5064081](https://support.microsoft.com/en-us/topic/august-29-2025-kb5064081-os-build-26100-5074-preview-3f9eb9e1-72ca-4b42-af97-39aace788d93).
* **[Networking (known issue)]** Sửa: Đã xảy ra vấn đề nơi các web server sử dụng HTTP.sys (chẳng hạn như Internet Information Services [IIS]) từ chối các yêu cầu HTTP đến với lỗi “NOT_SUPPORTED”.
* **[Screen readers]** Sửa: Sau các bản cập nhật gần đây, screen reader có thể bất ngờ nói "legacy window" mà không đọc nội dung cửa sổ khi tương tác với một số ứng dụng.

Microsoft cũng đang triển khai dần các tính năng sau cho người dùng sau khi cài đặt bản cập nhật:

* **[Start menu] _New!_** Start menu được thiết kế lại, giúp bạn truy cập ứng dụng nhanh và mượt hơn. Bố cục mới giúp bạn dễ tìm thứ cần thiết hơn bao giờ hết.  
   * **Scrollable ‘All’ section:** Trang chính giờ bao gồm phần “All” có thể cuộn, giúp dễ tìm ứng dụng hơn.  
   * **Category and grid views:** Chuyển giữa hai chế độ mới — chế độ danh mục nhóm ứng dụng theo loại và làm nổi bật các ứng dụng sử dụng thường xuyên, và chế độ lưới liệt kê ứng dụng theo thứ tự chữ cái với nhiều không gian ngang hơn để dễ quét. Menu ghi nhớ chế độ bạn chọn lần trước.  
   * **Responsive layout:** Start menu thích ứng với kích thước màn hình. Màn hình lớn hơn hiển thị nhiều ứng dụng ghim, đề xuất và danh mục hơn theo mặc định. Các phần như Pinned và Recommended mở rộng hoặc thu gọn dựa trên nội dung. Bạn có thể tùy chỉnh các chế độ này trong **Settings** > **Personalization** > **Start.**  
   * **Phone Link integration:** Một nút thiết bị di động mới bên cạnh Search cho phép bạn mở rộng hoặc thu gọn nội dung từ điện thoại đã kết nối. Tính năng này hỗ trợ Android và iOS ở hầu hết thị trường và sẽ ra mắt ở European Economic Area (EEA) vào 2025.
* **[File Explorer]**  
   * _New!_ 3 Recommended files trong **File Explorer Home** hiện có sẵn cho tài khoản Microsoft cá nhân và tài khoản cục bộ. Những tệp này bao gồm nội dung bạn thường xuyên sử dụng, đã tải xuống gần đây, hoặc thêm vào **File Explorer Gallery**. Nếu bạn không muốn thấy phần được đề xuất trong File Explorer Home, bạn có thể tắt nó trong **File Explorer Folder Options**. Khi tính năng này bị tắt, các thư mục ghim vào **Quick Access** sẽ xuất hiện thay thế.  
   * _New!_ StorageProvider APIs hiện có sẵn để các nhà cung cấp đám mây tích hợp với File Explorer Home. Các nhà phát triển có thể tìm hiểu cách [enable the system to query for suggested files](https://learn.microsoft.com/uwp/api/windows.storage.provider.istorageprovidersuggestionshandler?view=winrt-26100).  
   * Sửa: File Explorer context menu có thể bất ngờ chuyển qua lại giữa chế độ xem bình thường và **Show More Options** mỗi khi nhấp chuột phải.  
   * Sửa: Khi mở một thư mục từ ứng dụng khác (ví dụ, mở **Downloads folder** từ trình duyệt), chế độ xem tùy chỉnh của bạn — bao gồm sắp xếp tệp theo tên, thay đổi kích thước biểu tượng, hoặc loại bỏ nhóm — bất ngờ bị đặt lại về mặc định.  
   * Sửa: Phần thân cửa sổ **File explorer** có thể không còn phản hồi các cú nhấp chuột chuột sau khi gọi **context menu**.  
   * Sửa: Giải nén các thư mục lưu trữ rất lớn (1.5gb+) có thể thất bại với “Catastrophic Error” (mã lỗi 0x8000FFFF).  
   * Sửa: **File Explorer** có thể trở nên không phản hồi khi mở **Home**.
* **[Lock screen] _New!_** Các biểu tượng pin mới, bao gồm chỉ báo màu và phần trăm pin, giờ xuất hiện ở góc phải dưới của lock screen. Tính năng này giúp dễ dàng kiểm tra trạng thái sạc và mức pin của thiết bị ngay lập tức. Để tìm hiểu thêm về biểu tượng pin, xem **Taskbar**.
* **[Microsoft 365 Copilot] _New!_** Một trang **Microsoft 365 Copilot** mới đã được thêm vào trải nghiệm **Get Started** cho thiết bị thương mại có đăng ký Microsoft 365 hoạt động. Trang này giúp bạn tìm hiểu về tính năng Microsoft 365 Copilot và bắt đầu sử dụng dễ dàng hơn.
* **[Settings] _New!_** Mục “Email & accounts” giờ được gọi là “Your accounts.” Bạn quản lý tất cả tài khoản của mình trong **Settings** > **Accounts**.
* **[Taskbar]**  
   * _New!_ Các biểu tượng pin đã được cập nhật để dễ kiểm tra trạng thái PC ngay lập tức. Chỉ báo màu cho biết trạng thái sạc và mức pin: màu xanh lá chỉ PC đang sạc và ở tình trạng tốt, màu vàng cho thấy chế độ tiết kiệm pin đang bật ở 20% hoặc thấp hơn, và màu đỏ báo pin rất thấp. Các lớp phủ đơn giản giữ thanh tiến trình hiển thị, và biểu tượng xuất hiện trong system tray, Quick Settings và Settings, với hỗ trợ Lock screen sắp ra mắt. Để hiển thị phần trăm pin bên cạnh biểu tượng, vào **Settings** > **System** > **Power & battery**, sau đó bật Battery Percentage. Bạn vẫn có thể xem thông tin pin chi tiết bằng cách di chuột qua biểu tượng pin hoặc mở cài đặt **Power & battery**.​​​​  
   * **[Administrator Protection Preview] _New!_** [Administrator protection](https://techcommunity.microsoft.com/blog/windows-itpro-blog/administrator-protection-on-windows-11/4303482) nhằm bảo vệ quyền quản trị nổi tự do (free floating admin rights) cho quản trị viên. Nó cho phép người dùng thực hiện các tác vụ quản trị bằng đặc quyền just-in-time. Tính năng này mặc định bị tắt và có thể được bật bằng OMA-URI trong Microsoft Intune hoặc thông qua Group Policy.  
   * **[Display and Graphics]**  
         * Sửa: Ứng dụng và trình duyệt có thể hiển thị nội dung màn hình một phần không phản hồi khi các ứng dụng khác ở chế độ tối đa hoặc toàn màn hình đang cập nhật ở nền. Vấn đề này đặc biệt đáng chú ý khi cuộn, vì chỉ một phần nội dung cửa sổ có thể được cập nhật.  
         * Sửa: Sau khi bạn cài đặt [KB5064081](https://support.microsoft.com/en-us/topic/august-29-2025-kb5064081-os-build-26100-5074-preview-3f9eb9e1-72ca-4b42-af97-39aace788d93), một số video và trò chơi có thể bất ngờ chuyển sang màu đỏ.  
         * Sửa: Nếu **Connected Devices Platform Service** bị vô hiệu hóa, Settings có thể ngừng phản hồi hoặc đóng đột ngột khi bạn cố mở **Settings** > **System** > **Display**, kể cả khi khởi chạy từ **desktop context menu**.  
   * **[Input]** Sửa: Một vấn đề với microsoft.ink.dll và các API liên quan có thể khiến nhập bằng bút và chữ viết tay không phản hồi trong ứng dụng hoặc dẫn đến ứng dụng đóng bất ngờ do ném ngoại lệ.  
   * **[Narrator]** Sửa: Narrator bị lỗi khi cố khởi chạy trong quá trình thiết lập Windows bằng ISO.  
   * **[Open and Save Dialog]** Sửa: Một số ứng dụng có thể trở nên không phản hồi khi khởi chạy **Open or Save Dialog**.  
   * **[Remote Credential Guard]** Sửa: Các kịch bản Remote Credential Guard giữa các build Windows 11 mới nhất và Windows Server 2022 hoặc cũ hơn có thể bất ngờ thất bại.  
   * **[Sign in to your PC]:** Cải thiện: Đã thực hiện thay đổi nền tảng để cải thiện hiệu suất tải taskbar sau khi mở khóa PC từ chế độ ngủ. Điều này cũng giúp trong các trường hợp trường mật khẩu và các nội dung màn hình đăng nhập khác không hiển thị khi chuyển từ lock screen sang màn hình đăng nhập sau khi ngủ.  
   * **[Task Manager]** Sửa: Một số ứng dụng có thể bất ngờ không được nhóm cùng với tiến trình của chúng.  
   * **[Windows Update]**  
         * Cải thiện: Đã xử lý vấn đề nền tảng có thể khiến “Update and shutdown” không thực sự tắt PC sau khi cập nhật.  
         * Cải thiện: Đã xử lý vấn đề nền tảng có thể khiến Windows Update không cài đặt được với **error 0x800f0983**.

Microsoft cho biết hiện tại không có vấn đề đã biết nào với bản cập nhật này.

Ghi chú phát hành đầy đủ cho KB5067036 có thể được tìm thấy trong [support bulletin](https://support.microsoft.com/en-us/topic/october-28-2025-kb5067036-os-builds-26200-7019-and-26100-7019-preview-ec3da7dc-63ba-4b1d-ac41-cf2494d2123a#id0ebdj=gradual%5Frollout).