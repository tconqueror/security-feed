# How to spot dark web threats on your network using NDR

![Dark Web NDR](https://www.bleepstatic.com/content/posts/2025/10/14/dark-web-ndr.jpg)

Cybersecurity professionals recognize that enterprise networks are prime targets for dark web risks such as ransomware, unauthorized insider activity, and data exfiltration. What’s less obvious is that evidence of this activity often hides in plain sight, buried within everyday network traffic.

For security leaders using Network Detection and Response (NDR), these hidden signals become opportunities for the defense.

Wondering how to spot dark web threats on your network?

Start with these four essential steps to leverage NDR for detection and investigation:

## **Step 1: Know the gateways to the dark web**

Unlike the public web, the dark web relies on anonymizing tools like the Tor browser, Invisible Internet Project (I2P), and Freenet peer-to-peer (P2P) networks that obscure user origins, encrypt traffic, and evade detection.

Despite their ability to obfuscate activity, signs of dark web movement are still captured in network data.

Telltale signs include unusual port usage, encrypted traffic patterns, and communication with Tor entry or exit nodes (explored further in step 4).

## **Step 2: Understand NDR**

NDR systems monitor network traffic in real time, leveraging AI, machine learning, and behavioral analytics to identify suspicious or malicious activity. NDR also maintains comprehensive records of network activity, providing essential history and context.

With these insights, teams can integrate NDR into their SOC infrastructure and processes to improve mean time to detect (MTTD) and respond (MTTR) to cyber threats, including those posed by the dark web.

## **Step 3: Deploy NDR for comprehensive dark web visibility**

Monitor traffic across your core network, edge environments, and internal segments. Key recommendations include:

* **Position NDR sensors at strategic locations:**  
 Focus on network segments housing high-value assets to catch command-and-control (C2) activity and data exfiltration attempts.
* **Analyze north-south traffic:** Use NDR to inspect internal-to-external communications to detect possible dark web interactions.
* **Track lateral movement:** Monitor internal traffic between devices for signs that could indicate dark web-related threats.

## **Step 4: Detect and hunt with NDR**

### Begin with network baselining

NDR deployments often start with a 30-day network baselining period that allows the platform to learn your organization’s normal traffic. Once complete, NDR can automatically flag indicators of dark web activity, including:

* New communications with previously unknown external IPs
* Excessive peer connections
* Suspicious file transfer protocols or traffic to unusual domains
* Unusual outbound traffic masquerading as normal, signaling possible data exfiltration to dark web marketplaces

With the baseline established, you can now refine NDR settings to automate detection of targeted dark web indicators.

Note that if your network is already compromised, you must be careful to not let the NDR perceive threat activity as being “normal.”

This is why baselining the network requires active analysis and an understanding of your environment. 

### **Automate detection of Tor activity**

* Set up dynamic alerts for devices communicating over default Tor ports (9001, 9030, 9050).
* Monitor tunnel logs for irregular patterns like compressed Transport Layer Security (TLS) headers, unique negotiation behaviors, unusually long sessions, and high bandwidth usage.
* Scan for Tor traffic signatures, including distinctive packet lengths and handshakes.
* Track connections to known Tor entry nodes, relays, bridges, and Obfourscator or “obfs4” nodes. Flag traffic frequently switching between multiple external IPs or interacting with anonymization services.
* [Corelight’s Open NDR Platform ](https://corelight.com/products/open-ndr/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2)with [Investigator ](https://corelight.com/products/investigator?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2)can provide visibility into Tor connections through network metadata (including connection, protocol, and TLS connections and certificates), Suricata signatures, and machine learning algorithm detections.

## [Spot dark web threats with Corelight NDR](https://corelight.com/contact?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2)

Trusted to defend the world’s most sensitive networks, Corelight's Network Detection & Response (NDR) platform combines deep visibility with advanced behavioral and anomaly detections to help your SOC uncover new AI-powered threats and dark web activity.

[Take action against threats today](https://corelight.com/contact?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2)

### Monitor for I2P and P2P Connections

* Set dynamic alerts for traffic on I2P ports (7650–7659) and BitTorrent/P2P ports (6881–6889).
* Monitor for high outbound UDP traffic to random or external IPs, signaling I2P tunnels.
* Watch for periodic spikes to unfamiliar or unresolved IPs and obscure UDP ports that are common with I2P peer discovery.
* Detect persistent, long-duration P2P sessions across distributed IPs, indicating Freenet activity.
* Look for self-signed certificates typical of Freenet and other anonymization tools.
* Flag workstations and devices (including IoT) that show persistent connections to high-entropy or random domain names, a common sign of anonymization services.
* The Corelight [Encrypted Traffic Collection](https://corelight.com/products/analytics/encrypted-traffic?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2) can help identify unusual certificates, unexpected encryption, and other TLS anomalies that could indicate use of encrypted I2P and P2P connections.

### Track suspicious DNS activity

* Monitor DNS logs for queries to .onion addresses, uncommon subdomains, and attempts to access domains associated with anonymization tools.
* Flag queries to low-reputation, rarely used, or malicious domains, especially those linked to VPNs or proxies. For example, DNS requests involving the .su domain, reserved for the former Soviet Union, are almost never legitimate.
* Detect devices that avoid internal DNS and instead use external DNS servers. This could indicate the use of anonymization tools, but it is also likely a violation of the organization’s network security policies and preferences.

### Monitor VPN connections

* Detect connections to well-known consumer VPN providers (e.g., NordVPN, ExpressVPN, ProtonVPN).
* Alert on non-standard VPN ports (OpenVPN: 1194, Layer Two Transport Protocol, or L2TP: 1701).
* Flag traffic routed via OpenVPN, IPSec, or WireGuard, including use of custom SSL/TLS certificates tied to these services, to determine if they are allowed by current policies and practices.
* Corelight’s VPN Insights package identifies over 400 unique VPN protocols, providers, and types and logs them along with critical metadata (like country of origin) for investigation.

### Monitor for “impossible travel,” geolocation and similar anomalies

* Identify instances of “impossible travel” using IP geolocation data from users or devices (e.g., logins from distant countries when users are located in your offices).
* Detect connections from suspicious regions or countries outside your organization's normal operational scope.
* Look for traffic with no identifiable legitimate business application

### Flag lateral movement that signals possible infiltration

* Flag internal traffic that hops between multiple systems before reaching external endpoints.
* Monitor for unusual activity between internal devices, especially using unexpected protocols like SOCKS proxies/tunnels.
* Corelight’s Encrypted Traffic Collection can also identify unusual remote management traffic, even in encrypted connections, helping to see potentially malicious use of SSH and RDP as attackers move laterally within a network.

### Detect malware and command-and-control (C2) beaconing

* Use [Yara](https://corelight.com/products/yara?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2) to analyze files extracted from network traffic. Look for malware or suspicious binaries.
* Check logs for patterns of “check-in” activity. These may occur at regular intervals, such as every 5 minutes, or every hour.
* Corelight’s[ C2 Collection](https://corelight.com/products/analytics/command-and-control?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2) identifies dozens of attack frameworks, RATs, and malware that are often used to stage attacks, establish C2, and download additional tools for attack expansion.

### Add threat intelligence

* Correlate known dark web activity by adding threat intelligence feeds. Integrate feeds to flag Indicators of Compromise (IOCs) like hashes, IPs, and C2 domains.
* Consider hiring a third party threat intelligence service to monitor the dark web for chatter about your organization or data leaks from your environment.
* Track login attempts from suspicious or compromised locations with external credential monitoring.
* Corelight’s Intel Framework matches millions of indicators at line rate, generating alerts and logs for pinpoint detection and investigation.

A well-tuned NDR solution significantly enhances your organization’s ability to detect dark web activity and bolsters overall cybersecurity posture.

Corelight’s Open NDR Platform features integrated multi-layer detection, file analysis, advanced protocol monitoring, and comprehensive long-term network metadata collection.  
  
**To discover more about Corelight NDR or discuss how to activate these dark web detection capabilities within your own network, [visit corelight.com](http://corelight.com?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2).**

_Sponsored and written by [Corelight](https://corelight.com?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2)._