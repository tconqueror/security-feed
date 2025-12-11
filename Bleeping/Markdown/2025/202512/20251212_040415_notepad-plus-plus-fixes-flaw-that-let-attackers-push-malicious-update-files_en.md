# Notepad++ fixes flaw that let attackers push malicious update files

![Notepad++](https://www.bleepstatic.com/content/hl-images/2021/06/07/Notepad++.jpg)

Notepad++ version 8.8.9 was released to fix a security weakness in its WinGUp update tool after researchers and users reported incidents in which the updater retrieved malicious executables instead of legitimate update packages.

The first signs of this issue appeared in a [Notepad++ community forum topic](https://community.notepad-plus-plus.org/topic/27212/autoupdater-and-connection-temp-sh/6), where a user reported that Notepad++'s update tool, GUP.exe (WinGUp), spawned an unknown "%Temp%\\AutoUpdater.exe" executable that executed commands to collect device information.

According to the reporter, this malicious executable ran various reconnaissance commands and stored the output into a file called 'a.txt.'

```
cmd /c netstat -ano >> a.txt
cmd /c systeminfo >> a.txt
cmd /c tasklist >> a.txt
cmd /c whoami >> a.txt
```

The _autoupdater.exe_ malware then used the curl.exe command to exfiltrate the a.txt file to a remote site at temp\[.\]sh.

As GUP uses the libcurl library rather than the actual 'curl.exe' command and does not collect this type of information, other Notepad++ users speculated that the user had installed an unofficial, malicious version of Notepad++ or that the autoupdate network traffic was hijacked.

To help mitigate potential network hijacks, Notepad++ developer Don Ho released version 8.8.8 on November 18th, so that updates can be downloaded only from GitHub.

As a stronger fix, Notepad 8.8.9 was released on December 9th, which will prevent updates from being installed that are not signed with the developer's code-signing certificate.

"Starting with this release, Notepad++ & WinGUp have been hardened to verify the signature & certificate of downloaded installers during the update process. If verification fails, the update will be aborted." reads the [Notepad 8.8.9 security notice](https://community.notepad-plus-plus.org/topic/27298/notepad-v8-8-9-vulnerability-fix).

## Hijacked update URLs

Earlier this month, security expert Kevin Beaumont warned that he heard from three orgs that were impacted by security incidents linked to Notepad++.

"I've heard from 3 orgs now who've had security incidents on boxes with Notepad++ installed, where it appears Notepad++ processes have spawned the initial access." [explained Beaumont](http://doublepulsar.com/small-numbers-of-notepad-users-reporting-security-woes-371d7a3fd2d9).

"These have resulted in hands on keyboard threat actors."

The researcher says that all of the organizations he spoke to have interests in East Asia and that the activity appeared very targeted, with victims reporting hands-on reconnaissance activity after the incidents.

When Notepad++ checks for updates, it connects to https://notepad-plus-plus.org/update/getDownloadUrl.php?version=<versionnumber>. If there is a newer version, the endpoint will return XML data that provides the download path to the latest version:

```
<GUP>
<script/>
<NeedToBeUpdated>yes</NeedToBeUpdated>
<Version>8.8.8</Version>
<Location>https://github.com/notepad-plus-plus/notepad-plus-plus/releases/download/v8.8.8/npp.8.8.8.Installer.exe</Location>
</GUP>
```

Beaumont speculated that Notepad++'s autoupdate mechanism might have been hijacked in these incidents to push malicious updates that grant threat actors remote access.

"If you can intercept and change this traffic, you can redirect the download to any location it appears by changing the URL in the <Location> property," explained Beaumont.

"Because traffic to notepad-plus-plus.org is fairly rare, it may be possible to sit inside the ISP chain and redirect to a different download. To do this at any kind of scale requires a lot of resources," continued the researcher.

However, Beaumont noted that it is not uncommon for threat actors to use [malvertising to distribute malicious versions of Notepad++](https://www.bleepingcomputer.com/news/security/malicious-notepad-plus-plus-google-ads-evade-detection-for-months/) that install malware.

Notepad++'s security notice shares the same uncertainty, stating that they are still investigating how the traffic is being hijacked.

"The investigation is ongoing to determine the exact method of traffic hijacking. Users will be informed once tangible evidence regarding the cause is established," reads the [security notice](http://notepad-plus-plus.org/news/v889-released/).

The developer states that all Notepad++ users should upgrade to the latest version, 8.8.9\. They also noted that since v8.8.7, all official binaries and installers are signed with a valid certificate, and users who previously installed an older custom root certificate should remove it.

BleepingComputer contacted Notepad++'s developer on December 3rd with questions about the incidents but did not receive a reply.