# Docker Hub still hosts dozens of Linux images with the XZ backdoor

![Docker](https://www.bleepstatic.com/content/hl-images/2022/04/21/Docker__headpic.jpg)

The XZ-Utils backdoor, first discovered in March 2024, is still present in at least 35 Linux images on Docker Hub, potentially putting users, organizations, and their data at risk.

Docker Hub is the official public container image registry operated by Docker, allowing developers and organizations to upload or download prebuilt images and share them with the community.

Many CI/CD pipelines, developers, and production systems pull images directly from Docker Hub as base layers for their own containers, and if those images are compromised, the new build inherits the flaw or malicious code.

Binarly researchers have discovered numerous Docker images still impacted by the XZ-Utils backdoor.

"At first glance, this might not seem alarming: if the distribution packages were backdoored, then any Docker images based on them would be infected as well," reports Binarly.

"However, what we discovered is that some of these compromised images are still publicly available on Docker Hub. And even more troubling, other images have been built on top of these infected base images, making them transitively infected."

Binarly reported the images to Debian, one of the maintainers still offering backdoored images, who decided not to take them offline, citing low risk and importance of archiving continuity.

The XZ-Utils backdoor, tracked under CVE-2024-3094, was malicious code [hidden in the liblzma.so library](https://www.bleepingcomputer.com/news/security/red-hat-warns-of-backdoor-in-xz-tools-used-by-most-linux-distros/) of the xz-utils compression tool, versions 5.6.0 and 5.6.1.

It hooked the RSA_public_decrypt function in OpenSSH via glibc's IFUNC mechanism, so if an attacker with a special private key connected over SSH to an affected system, they could bypass authentication and remotely run commands as root.

The backdoor was stealthily injected by a long-time project contributor named "Jia Tan," and shipped in official Linux distro packages like Debian, Fedora, OpenSUSE, and Red Hat, making it one of the most severe software supply chain compromises last year.

The backdoor was discovered early on, giving attackers very little opportunity to leverage it, and scanners were released by [Binarly](https://www.bleepingcomputer.com/news/security/new-xz-backdoor-scanner-detects-implant-in-any-linux-binary/) and [Kaspersky](https://www.bleepingcomputer.com/news/software/kaspersky-releases-free-tool-that-scans-linux-for-known-threats/), among others, to help detect it on dependent open-source software.

## Debian's response

To the researchers' surprise, Debian did not bother to retract 64-bit images using the backdoored version of the library from Docker Hub, finding at least 35 of them that are still available for download.

Binarly comments that this figure is only a partial reflection of the real scale of the problem, as they did not perform a platform-wide scan for the XZ-Utils backdoor.

"We identified more than 35 images that ship with the backdoor," [explains Binarly in its report](https://www.binarly.io/blog/persistent-risk-xz-utils-backdoor-still-lurking-in-docker-images).

"While this may seem like a small number, we only scanned a small portion of the images published on DockerHub, stopping at second-order images."

Debian says they [intentionally opted not to remove these images](https://github.com/debuerreotype/docker-debian-artifacts/issues/246) from Docker Hub and to leave them as historical artifacts, telling users to only use up-to-date images and not old ones.

The maintainers made this decision as they believe the requirements for exploitation are unlikely, such as requiring sshd installed and running on the container, the attacker having network access to the SSH service on that container, and using a private key that matches the backdoor's trigger logic.

![Debian maintainer's response](https://www.bleepstatic.com/images/news/u/1220909/2025/August/report.jpg)

**Debian maintainer's response**  
_Source: Binarly_

Binarly expresses disagreement with this approach, underlining that merely making these images accessible to the public poses a significant risk from accidental pulls or use in automated builds.

The same applies to all images that may contain a compromised version of the XZ-Utils backdoor, so users should manually check and ensure the library is on version 5.6.2 or later ([the latest stable is 5.8.1](https://github.com/tukaani-project/xz/releases)).