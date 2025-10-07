# Docker makes Hardened Images Catalog affordable for small businesses

![Docker](https://www.bleepstatic.com/content/hl-images/2022/04/21/Docker_header.jpg)

The Docker team has announced unlimited access to its Hardened Images catalog to make access to secure software bundles affordable for all development teams at startups and SMBs.

Starting today, container images that have been verified to be free of known vulnerabilities (near-zero CVEs), are available to all users through a subscription and a 30-day free trial.

“We’re introducing unlimited access to the Docker Hardened Images catalog, making near-zero CVEs a practical reality for every team at an affordable price,” [reads the announcement](https://www.docker.com/blog/unlimited-access-to-docker-hardened-images-because-security-should-be-affordable-always/).

“With a single Hardened Images subscription, every team can access the full catalog: unlimited, secured, and always up to date.”

Docker is a widely used platform that allows developers to package applications and their dependencies into “containers,” allowing consistent and systematic deployment across different environments.

Container images are templates that include all the necessary code, runtime, libraries, and system tools for running an application.

### Reduced security risk

Hardened Images are [highly-secure versions](http://www.docker.com/products/dhi-enterprise-smb-startup/) of regular Docker images that eliminate the risk of known vulnerabilities as they are built from source code, benefit from continuous upstream patches, and lack unnecessary components.

Every hardened image also includes support for Vulnerability Exploitability eXchange (VEX), which puts the spotlight only on security issues that truly count.

Furthermore, Docker says that removing nonessential content, the attack surface decreases by up to 95%.

Docker partnered with independent cybersecurity auditors at SRLabs who validated that the Hardened Images are appropriately signed, rootless by default, include SBOM and VEX, and showed no root escapes or other high-severity breakout problems.

Hardened Images are also underpinned by a seven-day patch Service Level Agreement (SLA), meaning that when a new CVE affects a component used on the image, Docker must release a patched version within a week.

The Hardened Images catalog offers a broad range of images, including for artificial intelligence/machine learning, languages and runtimes (Python), databases (PostgreSQL), frameworks (NGINX), and infrastructure tools (Kafka).

The catalog also features FedRAMP-ready variants that meet stricter U.S. federal security standards.

All images from the Hardened Images catalog are compatible with Alpine and Debian Linux systems, can be easily integrated by changing a single Dockerfile line, and can be freely customized without losing the hardened baseline.

Docker Hub remains the default starting point for most container builds, but releasing the Hardened Images catalog to all users could mark the start of a significant elevation in the ecosystem’s security.