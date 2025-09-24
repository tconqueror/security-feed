# Kali Linux 2025.3 released with 10 new tools, wifi enhancements

![Kali Linux](https://www.bleepstatic.com/content/hl-images/2022/02/14/kali-bright.jpg)

Kali Linux has released version 2025.3, the third version of 2025, featuring ten new tools, Nexmon support, and NetHunter improvements.

Kali Linux is a distribution created for cybersecurity professionals and ethical hackers to conduct red team exercises, penetration testing, security audits, and research against networks.

## New tool added to Kali Linux 2025.3

As with every release, Kali Linux comes with new toys to play with.

With this release, we have ten new tools, which are listed below:

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

## Kali Nethunter and Nexmon updates

Nexmon is a firmware Patching Framework for Broadcom and Cypress wi-fi chips that allows you to enable Monitor Mode and Frame Injection.

The Kali Team [previously announced support](https://www.kali.org/blog/raspberry-pi-wi-fi-glow-up/) for the Nexmon framework in July, enabling Raspberry Pi users to enjoy enhanced Wi-Fi features for security engagements.

With this release, Nexmon is now included in Kali Linux, making it more accessible to Raspberry Pi and other devices.

"In Kali 2025.1, we changed how we package our Raspberry Pi kernel, as well as bump to a new major version," reads the [Kali Linux 2025.3 announcement](https://www.kali.org/blog/kali-linux-2025-3-release/).

"Now Nexmon support is back as well as supporting Raspberry Pi 5! Other devices can also use Nexmon, its not limited to Raspberry Pis."

In addition to Nexmon, Kali Nethunter has received some updates, including support for running it on the Samsung S10.

Kali NetHunter Car Hacking, CARsenal, has also received new features, including a new UI update and numerous bug fixes.

The Team says they will be releasing some videos in the future on how to CARsenal and demonstrating the various features.

## Other changes

This release also includes other changes and improvements, including:

* The VPN IP panel plugin (Xfce) now allows you to specify the interface you are monitoring, to easily copy the IP address of your VPN connection to the clipboard.
* Kali is dropping support for ARMel (Acorn RISC Machine, Little-Endian).
* You can now install Kernel modules with Magisk. However, Kali warns it's still in an experimental state.

## How to get Kali Linux 2025.3

To start using Kali Linux 2025.3, you can upgrade your existing installation, [select a platform](https://www.kali.org/get-kali/), or [directly download ISO images](https://cdimage.kali.org/kali-2025.3/) for new installs and live distributions.

For those updating from a previous version, you can use the following commands to upgrade to the latest version.

```xml
echo "deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware" | sudo tee /etc/apt/sources.list

sudo apt update && sudo apt -y full-upgrade

cp -vrbi /etc/skel/. ~/

[ -f /var/run/reboot-required ] && sudo reboot -f
```

If you are running Kali on the Windows Subsystem for Linux, upgrade to WSL2 for a better experience, which includes the ability to use graphical apps.

You can check the WSL version used by Kali with the 'wsl -l -v' command in a Windows command prompt.

Once done upgrading, you can check if the upgrade was successful by using the following command:

```
grep VERSION /etc/os-release
```

You can view the [complete changelog](https://www.kali.org/blog/kali-linux-2025-3-release/) for Kali 2025.3 on Kali's website.