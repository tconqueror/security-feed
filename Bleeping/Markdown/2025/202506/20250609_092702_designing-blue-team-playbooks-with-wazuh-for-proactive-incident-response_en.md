# Designing Blue Team playbooks with Wazuh for proactive incident response

![Wazuh header](https://www.bleepstatic.com/content/posts/2025/06/08/blue-team-header.png)

In cybersecurity, Blue Teams are responsible for defending an organization’s IT environment, including networks, endpoints, applications, and data against various types of threats. Their role goes beyond protecting IT assets; they also ensure operational continuity, monitor for malicious activity, and respond to incidents in real-time. To operate effectively, these teams rely on structured processes known as playbooks.

Blue Team playbook is a detailed guide outlining how to identify, contain, and remediate specific security incidents. These playbooks help ensure that incident responses are consistent, timely, and aligned with organizational policies and regulatory requirements, ultimately minimizing the impact of cyberattacks. They include specific prerequisites, workflows, checklists, and investigation steps for various incident scenarios.

## Key elements of Blue Team playbooks

While every organization may customize its playbooks to suit its specific environment, certain procedures are required to respond to incident use cases effectively:

* **Prerequisites:** The foundational requirements that must be in place before launching an investigation. This includes having appropriate security tooling, defined roles, relevant detection rules, and alerting logic, among others.
* **Workflow:** The logical sequence of steps followed during incident response. It typically follows a model that shows how an incident is detected, escalated, triaged, contained, and resolved.
* **Checklist:** A list of tasks used to track and verify each step in the workflow, ensuring all necessary actions are taken to mitigate and remediate an incident effectively.
* **Investigation playcards:** Detailed step-by-step instructions tailored to specific incident use cases and distinct attack vectors. Each playcard should include log sources, indicators of compromise (IoC), related MITRE ATT&CK techniques, containment, and recovery activities.

At the core of these playbooks is Incident Response (IR), the formalized process of detecting, investigating, and mitigating security incidents. Playbooks implement IR by translating high-level procedures into actionable steps for specific threats, making them essential tools for effective security operations.

### Incident use cases covered by Blue Team playbooks

Blue Team playbooks are designed to respond to various threat attacks. Some of the common incident use cases include:

* Brute-force login attempts across SSH, RDP, or web portals.
* Malware infections and unauthorized file changes.
* Insider threats and anomalous user behaviors.
* Privilege escalation and suspicious process executions on endpoints.
* Data exfiltration attempts via abnormal network activity.
* Web application attacks, including web shell uploads and exploitation attempts.

By mapping each use case to a predefined response strategy, Blue Teams can act quickly, reducing the mean time to respond (MTTR) and limiting potential damage.

## [Strengthen Your Blue Team Playbooks with Wazuh](https://wazuh.com/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer)

Unlock the full potential of your Blue Team operations. Discover how Wazuh, an open-source security platform, empowers real-time threat detection, automated response, and comprehensive incident management for various attack scenarios.

Enhance your cyber defenses today!

[Learn More About Wazuh](https://wazuh.com/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer)

## Understanding the role of Wazuh in Blue Team playbooks

Effective incident response requires tools that offer real-time security monitoring, automated response, and correlation-based threat detection. [Wazuh](https://wazuh.com/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer), a free and open source security platform, provides these capabilities, enabling security teams to detect, analyze, and respond to incidents efficiently.

Wazuh unifies Security Information and Event Management (SIEM) functionalities with Extended Detection and Response (XDR) capabilities. Its capabilities allow for the correlation and analysis of security data across diverse endpoints and environments, including on-premises, cloud, and hybrid infrastructures. Its real-time threat detection, log analysis, and file integrity monitoring capabilities make it an important asset for Blue Teams. These features make it invaluable during all four major phases of the incident response lifecycle.

![Four phases of incident response lifecycle](https://www.bleepstatic.com/images/news/security/w/wazuh/blue-team-playbook/four-phases.jpg)

Incident response (IR) involves a structured approach that includes preparation, detection, analysis, containment, eradication, recovery, and post-incident activities to capture lessons learned. By integrating Wazuh into the incident response lifecycle, organizations can achieve the following:

* Real-time detection through centralized log analysis and file integrity monitoring.
* Automated alerting based on customizable rules to trigger responses.
* Behavioral monitoring of endpoints, servers, and cloud environments.
* Built-in incident response actions to contain and isolate threats.
* Compliance and audit reporting features for post-incident documentation.

### Integrating Wazuh into your Blue Team playbook

The following playbook examples demonstrate how Wazuh can be applied to real-world threat scenarios, showcasing its role in detection and response across diverse attack vectors:

#### Playbook 1: Credential dumping on a Windows endpoint

Credential dumping is a common post-exploitation technique that attackers use to harvest account credentials stored in memory or registry hives. These credentials can be subsequently used for lateral movement and unauthorized access to restricted information. Wazuh helps detect this behavior on Windows endpoints by leveraging security event logs, Sysmon logs, and process monitoring modules.

Wazuh can be configured to monitor suspicious access to `lsass.exe`, registry queries to `SAM` or `SECURITY` hives, and abnormal execution of credential extraction tools such as Mimikatz. Alerts are generated using pre-defined rules correlating parent-child process relationships, command line arguments, and known IoC patterns.

For example, Wazuh out-of-the-box rules can [detect Impacket](https://wazuh.com/blog/detecting-impacket-with-wazuh/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) abuse against monitored Windows endpoints. Impacket is a collection of Python-based scripts designed for manipulating network protocols and exploiting Windows services.

When Impacket attack tools such as `secretsdump.py` are executed against a Wazuh agent, Wazuh immediately detects the activity. It then triggers alerts visible on the Wazuh dashboard for security analysts to review and respond.

![Figure 1: Alerts on a Wazuh dashboard from the execution of secretsdump.py.](https://www.bleepstatic.com/images/news/security/w/wazuh/blue-team-playbook/wazuh-alerts.png)

**Figure 1: Alerts on a Wazuh dashboard from the execution of secretsdump.py**

#### Playbook 2: Web shell on a compromised web server

Web shells are malicious scripts that enable threat actors to maintain persistent access on compromised web servers and launch additional attacks. Threat actors favor this technique to create backdoors within their victims’ environments.

Wazuh detects web shells using a combination of file integrity monitoring (FIM) and threat detection capabilities. Blue Teams can configure Wazuh to monitor high-risk directories and flag unauthorized file creations or modifications that may indicate the presence of a web shell. Wazuh FIM generates alerts whenever changes occur in specified paths, enabling early tampering detection within monitored endpoints.

In addition to monitoring file changes, Wazuh includes built-in rules that help detect suspicious activity on web servers. These rules flag behaviors like executing non-standard scripts or using unexpected HTTP methods. Blue Teams can also create custom rules to detect specific malware behaviors.

Below is an additional rule written to trigger alerts when the Wazuh manager detects files modified within monitored directories with PHP web shell signatures:

```
<group>
<rule id="100502" level="15">
    <if_sid>100501</if_sid>
    <field name="changed_content" type="pcre2">(?i)passthru|exec|eval|shell_exec|assert|str_rot13|system|phpinfo|base64_decode|chmod|mkdir|fopen|fclose|readfile|show_source|proc_open|pcntl_exec|execute|WScript.Shell|WScript.Network|FileSystemObject|Adodb.stream</field>
    <description>[File Modification]: File $(file) contains a web shell</description>
    <mitre>
      <id>T1105</id>
      <id>T1505.003</id>
    </mitre>
  </rule>
</group>
```

The following rule inspects modified files for suspicious PHP functions often used in web shells. The `changed_content` field represents the contents of the modified file, which Wazuh scans for patterns like `eval`, `exec`, and `base64_decode`. When matched, it triggers a high-severity alert and maps the behavior to relevant MITRE ATT&CK techniques.

#### Playbook 3: Suspicious data exfiltration

Data exfiltration can be hard to detect, especially when attackers leverage legitimate tools to move data and evade detection. This technique, known as Living Off the Land (LOTL), involves the misuse of native operating system utilities, making malicious activities blend with normal operations. Wazuh supports network activity monitoring, command execution tracking, and file access auditing to uncover abnormal outbound activity.

By monitoring shell history, large file transfers, or tools like `scp`, `curl`, or `netcat`, Wazuh alerts teams to high-volume transfers or unusual destinations. Wazuh also utilizes the GeoIP feature to flag connections from and to suspicious locations, helping you detect and escalate potential exfiltration attempts in real-time.

The blog post on [detecting data exfiltration performed using LOTL tools](https://wazuh.com/blog/detecting-data-exfiltration-using-living-off-the-land-tools-with-wazuh/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) simulates various data exfiltration scenarios and how they can be detected using Wazuh.

It demonstrates how Wazuh can monitor commands executed via PowerShell, Command Prompt, and built-in Windows utilities to identify suspicious file transfers. By collecting and analyzing event logs, Wazuh agents can detect indicators like the use of `certutil`, `bitsadmin`, and `curl` for unauthorized data movement.

Custom rules and decoders can generate alerts when these tools are misused, helping Blue Teams respond quickly to exfiltration attempts.

**Figure 2: Wazuh uses custom rules to trigger alerts when the BITS service is abused**

#### Playbook 4: Brute-force login attack

Brute-forcing is a common attack vector that threat actors use to gain unauthorized access to endpoints and services. Services like SSH on Linux endpoints and RDP on Windows are usually prone to brute-force attacks. Wazuh detects brute-force attacks by correlating multiple authentication failure events across monitored endpoints. On Linux endpoints, it identifies these attacks out-of-the-box by parsing authentication logs such as `/var/log/auth.log` using log data detection capabilities.

Wazuh decoders parse raw log data from authentication services to extract structured information about failed login attempts. This includes details like source IP address, username, and timestamp. Once decoded, Wazuh correlation rules analyze this data to detect patterns of rapid or repeated failures from the same IP address, triggering alerts for potential brute-force attacks.

When the defined alert threshold is met, Wazuh uses its [Active Response](https://documentation.wazuh.com/current/user-manual/capabilities/active-response/ar-use-cases/blocking-ssh-brute-force.html?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) capabilities to run scripts to take action on certain triggers. For example, Wazuh can trigger an active response to block the offending IP address using firewall rules like `iptables`.

The blog post on monitoring [Rapid SCADA with Wazuh](https://wazuh.com/blog/monitoring-rapid-scada-with-wazuh/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) illustrates how brute-force login attempts against industrial control systems can be detected using log data analysis capability. Wazuh monitors authentication logs from Rapid SCADA systems, parsing events that indicate repeated failed login attempts. Custom rules identify abnormal patterns, such as multiple failures within a short time frame.

These rules generate alerts that highlight potential brute-force activity, allowing security teams to respond quickly. By analyzing log data from SCADA systems, Wazuh enables early detection of unauthorized access attempts and other anomalies within industrial control environments.

**Figure 3: Wazuh detects brute-force attempts after multiple failed authentication attempts**

### Integrating Wazuh with other security tools

To build effective Blue Team playbooks, organizations need tools that not only detect threats but also work seamlessly within a broader security ecosystem. Wazuh supports this by integrating with a range of external tools across the incident response lifecycle:

* **SOAR platforms** such as TheHive and Shuffle help automate case management and streamline the execution of incident response playbooks.
* **Threat intelligence feeds**, including VirusTotal, AlienVault OTX, and AbuseIPDB, enrich alert data with external context, enabling faster and more informed triage.
* **Ticketing systems** like Jira integrate with Wazuh to facilitate efficient incident tracking, assignment, and team communication.
* **Cloud platforms** such as AWS, Azure, and GCP can be monitored by Wazuh to detect configuration issues, anomalous activity, and potential security breaches in cloud workloads.

## Conclusion

Each of these playbooks highlights the adaptability of Wazuh to support Blue Team operations. Whether responding to a credential-harvesting attack or detecting a persistent foothold through a web shell, Wazuh gives defenders the tools to act quickly, backed by a database of community-driven threat detection rules and open source integrations.

Learn more about Wazuh by checking out their [documentation](https://documentation.wazuh.com/current/index.html?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) and joining their [community](https://wazuh.com/community/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer) of professionals for support.

_Sponsored and written by [Wazuh](https://wazuh.com/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=referral&utm%5Fcampaign=wazuh%5Fbleepingcomputer)._