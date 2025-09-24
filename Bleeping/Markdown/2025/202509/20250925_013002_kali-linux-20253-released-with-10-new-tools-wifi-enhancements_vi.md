# Kali Linux 2025.3 được phát hành với 10 công cụ mới, cải tiến Wi-Fi

![Kali Linux](https://www.bleepstatic.com/content/hl-images/2022/02/14/kali-bright.jpg)

Kali Linux đã phát hành phiên bản 2025.3, bản thứ ba của năm 2025, với mười công cụ mới, hỗ trợ Nexmon và các cải tiến cho NetHunter.

Kali Linux là một bản phân phối được tạo ra cho các chuyên gia an ninh mạng và ethical hackers để tiến hành các bài tập red team, kiểm thử xâm nhập, kiểm toán bảo mật, và nghiên cứu trên các mạng.

## Công cụ mới được thêm vào Kali Linux 2025.3

Như mọi lần phát hành, Kali Linux đi kèm những "đồ chơi" mới để khám phá.

Trong bản phát hành này, chúng tôi có mười công cụ mới, được liệt kê bên dưới:

* **[Caido](https://www.kali.org/tools/caido/)** \- The client side of caido (the graphical/desktop aka the main interface) - a web security auditing toolkit
* **[Caido-cli](https://www.kali.org/tools/caido-cli/)** \- The server section of caido - a web security auditing toolkit
* **[Detect It Easy (DiE)](https://www.kali.org/tools/detect-it-easy/)** \- File type identification
* **[Gemini CLI](https://www.kali.org/tools/gemini-cli/)** \- An open-source AI agent that brings the power of Gemini directly into your terminal
* **[krbrelayx](https://www.kali.org/tools/krbrelayx/)** \- Kerberos relaying and unconstrained delegation abuse toolkit
* **[ligolo-mp](https://www.kali.org/tools/ligolo-mp/)** \- Multiplayer pivoting solution
* **[llm-tools-nmap](https://www.kali.org/tools/llm-tools-nmap/)** \- Enables LLMs to perform network discovery and security scanning tasks using the nmap
* **[mcp-kali-server](https://www.kali.org/tools/mcp-kali-server/)** \- MCP configuration to connect AI agent to Kali
* **[patchleaks](https://www.kali.org/tools/patchleaks/)** \- Spots the security fix and provides detailed description so you can validate - or weaponize - it fast
* **[vwifi-dkms](https://www.kali.org/tools/vwifi-dkms/)** \- Setup "dummy" wifi networks, establishing connections, and disconnecting from them

## Cập nhật Kali Nethunter và Nexmon

Nexmon là một Framework chỉnh sửa firmware cho các chip wi‑fi Broadcom và Cypress cho phép bạn bật Monitor Mode và Frame Injection.

Kali Team trước đây đã [thông báo hỗ trợ](https://www.kali.org/blog/raspberry-pi-wi-fi-glow-up/) cho framework Nexmon vào tháng Bảy, cho phép người dùng Raspberry Pi tận hưởng các tính năng Wi‑Fi nâng cao cho các hoạt động an ninh.

Với bản phát hành này, Nexmon hiện đã được bao gồm trong Kali Linux, giúp nó dễ tiếp cận hơn với Raspberry Pi và các thiết bị khác.

"Trong Kali 2025.1, chúng tôi đã thay đổi cách đóng gói kernel cho Raspberry Pi của mình, cũng như nâng cấp lên một phiên bản chính mới," trích thông báo [Kali Linux 2025.3 announcement](https://www.kali.org/blog/kali-linux-2025-3-release/).

"Giờ đây hỗ trợ Nexmon đã trở lại cũng như hỗ trợ Raspberry Pi 5! Các thiết bị khác cũng có thể sử dụng Nexmon, nó không giới hạn ở Raspberry Pis."

Ngoài Nexmon, Kali Nethunter đã nhận được một số cập nhật, bao gồm hỗ trợ chạy trên Samsung S10.

Kali NetHunter Car Hacking, CARsenal, cũng đã nhận được các tính năng mới, bao gồm cập nhật giao diện mới và nhiều sửa lỗi.

Nhóm cho biết họ sẽ phát hành một số video trong tương lai về cách sử dụng CARsenal và trình diễn các tính năng khác nhau.

## Những thay đổi khác

Bản phát hành này cũng bao gồm các thay đổi và cải tiến khác, bao gồm:

* Plugin VPN IP panel (Xfce) giờ cho phép bạn chỉ định giao diện bạn đang giám sát, để dễ dàng sao chép địa chỉ IP của kết nối VPN vào clipboard.
* Kali sẽ ngừng hỗ trợ ARMel (Acorn RISC Machine, Little-Endian).
* Bạn giờ có thể cài đặt các Kernel modules với Magisk. Tuy nhiên, Kali cảnh báo tính năng này vẫn đang ở trạng thái thử nghiệm.

## Cách có Kali Linux 2025.3

Để bắt đầu sử dụng Kali Linux 2025.3, bạn có thể nâng cấp cài đặt hiện có của mình, [chọn nền tảng](https://www.kali.org/get-kali/), hoặc [tải trực tiếp các ISO images](https://cdimage.kali.org/kali-2025.3/) cho cài đặt mới và bản live.

Đối với những người cập nhật từ phiên bản trước, bạn có thể sử dụng các lệnh sau để nâng cấp lên phiên bản mới nhất.

```xml
echo "deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware" | sudo tee /etc/apt/sources.list

sudo apt update && sudo apt -y full-upgrade

cp -vrbi /etc/skel/. ~/

[ -f /var/run/reboot-required ] && sudo reboot -f
```

Nếu bạn đang chạy Kali trên Windows Subsystem for Linux, hãy nâng cấp lên WSL2 để có trải nghiệm tốt hơn, bao gồm khả năng sử dụng các ứng dụng đồ họa.

Bạn có thể kiểm tra phiên bản WSL đang dùng bởi Kali với lệnh 'wsl -l -v' trong một cửa sổ lệnh Windows.

Khi hoàn tất nâng cấp, bạn có thể kiểm tra xem việc nâng cấp có thành công hay không bằng cách sử dụng lệnh sau:

```
grep VERSION /etc/os-release
```

Bạn có thể xem [changelog đầy đủ](https://www.kali.org/blog/kali-linux-2025-3-release/) cho Kali 2025.3 trên website của Kali.