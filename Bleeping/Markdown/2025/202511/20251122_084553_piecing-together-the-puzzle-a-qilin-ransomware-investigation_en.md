# Piecing Together the Puzzle: A Qilin Ransomware Investigation

![Huntress header](https://www.bleepstatic.com/content/posts/2025/11/19/huntress-header.jpg)

_Written by Lindsey O’Donnell-Welch, Ben Folland, Harlan Carvey of Huntress Labs._

A big part of a security analyst’s everyday role is figuring out what actually happened during an incident. We can do that by piecing together breadcrumbs–whether that’s through logs, antivirus detections, and other clues–that help us understand how the attacker achieved initial access and what they did after.

However, it’s not always cut and dry: sometimes there are external factors that limit our visibility. The Huntress agent might not be deployed across all endpoints, for example, or the targeted organization might install the Huntress agent after a compromise has already occurred.

In these cases, we need to get creative and look at multiple data sources in order to determine what actually happened.

Recently, we analyzed an incident where both of the above factors were true: on October 11, an organization installed the Huntress agent post-incident, and initially on one endpoint.

When it comes to visibility, this incident was less about looking through a keyhole, and more akin to looking through a pinhole. Even so, Huntress analysts were able to derive a great deal of information regarding the incident.

## The Qilin incident: What we started with

The Huntress agent was installed on a single endpoint following a [Qilin ransomware](https://www.darktrace.com/blog/a-busy-agenda-darktraces-detection-of-qilin-ransomware-as-a-service-operator) infection. What does that mean from the perspective of an analyst trying to figure out what happened?

We had limited clues to start: there was no endpoint detection and response (EDR) or SIEM telemetry available, and Huntress-specific ransomware canaries weren’t tripped. Because we were also on one endpoint, our visibility was limited to the activity that had occurred on that specific endpoint within the broader environment’s infrastructure. 

As a result, all Huntress analysts had to start with to unravel this incident was the managed antivirus (MAV) alerts. Once the Huntress agent was added to the endpoint, the SOC was alerted to existing MAV detections, some of which are illustrated in Figure 1.

![Figure 1: MAV alerts that tripped after the ransom note was dropped](https://www.bleepstatic.com/images/news/security/h/huntress-labs/qilin-investigation/mav-alerts.jpg)

**Figure 1: MAV alerts that tripped after the ransom note was dropped**

## [Simplify Your Path to CMMC Compliance](https://www.huntress.com/upcoming-webinars/cmmc-12-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-12-edr-na-prospect-iis-x-cmmc-december%5Fwebinar&hnt=iiyvinrppkii)

Preparing for CMMC Level 2 certification doesn’t have to be overwhelming.

Huntress provides the tools, documentation, and expert guidance you need to streamline your audit process and protect your contracts. Let us help you achieve compliance faster and more affordably.

[Learn More](https://www.huntress.com/upcoming-webinars/cmmc-12-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-12-edr-na-prospect-iis-x-cmmc-december%5Fwebinar&hnt=iiyvinrppkii)

Analysts began tasking files from the endpoint, starting with a specific subset of the Windows Event Logs (WEL).

From those logs, analysts could see that on 8 Oct 2025, the threat actor accessed the endpoint and installed the **Total Software Deployment Service**, as well as a rogue instance of the **ScreenConnect RMM**, one that pointed to IP address **94.156.232\[.\]40**.

Searching VirusTotal for the IP address provided the insight illustrated in Figure 2.

![Figure 2: VirusTotal response for the IP address 94.156.232[.]40](https://www.bleepstatic.com/images/news/security/h/huntress-labs/qilin-investigation/virustotal.jpg)

**Figure 2: VirusTotal response for the IP address 94.156.232\[.\]40**

An interesting aspect of the installation was that **LogMeIn** was apparently legitimately installed on the endpoint on 20 Aug 2025 from the file **%user%\\Downloads\\LogMeIn.msi**.

Then, on 8 Oct, the rogue ScreenConnect instance was installed from the file **C:\\Users\\administrator\\AppData\\Roaming\\Installer\\LogmeinClient.msi**.

Further, the timeline indicates that on 2 Oct, the file **%user%\\Downloads\\LogMeIn Client.exe** was submitted by Windows Defender for review, and no other action was taken after that event. 

Pivoting from the ScreenConnect installation to ScreenConnect activity events within the timeline of activity, analysts saw that on 11 Oct, three files were transferred to the endpoint via the **ScreenConnect** instance; **r.ps1**, **s.exe**, and **ss.exe**.

Digging in a bit deeper, only **r.ps1** was still found on the endpoint (shown below).

```
$RDPAuths = Get-WinEvent -LogName
'Microsoft-Windows-TerminalServices-RemoteConnectionManager/Operational'
-FilterXPath @'
<QueryList><Query Id="0"><Select>
  *[System[EventID=1149]]
</Select></Query></QueryList>
'@
# Get specific properties from the event XML
[xml[]]$xml=$RDPAuths|Foreach{$_.ToXml()}
$EventData = Foreach ($event in $xml.Event) {
  # Create custom object for event data
  New-Object PSObject -Property @{
   TimeCreated = (Get-Date ($event.System.TimeCreated.SystemTime) -Format 'yyyy-MM-dd hh:mm:ss K')
   User = $event.UserData.EventXML.Param1
   Domain = $event.UserData.EventXML.Param2
   Client = $event.UserData.EventXML.Param3
  }
}
$EventData | FT
```

Based on the contents of the script, it would appear that the threat actor was interested in determining IP addresses, domains, and usernames associated with RDP accesses to the endpoint. 

However, the Windows Event Log contained a **Microsoft-Windows-PowerShell/4100** message stating:

**Error Message = File C:\\WINDOWS\\systemtemp\\ScreenConnect\\22.10.10924.8404\\Files\\r.ps1 cannot be loaded because running scripts is disabled on this system.**

This message was logged within 20 seconds of the script being transferred to the endpoint, and the threat actor attempting to run it. 

## Parsing through PCA logs

The other two files, **s.exe** and **ss.exe**, took a bit more work to unravel, because they were no longer found on the endpoint.

However, Huntress analysts were able to take advantage of data sources on the Windows 11 endpoint, specifically the AmCache.hve file and the [Program Compatibility Assistant](https://www.sygnia.co/blog/new-windows-11-pca-artifact/) (PCA) log files to obtain hashes for the files, and to see that while the threat actor had attempted to execute the files, both apparently failed. 

The threat actor disabled Windows Defender, which were seen in [Windows Defender event records](https://learn.microsoft.com/en-us/defender-endpoint/troubleshoot-microsoft-defender-antivirus), starting with event ID 5001, indicating that the Real-Time Protection feature was disabled. This was followed by several event ID 5007 records, indicating that features such as **SpyNetReporting** and **SubmitSamplesConsent** had been modified (in this case, disabled), as well as SecurityCenter messages indicating that Windows Defender had entered a **SECURITY\_PRODUCT\_STATE\_SNOOZED** state.

The threat actor then attempted to launch **s.exe**, which was almost immediately followed by the message “Installer failed” in the PCA logs. Based on the identified VirusTotal detections shown in Figure 3, and the [behaviors identified by VirusTotal](https://www.virustotal.com/gui/file/af9925161d84ef49e8fbbb08c3d276b49d391fd997d272fe1bf81f8c0b200ba1/behavior), this file appears to be an [infostealer](https://www.huntress.com/blog/infostealers-crash-course-tradecraft-tuesday-recap). 

**Figure 3: VirusTotal response for s.exe file**

The messages in the PCA logs provide indications that the file, identified as an installer, failed to execute.

Seven seconds later, the threat actor attempted to run **ss.exe**, which was immediately followed by the legitimate Windows application, **c:\\windows\\syswow64\\werfault.exe**, being launched. The PCA logs then contained three consecutive messages stating, “PCA resolve is called, resolver name: CrashOnLaunch, result: 0” with respect to **ss.exe**, all indicating that the application did not run. 

Again, prior to attempting to run the above two files, the threat actor disabled Windows Defender at **2025-10-11 01:34:21 UTC**, resulting in the Windows Defender status being reported as **SECURITY\_PRODUCT\_STATE\_SNOOZED**. At **2025-10-11 03:34:56 UTC**, the threat actor accessed the endpoint remotely, and then at **2025-10-11 03:35:13 UTC**, there were multiple Windows Defender detections for attempts to create ransom notes (i.e., **Behavior:Win32/GenRansomNote**), as well as Windows Defender messages indicating that remediation attempts failed.

At this point, the Windows Defender status was reported as **SECURITY\_PRODUCT\_STATE\_ON**. The Windows Defender detection, coupled with the preceding remote login, appears to indicate that the ransomware executable was launched from another endpoint, [against network shares](https://www.huntress.com/blog/dispelling-ransomware-deployment-myths).

Figure 4 illustrates an excerpt of a Qilin ransom note found on the endpoint.

**Figure 4: Qilin ransom note excerpt**

Qilin ransomware is a “ransomware-as-a-service” (RaaS) variant, meaning that while the ransomware logistics is managed from a central location, each affiliate likely follows a different attack pattern, leaving behind different traces and artifacts.

For example, a number of Qilin incidents observed by Huntress analysts have started with the threat actor logging in via the Remote Desktop Protocol (RDP), and all included similar ransom notes and encrypted file extensions.

However, in only one incident did analysts observe the use of [s5cmd for data exfiltration](https://www.huntress.com/blog/exposing-data-exfiltration-lolbin-ttp-binaries). 

## The value of multiple data sources in an investigation

Throughout this investigation, Huntress analysts weren’t looking through a keyhole. Remember, the Huntress agent was installed post-incident, so there was no EDR telemetry, no SIEM data, and no ransomware canaries on which to build an understanding of the incident progression.

In addition, at the time the MAV alerts were received in the Huntress portal, this was the only endpoint within the infrastructure with a Huntress agent installed. 

Rather than looking through a keyhole, analysts were looking through a pinhole. Yet, relying on multiple data sources led not only to a deeper understanding of the threat actor’s attempted activities on the endpoint, but also served to validate findings and provide a clearer picture of what actually occurred.

For example, understanding that the threat actor used a rogue ScreenConnect instance to attempt to deploy several malicious files–including one that appeared to be an infostealer–can help inform the victim company when they are trying to determine the scope of the incident and how to respond.

During an investigation, particularly one that is time-sensitive or even just assumed to be, it’s easy to fall prey to finding an artifact and building a story around it without first verifying or validating it. It can be easy to think, “...this is anomalous to me…”, without really considering if it’s anomalous within the infrastructure itself, particularly if the investigation is being performed by looking through a pinhole.

Validating activity across multiple data sources, and not jumping to the first indicator as the basis for malicious activity, provides a much more accurate picture of the threat actor’s activities, and provides a foundation for more accurate decisions and remediations.

## Meet Huntress: Demo & AMA

Cyber threats don’t take breaks, and neither do we. At Huntress, we’re always innovating because the job never stops when it comes to leveling up security and protecting businesses like yours.

Bring your toughest questions, real-world scenarios, and security headaches. Let's tackle them together.

**[Reserve for the webinar!](https://www.huntress.com/upcoming-webinars/meet-huntress-demo-and-ama-na-1217?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-08-camp-multi-na-prospect-iis-x-ama%5F2h2025&hnt=em8p1so4ba5o)**  