# Amazon disrupts Russian GRU hackers attacking edge network devices

![Amazon disrupts Russian GRU hackers attacking edge network devices](https://www.bleepstatic.com/content/hl-images/2023/01/06/Amazon_AWS.jpg)

The Amazon Threat Intelligence team has disrupted active operations attributed to hackers working for the Russian foreign military intelligence agency, the GRU, who targeted customers' cloud infrastructure.

The cloud services provider observed a focus on Western critical infrastructure, especially the energy sector, in activity that started in 2021.

Over time, the threat actor pivoted from exploiting vulnerabilities (zero-days and known ones) to leveraging misconfigured edge devices for initial access.

[![Wiz](https://www.bleepstatic.com/content/webinar-images/Action1-970x250-watch-now.jpg)](/mgo/72/) 

### Fewer vulnerabilies exploited

CJ Moses, the CISO of Amazon Integrated Security, notes that up to 2024, the "years-long" campaign exploited multiple vulnerabilities in WatchGuard, Confluence, and Veeam as the primary initial access vector and targeted misconfigured devices.

This year, though, the threat actor relied less on vulnerabilities and more on targeting misconfigured customer network edge devices, such as enterprise routers, VPN gateways, network management appliances, collaboration platforms, and cloud-based project management solutions.

"Targeting the 'low-hanging fruit' of likely misconfigured customer devices with exposed management interfaces achieves the same strategic objectives, which is persistent access to critical infrastructure networks and credential harvesting for accessing victim organizations’ online services," [Moses explains](https://aws.amazon.com/blogs/security/amazon-threat-intelligence-identifies-russian-cyber-threat-group-targeting-western-critical-infrastructure/).

"The threat actor’s shift in operational tempo represents a concerning evolution: while customer misconfiguration targeting has been ongoing since at least 2022, the actor maintained sustained focus on this activity in 2025 while reducing investment in zero-day and N-day exploitation," he added.

However, the tactical evolution did not reflect any change in the group’s operational objectives: stealing credentials and moving laterally on the victim network with as little exposure and as few resources as possible.

Based on targeting patterns and overlaps in infrastructure seen in attacks from Sandworm (APT44, Seashell Blizzard) and Curly COMrades, Amazon assesses with high confidence that the observed attacks were carried out by hackers working for the Russian GRU.

Amazon believes that the Curly COMRades hackers, [first reported by Bitdefender](https://www.bleepingcomputer.com/news/security/curly-comrades-cyberspies-hit-govt-orgs-with-custom-malware/), may be tasked with [post-compromise activity](https://www.bleepingcomputer.com/news/security/russian-hackers-abuse-hyper-v-to-hide-malware-in-linux-vms/) in a broader GRU campaing involving multiple specialized subclusters.

### Spreading on the network

Although Amazon did not directly observe the extraction mechanism, evidence in the form of delays between device compromise and leveraging the credentials, and abuse of organization credentials, points to passive packet capturing and traffic interception.

Compromised devices were customer-managed network appliances hosted on AWS EC2 instances, and Amazon noted that the attacks did not leverage flaws on the AWS service itself.

After discovering the attacks, Amazon took immediate action to protect compromised EC2 instances and notified affected customers of the breach. Moreover, they shared intelligence with impacted vendors and industry partners.

"Through coordinated efforts, since our discovery of this activity, we have disrupted active threat actor operations and reduced the attack surface available to this threat activity subcluster," Amazon said.

Amazon has shared the offending IP addresses in its report but warned not to block them without first conducting a contextual investigation because they are legitimate servers that the threat actor compromised to proxy its traffic.

The company further recommended a series of “immediate priority actions” for next year, such as auditing network devices, watching for credential replay activity, and monitoring access to administrative portals.

In AWS environments specifically, it is recommended to isolate management interfaces, restrict security groups, and enable CloudTrail, GuardDuty, and VPC Flow Logs.