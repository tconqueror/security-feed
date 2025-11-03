# Hackers use RMM tools to breach freighters and steal cargo shipments

![Hackers use RMM tools to breach freighters and steal cargo shipments](https://www.bleepstatic.com/content/hl-images/2025/11/03/truck.jpg)

Threat actors are targeting freight brokers and trucking carriers with malicious links and emails to deploy remote monitoring and management tools (RMMs) that enable them to hijack cargo and steal physical goods.

Researchers tracked the activity to June, but they found evidence of these types of campaigns delivering NetSupport and ScreenConnect since January. 

According to email security firm Proofpoint, these attacks is becoming more popular, with nearly two dozen campaigns recorded since August, each of them sending up to a thousand messages.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

The targets are primarily North American entities; however, Proofpoint has also observed similar activity in Brazil, Mexico, India, Germany, Chile, and South Africa.

## Digitized cargo theft

Cargo theft involves stealing commercial shipments by hijacking trucks or trailers in transit, by re-routing them, or by impersonating legitimate carriers. The goods are then redirected to fraudulent pickup points.

The National Insurance Crime Bureau (NICB) estimates cargo theft losses in the U.S. to $35 billion annually.

Today, cybercriminals focus on exploiting gaps in the digital segment of the supply chain that helps companies move goods more efficiently.

The attacker’ primary goal is to install RMMs like ScreenConnect, SimpleHelp, PDQ Connect, Fleetdeck, N-able, and LogMeIn Resolve on the target companies’ systems, which give them full remote control, reconnaissance, and credential harvesting capabilities.

To achieve this goal, they use compromised accounts for load boards to post fraudulent freight listings, or breach broker and dispatcher email accounts, and then hijack email threads to lead victims to a malicious URL.

![Email response sent to victims hooked by the lure](https://www.bleepstatic.com/images/news/u/1220909/2025/October/email(3).jpg)

**Email response sent to carriers hooked by the load-board lure**  
_Source: Proofpoint_

According to the researchers, the threat actor achieves their goal by sending emails directly to asset-based carriers, freight brokerage firms, and integrated supply-chain providers, but this occurred mostly for larger entities.

**Direct email sent to larger firms**  
_Source: Proofpoint_

At this stage, social engineering plays a key role, where the attackers tailor their messages for urgent load negotiations and exploit trust in load packets, showing knowledge of how the freight industry operates.

The external pages are well crafted and appear legitimate by placing convincing carrier branding, and lead to downloading executables or installer MSI files that install an RMM tool.

By means of these tools, which are legitimate software, the attacker can control the compromised machine and can modify bookings, block dispatcher notifications, add their own devices to dispatcher phone extensions, and book loads under the compromised carrier’s identity.

“These RMMs are often used in tandem; for example, PDQ Connect has been observed downloading and installing both ScreenConnect and SimpleHelp,” Proofpoint [explains](http://www.proofpoint.com/us/blog/threat-insight/remote-access-real-cargo-cybercriminals-targeting-trucking-and-logistics).

“Once initial access is established, the threat actor conducts system and network reconnaissance and deploys credential harvesting tools such as WebBrowserPassView,” the researchers say.

Reconnaissance and credential harvesting indicate a wider attack purpose that includes pivoting deeper in the compromised environments.

**Overview of the attack**  
_Source: Proofpoint_

Proofpoint notes that the attacks suggest insider knowledge of the routes, timing, and high-value cargo types, enabling cybercriminals to select the most profitable shipments to steal.

The researchers believe that the hackers "are working with organized crime groups to compromise entities in the surface transportation industry" and hijack cargo freight.

One carrier company targeted in such attacks explains that the hackers tricked their dispatcher into installing an RMM tool and took control of their account.

The attacker "deleted every booking email and blocked notifications" and added their device to the dispatcher's phone extension. This allowed them to impersonate the victim company and talk directly to brokers.

"When booking loads, he used our official MC email + phone (listed on FMCSA)," a representative of the victim [carrier says](https://www.reddit.com/r/FreightBrokers/comments/1ndwsio/how%5Four%5Fcompany%5Fgot%5Fhacked%5Fand%5Falmost%5Flost%5F8/), adding that "Brokers, Highway, MyCarrierPackets would call our number and email — the hacker answered, verified everything, and got the loads."

Stolen cargo, which includes commodities such as food, beverages, and electronics, is physically intercepted or rerouted and later sold online or shipped overseas.

While Proofpoint has observed RMM tools being used in the attacks, the company notes that information stealers such as NetSupport, DanaBot, Lumma Stealer, and StealC were also deployed in related activities, although attribution to specific clusters was not possible.

Recommended defenses include restricting the installation of unapproved RMM tools, monitoring network activity, and blocking .EXE and .MSI file attachments at the email gateway level.