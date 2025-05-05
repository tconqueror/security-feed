# Microsoft finds default Kubernetes Helm charts can expose data

![Kubernetes](https://www.bleepstatic.com/content/hl-images/2024/04/17/Kubernetes.jpg)

Microsoft warns about the security risks posed by default configurations in Kubernetes deployments, particularly those using out-of-the-box Helm charts, which could publicly expose sensitive data.

In many cases, those Helm charts required no authentication, left exploitable ports open, and used weak or hardcoded passwords that were trivial to break.

A report published by security researchers Michael Katchinskiy and Yossi Weizman of Microsoft Defender for Cloud Research highlights three cases as examples of a broader security issue that puts Kubernetes workloads at risk.

## Ease vs security

Kubernetes is a widely used open-source platform designed to automate the deployment, scaling, and management of containerized applications.

Helm is a package manager for Kubernetes, and charts are templates/blueprints for deploying apps on the platform, providing YAML files that define key resources needed to run an app.

Helm charts are popular because they simplify and speed up complex deployments. However, as highlighted in Microsoft's report, in many cases, the default settings in those charts lack proper security measures.

Users inexperienced with cloud security often deploy those Helm charts as they are, unintentionally exposing services to the internet and allowing attackers to scan and exploit misconfigured applications.

![Apache Pinot Helm chart instructions](https://www.bleepstatic.com/images/news/u/1220909/2025/May/image.jpg)

**Apache Pinot Helm chart instructions**  
_Source: Microsoft_

"Default configurations that lack proper security controls create a severe security threat," [warns the Microsoft researchers](https://techcommunity.microsoft.com/blog/microsoftdefendercloudblog/the-risk-of-default-configuration-how-out-of-the-box-helm-charts-can-breach-your/4409560).

"Without carefully reviewing the YAML manifests and Helm charts, organizations may unknowingly deploy services lacking any form of protection, leaving them fully exposed to attackers."

"This is particularly concerning when the deployed application can query sensitive APIs or allow administrative actions, which is exactly what we will shortly see."

The researchers highlight three cases of Helm charts that put Kubernetes environments at risk of attacks, summarized as follows.

* **Apache Pinot**: Exposes core services (pinot-controller and pinot-broker) via Kubernetes LoadBalancer services without any authentication.
* **Meshery**: Public sign-up is allowed from exposed IP, allowing anyone to register and gain access to cluster operations.
* **Selenium Grid**: A NodePort exposes the service across all nodes in a cluster, relying only on external firewall rules for protection. The issue doesn't impact the official Helm chart, but many widely referenced GitHub projects.

Concerning Selenium Grid, Wiz and other cybersecurity firms have [previously observed](https://www.bleepingcomputer.com/news/security/misconfigured-selenium-grid-servers-abused-for-monero-mining/) attacks targeting misconfigured instances to deploy XMRig miners to mine Monero cryptocurrency.

To mitigate the risks, Microsoft recommends carefully reviewing the default configuration of Helm charts to evaluate it from a security perspective, ensuring that it includes authentication and network isolation.

Additionally, it is recommended to perform regular scans for misconfigurations that expose workload interfaces publicly and closely monitor containers for suspicious activity.