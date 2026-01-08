# Cisco switches hit by reboot loops due to DNS client bug

![Cisco](https://www.bleepstatic.com/content/hl-images/2024/07/18/Cisco.jpg)

Multiple Cisco switch models are suddenly experiencing reboot loops after logging fatal DNS client errors, according to reports seen by BleepingComputer.

Starting at approximately 2 AM, what appears to be a firmware bug in the switches' internal DNS client service began treating DNS lookup failures as fatal errors, causing affected devices to reboot repeatedly.

Switches impacted by the bug are logging fatal errors similar to the following before rebooting:

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

```
DNS_CLIENT - SRCADDRFAIL - Result is 2. Failed to identify address for specified name 'www.cisco.com.', requested addr type 2.    ***** FATAL ERROR *****   Reporting Task: DNSC. [debug data] ***** END OF FATAL ERROR *****   

```

Based on reports from administrators who contacted BleepingComputer, Reddit discussions, and Cisco Community forum \[[1](https://community.cisco.com/t5/switches-small-business/cisco-cbs250-and-c1200-dns-crash/td-p/5359999), [2](https://community.cisco.com/t5/switches-small-business/got-fatal-error-cbs350-24t-4g/td-p/5359883?utm%5Fsource=chatgpt.com)\] posts, the fatal errors originate from the DNSC (DNS Client) task and occur when the switches attempt to resolve "www.cisco.com" and NTP time servers.

Administrators report that the reboot cycle repeats every few minutes, severely disrupting network operations.

"The cycle repeats every few minutes. This is obviously pretty disruptive and I'm not going to be able to sustain operations like this for very long," a Cisco customer wrote on [Reddit](https://www.reddit.com/r/Cisco/comments/1q7h9kc/sg550x%5Fseries%5Fswitches%5Fnew%5Ffatal%5Ferrors/).

Based on reports, the bug appears to impact a wide range of Cisco switch models, including:

* Cisco CBS250 series
* Cisco CBS350 series (including the CBS350-24P-4G)
* Cisco Catalyst C1200 series
* Cisco SG350
* Cisco SG350X
* Cisco SG550X series

Several administrators report that the failures began around the same time across separate networks, suggesting the issue was globally triggered or tied to a time-based condition.

While Cisco has not yet publicly disclosed the root cause, BleepingComputer was told that Cisco support acknowledged the issue to at least one customer, stating it affects CBS, SG, and Catalyst 1200/1300 switches.

For now, administrators have discovered temporary workarounds that stop the reboot loops, including disabling DNS resolution, disabling SNTP or time synchronization, and blocking outbound internet access from switch management interfaces.

Multiple users report that disabling DNS configurations stopped the reboot loops, even when DNS servers were reachable and functioning normally. In Cisco Community forum posts, users also confirmed that removing DNS resolution resolved the reboot loops.

BleepingComputer has contacted Cisco for comment and will update this article as more information becomes available.