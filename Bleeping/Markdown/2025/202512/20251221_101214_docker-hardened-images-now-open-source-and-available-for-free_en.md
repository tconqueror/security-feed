# Docker Hardened Images now open source and available for free

![Docker](https://www.bleepstatic.com/content/hl-images/2022/04/21/Docker_header.jpg)

More than a 1,000 Docker Hardened Images (DHI) are now freely available and open source for software builders, under the Apache 2.0 license.

Docker is a popular platform that enables developers to build, test, and deploy applications quickly inside container images that include the required dependencies, allowing for predictable and repeatable results across various systems and environments.

DHIs, launched in May this year, are secure, minimal, production-ready Docker base images maintained directly by Docker. They are designed to reduce the attack surface and supply-chain risks at the container layer.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

DHIs are rootless, stripped of unnecessary components, free of known vulnerabilities, and support the Vulnerability Exploitability eXchange (VEX) standard for leaner security management.

They are also guaranteed to push fixes for new flaws in existing DHI components within 7 days of their disclosure.

In October, the Docker team announced that it would [open unlimited access](https://www.bleepingcomputer.com/news/security/docker-makes-hardened-images-catalog-affordable-for-small-businesses/) to its entire DHI catalog of 1,000 images to all developer teams and also offer a 30-day free trial to all subscribers.

However, Docker decided to move DHIs from being a commercial offering to making them available subscription-free for all developers.

“Today, we are establishing a new industry standard by making DHI freely available and open source to everyone who builds software. All 26 Million+ developers in the container ecosystem,” [reads the announcement](https://www.docker.com/blog/docker-hardened-images-for-every-developer/).

“DHI is fully open and free to use, share, and build on with no licensing surprises, backed by an Apache 2.0 license. DHI now gives the world a secure, minimal, production-ready foundation from the very first pull,” the company said.

Docker has highlighted that the move does not come with security discounts for DHI, as the images remain SBOM-verifiable, the builds provide SLSA Build Level 3 provenance, and every image is accompanied by proof of authenticity.

However, the 7-day critical CVE patching commitment (SLA) is still exclusive to the commercial tier, DHI Enterprise, which is still available. Patches will still be provided to the free tier, but not within a pre-defined time period.

Regarding DHI Enterprise and the time to fix flaws, Docker states it aims to reduce it to a single day or even less. The commercial tier also allows modifying DHI images, configuring runtimes, and installing additional tools.

Docker users can access the full DHI catalog and subscription options [from here](https://www.docker.com/products/hardened-images/).