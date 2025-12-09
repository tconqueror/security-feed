# Windows PowerShell now warns when running Invoke-WebRequest scripts

![Windows PowerShell](https://www.bleepstatic.com/content/hl-images/2021/06/16/PowerShell.jpg)

Microsoft says Windows PowerShell now warns when running scripts that use the Invoke-WebRequest cmdlet to download web content, aiming to prevent potentially risky code from executing.

As Microsoft explains, this mitigates a high-severity PowerShell remote code execution vulnerability [(CVE-2025-54100](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-54100)), which primarily affects enterprise or IT-managed environments that use PowerShell scripts for automation, since PowerShell scripts are not as commonly used outside such environments.

The warning has been added to Windows PowerShell 5.1, the PowerShell version installed by default on Windows 10 and Windows 11 systems, and is designed to add the same secure web parsing process available in PowerShell 7.

PowerShell will alert you that, without precautions, scripts contained in web pages downloaded using the "Invoke-WebRequest' cmdlet could execute on your system. By default, if you press 'Enter' or select 'No,' the operation will be canceled, and PowerShell will suggest rerunning the command with the '-UseBasicParsing' parameter for safer processing.

When choosing 'Yes,' PowerShell will parse the page using the older method (full HTML parsing), allowing the content and embedded scripts to load as before. In short, selecting 'Yes 'means you accept the risk, while choosing 'No' stops the action to protect your system.

"Windows PowerShell 5.1 now displays a security confirmation prompt when using the Invoke-WebRequest command to fetch web pages without special parameters," [Microsoft explains](https://support.microsoft.com/en-us/topic/powershell-5-1-preventing-script-execution-from-web-content-7cb95559-655e-43fd-a8bd-ceef2406b705) in a Tuesday advisory.

"This prompt warns that scripts in the page could run during parsing and advises using the safer -UseBasicParsing parameter to avoid any script execution. Users must choose to continue or cancel the operation."

After you install the KB5074204 update, IT admins will see the following confirmation prompt warning of script code execution risks:

```
Security Warning: Script Execution Risk
Invoke-WebRequest parses the content of the web page. Script code in the web page might be run when the page is parsed.
      RECOMMENDED ACTION:
      Use the -UseBasicParsing switch to avoid script code execution.
      Do you want to continue?
			```
 
For additional details, see [KB5074596: PowerShell 5.1: Preventing script execution from web content](https://support.microsoft.com/help/5072034).
```

To avoid having their automation scripts hang until manual confirmation, admins are advised to update their scripts to use the UseBasicParsing safe parameter explicitly.

It's also important to note that in PowerShell, the 'curl' command is aliased to the Invoke-WebRequest cmdlet, so you will also see these new warnings when running scripts invoking curl commands.

"Most PowerShell scripts and commands that use the Invoke-WebRequest command will continue to work with little or no modification," Microsoft noted.

"For example, scripts that only download content or work with the response body as text or data are not affected and require no changes."