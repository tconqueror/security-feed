# Microsoft Defender portal outage disrupts threat hunting alerts

![Microsoft Defender for Endpoint](https://www.bleepstatic.com/content/hl-images/2023/10/11/Microsoft-Defender_for_Endpoint.jpg)

Microsoft is working to mitigate an ongoing incident that has been blocking access to some Defender XDR portal capabilities for the past 10 hours.

According to an admin center service alert ([DZ1191468](https://admin.microsoft.com/#/MessageCenter/:/messages/DZ1191468)) seen by BleepingComputer, this outage may affect customers attempting to access or use features in the Defender portal.

The issues are caused by what Microsoft describes as a "spike in traffic caused high Central Processing Unit (CPU) utilization on components that facilitate Microsoft Defender portal functionalities."

When it acknowledged the outage this morning at 06:10 UTC, Microsoft also tagged it as an incident, a designation commonly used for critical service issues that typically involve noticeable user impact.

Microsoft has since applied mitigation measures to address the impact and increased processing throughput, with telemetry showing that availability has recovered for some impacted customers, according to an 8 AM UTC update.

![Defender XDR portal outage](https://www.bleepstatic.com/images/news/u/1109292/2025/Defender-portal-outage.png)

Microsoft is now analyzing HTTP Archive (HAR) traces provided by impacted customers and said that, besides blocked access, the impacted portal functionality currently includes, but is not limited to, missing advanced threat-hunting alerts and devices not appearing.

"We've received confirmation from additional organizations that the issue is resolved for them, and monitoring telemetry continues to show CPU utilization remains within acceptable thresholds," it added roughly two hours later.

"We're working with a small number of organizations who reported that the issue still persists and coordinating with them to collect additional client-side diagnostics and HTTP Archive format (HAR) traces to assist our investigation."

_This is a developing story..._