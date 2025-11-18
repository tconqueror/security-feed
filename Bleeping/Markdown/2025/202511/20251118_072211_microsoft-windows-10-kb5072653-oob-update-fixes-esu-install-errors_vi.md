# Microsoft: Windows 10 KB5072653 bản cập nhật ngoài lịch (OOB) sửa lỗi cài đặt ESU

![Windows 10](https://www.bleepstatic.com/content/hl-images/2021/09/20/Windows.jpg)

Microsoft đã phát hành bản cập nhật khẩn cấp Windows 10 KB5072653 ngoài lịch để giải quyết các vấn đề đang diễn ra liên quan đến việc cài đặt các extended security updates tháng Mười Một.

Windows 10 đã đến hạn kết thúc hỗ trợ vào ngày 14 tháng 10, 2025, và Microsoft không còn giới thiệu các tính năng mới hoặc phát hành các bản cập nhật bảo mật miễn phí.

Đối với người dùng cá nhân và khách hàng doanh nghiệp muốn tiếp tục sử dụng Windows 10, Microsoft cung cấp chương trình ESU.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Người tiêu dùng có thể nhận các extended security updates thêm một năm bằng cách trả $30, sao lưu cài đặt Windows của họ vào tài khoản Microsoft, hoặc đổi 1.000 điểm Microsoft reward.

Khách hàng doanh nghiệp có thể mua giấy phép ESU trong 3 năm, đưa tổng chi phí cho mỗi thiết bị lên $427.

Trong khuôn khổ Patch Tuesday tháng Mười Một, Microsoft đã phát hành [the first Windows 10 extended security update](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-kb5068781-the-first-windows-10-extended-security-update/). Tuy nhiên, một số khách hàng tiêu dùng và doanh nghiệp nhận thấy rằng bản cập nhật không được đề nghị đúng cách cho các thiết bị, hoặc họ [thất bại với lỗi 0x800f0922 (CBS\_E\_INSTALLERS\_FAILED)](https://www.bleepingcomputer.com/news/microsoft/microsoft-windows-10-kb5068781-esu-update-may-fail-with-0x800f0922-errors/).

## Microsoft phát hành bản sửa khẩn cấp

Hôm nay, Microsoft đã phát hành "KB5072653 Extended Security Updates (ESU) Licensing Preparation Package," khắc phục lỗi 0x800f0922 mà người dùng gặp phải khi cố gắng cài đặt bản cập nhật ESU.

"Những tổ chức bị ảnh hưởng bởi vấn đề này có thể khắc phục bằng cách cài đặt [KB5072653: Extended Security Updates (ESU) Licensing Preparation Package for Windows 10](https://support.microsoft.com/help/5072653), được phát hành vào ngày 17 tháng 11, 2025." trích từ một thông cáo hỗ trợ của Microsoft.

"Một khi bạn cài đặt gói chuẩn bị này ([KB5072653](https://support.microsoft.com/help/5072653)), bạn sẽ có thể triển khai bản cập nhật bảo mật tháng 11 2025 ([KB5068781](https://support.microsoft.com/help/5068781))."

Để cài đặt bản cập nhật, một thiết bị Windows phải đang chạy Windows 10 22H2 và đã cài đặt bản cập nhật tích lũy tháng 10 2025 [KB5066791](https://www.bleepingcomputer.com/news/microsoft/final-windows-10-patch-tuesday-update-rolls-out-as-support-ends/).

Sau đó họ có thể kiểm tra các bản cập nhật mới bằng Windows Update, và KB5072653 sẽ được cài đặt tự động.

Microsoft cho biết sau khi cập nhật KB5072653 được cài đặt và Windows được khởi động lại, người dùng nên chạy lại Windows Update để cài đặt thành công bản extended security update tháng Mười Một.

Tuy nhiên, một số quản trị viên Windows doanh nghiệp đã báo cáo \[[1](https://www.reddit.com/r/SCCM/comments/1ovetfu/kb5068781%5Fsupersedes%5Flast%5Fpatch%5Fof%5Fw10/), [2](https://www.reddit.com/r/sysadmin/comments/1owu7t9/purchased%5Fand%5Finstalled%5Fesu%5Fproduct%5Fkey%5Ffor%5F1/)\] rằng WSUS và SCCM không báo chính xác rằng một thiết bị Windows 10 cần bản cập nhật extended security update, ngay cả khi thiết bị đó đã được đăng ký đúng trong chương trình.

Microsoft cho biết họ sẽ phát hành một Scan Cab mới với metadata được cập nhật cho bản cập nhật này để thực hiện kiểm tra tuân thủ bản cập nhật một cách chính xác.

"Một Scan Cab mới bao gồm metadata cho [KB5072653](https://support.microsoft.com/help/5072653) sẽ sớm có sẵn cho các tổ chức sử dụng cab file để kiểm tra tuân thủ bản cập nhật. Chúng tôi sẽ cập nhật thông báo này khi Scan Cab mới có sẵn," Microsoft giải thích.

BleepingComputer đã liên hệ với Microsoft để xác định liệu điều này có giải quyết vấn đề mà một số quản trị viên Windows đã báo cáo hay không.

Để có thêm hiểu biết về các chiến lược quản lý bản vá hiện đại và cách các tổ chức có thể hợp lý hóa và củng cố quy trình cập nhật của họ, BleepingComputer đang tổ chức một webinar [December 2 webinar with Action1](https://onlinexperiences.com/scripts/Server.nxp?LASCmd=AI:4;F:QS!10100&ShowUUID=84B6E94D-9C81-4F9B-841F-7D435B7FF576&AffiliateData=bleepingcomputer%5Fesuoob%5Fart%5Fsc-cybercast-bc-2025-dec-a1).