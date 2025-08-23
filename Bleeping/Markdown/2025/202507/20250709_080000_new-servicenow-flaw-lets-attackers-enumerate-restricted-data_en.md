# New ServiceNow flaw lets attackers enumerate restricted data

![Data leak](https://www.bleepstatic.com/content/hl-images/2024/08/16/data-leak.jpg)

A new vulnerability in ServiceNow, dubbed Count(er) Strike, allows low-privileged users to extract sensitive data from tables to which they should not have access.

ServiceNow is a cloud-based platform that enables organizations to manage digital workflows for their enterprise operations. It is widely adopted across various industries, including public sector organizations, healthcare, financial institutions, and large enterprises.

The flaw was discovered by Varonis Threat Labs in February 2025 and assigned the CVE-2025-3648 identifier, and may impact configurations with misconfigured or overly permissive ACLs.

ServiceNow [released additional access control frameworks](https://support.servicenow.com/kb?id=kb%5Farticle%5Fview&sysparm%5Farticle=KB2139567) in the Xanadu and Yokohama versions, released last month, to address the issue. However, all admins should review existing tables to ensure their data is properly locked down.

## The Count(er) Strike flaw

ServiceNow utilizes Access Control Lists (ACLs) to restrict access to data within its tables. Each ACL evaluates four conditions when determining if a user should have access to a specific resource:

* Required roles
* Security attributes
* Data conditions
* Script conditions

For a user to gain access to a resource, all of these conditions must be satisfied.

However, if a resource is protected with multiple ACLs, ServiceNow previously used an "Allow if" condition, meaning that if a user satisfied just one ACL, they could gain access, even if other ACLs would have blocked them.

In some cases, this granted full access. However, in others, it allowed partial access, such as record counts that could be exploited, as explained later in the article.

"Each resource or table in ServiceNow can have numerous ACLs, each defining different conditions for access," [explains the Varonis report.](https://www.varonis.com/blog/counter-strike-servicenow).

"However, if a user passes just one ACL, they gain access to the resource, even if other ACLs might not grant access. If there is no ACL present for the resource, access will default to the default access property which is set to deny in most cases."

This permissive model led Varonis to discover that it was possible to gain partial access, which could be used to enumerate protected data, even though the user may have failed more restrictive ACLs.

Varonis found that if a user fails the `data` condition or `script` condition, ServiceNow still returns the record count in the UI and source HTML. The page also states that some results were removed due to security constraints.

![Restricted data still showing record counts and fields](https://www.bleepstatic.com/images/news/security/vulnerabilities/s/servicenow/counterstrike/record-counts.png)

**Restricted data still showing record counts and fields**  
_Source: Varonis_

With this partial data, Varonis began manipulating URL-based filters, such as `STARTSWITH`, `CONTAINS`, `=`, and `!=` to enumerate the contents of records one character or condition at a time.

For example:

```
https://[my_company].service-now.com/task_list.do?sysparm_query=short_descriptionSTARTSWITHp
```

Repeating this process with different values and queries allows for the retrieval of data one character or digit at a time.

To automate this procedure, Varonis created a script that successfully enumerated data records from a table to which they had limited access.

![Enumerating data using a script](https://www.bleepstatic.com/images/news/security/vulnerabilities/s/servicenow/counterstrike/enumerating-dta.png)

**Enumerating data using a script**  
_Source: Varonis_

Even when record data isn't displayed, the record count leaks enough information to determine fields, including credentials, PII, and internal configuration data.

Varonis warned that self-registered users could also use this attack. Self-registration is a feature that allows users to create accounts and access the instance with minimal privileges, which can still be used to launch an attack.

"Though it is rare for instances to allow anonymous registration and access, this configuration was found in the ServiceNow systems of several Fortune 500 companies," warned Varonis.

## Mitigating the attack

Varonis told BleepingComputer that they tested the attack against ServiceNow's ITSM product, but stated that it should also apply to all ServiceNow products that utilize the same ACL logic.

ServiceNow has now addressed the attack by:

* Introducing 'Deny Unless' ACLs, which require users to pass **all** ACLs to gain access to a dataset.
* Adding Query ACLs, which restrict these types of enumeration queries using range operators.
* Recommending the use of Security Data Filters, which hide row counts and suppress inference cues.

However, customers should still manually review their tables and modify ACLs to make sure they are not overly permissive, and thus vulnerable to this attack.

Varonis says that it has not seen any evidence that this vulnerability has been exploited in the wild.