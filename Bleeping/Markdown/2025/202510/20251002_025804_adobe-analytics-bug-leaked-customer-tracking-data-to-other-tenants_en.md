# Adobe Analytics bug leaked customer tracking data to other tenants

![Adobe](https://www.bleepstatic.com/content/hl-images/2023/09/12/adobe.jpg)

Adobe is warning its Analytics customers that an ingestion bug caused data from some organizations to appear in the analytics instances of others for approximately one day.

Adobe disclosed the issue on its status page, stating that it began on September 17, 2025, at 12:20 UTC, when a performance optimization change introduced a bug in Analytics Edge data collection. 

The status page states that the flaw caused "errant values" to appear in Analysis Workspace reports and that Adobe engineering teams are working to cleanse impacted datasets. 

"On September 17, 2025, at 12:20 UTC, a service disruption impacted Adobe Analytics customers globally, including applications dependent on Adobe Analytics data," reads Adobe's status entry for an Analytics issue.

"The disruption was caused by a bug introduced during a recent performance optimization change to Adobe Analytics data collection, which led to errant values appearing in Analysis Workspace reports."

The bug impacted numerous Analytics services, including Data Collection, Media Processing, Customer Attributes, and reporting applications. 

Adobe reverted the change on September 18 at 11:00 UTC and said the incident was not caused by malicious activity or a cybersecurity incident.

While Adobe's status only says "errant data," a private customer advisory shared with BleepingComputer states that fields in some data were overwritten with values from other customers' data streams.

The company states that this impacted approximately 3–5% of the collected data, with corrupted rows being found within Data Feeds, Live Stream, scheduled reports, and other integrations.

As many products ingest data from Adobe Analytics, they too were impacted, including Customer Journey Analytics, Real-Time CDP, and Adobe Journey Optimizer. 

The advisor instructs customers to immediately delete all impacted data from their systems, backups, and downstream environments, since it may contain information originating from other customers.

"All impacted Adobe Analytics customers who use Data Feeds or Live Stream should immediately delete or purge any data received between September 17, 12:20 UTC, and September 18, 2025, 11:00 UTC, since it may contain specific field information from other Adobe customers," reads the advisory seen by BleepingComputer.

"Please also remove all potentially impacted data from your systems, backups, and any downstream environments where it may have been stored or processed."  
  
"This action is necessary to help prevent further retention or use of data that may have been inadvertently exposed. The only other party that could have potentially viewed the data is an Adobe contracted customer."

While Adobe maintains that it is against its policies to collect personal data through its Analytics platform, BleepingComputer has learned that customers do not always follow these policies.

"That means, the web tracking of company A shows information of company B. This includes anything that company B tracked, including sensitive data like email addresses, session hashes, on-site search data, etc," an Analytics consultant told BleepingComputer.

Another customer stated that the implications were far-reaching, viewing the Adobe Analytics data leak as a significant issue with potential risks under VPPA, CPPA, and GDPR.

They also warned that because the ingestion bug wrote other customers' data directly into downstream business intelligence systems, it was embedded into backups, exports, and other systems that utilize the platform.

BleepingComputer contacted Adobe for clarification, but the company only referred us back to its public status page and did not respond to further questions.

Adobe states that it is continuing to cleanup the data and will notify customers when the platform can once again be used for valid reporting.