# Dangerous runC flaws could allow hackers to escape Docker containers

![Dangerous runC flaws could allow hackers to escape Docker containers](https://www.bleepstatic.com/content/hl-images/2024/08/28/hacker.jpg)

Three newly disclosed vulnerabilities in the runC container runtime used in Docker and Kubernetes could be exploited to bypass isolation restrictions and get access to the host system.

The security issues, tracked as CVE-2025-31133, CVE-2025-52565, and CVE-2025-52881 (all ), were reported this week and disclosed by SUSE software engineer and Open Container Initiative (OCI) board member [Aleksa Sarai](https://seclists.org/oss-sec/2025/q4/138).

runC is a [universal container runtime](https://www.docker.com/blog/runc/) and the OCI reference implementation for running containers. It is responsible for low-level operations such as creating the container process, setting up namespaces, mounts, and cgroups that higher-level tools, like Docker and Kubernetes, can call.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

An attacker exploiting the vulnerabilities could obtain write access to the underlying container host with root privileges:

* [**CVE-2025-31133**](https://github.com/opencontainers/runc/security/advisories/GHSA-9493-h29p-rfm2) — runC uses /dev/null bind-mounts to “mask” sensitive host files. If an attacker replaces /dev/null with a symlink during container init, runc can end up bind-mounting an attacker-controlled target read-write into the container — enabling writes to /proc, and container escape.
* [**CVE-2025-52565**](https://github.com/opencontainers/runc/security/advisories/GHSA-qw9x-cqr3-wc7r) — The /dev/console bind mount can be redirected via races/symlinks so that runc mounts an unexpected target into the container before protections are applied. That again can expose writable access to critical procfs entries and enable breakouts.
* [**CVE-2025-52881**](https://github.com/opencontainers/runc/security/advisories/GHSA-cgrx-mc8f-2prm) — runC can be tricked into performing writes to /proc that are redirected to attacker-controlled targets. It can bypass LSM relabel protections in some variants and turns ordinary runc writes into arbitrary writes to dangerous files like /proc/sysrq-trigger.

CVE-2025-31133 and CVE-2025-52881 affect all versions of runC, while CVE-2025-52565 impacts runC versions 1.0.0-rc3 and later. Fixes are available in runC versions [1.2.8](https://github.com/opencontainers/runc/releases/tag/v1.2.8), [1.3.3](https://github.com/opencontainers/runc/releases/tag/v1.3.3), [1.4.0-rc.3](https://github.com/opencontainers/runc/releases/tag/v1.4.0-rc.3), and later.

## Exploitability and risk

Researchers at cloud security company Sysdig [note](http://www.sysdig.com/blog/runc-container-escape-vulnerabilities) that exploiting the three vulnerabilities "require the ability to start containers with custom mount configurations," which an attacker can achieve through malicious container images or Dockerfiles.

Currently, there have been no reports of any of the flaws being actively exploited in the wild.

In an advisory this week, Sysdig shares that attempts to exploit any of the three security issues can be detected by monitoring suspicious symlink behaviors.

RunC developers also shared mitigation actions, which include activating user namespaces for all containers without mapping the host root user into the container's namespace.

This precaution should block the most important parts of the attack because of the Unix DAC permissions that would prevent namespaced users from accessing relevant files.

Sysdig also recommends using rootless containers, if possible, to reduce the potential damage from exploiting a vulnerability.