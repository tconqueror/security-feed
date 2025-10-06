# Zeroday Cloud hacking contest offers $4.5 million in bounties

![Zeroday Cloud hacking contest offers $4.5 million in bounties](https://www.bleepstatic.com/content/hl-images/2025/10/06/logo.jpg)

A new hacking competition called Zeroday Cloud, focused on open-source cloud and AI tools, announced a total prize pool of $4.5 million in bug bounties for researchers that submit exploits for various targets.

The contest is launched by the research arm of cloud security company Wiz in partnership with Google Cloud, AWS, and Microsoft, and is scheduled for December 10 and 11 at the Black Hat Europe conference in London, UK.

[Zeroday Cloud](http://www.zeroday.cloud/) has six separate categories researchers can participate in, with bug bounties between $10,000 and $300,000:

* **AI** – Ollama ($25k), Vllm ($25k), Nvidia Container Toolkit ($40k)
* **Kubernetes and Cloud-Native** – Kubernetes API Server ($80k), Kubelet Server ($40k), Grafana ($10k auth RCE, $40k pre-auth RCE), Prometheus ($40k), Fluent Bit ($10k)
* **Containers and Virtualization** – Docker ($40 user-provided image, $60k arbitrary image), Containerd ($40 user-provided image, $60k arbitrary image), Linux Kernel ($30k container escape on Ubuntu)
* **Web Servers** – nginx ($300k), Apache Tomcat ($100k), Envoy ($50k), Caddy ($50k)
* **Databases** – Redis ($25k auth RCE, $100k pre-auth RCE), PostgreSQL ($20k auth RCE, $100k pre-auth RCE), MariaDB ($20k auth RCE, $100k pre-auth RCE)
* **DevOps & Automation** – Apache Airflow ($40k), Jenkins ($40k), GitLab CE ($40k)

The rules of the competition say that submitted exploits should result in complete compromise of the target. Wiz explains that this means "a full Container/VM Escape for the Virtualization category, and a 0-click Remote Code Execution (RCE) vulnerability for other targets."

The organizers also provide the [conditions for each target](http://github.com/wiz-sec-public/zeroday-cloud-2025), as well as the instructions and technical resources (Docker container with target on default configuration) security researchers can use to test their exploits.

Researchers who register through the HackerOne platform and complete their ID verification and Tax Forms by November 20, are free to submit exploits for as many targets as they like, but they are limited to only one entry per target.

Submitters of approved exploits will be invited to demonstrate them live during the event, either alone or in a team of up to five members.

People residing in embargoed or sanctioned countries such as Russia, China, Iran, North Korea, Cuba, Sudan, Syria, Libya, Lebanon, and also the regions of Crimea and Donetsk, are restricted from participating in the Zeroday Cloud contest.

The complete rules for the zeroday.cloud hacking competition are [available here](https://www.zeroday.cloud/rules).

The announcement for the event, however, did not resonate well with the organizers of the Pwn2Own hacking competitions that have been going with great success for several years.

In a public post, Trend Micro [called out Wiz](https://www.linkedin.com/posts/trend-micro%5Fzeroday-cloud-cloud-security-hacking-competition-activity-7379280371676479488-q3bB?utm%5Fsource=share&utm%5Fmedium=member%5Fdesktop&rcm=ACoAAAq9GN8BFZwqjlHinmMEs4Drc4jOYzu2adM) for copying the rules for Pwn2Own Ireland. Juan Pablo Castro, Director of Cybersecurity Strategy & Technology at Trend Micro, said that Gemini's output when comparing the rules for the two events were a "word-for-word" copy.

Wiz responded with a [defusing statement](https://www.linkedin.com/feed/update/urn:li:activity:7378846266895790080?commentUrn=urn%3Ali%3Acomment%3A%28activity%3A7378846266895790080%2C7379330526891085824%29&replyUrn=urn%3Ali%3Acomment%3A%28activity%3A7378846266895790080%2C7379865041333841920%29&dashCommentUrn=urn%3Ali%3Afsd%5Fcomment%3A%287379330526891085824%2Curn%3Ali%3Aactivity%3A7378846266895790080%29&dashReplyUrn=urn%3Ali%3Afsd%5Fcomment%3A%287379865041333841920%2Curn%3Ali%3Aactivity%3A7378846266895790080%29), admitting that the Pwn2Own rulebook was "a trusted, mature framework by which we were inspired."