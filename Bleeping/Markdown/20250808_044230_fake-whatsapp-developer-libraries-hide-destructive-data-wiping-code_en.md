# Fake WhatsApp developer libraries hide destructive data-wiping code

![WhatsApp](https://www.bleepstatic.com/content/hl-images/2022/05/31/whatsapp-red-noglow.jpg)

Two malicious NPM packages posing as WhatsApp development tools have been discovered deploying destructive data-wiping code that recursively deletes files on a developer's computers.

Two malicious NPM packages currently available in the registry target WhatsApp developers with destructive data-wiping code.

The packages, [discovered by researchers at Socket](https://socket.dev/blog/malicious-npm-packages-target-whatsapp-developers-with-remote-kill-switch), masquerade as WhatsApp socket libraries and were downloaded over 1,100 times since their publication last month.

Despite Socket having filed takedown requests and flagging the publisher, nayflore, both remain available at the time of writing.

The names of the two malicious packages are [naya-flore](https://www.npmjs.com/package/naya-flore) and [nvlore-hsc](https://www.npmjs.com/package/nvlore-hsc), though the same publisher has submitted more on NPM, like nouku-search, very-nay, naya-clone, node-smsk, and @veryflore/disc.

Although these additional five packages are not currently malicious, extreme caution is advised, as an update pushed at any time could inject dangerous code.

All these packages mimic legitimate WhatsApp developer libraries used for building bots and automation tools around the WhatsApp Business API.

Socket notes that these libraries have recently experienced a significant surge in demand, as more businesses utilize WhatsApp's Cloud API for customer communication.

## Wiper code

Both naya-flore and nvlore-hs contain a function called 'requestPairingCode,' that is supposed to handle WhatsApp pairing, but which retrieves a base64 JSON file from a GitHub address.

The JSON file contains a list of Indonesian phone numbers that act as a kill switch, excluding owners of these numbers from the malicious functionality.

For the rest (valid targets), the code executes the 'rm -rf \*' command, which deletes all files recursively in the current directory, effectively wiping code from the developer's system.

![The data wiping code](https://www.bleepstatic.com/images/news/u/1220909/2025/August/wiper.jpg)

**The data wiping code**  
_Source: Socket_

Socket also discovered a dormant data exfiltration function ('generateCreeds'), which could exfiltrate the victim's phone number, device ID, status, and hardcoded key. This function is present but commented out in both packages, so it's disabled.

![The currently disabled data exfiltration function](https://www.bleepstatic.com/images/news/u/1220909/2025/August/data-exfil.jpg)

**The currently disabled data exfiltration function**  
_Source: Socket_

## Go ecosystem hit too

In parallel news, Socket also [discovered 11 malicious Go packages](https://socket.dev/blog/11-malicious-go-packages-distribute-obfuscated-remote-payloads) that use string-array obfuscation to silently execute remote payloads at runtime.

These packages spawn a shell, fetch a second-stage script or executable from .icu or .tech domains, and run it in memory, targeting both Linux CI servers and Windows workstations.

The majority of the packages are typosquats, meaning they bet on developer mis-types and confusion to trick them into downloading them.

**Search results containing links to a malicious package**  
_Source: Socket_

The malicious packages and their locations are listed below:

* github.com/stripedconsu/linker
* github.com/agitatedleopa/stm
* github.com/expertsandba/opt
* github.com/wetteepee/hcloud-ip-floater
* github.com/weightycine/replika
* github.com/ordinarymea/tnsr_ids
* github.com/ordinarymea/TNSR_IDS
* github.com/cavernouskina/mcp-go
* github.com/lastnymph/gouid
* github.com/sinfulsky/gouid
* github.com/briefinitia/gouid

Most of them are still live, so Go developers are advised to be very cautious and double-check their building blocks before using them in their environments.