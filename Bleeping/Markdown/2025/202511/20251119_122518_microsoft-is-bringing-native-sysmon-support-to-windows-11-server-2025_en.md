# Microsoft is bringing native Sysmon support to Windows 11, Server 2025

![Windows utility](https://www.bleepstatic.com/content/hl-images/2020/09/18/windows-utility.jpg)

Microsoft announced today that it is integrating Sysmon natively into Windows 11 and Windows Server 2025 next year, making it unnecessary to deploy the standalone Sysinternals tools.

"Next year, Windows updates for Windows 11 and Windows Server 2025 will bring Sysmon functionality natively to Windows," reads an [announcement](https://techcommunity.microsoft.com/blog/windows-itpro-blog/native-sysmon-functionality-coming-to-windows/4468112) by Sysinternals creator Mark Russinovich.

"Sysmon functionality allows you to use custom configuration files to filter captured events. These events are written to the Windows event log. enabling a wide range of use cases including by security applications."

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Sysmon (or System Monitor) is a free Microsoft Sysinternals tool that can be configured to monitor for and block malicious/suspicious activity and log events to the Windows Event Log.

By default, Sysmon monitors basic events, such as process creation and termination. However, it is possible to create advanced configuration files that let you monitor and perform more advanced behavior, such as monitoring [process tampering](https://www.bleepingcomputer.com/news/microsoft/microsoft-sysmon-now-detects-malware-process-tampering-attempts/), [DNS queries](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-sysmon-10-with-dns-query-logging-feature/), [executable file creation](https://www.bleepingcomputer.com/news/microsoft/microsoft-sysmon-now-detects-when-executables-files-are-created/), [Windows clipboard changes](https://www.bleepingcomputer.com/news/microsoft/microsoft-sysmon-now-logs-data-copied-to-the-windows-clipboard/), and [auto-backing up deleted files](https://www.bleepingcomputer.com/news/software/microsoft-releases-sysmon-11-with-auto-backup-of-deleted-files/).

Sysmon is a very popular tool for threat hunting and diagnosing persistent issues in Windows, but it normally needs to be installed individually on devices, making it harder to manage and reducing coverage in large IT environments.

With Sysmon now natively supported in Windows, users and admins can install it via Windows 11's "Optional features" settings dialog and receive new software updates directly through Windows Update, making deployment and management much easier.

Microsoft says the built-in capabilities will retain Sysmon's standard feature set, including support for custom configuration files and advanced event filtering.

Once installed, admins can enable it via the Command Prompt using the following command for basic monitoring:

```
sysmon -i
```

For more advanced monitoring using a custom configuration file, users can deploy it using the following command:

```
sysmon -i <name_of_config_file>
```

For example, if you wanted to log when new executables are created under the C:\\ProgramData\\ and C:\\Users\\ folders, you can use the following configuration file:

```
<Sysmon schemaversion="4.90">
  <!-- Capture all hashes -->
  <HashAlgorithms>MD5,SHA256</HashAlgorithms>
  <EventFiltering>
    <!-- Log executable file creations -->
    <FileExecutableDetected onmatch="include">
    <TargetFilename condition="begin with">C:\ProgramData\</TargetFilename>
    <TargetFilename condition="begin with">C:\Users\</TargetFilename>
    </FileExecutableDetected>
  </EventFiltering>
</Sysmon>
```

Now, when a new executable is created in one of those directories, Windows logs it to the Event Logs, as shown below.

![Sysmon event 29 -File Executable Detected](https://www.bleepstatic.com/images/news/software/s/sysinternals/sysmon/v15/event-viewer.jpg)

**Sysmon event 29 -File Executable Detected**  
_Source: BleepingComputer_

Other popular events logged by Sysmon include:

* **Event ID 1** – Process Creation: Useful for detecting suspicious command-line activity.
* **Event ID 3** – Network Connection: Logs outbound connections for anomaly detection or C2 activity.
* **Event ID 8** – Process Access: Can expose attempts to access LSASS for credential dumping.
* **Event ID 11** – File Creation: Tracks script file generation often used in malware staging.
* **Event ID 25** – Process Tampering: Helps identify process hollowing and other evasion techniques.
* **Event IDs 20 & 21** – WMI Events: Captures persistent activity through WMI consumers and filters.

Microsoft also confirmed that it will finally release comprehensive documentation on using Sysmon next year, as well as bring new enterprise management features and AI-powered threat detection capabilities.

For now, if you wish to test or deploy Sysmon in your environment, you can do so using the individual tool on [the Sysinternals site](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon) and by reviewing [SwiftOnSecurity's example Sysmon configuration](https://github.com/SwiftOnSecurity/sysmon-config).