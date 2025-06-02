# SentinelOne: Last week’s 7-hour outage caused by software flaw

![SentinelOne](https://www.bleepstatic.com/content/hl-images/2025/06/02/SentinelOne-headpic.jpg)

American cybersecurity company SentinelOne revealed over the weekend that a software flaw triggered a seven-hour-long outage on Thursday.

This massive outage affected multiple customer-facing services in what SentinelOne described as a "global service disruption."

SentinelOne acknowledged the outage in a post published Thursday, reassuring customers that their systems were still protected.

"Customer endpoints are still protected at this time, but managed response services will not have visibility. Threat data reporting is delayed, not lost. Our initial RCA suggests this is not a security incident," SentinelOne [said](https://www.sentinelone.com/blog/update-on-may-29-outage#heading-1).

In a root cause analysis issued two days later, the company confirmed the incident's root cause was not a cyberattack or a security breach but a software flaw in an infrastructure control system that deleted critical network routes and DNS resolver rules automatically, which caused most services to go down in all regions.

Services were brought down after all required connecting infrastructure became reachable after a flaw in an outgoing cloud management function led to the restoration of an empty backup of the AWS Transit Gateway route table.

"SentinelOne is currently in the process of transitioning our production systems to a new cloud architecture built on Infrastructure-as-Code (IaC) principles. The deletion occurred after a soon-to-be-deprecated (i.e. outgoing) control system was triggered by the creation of a new account," SentinelOne [explained](https://www.sentinelone.com/blog/update-on-may-29-outage/).

"A software flaw in the control system's configuration comparison function misidentified discrepancies and applied what it believed to be the appropriate configuration state, overwriting previously established network settings. As this outgoing control system is no longer our source of truth for network configurations, it restored an empty route table."

As a result of this outage, programmatic access to the company's services was also interrupted, while Unified Asset Management/Inventory and Identity services were also brought down, blocking customers from viewing vulnerabilities or accessing identity consoles.

The company added that the outage may have impacted data ingestion from various third-party services, as well as Managed Detection and Response (MDR) alerts.

SentinelOne says the customers' endpoints remained protected, even though their security teams couldn't log into the SentinelOne management console, access SentinelOne data, or manage SentinelOne services.