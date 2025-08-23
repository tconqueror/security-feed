# Supply chain attack hits Gluestack NPM packages with 960K weekly downloads

![NPM](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_logo_headpic.jpg)

A significant supply chain attack hit NPM after 16 popular Gluestack 'react-native-aria' packages with over 950,000 weekly downloads were compromised to include malicious code that acts as a remote access trojan (RAT).

BleepingComputer determined that the compromise began on June 6 at 4:33 PM EST, when a new version of the react-native-aria/focus package was published to NPM. Since then, 16 of the 20 Gluestack [react-native-aria packages](https://www.npmjs.com/org/react-native-aria) have been compromised on NPM, with the threat actors publishing a new version as recently as two hours ago.

![Ongoing compromise of NPM packages](https://www.bleepstatic.com/images/news/security/g/gluestack/npm-supply-chain-attack/gluestack-2-hours.jpg)

**Ongoing compromise of NPM packages**  
_Source: BleepingComputer_

The supply chain attack was discovered by cybersecurity firm [Aikido Security,](https://www.aikido.dev/) who discovered obfuscated code injected into the `lib/index.js` file for the following packages:

| **Package Name**               | **Version** | **Weekly Downloads** |
| ------------------------------ | ----------- | -------------------- |
| react-native-aria/button       | 0.2.11      | 51,000               |
| react-native-aria/checkbox     | 0.2.11      | 81,000               |
| react-native-aria/combobox     | 0.2.10      | 51,000               |
| react-native-aria/disclosure   | 0.2.9       | 3                    |
| react-native-aria/focus        | 0.2.10      | 100,000              |
| react-native-aria/interactions | 0.2.17      | 125,000              |
| react-native-aria/listbox      | 0.2.10      | 51,000               |
| react-native-aria/menu         | 0.2.16      | 22,000               |
| react-native-aria/overlays     | 0.3.16      | 96,000               |
| react-native-aria/radio        | 0.2.14      | 78,000               |
| react-native-aria/switch       | 0.2.5       | 477                  |
| react-native-aria/toggle       | 0.2.12      | 81,000               |
| react-native-aria/utils        | 0.2.13      | 120,000              |
| gluestack-ui/utils             | 0.1.17      | 55,000               |
| react-native-aria/separator    | 0.2.7       | 65                   |
| react-native-aria/slider       | 0.2.13      | 51,000               |

These packages are very popular, with approximately 960,000 weekly downloads, making this a supply chain attack that could have widespread consequences.

The malicious code is heavily obfuscated and is appended to the last line of source code in the file, padded with many spaces, so it's not easily spotted when using the code viewer on the NPM site.

![Malicious code added to end of index.js file](https://www.bleepstatic.com/images/news/security/g/gluestack/npm-supply-chain-attack/gluestack-compromise.jpg)

**Malicious code added to end of index.js file**  
_Source: BleepingComputer_

Aikido told BleepingComputer that the malicious code is nearly identical to a remote access trojan in [another NPM compromise they discovered](https://www.aikido.dev/blog/catching-a-rat-remote-access-trojian-rand-user-agent-supply-chain-compromise) last month.

The researcher's analysis of the previous campaign explains that the remote access trojan will connect to the attackers' command and control server and receive commands to execute.

These commands include:

* **cd -** Change current working directory
* **ss\_dir -** Reset directory to script’s path
* **ss\_fcd:<path>** \- Force change directory to <path>
* **ss\_upf:f,d -** Upload single file f to destination d
* **ss\_upd:d,dest -** Upload all files under directory d to destination dest
* **ss\_stop -** Sets a stop flag to interrupt current upload process
* **Any other input -** Treated as a shell command, executed via child\_process.exec()

The trojan also performs Windows PATH hijacking by prepending a fake Python path (%LOCALAPPDATA%\\Programs\\Python\\Python3127) to the PATH environment variable, allowing the malware to silently override legitimate python or pip commands to execute malicious binaries.

Aikido sercurity researcher Charlie Eriksen has attempted to contact Gluestack about the compromise by creating [GitHub issues](https://github.com/gluestack/gluestack-ui/issues/2894) on each of the project's repositories, but there has not been any response at this time.

"No response from package maintainers (it's morning on a saturday in the US which is prob exactly why its happening now)," Arkido told BleepingComputer.

"NPM we have contacted and reported each package, this is a process that usually takes multiple days for NPM to address though."

Aikido also attributes this attack to the same threat actors who compromised four other NPM packages earlier this week named _biatec-avm-gas-station_, _cputil-node_, _lfwfinance/sdk_, and _lfwfinance/sdk-dev_.

BleepingComputer reached out to Gluestack about the compromised packages but has not received a reply at this time.