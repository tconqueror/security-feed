# Ruckus Networks leaves severe flaws unpatched in management devices

![Ruckus Networks leaves severe flaws unpatched in management devices](https://www.bleepstatic.com/content/hl-images/2023/05/09/ruckus.jpg)

Multiple vulnerabilities that remain unpatched in Ruckus Wireless management products could be exploited to fully compromise the network environment they serve.

The issues affect Ruckus Wireless Virtual SmartZone (vSZ) and Ruckus Network Director (RND), and range from unauthenticated remote code execution to hardcoded passwords or SSH public and private keys.

Ruckus vSZ is a centralized wireless network controller that can manage tens of thousands of Ruckus access points and clients, allowing configuration, monitoring, and controlling large-scale WiFi deployments. Ruckus RND is a management tool for vSZ clusters.

The two products are typically used by large organizations and public entities in need of scalable and robust WiFi infrastructure.

The vulnerabilities were reported to Carnegie Mellon University’s CERT Coordination Center (CERT/CC) by Noam Moshe, a member of Team82, Claroty's research division.

Neither CERT/CC nor Moshe were able to contact Ruckus Wireless (now Ruckus Networks) or its parent company, CommScope, about the security problems, which remain unfixed at the time of publishing.

The problems impacting the two Ruckus Networks products received identifiers and are described as follows:

* **CVE-2025-44957** – hardcoded secrets in vSZ that allow bypassing authentication and admin-level access using crafted HTTP headers and valid API keys
* **CVE-2025-44962** – path traversal in vSZ that allows arbitrary file reads for authenticated users
* **CVE-2025-44954** – vSZ has hardcoded default public/private SSH keys that allows anyone to connect to vulnerable devices with root access
* **CVE-2025-44960** – vSZ has an API route with a user-controlled parameter that isn't sanitized, allowing execution of arbitrary operating system commands
* **CVE-2025-44961** – command injection in vSZ allows an authenticated user to supply an unsanitized IP address to an OS command
* **CVE-2025-44963** – RND uses a hardcoded backend JWT secret key, allowing anyone with it to forge valid admin session tokens
* **CVE-2025-44955** – RND includes a "jailed" environment with a built-in jailbreak using a weak, hardcoded password to gain root access
* **CVE-2025-6243** – RND includes a root-privileged user (sshuser) with hardcoded public/private SSH keys that allow root access
* **CVE-2025-44958** – RND encrypts stored passwords with a hardcoded weak secret key and can return them in plaintext if compromised

Although severity scores have not been calculated, CERT/CC highlights the broad impact of the vulnerabilities, their potential for exploitation, and the possibility to chain them for a more impactful attack.

"\[The\] impact of these vulnerabilities varies from information leakage to total compromise of the wireless environment managed by the affected products," [reads the bulletin](https://kb.cert.org/vuls/id/613753).

"As an example, an attacker with network access to Ruckus Wireless vSZ can exploit CVE-2025-44954 to gain full administrator access that will lead to total compromise of the vSZ wireless management environment."

"Furthermore, multiple vulnerabilities can be chained to create chained attacks that can allow the attacker to combine attacks to bypass any security controls that prevent only specific attacks."

With no patches available and no clear information on when they might be released, administrators with Ruckus vSZ and RND on their network are recommended to limit access to Ruckus management interfaces to isolated, trusted networks and enforce access over secure protocols only.

BleepingComputer attempted to contact Ruckus via multiple communication channels, but we were unable to reach out.