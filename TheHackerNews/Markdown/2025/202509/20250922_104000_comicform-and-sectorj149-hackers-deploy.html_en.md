# ComicForm and SectorJ149 Hackers Deploy Formbook Malware in Eurasian Cyberattacks

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg3W5z25Hk46W7WFVmyS2iSNtOYmAK4fRnhASGkeouZ2%5FUJ3B6D8rD8uIIvq4rNV8utNMz4BH8PM0IjVxU9eHafMyt%5FlGCbyWSN8LIV1u5Sx0cJCJ9s6jQWnEk7ylgTAd-vAv2mtZ4mm7iywqSAn2uWPuVdUkcPavvtYENojp%5FixrgpvxO0wc63b8khjQ%5FD/s728-rw-e365/pdf-malware.jpg)

Organizations in Belarus, Kazakhstan, and Russia have emerged as the target of a phishing campaign undertaken by a previously undocumented hacking group called **ComicForm** since at least April 2025.

The [activity](https://www.f6.ru/blog/comicform/) primarily targeted industrial, financial, tourism, biotechnology, research, and trade sectors, cybersecurity company F6 said in an analysis published last week.

The attack chain involves sending emails bearing subject lines like "Waiting for the signed document," "INvoice for Payment," or "Reconciliation Act for Signature," urging recipients to open an RR archive, within which there exists a Windows executable that masquerades as a PDF document (e.g., "Акт\_сверки pdf 010.exe"). The messages, written in Russian or English, are sent from email addresses registered in the .ru, .by, and .kz top-level domains.

The executable is an obfuscated .NET loader designed to launch a malicious DLL ("MechMatrix Pro.dll"), which subsequently runs a third-stage payload, another DLL named "Montero.dll" that serves as a dropper for the [Formbook](https://thehackernews.com/2024/07/cybercriminals-target-polish-businesses.html) malware, but not before creating a scheduled task and configuring Microsoft Defender exclusions to evade detection.

[](https://thehackernews.uk/exec-guide-d)

Interestingly, the binary has also been found to contain Tumblr links pointing to completely harmless GIFs of comic superheroes like Batman, giving the threat actor its name. "These images were not used in any attack, but were merely part of the malware code," F6 researcher Vladislav Kugan said.

Analysis of ComicForm's infrastructure has revealed signs that phishing emails have also been directed against an unspecified company operating in Kazakhstan in June 2025 and a Belarusian bank in April 2025.

F6 also said it detected and blocked phishing emails sent to Russian manufacturing companies from the email address of a Kazakhstan-based industrial company as recently as July 25, 2025\. These digital missives prompt prospective targets to click on an embedded link to confirm their account and avoid a potential block.

Users who click on the link are redirected to a bogus landing page mimicking the login page of a domestic document management service to facilitate credential theft by transmitting the entered information to an attacker-controlled domain in the form of an HTTP POST request.

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjQ1jsQzH8lfB0PNft2OYDsrjMSK2gigrGtU7J7hfDgUEY7ouWiXRFX2rG87OSia5r7JsxiJ7bfwx1wyLxc%5F9FKQZ2ivNevmS3HKZsjiN3z10kiQ3srR4JxxjxPWDCzXGAz6wJ8Abzkb99lMUklD3a5Z1Rab9mlVdxNB0QWRRQPr73sxHw4h9KpFUF0907K/s728-rw-e365/phish.png)

"Additionally, JavaScript code was found in the page body that extracts the email address from URL parameters, populates the input field with id="email" , extracts the domain from the email address, and sets a screenshot of that domain's website (via the screenshotapi\[.\]net API) as the background of the phishing page," Kugan explained.

The attack aimed at the Belarusian bank involved sending a phishing email with an invoice-themed lure to trick users into entering their email addresses and phone numbers in a form, which are then captured and sent to an external domain.

"The group attacks Russian, Belarusian, and Kazakh companies from various sectors, and the use of English-language emails suggests that the attackers are also targeting organizations in other countries," F6 said. "The attackers employ both phishing emails distributing FormBook malware and phishing resources disguised as web services to harvest access credentials."

### Pro-Russian Group Targets South Korea with Formbook

The disclosure comes as the NSHC ThreatRecon Team disclosed details of a pro-Russian cybercrime group that has targeted manufacturing, energy, and semiconductor sectors in South Korea. The activity has been attributed to a cluster called [SectorJ149](https://thehackernews.com/2024/10/russian-romcom-attacks-target-ukrainian.html) (aka UAC-0050).

The attacks, observed in November 2024, commenced with spear-phishing emails targeting executives and employees using lures related to production facility purchases or quotation requests, leading to the execution of commodity malware families like Lumma Stealer, Formbook, and Remcos RAT by means of a Visual Basic Script distributed as a Microsoft cabinet (CAB) archive.

[](https://thehackernews.uk/cis-security-suite)

The Visual Basic Script is engineered to run a PowerShell command that reaches out to a Bitbucket or GitHub repository to fetch a JPG image file, which conceals a loader executable responsible for launching the final stealer and RAT payloads.

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjnFtftqu8vEN1EOcECou09KDi4PT3g7DOYIxx6kROD1i-TOKzd%5FgHDHSa8WSryyXdZGA8RRXGU7PFoz364T22xsT2lCMxzen%5FD%5FNSYXghZn8kDUmSZyW4g6cUj0RkyuKkqaHWzSDP6O795%5FUxvRw-VeAzw7i%5FM2WVk4HGLraDDIjuzqssz6dEab874FXzC/s728-rw-e365/second.jpg)

"The PE Malware executed directly in the memory area is a loader-type Malware that downloads additional malicious data disguised as a text file (.txt) through a URL included in the provided parameter values, decrypts it, and then generates and executes the PE Malware," the Singaporean cybersecurity company [said](https://medium.com/@nshcthreatrecon/hacking-activities-of-pro-russian-cyber-crime-group-targeting-korean-companies-8e349ae90401).

"In the past, the SectorJ149 group primarily operated for financial gain, but the recent hacking activities targeting Korean companies are believed to have a strong hacktivist nature, using hacking techniques to convey political, social, or ideological messages."