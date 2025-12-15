# Google links more Chinese hacking groups to React2Shell attacks

![Chinese hackers](https://www.bleepstatic.com/content/hl-images/2025/12/04/Chinese-hackers.jpg)

​Over the weekend, ​Google's threat intelligence team linked five more Chinese hacking groups to attacks exploiting the maximum-severity "[React2Shell](https://react2shell.com/)" remote code execution vulnerability.

Tracked as [CVE-2025-55182](https://www.bleepingcomputer.com/news/security/critical-react2shell-flaw-in-react-nextjs-lets-hackers-run-javascript-code/), this actively exploited flaw affects the React open-source JavaScript library and allows unauthenticated attackers to execute arbitrary code in React and Next.js applications with a single HTTP request.

While multiple React packages (i.e., react-server-dom-parcel, react-server-dom-turbopack, and react-server-dom-webpack) are vulnerable in their default configurations, the vulnerability only affects React versions 19.0, 19.1.0, 19.1.1, and 19.2.0 released over the past year.

After the attacks began, Palo Alto Networks [reported](https://unit42.paloaltonetworks.com/cve-2025-55182-react-and-cve-2025-66478-next/) that dozens of organizations had been breached, including incidents linked to Chinese state-backed threat actors. The attackers are exploiting the flaw to execute commands and steal AWS configuration files, credentials, and other sensitive information.

The Amazon Web Services (AWS) security team [also warned](https://www.bleepingcomputer.com/news/security/react2shell-critical-flaw-actively-exploited-in-china-linked-attacks/) that the China-linked Earth Lamia and Jackpot Panda threat actors had begun exploiting React2Shell within hours of the vulnerability's disclosure.

## Five more Chinese hacking groups linked to attacks

On Saturday, the Google Threat Intelligence Group (GTIG) reported detecting at least five more Chinese cyber-espionage groups joining ongoing React2Shell attacks that started after the flaw was disclosed [on December 3](https://www.bleepingcomputer.com/news/security/critical-react2shell-flaw-in-react-nextjs-lets-hackers-run-javascript-code/).

The list of state-linked threat groups exploiting the flaw now also includes UNC6600 (which deployed MINOCAT tunneling software), UNC6586 (the SNOWLIGHT downloader), UNC6588 (the COMPOOD backdoor payload), UNC6603 (an updated version of the HISONIC backdoor), and UNC6595 (ANGRYREBEL.LINUX Remote Access Trojan).

"Due to the use of React Server Components (RSC) in popular frameworks like Next.js, there are a significant number of exposed systems vulnerable to this issue," [GTIG researchers said](http://cloud.google.com/blog/topics/threat-intelligence/threat-actors-exploit-react2shell-cve-2025-55182/).

"GTIG has also observed numerous discussions regarding CVE-2025-55182 in underground forums, including threads in which threat actors have shared links to scanning tools, proof-of-concept (PoC) code, and their experiences using these tools."

While investigating these attacks, GTIG also spotted Iranian threat actors targeting the flaw and financially motivated attackers deploying XMRig cryptocurrency mining software on unpatched systems.

Shadowserver Internet watchdog group [is currently tracking](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=7&source=http%5Fvulnerable&source=http%5Fvulnerable6&tag=cve-2025-55182%2B&dataset=unique%5Fips&limit=100&group%5Fby=tag&stacking=stacked&auto%5Fupdate=on) over 116,000 IP addresses vulnerable to React2Shell attacks, with over 80,000 in the United States.

![Devices vulnerable to React2Shell attacks](https://www.bleepstatic.com/images/news/u/1109292/2025/Devices%20vulnerable%20to%20React2Shell%20attacks.jpg)

_Devices vulnerable to React2Shell attacks (Shadowserver)_

​GreyNoise has also observed [over 670 IP addresses](https://viz.greynoise.io/query/tags:%22React%20Server%20Components%20Unsafe%20Deserialization%20CVE-2025-55182%20RCE%20Attempt%22%20last%5Fseen:1d) attempting to exploit the React2Shell remote code execution flaw over the past 24 hours, primarily originating from the United States, India, France, Germany, the Netherlands, Singapore, Russia, Australia, the United Kingdom, and China.

On December 5, Cloudflare linked a [global website outage](https://www.bleepingcomputer.com/news/technology/cloudflare-down-websites-offline-with-500-internal-server-error/) to [emergency mitigations](https://www.bleepingcomputer.com/news/security/cloudflare-blames-todays-outage-on-emergency-react2shell-patch/) for the React2Shell vulnerability.