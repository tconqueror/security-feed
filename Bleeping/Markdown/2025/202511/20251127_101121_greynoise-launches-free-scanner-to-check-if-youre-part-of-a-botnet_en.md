# GreyNoise launches free scanner to check if you're part of a botnet

![GreyNoise launches free scanner to check if you're part of a botnet](https://www.bleepstatic.com/content/hl-images/2024/04/02/scanner.jpg)

GreyNoise Labs has launched a free tool called GreyNoise IP Check that lets users check if their IP address has been observed in malicious scanning operations, like botnet and residential proxy networks.

The threat monitoring firm that tracks internet-wide activity via a global sensor network says this problem has grown significantly over the past year, with many users unknowingly helping malicious online activity.

"Over the past year, residential proxy networks have exploded and have been turning home internet connections into exit points for other people's traffic," [explains GreyNoise](https://www.greynoise.io/blog/your-ip-address-might-be-someone-elses-problem).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Sometimes folks knowingly install software that does this in exchange for a few dollars. More often, malware sneaks onto devices, usually via nefarious apps or browser extensions, and quietly turns them into nodes in someone else's infrastructure."

While there are ways to determine if someone has become part of malicious botnet activity, like examining device logs, configurations, network traffic, and activity patterns, a tool that simply checks the IP address is the least intrusive method

People visiting the [scanner's webpage](https://check.labs.greynoise.io/) will get one of the three possible results:

1. **Clean**: No malicious scanning activity detected.
2. **Malicious/Suspiciou**s: The IP has shown scanning behavior. Users should investigate devices on their network.
3. **Common Business Service**: The IP belongs to a VPN, corporate network, or cloud provider, and the scanning activity is normal for those environments.

![Clean scan result](https://www.bleepstatic.com/images/news/u/1220909/2025/November/scanresult.jpg)

**Clean scan result**  
_Source: BleepingComputer_

When any activity is correlated with the provided IP address, the platform will also include a 90-dayhistorical timeline, which may help pinpoint a potential infection point.

For example, when the installation of a bandwidth-sharing client or a shady application precedes malicious scanning, strong correlations can be made that enable remediation action.

**Historic activity data**  
_Source: GreyNoise_

For more technical users, GreyNoise also provides an unauthenticated, rate-limit-free JSON API accessible via curl, which can be integrated into scripts or checking systems.

If your scan results show 'Malicious/Suspicious,' it's a good idea to start the investigation by running malware scans on all devices on the same network, especially focusing on devices like routers and smart TVs.

Users are advised to update their devices to the latest available firmware, change admin credentials, and disable remote access features if they're not needed.