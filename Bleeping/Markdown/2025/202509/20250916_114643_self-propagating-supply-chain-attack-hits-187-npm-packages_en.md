# Self-propagating supply chain attack hits 187 npm packages

![npm](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM.jpg)

Security researchers have identified at least 187 npm packages compromised in an ongoing supply chain attack, with a malicious self-propagating payload to infect other packages.

The coordinated worm-style campaign dubbed 'Shai-Hulud' started yesterday with the compromise of the _@ctrl/tinycolor_ npm package, which receives over 2 million weekly downloads.

Since then, the campaign has expanded significantly and now includes packages published under CrowdStrike's npm namespace.

## From _tinycolor_ to CrowdStrike

Yesterday, Daniel Pereira, a senior backend software engineer, [alerted](https://www.linkedin.com/posts/daniel-pereira-b17a27160%5Fnpm-profile-activity-7373489836437114880-D9ma?utm%5Fsource=share&utm%5Fmedium=member%5Fdesktop&rcm=ACoAAArUYTQBMx2P2SMFdIx-wUs7H1hfLGpuhVM) the community to a large-scale software supply chain attack affecting the world's largest JavaScript registry, npmjs.com.

"There is a \[sic\] malware spreading live in npm as you read this," wrote the engineer, cautioning everyone to refrain from installing the latest versions of the _[@ctrl/tinycolor](https://www.npmjs.com/package/@ctrl/tinycolor)_ project.

![Pereira's LinkedIn post alerting everyone to ongoing npm supply chain attack](https://www.bleepstatic.com/images/news/u/1164866/2025/Sep/npm-supply-chain-attack-crowdstrike/dan-p-post.jpg)

**Pereira alerting everyone to ongoing npm supply chain attack**

Pereira had been [trying to](http://linkedin.com/feed/update/urn:li:activity:7373418115398995968/) get GitHub's attention in the last 24 hours through more discreet channels to discuss the ongoing attack as "a lot of repos were targeted," and disclosing the attack publicly could put people at risk.

"But contacting GitHub is too hard. For instance, secrets are being exposed in repos. This is serious," wrote the engineer.

Software supply chain security firm Socket [began investigating the compromise](https://socket.dev/blog/tinycolor-supply-chain-attack-affects-40-packages) and identified at least 40 packages that were compromised in this campaign. Today, both Socket and Aikido researchers have [identified additional packages](http://www.aikido.dev/blog/s1ngularity-nx-attackers-strike-again#:~:text=publishing%20rights.-,Impacted%20packages,-Package), bringing the count up to at least 187\. 

StepSecurity [also published](https://www.stepsecurity.io/blog/ctrl-tinycolor-and-40-npm-packages-compromised) a technical breakdown with deobfuscated snippets and attack-flow diagrams, largely confirming Socket's initial findings.

Affected packages include several ones published by CrowdStrike's npmjs account _[crowdstrike-publisher](https://www.npmjs.com/~crowdstrike-publisher)_.

BleepingComputer reached out to the cybersecurity solutions provider for comment:

"After detecting several malicious Node Package Manager (NPM) packages in the public NPM registry, a third-party open source repository, we swiftly removed them and proactively rotated our keys in public registries," a CrowdStrike spokesperson shared with BleepingComputer.  
  
"These packages are not used in the Falcon sensor, the platform is not impacted and customers remain protected. We are working with NPM and conducting a thorough investigation."

## Self-propagating worm uses TruffleHog to steal secrets

The compromised versions include a self-propagating mechanism that targets other packages by the same maintainer.

The malware downloads each package by a maintainer, modifies its _package.json_, injects a _bundle.js_ script (shown below), repacks the archive, and republishes it, thereby "enabling automatic trojanization of downstream packages," as Socket researchers explained.

![bundle.js file uses TruffleHog to exfiltrate secrets ](https://www.bleepstatic.com/images/news/u/1164866/2025/Sep/npm-supply-chain-attack-crowdstrike/socket-bundle_js-file.jpg)

**bundle.js file downloads TruffleHog to exfiltrate secrets** (Socket)

The _bundle.js_ script makes use of TruffleHog, a legitimate secret scanner that can be used by developers and security professionals to find accidentally leaked sensitive information like API keys, passwords, and tokens within code repositories and other data sources.

The malicious script, however, abuses the tool to search the host for tokens and cloud credentials.

"It validates and uses developer and CI credentials, creates a GitHub Actions workflow inside repositories, and exfiltrates results to a hardcoded webhook (hxxps://webhook\[.\]site/bb8ca5f6-4175-45d2-b042-fc9ebb8170b7)," explains Socket.

The name 'Shai-Hulud' comes from the _shai-hulud.yaml_ workflowfiles used by malware found in the compromised versions, and is a reference to the giant sandworms in Frank Herbert's [_Dune_](https://en.wikipedia.org/wiki/Sandworm%5F%28Dune%29) series.

"While not a unique reference, its presence reinforces that the attacker deliberately branded the campaign 'Shai-Hulud,'" [stated](https://socket.dev/blog/ongoing-supply-chain-attack-targets-crowdstrike-npm-packages) Socket researchers Kush Pandya and Peter van der Zee today.

The malware found in additional packages identified today is identical to the previous strand that used _bundle.js_ to:

* Download and execute the legitimate secret scanning tool, TruffleHog
* Search the host for secrets like tokens and cloud credentials
* Check if the discovered developer and CI credentials are valid
* Create unauthorized GitHub Actions workflows within repositories
* Exfiltrate sensitive data to a hardcoded webhook endpoint

## Incident follows ongoing large-scale attacks like nx 's1ngularity'

What makes this supply-chain attack stand out, beyond the popular packages it hit, is its timing.

The attack follows two high-profile supply chain attacks occurring in the same month.

The first week of September, AI-powered malware [hit 2,180 GitHub accounts](https://www.bleepingcomputer.com/news/security/ai-powered-malware-hit-2-180-github-accounts-in-s1ngularity-attack/) in what was dubbed the 's1ngularity' attack.

While the root cause of today's attack is still being investigated, practitioners, including Pereira, hypothesize that today's attack may have been orchestrated by the attackers behind 's1ngularity'.

Earlier this month, maintainers of the popular [chalk and debug npm packages](https://www.bleepingcomputer.com/news/security/hackers-hijack-npm-packages-with-2-billion-weekly-downloads-in-supply-chain-attack/) also fell victim to phishing, in a separate attack, leading to their projects being compromised. 

The ripple effects of these attacks extend deep into the dependency chain, potentially impacting widely used projects such as Google Gemini CLI, which [released a statement](https://github.com/google-gemini/gemini-cli/discussions/8385) over the weekend:

"We want to be clear: The Gemini CLI source code itself was not compromised, and our servers remain secure," wrote Ryan J. Salva, Google's Senior Director of Product Management.

"However, this incident may have affected users who installed or updated the Gemini CLI during the attack window using the NPM installation method. We are providing details on the incident, clarifying who is impacted, and outlining the steps users should take to ensure their systems are secure."

These ongoing attacks demonstrate the fragility of the modern software supply chain, where a single malicious pull request or compromised maintainer account can ripple out to hundreds of projects.

While vendors like Google and CrowdStrike stress their core platforms remain secure, the incident underscores the urgent need for developers to safeguard their software builds and pipelines.

Affected users should audit their environments and logs for signs of compromise, rotate all secrets and CI/CD tokens, and review dependency trees for malicious versions. Pinning dependencies to trusted releases and limiting the scope of publishing credentials remain critical steps to reduce exposure to package-level compromises.