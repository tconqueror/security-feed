# Critical Docker Desktop flaw lets attackers hijack Windows hosts

![Critical Docker Desktop flaw lets attackers hijack Windows hosts](https://www.bleepstatic.com/content/hl-images/2022/04/21/Docker__headpic.jpg)

A critical vulnerability in Docker Desktop for Windows and macOS allows compromising the host by running a malicious container, even if the Enhanced Container Isolation (ECI) protection is active.

The security issue is a server-side request forgery (SSRF) now identified as [CVE-2025-9074](https://nvd.nist.gov/vuln/detail/CVE-2025-9074), and it received a critical severity rating of 9.3.

“A malicious container running on Docker Desktop could access the Docker Engine and launch additional containers without requiring the Docker socket to be mounted,” [reads Docker’s bulletin](https://docs.docker.com/desktop/release-notes/#4443).

“This could allow unauthorized access to user files on the host system. Enhanced Container Isolation (ECI) does not mitigate this vulnerability.”

Security researcher and bug bounty hunter [Felix Boulet](https://www.linkedin.com/in/felix-boulet/) found that the Docker Engine API could be reached without authentication at ‘http://192.168.65.7:2375/’ from inside any running container.

The [researcher demonstrated](http://blog.qwertysecurity.com/Articles/blog3) the creation and start-up of a new container that binds the Windows host’s C: drive to the container’s filesystem by using two wget HTTP POST requests.

Boulet’s proof-of-concept (PoC) exploit does not require code execution rights inside the container.

[Philippe Dugre](https://www.linkedin.com/in/zer0x64/), a DevSecOps engineer at technology company Pvotal Technologies and a challenge designer for the NorthSec cybersecurity conference, confirmed that the vulnerability affected Docker Desktop Windows and macOS but not the Linux version.

Dugre says that the vulnerability is less dangerous on macOS due to safeguards in the operating system. While he was able to create a file in the user's home directory on Windows, the same could not be achieved on macOS without the user providing permission.

"On Windows, since the Docker Engine runs via WSL2, the attacker can mount as an administrator the entire filesystem, read any sensitive file, and ultimately overwrite a system DLL to escalate the attacker to administrator of the host system," - [Phillippe Dugre](https://pvotal.tech/breaking-dockers-isolation-using-docker-cve-2025-9074/)

"On MacOS, however, the Docker Desktop application still has a layer of isolation and trying to mount a user directory prompts the user for permission. By default, the docker application does not have access to the rest of the filesystem and does not run with administrative privileges, so the host is a lot safer than in the Windows case," he says.

Nevertheless, the researcher warns that there is room for malicious activity even on macOS because an attacker has complete control over the application and the containers, which creates the risk of backdooring or modifying the configuration without the need for permission.

Dugre says that the vulnerability is easy to leverage, and his exploit confirms this as it consists of just three lines of Python code.

The vulnerability was reported responsibly to Docker, who responded quickly and addressed it in a new Docker Desktop version, 4.44.3, released last week.