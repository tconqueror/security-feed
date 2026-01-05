# Các bản fork IDE của VSCode khiến người dùng dễ bị tấn công qua "gợi ý tiện ích mở rộng"

![Các bản fork IDE của VSCode khiến người dùng dễ bị tấn công qua "gợi ý tiện ích mở rộng"](https://www.bleepstatic.com/content/hl-images/2025/03/18/Blockchain-2.jpg)

Các giải pháp môi trường phát triển tích hợp (IDE) được hỗ trợ AI phổ biến, chẳng hạn như Cursor, Windsurf, Google Antigravity và Trae, gợi ý các tiện ích mở rộng mà không tồn tại trong registry OpenVSX, cho phép tác nhân đe dọa chiếm namespace và tải lên các tiện ích mở rộng độc hại.

Những IDE được hỗ trợ AI này là các fork từ Microsoft VSCode, nhưng không thể sử dụng các tiện ích mở rộng trên cửa hàng chính thức do hạn chế bản quyền. Thay vào đó, chúng được hỗ trợ bởi OpenVSX, một thị trường mã nguồn mở thay thế cho các tiện ích mở rộng tương thích với VSCode.

Kết quả của việc fork, các IDE kế thừa danh sách các tiện ích mở rộng được khuyến nghị chính thức, được mã hóa cứng trong các tệp cấu hình, vốn trỏ tới Visual Studio Marketplace của Microsoft.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Những gợi ý này xuất hiện dưới hai hình thức: một là theo tệp, được kích hoạt khi mở một tệp như _azure-pipelines.yaml_, và gợi ý tiện ích mở rộng Azure Pipelines; dạng còn lại là theo phần mềm, xảy ra khi phát hiện PostgreSQL đã được cài trên hệ thống của nhà phát triển và đề xuất một tiện ích mở rộng PostgreSQL.

![Cursor IDE recommends extension non-existent in OpenVSX](https://www.bleepstatic.com/images/news/u/1100723/Azure-Pipelines_suggestion_Koi.png)

**Cursor IDE recommends extension not present in OpenVSX**  
_nguồn: Koi_

Tuy nhiên, không phải tất cả các tiện ích mở rộng được gợi ý đều tồn tại trên OpenVSX, nên các namespace của nhà xuất bản tương ứng đang chưa được ai đăng ký.

Các nhà nghiên cứu tại công ty bảo mật chuỗi cung ứng Koi cho biết một tác nhân đe dọa có thể lợi dụng niềm tin của người dùng vào các đề xuất ứng dụng và đăng ký các namespace chưa có chủ để phát tán phần mềm độc hại.

_nguồn: Koi Security_

Nhóm nghiên cứu đã báo cáo vấn đề cho Google, Windsurf và Cursor vào cuối tháng 11 năm 2025. Google phản ứng bằng cách loại bỏ 13 đề xuất tiện ích mở rộng khỏi IDE của họ vào ngày 26 tháng 12, nhưng Cursor và Windsurf vẫn chưa phản hồi.

Trong khi đó, các nhà nghiên cứu của Koi [đã chiếm các namespace](https://www.koi.ai/blog/how-we-prevented-cursor-windsurf-google-antigravity-from-recommending-malware) của các tiện ích mở rộng sau để ngăn chặn khai thác độc hại:

* ms-ossdata.vscode-postgresql
* ms-azure-devops.azure-pipelines
* msazurermtools.azurerm-vscode-tools
* usqlextpublisher.usql-vscode-ext
* cake-build.cake-vscode
* pkosta2005.heroku-command

Các nhà nghiên cứu đã tải lên các tiện ích mở rộng placeholder không hoạt động, không cung cấp chức năng thực sự nhưng vẫn chặn được một cuộc tấn công chuỗi cung ứng.

Ngoài ra, họ đã phối hợp với Eclipse Foundation, phía điều hành OpenVSX, để xác minh các namespace còn được tham chiếu, loại bỏ các đóng góp không chính thức và áp dụng các biện pháp bảo vệ ở mức registry rộng hơn.

Hiện tại, chưa có dấu hiệu rằng các tác nhân độc hại đã khai thác lỗ hổng bảo mật này trước khi các nhà nghiên cứu của Koi phát hiện và hành động.

Người dùng các IDE đã fork được khuyến cáo luôn xác minh các đề xuất tiện ích mở rộng bằng cách truy cập thủ công registry OpenVSX và kiểm tra rằng chúng đến từ một nhà xuất bản đáng tin cậy.