# ‘PlushDaemon’ hackers hijack software updates in supply-chain attacks

![China](https://www.bleepstatic.com/content/hl-images/2025/05/28/China.jpg)

A China-linked threat actor tracked as 'PlushDaemon' is hijacking software update traffic using a new implant called EdgeStepper in cyberespionage operations.

Since 2018, PlushDaemon hackers have targeted individuals and organizations in the United States, China, Taiwan, Hong Kong, South Korea, and New Zealand with custom malware, such as the SlowStepper backdoor.

PlushDaemon has compromised electronics manufacturers, universities, and a Japanese automotive manufacturing plant in Cambodia. Telemetry data from cybersecurity firm ESET indicates that since 2019, the threat actor has relied on malicious updates to breach target networks.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

![PlushDaemon victims since 2023](https://www.bleepstatic.com/images/news/u/1220909/2025/November/map(1).jpg)

**PlushDaemon victims since 2023**  
_Source: ESET_

### Attack chain

The attackers gain access to routers by exploiting known vulnerabilities or weak admin passwords, install the EdgeStepper implant, and then redirect software-update traffic to their own infrastructure.

EdgeStepper works by intercepting DNS queries and redirecting them to a malicious DNS node after confirming that the domain is employed for delivering software updates, ESET researchers explain in a report shared with BleepingComputer.

When a victim tries to update their software, they receive the LittleDaemon malware downloader for Windows disguised as a DLL file named ‘_popup\_4.2.0.2246.dll._’

**Overview of the attack**  
_Source: ESET_

LittleDaemon fetches another malware dropper named DaemonicLogistics, decrypted and executed in memory, that retrieves PlushDaemon's signature backdoor, SlowStepper.

The backdoor has been [previously documented](https://www.bleepingcomputer.com/news/security/ipany-vpn-breached-in-supply-chain-attack-to-push-custom-malware/) in attacks against users of the South Korean VPN product IPany. During those attacks, users downloaded a trojanized installer from the vendor’s official website.

The SlowStepper malware lets hackers collect detailed system information, run extensive file operations, execute commands, and run various Python-based spyware tools that can steal data from the browser, intercept keystrokes, and collect credentials.