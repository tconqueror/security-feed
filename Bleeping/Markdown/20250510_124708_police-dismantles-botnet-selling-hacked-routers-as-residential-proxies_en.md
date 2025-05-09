# Police dismantles botnet selling hacked routers as residential proxies

![Botnet](https://www.bleepstatic.com/content/hl-images/2023/11/01/botnet-kill-switch.jpg)

Law enforcement authorities have dismantled a botnet that infected thousands of routers over the last 20 years to build two networks of residential proxies known as Anyproxy and 5socks.

The U.S. Justice Department also indicted three Russian nationals (Alexey Viktorovich Chertkov, Kirill Vladimirovich Morozov, and Aleksandr Aleksandrovich Shishkin) and a Kazakhstani (Dmitriy Rubtsov) for their involvement in operating, maintaining, and profiting from these two illegal services.

During this joint action dubbed 'Operation Moonlander,' U.S. authorities worked with prosecutors and investigators from the Dutch National Police, the Netherlands Public Prosecution Service (Openbaar Ministerie), and the Royal Thai Police, as well as analysts with Lumen Technologies' Black Lotus Labs.

[Court documents](http://legacy.www.documentcloud.org/documents/25935130-anyproxy-and-5socks-indictment/) show that the now-dismantled botnet infected older wireless internet routers worldwide with malware since at least 2004, allowing unauthorized access to compromised devices to be sold as proxy servers on Anyproxy.net and 5socks.net. The two domains were managed by a Virginia-based company and hosted on servers globally.

"The botnet controllers require cryptocurrency for payment. Users are allowed to connect directly with proxies using no authentication, which, as documented in previous cases, can lead to a broad spectrum of malicious actors gaining free access," [Black Lotus Labs said](http://blog.lumen.com/black-lotus-labs-helps-demolish-major-criminal-proxy-network/).

"Given the source range, only around 10% are detected as malicious in popular tools such as VirusTotal, meaning they consistently avoid network monitoring tools with a high degree of success. Proxies such as this are designed to help conceal a range of illicit pursuits including ad fraud, DDoS attacks, brute forcing, or exploiting victim's data."

![Map of infected routers](https://www.bleepstatic.com/images/news/u/1109292/2025/Location_of_infected_routers.jpg)

_Map of compromised routers (Black Lotus Labs)_

Their users paid a monthly subscription ranging from $9.95 to $110 per month, depending on the requested services. "The website's slogan, 'Working since 2004!,' indicates that the service has been available for more than 20 years," the Justice Department [said today](https://www.justice.gov/usao-ndok/pr/botnet-dismantled-international-operation-russian-and-kazakhstani-administrators).

The four defendants advertised the two services (promoting over 7,000 proxies) as residential proxy services on various websites, including ones used by cybercriminals, and they allegedly collected over $46 million from selling subscriptions providing access to the infected routers part of the Anyproxy botnet.

They operated the Anyproxy.net and 5socks.net websites using servers registered and hosted at JCS Fedora Communications, a Russian internet hosting provider. They also used servers in the Netherlands, Türkiye, and other locations to manage the Anyproxy botnet and the two websites.

They were all charged with conspiracy and damage to protected computers, while Chertkov and Rubtsov were also accused of falsely registering a domain name.

![5Socks.net seizure banner](https://www.bleepstatic.com/images/news/u/1109292/2025/5Socks_seizure_banner.jpg)

_5Socks.net seizure banner (BleepingComputer)_

## Targeting end-of-life (EoL) routers

On Wednesday, the FBI also issued a flash advisory and a public service announcement warning that this botnet was [targeting patch end-of-life (EoL) routers](https://www.bleepingcomputer.com/news/security/fbi-end-of-life-routers-hacked-for-cybercrime-proxy-networks/) with a variant of the TheMoon malware.

The FBI warned that the attackers are installing proxies later used to evade detection during cybercrime-for-hire activities, cryptocurrency theft attacks, and other illegal operations.

The list of devices commonly targeted by the botnet includes Linksys and Cisco router models, including:

* Linksys E1200, E2500, E1000, E4200, E1500, E300, E3200, E1550
* Linksys WRT320N, WRT310N, WRT610N
* Cisco M10 and Cradlepoint E100

"Recently, some routers at end of life, with remote administration turned on, were identified as compromised by a new variant of TheMoon malware. This malware allows cyber actors to install proxies on unsuspecting victim routers and conduct cyber crimes anonymously," the FBI said.

"Such residential proxy services are particularly useful to criminal hackers to provide anonymity when committing cybercrimes; residential-as opposed to commercial—IP addresses are generally assumed by internet security services as much more likely to be legitimate traffic," today's indictment added. "In this way, conspirators obtained a private financial gain from the sale of access to the compromised routers."