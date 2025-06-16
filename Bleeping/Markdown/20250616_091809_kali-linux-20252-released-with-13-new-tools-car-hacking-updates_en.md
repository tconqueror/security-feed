# Kali Linux 2025.2 released with 13 new tools, car hacking updates

![Kali](https://www.bleepstatic.com/content/hl-images/2025/04/28/kali-white.jpg)

Kali Linux 2025.2, the second release of the year, is now available for download with 13 new tools and an expanded car hacking toolkit.

Designed for cybersecurity professionals and ethical hackers, the Kali Linux distribution facilitates security audits, penetration testing, and network research.

The Kali Team has added many new features and refined the distro's user interface. Notable changes include:

* Renamed and updated car hacking toolset
* Kali Menu and UI refresh
* Updates to Kali NetHunter
* Additional hacking tools

## Renamed and expanded car hacking toolkit

In this release, the CAN Arsenal was renamed CARsenal to better reflect its purpose as a car hacking toolset and now has a more user-friendly interface.

The Kali Team has also added new tools, including:

* **hlcand**: Modified slcand for ELM327 use
* **VIN Info**: Decode your VIN identifier
* **CaringCaribou**: Actually provide Listener, Dump, Fuzzer, Send, UDS and XCP modules
* **ICSim**: Provide a great simulator to play with VCAN and test CARsenal toolset without hardware needed

## Kali Menu and UI refresh

The Kali Menu was also reorganized to align with the MITRE ATT&CK framework, making it easier for both red and blue teams to find the right tools.

The menu structure was previously based on older systems like WHAX and BackTrack, which unfortunately lacked proper design planning and made it difficult to scale and add new tools, resulting in confusion when trying to locate similar tools.

"Now, we have created a new system and automated many aspects, making it easier for us to manage, and easier for you to discover items. Win win. Over time, we hope to start to add this to kali.org/tools/," the Kali Team said.

"Currently Kali Purple still follows NIST CSF (National Institute of Standards and Technology Critical Infrastructure Cybersecurity), rather than MITRE D3FEND."

![New Kali Menu](https://www.bleepstatic.com/images/news/u/1109292/2025/kali-menu.png)

_New Kali Menu (Kali Team)_

GNOME has been updated to version 48, featuring notification stacking, performance improvements, dynamic triple buffering, and an enhanced image viewer. It also includes digital well-being tools for battery health preservation and HDR support.

The user interface has been refined for a sharper look with improved themes, and the document reader Evince has been replaced with the new Papers app.

KDE Plasma has now reached version 6.3, which packs a massive overhaul of fractional scaling, accurate screen colors when using the Night Light, more accurate CPU usage in the system monitor, Info Center with more information, like GPU data or battery cycle counts, and many more customization features.

## New tools in Kali Linux 2025.2

This new Kali Linux release also adds 23 new toys to test:

* [azurehound](https://www.kali.org/tools/azurehound/) \- BloodHound data collector for Microsoft Azure
* [binwalk3](https://www.kali.org/tools/binwalk3/) \- Firmware Analysis Tool
* [bloodhound-ce-python](https://www.kali.org/tools/bloodhound-ce-python/) \- Python based ingestor for BloodHound CE
* [bopscrk](https://www.kali.org/tools/bopscrk/) \- Generate smart and powerful wordlists
* [chisel-common-binaries](https://www.kali.org/tools/chisel-common-binaries/) \- Prebuilt binaries for chisel
* [crlfuzz](https://www.kali.org/tools/crlfuzz/) \- Fast tool to scan CRLF vulnerability written in Go (Submitted by [@Arszilla](https://gitlab.com/Arszilla))
* [donut-shellcode](https://www.kali.org/tools/donut-shellcode/) \- Generates position-independent shellcode from memory and runs them
* [gitxray](https://www.kali.org/tools/gitxray/) \- Scan GitHub repositories and contributors to collect data (Submitted by [@weirdlantern](https://gitlab.com/weirdlantern/))
* [ldeep](https://www.kali.org/tools/ldeep/) \- In-depth LDAP enumeration utility
* [ligolo-ng-common-binaries](https://www.kali.org/tools/ligolo-ng-common-binaries/) \- Prebuilt binaries for Advanced ligolo-ng
* [rubeus](https://www.kali.org/tools/rubeus/) \- Raw Kerberos interaction and abuses
* [sharphound](https://www.kali.org/tools/sharphound/) \- BloodHound CE collector
* [tinja](https://www.kali.org/tools/tinja/) \- CLI tool for testing web pages for template injection

## Kali NetHunter Updates

Besides a revamped car hacking toolset, Kali Linux 2025.2 introduces wireless injection, de-authentication, and WPA2 handshake capture support for the first smartwatch, the TicWatch Pro 3 (all variants with bcm43436b0 chipset).

Kali Team also [shared a teaser](https://www.youtube.com/watch?v=nbX27%5FyCTmc) featuring Kali NetHunter KeX running on Android Auto head units and introduced new and updated Kali NetHunter Kernels, including:

* (New) **Xiaomi Redmi 4/4X** (A13) (by [@MomboteQ](https://gitlab.com/momboteq))
* (New) **Xiaomi Redmi Note 11** (A15) (by [@Madara273](https://gitlab.com/Madara273))
* (Updated) **Realme C15** (A10) (by [@Frostleaft07](https://gitlab.com/Frostleaft07))
* (Updated) **Samsung Galaxy S10** (A14,A15/exynos9820) (by [@V0lk3n](https://gitlab.com/V0lk3n))
* (Updated) **Samsung Galaxy S9** (A13/exynos9810) (by [@V0lk3n](https://gitlab.com/V0lk3n))

## How to get Kali Linux 2025.2

To start using Kali Linux 2025.2, upgrade your existing installation, [select a platform](https://www.kali.org/get-kali/), or [directly download ISO images](https://cdimage.kali.org/kali-2025.2/)for new installs and live distributions.

Kali users updating from a previous version can use the following commands to upgrade to the latest version.

```
echo "deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware" | sudo tee /etc/apt/sources.list

sudo apt update && sudo apt -y full-upgrade

cp -vrbi /etc/skel/. ~/

[ -f /var/run/reboot-required ] && sudo reboot -f
```

If you're using Kali on WSL, consider upgrading to WSL 2 for better support of graphical applications. To check your WSL version, run 'wsl -l -v' in a Windows command prompt.

Once upgraded, you can check if the upgrade was successful using the following command: `grep VERSION /etc/os-release`.

You can check the complete changelog for Kali Linux 2025.2 [on Kali's website](https://www.kali.org/blog/kali-linux-2025-2-release/).