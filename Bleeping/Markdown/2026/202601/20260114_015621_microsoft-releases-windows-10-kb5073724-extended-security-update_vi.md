# Microsoft phát hành bản cập nhật bảo mật mở rộng Windows 10 KB5073724

![Windows 10](https://www.bleepstatic.com/content/hl-images/2024/09/10/windows-10-gradient.jpg)

Microsoft đã phát hành bản cập nhật bảo mật mở rộng KB5073724 để sửa các bản cập nhật bảo mật Patch Tuesday, bao gồm 3 lỗ hổng zero-day và một bản sửa cho chứng chỉ Secure Boot sắp hết hạn.

Nếu bạn đang chạy Windows 10 Enterprise LTSC hoặc đã đăng ký chương trình ESU, bạn có thể cài đặt bản cập nhật này như bình thường bằng cách vào **Settings**, nhấp vào **Windows Update**, và thực hiện thủ công **'Check for Updates'**.

![Windows 10 KB5073724 update](https://www.bleepstatic.com/images/news/security/microsoft/KB5073724.jpg)

**Cập nhật Windows 10 KB5073724**  
_Nguồn: BleepingComputer_

Sau khi cài đặt bản cập nhật này, Windows 10 sẽ được cập nhật lên build 19045.6809, và Windows 10 Enterprise LTSC 2021 sẽ được cập nhật lên build 19044.6809.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

## Có gì mới trong Windows 10 KB5073724

Microsoft không còn phát hành các tính năng mới cho Windows 10, và [KB5073724 update](https://support.microsoft.com/en-us/topic/january-13-2026-kb5073724-os-builds-19045-6809-and-19044-6809-bd960b49-050e-432f-a9d5-2454cb377fed) chỉ chứa các bản sửa lỗi bảo mật và sửa lỗi được giới thiệu bởi các bản cập nhật bảo mật trước đó.

Với [January 2026 Patch Tuesday](https://www.bleepingcomputer.com/news/microsoft/microsoft-january-2026-patch-tuesday-fixes-3-zero-days-114-flaws/), Microsoft đã sửa 114 lỗ hổng, bao gồm ba lỗ hổng zero-day.

KB5073724 sửa một lỗ hổng leo thang đặc quyền đang bị khai thác trong các trình điều khiển modem tích hợp của Agere, một lỗ hổng bảo mật trong thư viện bên thứ ba WinSqlite DLL, và các cập nhật để xử lý việc chứng chỉ Secure Boot sắp hết hạn.

* **[Trình điều khiển]** Bản cập nhật này gỡ bỏ các trình điều khiển modem sau: agrsm64.sys (x64), agrsm.sys (x86), smserl64.sys (x64) và smserial.sys (x86). Phần cứng modem phụ thuộc vào các trình điều khiển cụ thể này sẽ không còn hoạt động trên Windows.
* **[Secure Boot]** Bắt đầu với bản cập nhật này, các cập nhật chất lượng Windows bao gồm một tập con dữ liệu nhắm mục tiêu thiết bị có độ tin cậy cao xác định các thiết bị đủ điều kiện tự động nhận các chứng chỉ Secure Boot mới. Thiết bị sẽ chỉ nhận các chứng chỉ mới sau khi thể hiện đủ tín hiệu cập nhật thành công, đảm bảo triển khai an toàn và theo từng giai đoạn.
* **[WinSqlite3.dll]** Đã sửa: Thành phần lõi của Windows, WinSqlite3.dll, đã được cập nhật. Trước đây, một số phần mềm bảo mật có thể đã phát hiện thành phần này là có lỗ hổng.

Kể từ tháng 6 năm 2025, [Microsoft đã cảnh báo](https://support.microsoft.com/en-us/topic/windows-secure-boot-certificate-expiration-and-ca-updates-7ff40d33-95dc-4c3c-8725-a9b95457578e) rằng nhiều chứng chỉ Windows Secure Boot được cấp vào năm 2011 sẽ hết hạn vào năm 2026, và các hệ thống không cập nhật chúng có nguy cơ làm hỏng các bảo vệ Secure Boot.

| **Chứng chỉ sắp hết hạn**                  | **Ngày hết hạn** | **Chứng chỉ mới**                  | **Vị trí lưu trữ** | **Mục đích**                                          |
| ----------------------------------------- | ------------------- | ------------------------------------ | -------------------- | ---------------------------------------------------- |
| **Microsoft Corporation KEK CA 2011**     | June 2026           | Microsoft Corporation KEK 2K CA 2023 | Stored in KEK        | Ký các bản cập nhật cho DB và DBX.                         |
| **Microsoft Windows Production PCA 2011** | Oct 2026            | Windows UEFI CA 2023                 | Stored in DB         | Được dùng để ký trình tải khởi động của Windows.            |
| **Microsoft UEFI CA 2011_\*_**            | June 2026           | Microsoft UEFI CA 2023               | Stored in DB         | Ký các bootloader bên thứ ba và ứng dụng EFI. |
| **Microsoft UEFI CA 2011_\*_**            | June 2026           | Microsoft Option ROM UEFI CA 2023    | Stored in DB         | Ký các option ROM bên thứ ba                        |

Những chứng chỉ này được dùng để xác thực các thành phần khởi động của Windows, bootloader bên thứ ba, và các bản cập nhật hủy bỏ Secure Boot. Nếu các chứng chỉ hết hạn, thì Secure Boot có thể bị phá vỡ, cho phép các tác nhân đe dọa vượt qua các biện pháp bảo vệ.

Trong phần bản cập nhật hôm nay, Microsoft đang triển khai các bản cập nhật nhắm mục tiêu tới các hệ thống để cập nhật chứng chỉ Secure Boot. Các bản cập nhật này sẽ được triển khai tới thêm các hệ thống theo thời gian.

Microsoft cho biết hiện không có vấn đề đã biết với bản cập nhật này.