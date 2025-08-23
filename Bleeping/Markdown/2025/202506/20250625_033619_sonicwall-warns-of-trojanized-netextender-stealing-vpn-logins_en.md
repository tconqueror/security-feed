# SonicWall warns of trojanized NetExtender stealing VPN logins

![SonicWall](https://www.bleepstatic.com/content/hl-images/2022/05/13/SonicWall.jpeg)

SonicWall is warning customers that threat actors are distributing a trojanized version of its NetExtender SSL VPN client used to steal VPN credentials.

The fake software, which was discovered by SonicWall's and Microsoft Threat Intelligence (MSTIC) researchers, mimics the legitimate NetExtender v10.3.2.27, the latest available version.

The malicious installer file is hosted on a spoofed website that is made to appear authentic, tricking visitors into thinking they are downloading software from SonicWall.

Although the installer file is not digitally signed by SonicWall, it is signed by "CITYLIGHT MEDIA PRIVATE LIMITED," allowing it to bypass elementary defenses.

![Digital signature on the modified file](https://www.bleepstatic.com/images/news/u/1220909/2025/June/signature.jpg)

**Digital signature on the modified file**  
_Source: SonicWall_

The goal of the trojanized application is to steal VPN configuration and account credentials and exfiltrate them to the attacker.

SonicWall NetExtender is a remote access VPN client that allows users to securely connect to their organization's internal network from remote locations.

It is specifically designed to work with SonicWall SSL VPN appliances and firewalls, and it's typically used by remote staff of small to medium businesses, IT administrators, and contractors across a broad spectrum of industry types.

SonicWall and Microsoft found two modified binaries of their product distributed by the malicious spoofed sites.

A modified **NeService.exe** with its validation logic patched to bypass digital certificate checks and the **NetExtender.exe** file, which was modified to steal data.

"Additional code was added to send VPN configuration information to a remote server with the IP address 132.196.198.163 over port 8080," explains the [SonicWall advisory](https://www.sonicwall.com/blog/threat-actors-modify-and-re-create-commercial-software-to-steal-users-information).

"Once the VPN configuration details are entered and the “Connect” button is clicked, the malicious code performs its own validation before sending the data to the remote server. Stolen configuration information includes the username, password, domain, and more."

![Highlighted modifications on the 'NetExtender.exe' file](https://www.bleepstatic.com/images/news/u/1220909/2025/June/code.jpg)

**Malicious code on the 'NetExtender.exe' file**  
_Source: SonicWall_

Sonicwall recommends that users only download software from the official portals at sonicwall.com and mysonicwall.com.

The firm's security tools and Microsoft Defender now detect and block malicious installers, though other security tools might not.

Typically, people are redirected to spoofed websites that deliver trojanized installers via malvertising, SEO poisoning, direct messages, forum posts, and YouTube or TikTok videos.

When downloading software, use the vendor's official website and skip all promoted results. Also, always scan downloaded files on an up-to-date AV before executing them on your device.