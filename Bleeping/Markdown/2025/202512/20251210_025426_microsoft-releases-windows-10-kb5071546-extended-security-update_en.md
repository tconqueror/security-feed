# Microsoft releases Windows 10 KB5071546 extended security update

![Windows 10](https://www.bleepstatic.com/content/hl-images/2024/09/10/windows-10-gradient.jpg)

Microsoft has released the KB5071546 extended security update to resolve 57 security vulnerabilities, including three zero-day flaws.

If you are running Windows 10 Enterprise LTSC or are enrolled in the ESU program, you can install this update like normal by going into **Settings**, clicking on **Windows Update,** and manually performing a **'Check for Updates**.'

![Windows 10 KB5071546 update](https://www.bleepstatic.com/images/news/Microsoft/Windows-10/esu/KB5071546.jpg)

**Windows 10 KB5071546 update**  
_Source: BleepingComputer_

As this update is mandatory, it will automatically install and prompt you to restart your device when it is complete.

After installing this update, Windows 10 will be updated to build 19045.6691, and Windows 10 Enterprise LTSC 2021 will be updated to build 19044.6691.

## What's new in Windows 10 KB5071546

Microsoft is no longer releasing new features for Windows 10, and the [KB5071546 update](https://support.microsoft.com/en-us/topic/december-9-2025-kb5071546-os-builds-19045-6691-and-19044-6691-8a3638de-3024-40bb-a41f-bcc09893758b) contains only security updates and fixes for bugs introduced by previous security updates.

With this release, Microsoft has fixed a remote code execution zero-day vulnerability in PowerShell tracked as [CVE-2025-54100](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-54100) that could allow malicious scripts embedded in a webpage to be executed when the page is retrieved using the "[Invoke-WebRequest](https://learn.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.5)" command:

* **\[PowerShell 5.1\]** The [Invoke-WebRequest](https://learn.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.5) command now includes a confirmation prompt with a security warning of a script execution risk. You can choose to continue or cancel the request. For additional details, see [CVE-2025-54100](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-54100) and [KB5074596: PowerShell 5.1: Preventing script execution from web content](https://support.microsoft.com/topic/7cb95559-655e-43fd-a8bd-ceef2406b705).

When running PowerShell scripts that use the "[Invoke-WebRequest](https://learn.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.5)" command, PowerShell 5.1 (the default version on Windows 10) will now display a warning that this could cause scripts on the page to be executed.

If a page is untrusted, Windows users should use the -UseBasicParsing command line argument to prevent embedded scripts from being parsed.

Security Warning: Script Execution Risk

Invoke-WebRequest parses the content of the web page. Script code in the web page might be run when the page is parsed.

```
Security Warning: Script Execution Risk
Invoke-WebRequest parses the content of the web page. Script code in the web page might be run when the page is parsed.
      RECOMMENDED ACTION:
      Use the -UseBasicParsing switch to avoid script code execution.
      Do you want to continue?
			```
 
 
For additional details, see [KB5074596: PowerShell 5.1: Preventing script execution from web content](https://support.microsoft.com/help/5072034).
```

Microsoft has released [an advisory](https://support.microsoft.com/en-us/topic/powershell-5-1-preventing-script-execution-from-web-content-7cb95559-655e-43fd-a8bd-ceef2406b705) on when and how to use this command-line flag.

Microsoft states that there are no known issues with this update.