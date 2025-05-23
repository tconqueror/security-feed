# Dozens of malicious packages on NPM collect host and network data

![Dozens of malicious packages on NPM collect host and network data](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_head_pic.jpg)

60 packages have been discovered in the NPM index that attempt to collect sensitive host and network data and send it to a Discord webhook controlled by the threat actor.

According to [Socket’s Threat Research team](https://socket.dev/blog/60-malicious-npm-packages-leak-network-and-host-data), the packages were uploaded to the NPM repository starting May 12 from three publisher accounts.

Each of the malicious packages contains a post-install script that automatically executes during ‘npm install’ and collects the following information:

* Hostname
* Internal IP address
* User home directory
* Current working directory
* Username
* System DNS servers

The script checks for hostnames related to cloud providers, reverse DNS strings, in an attempt to determine if it is running in an analysis environment.

Socket did not observe the delivery of second-stage payloads, privilege escalation, or any persistent mechanisms. However, given the type of data collected, the danger of targeted network attacks is significant.

## Packages still available on NPM

The researchers reported the malicious packages but at the time of writing they were still available on NPM and showed a cumulative download count of 3,000. By publishing time, though, none of them were present in the repository.

To trick developers into using them, the threat actor behind the campaign used names similar to legitimate packages in the index, like ‘flipper-plugins,’ ‘react-xterm2,’ and ‘hermes-inspector-msggen,’ generic trust-evoking names, and others that hint at testing, possibly targeting CI/CD pipelines.

The complete list of the 60 malicious packages is available at the bottom section of Socket’s report.

If you have installed any of them, it is recommended to remove them immediately and perform a full system scan to eradicate any infection remnants.

## Data wipers on NPM

Another malicious campaign that [Socket uncovered](https://socket.dev/blog/malicious-npm-packages-target-react-vue-and-vite-ecosystems-with-destructive-payloads) yesterday on NPM involved eight malicious packages that mimic legitimate tools through typosquatting but can delete files, corrupt data, and shut down systems.

The packages, which targeted the React, Vue.js, Vite, Node.js, and Quill ecosystems, existed on NPM for the past two years, getting 6,200 downloads.

Evading this long was partly due to the payloads being activated based on hardcoded system dates and were structured to progressively destroy framework files, corrupt core JavaScript methods, and sabotage browser storage mechanisms.

![Script designed to delete Vue.js-related files on June 19–30, 2023](https://www.bleepstatic.com/images/news/u/1220909/2025/May/code(1).jpg)

**Script designed to delete Vue.js-related files on June 19–30, 2023**  
_Source: Socket_

The threat actor behind this campaign, who published them under the name ‘xuxingfeng’, has also listed several legitimate packages to build trust and evade detection.

Although the danger has passed now based on the hardcoded dates, removing the packages is crucially important as their author could introduce updates that will re-trigger their wiping functions in the future.