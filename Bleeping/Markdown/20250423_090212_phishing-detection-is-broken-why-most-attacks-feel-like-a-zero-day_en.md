# Phishing detection is broken: Why most attacks feel like a zero day

![Push phishing attack header](https://www.bleepstatic.com/content/posts/2025/04/22/push-header.jpg)

Phishing attacks remain a huge challenge for organizations in 2025. In fact, with attackers increasingly leveraging identity-based techniques over software exploits, phishing arguably poses a bigger threat than ever before.

With MFA-bypassing phishing kits the new normal, capable of phishing accounts protected by SMS, OTP, and push-based methods, detection controls are being put under constant pressure as prevention controls fall short.

A key challenge with phishing detection is that based on the indicators that we as an industry use to commonly detect phishing pages, pretty much every phishing attack looks different and uses a unique combination of domain, URL, IPs, page composition, target app, etc. Effectively, every phishing attack is completely novel. You might even describe them as “zero-days” (cue the collective sharp intake of breath)...

The goal here isn’t to sensationalize phishing attacks — quite the opposite. Rather, this shines a light on the state of phishing detection controls. Frankly, if every phishing attack is a zero-day, something has gone very wrong with how we detect these attacks…

## Phishing detection 101

Most phishing attacks involve the delivery of a malicious link to a user. The user clicks the link and loads a malicious page. In the vast majority of cases, the malicious page is a login portal for a specific website, where the goal for the attacker is to steal the victim’s account.

Phishing detection, at its core, relies on blocklists made up of indicators of compromise (IoCs) relating to phishing pages that have been successfully identified as malicious. These IoCs consist of malicious domains, URLs, and IPs that have appeared in an attack.

IoCs are collected by security vendors and service providers across a range of sources. Mostly though, the malicious page needs to be used in a phishing campaign before it has a chance of being detected. This means that a would-be victim needs to interact with it in some way — either by falling for a phishing attack, or reporting it as suspicious.

Once a page is flagged, it can be investigated — either manually (by a security person) or automatically (by a product/tool). If the page can be accessed and analyzed, and malicious content is found (more on this later) then the page’s IoCs can be collected and added to a blocklist.

This information will then begin to circulate across the various threat intelligence feeds and security products leveraging this information. The majority of phishing detection and control enforcement is focused at the email and network layer — typically at the Secure Email Gateway (SEG), Secure Web Gateway (SWG)/proxy, or both.

![IoC-based blocklists underpin phishing detection and blocking](https://www.bleepstatic.com/images/news/security/p/push/phishing-novel-attack/2.png)

**IoC-based blocklists underpin phishing detection and blocking**

If you’re following the thought pattern here, you can probably already see the root of the problem. To detect and block a phishing page, it needs to be used in an attack first…

## [Protect and defend your identity attack surface with Push Security](https://pushsecurity.com/demo?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article)

Book a demo to see how Push's browser-based identity security platform prevents account takeover attacks like MFA-bypass phishing, credential stuffing, password spraying, and session hijacking.

Find, fix, and defend workforce identities where they're created and used — in employee browsers.

[Book a demo or try it for free](https://pushsecurity.com/demo?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article)

## Why most phishing attacks are completely novel

Attackers know that phishing detection and blocking:

* Relies on blocklisting IoCs like domains, URLs and IPs
* Is situated at the email and network layer
* Requires that a page is accessed and analyzed before it can be blocked

These methods have remained practically unchanged for more than a decade. So it stands to reason that attackers are getting pretty good at avoiding them.

### It’s easy for attackers to evade IoC-based detections

Phishing domains are highly disposable by nature. Attackers are buying them in bulk, constantly taking over legitimate domains, and generally planning for the fact that they’ll get through a lot of them.

Modern phishing architecture is also able to dynamically rotate and update commonly signatured elements — for example, by dynamically rotating the links served to visitors from a continually refreshed pool (so every person that clicks the link gets served a different URL) and even going as far as using things like one-time magic links (which also means that any security team members trying to investigate the page later won’t be able to do so).

You could look at which IP address the user connects to, but these days it’s very simple for attackers to add a new IP to their cloud-hosted server. If a domain is flagged as known-bad, the attacker only has to register a new domain, or compromise a WordPress server on an already trusted domain. Both of these things are happening on a massive scale as attackers pre-plan for the fact that their domains will be burned at some point.

Ultimately, this means that blocklists just aren’t that effective — because it’s trivial for attackers to change the indicators being used to create detections. If you think about the Pyramid of Pain, these indicators sit right at the bottom — the kind of thing we’ve been moving away from for years in the endpoint security world.

### Phishing doesn’t just happen over email

To evade email-based detections, attackers are going multi- and cross-channel with their attacks.

![Attackers are bypassing email by targeting their victims across IM, social media, using malicious ads, and by sending messages using trusted apps](https://www.bleepstatic.com/images/news/security/p/push/phishing-novel-attack/3.png)

**Attackers are bypassing email by targeting their victims across IM, social media, using malicious ads, and by sending messages using trusted apps**

Not only are attackers using different phishing vectors, they’re chaining them together to prevent security tools from intercepting the link. So for example, a social media message that sends you a non-malicious PDF with a link embedded in it, that finally directs you to a malicious webpage.

It’s worth also pointing out the limitations of email-based solutions here too. Email has some additional checks around the sender’s reputation and things like DMARC/DKIM, but these don’t actually identify malicious pages. Similarly, some modern email solutions are doing much deeper analysis of the content of an email. But… that doesn’t really help with identifying the phishing sites themselves (just indicates that one might be linked in the email). This is much more appropriate for BEC-style attacks where the goal is to social engineer the victim, as opposed to linking them to a malicious page. And this still doesn’t help with attacks launched over different mediums as we’ve highlighted above.

In any case, while modern email solutions can bring a lot more to the table, neither email or network (proxy) based tools can’t definitively know that a page is malicious unless they can access the page and analyze it…

### Attackers are preventing their pages from being analyzed

Both email and network (proxy) based solutions rely on being able to inspect and analyze a page to identify whether it is malicious or not, after which IoCs are generated that can be enforced when a link is clicked (or received in your email inbox).

Modern phishing pages aren’t static HTML — like most other modern web pages, these are dynamic web apps rendered in the browser, with JavaScript dynamically rewriting the page and launching the malicious content. This means that most basic, static checks fail to identify the malicious content running on the page.

To address this, both email and network security tools will try to explode links in a sandbox to observe the page’s behavior. But attackers are getting around this simply by implementing bot protection by requiring user interaction with a CAPTCHA or Cloudflare Turnstile.

**Implementing bot checks like Clouflare Turnstile is an effective way to bypass sandbox analysis tools**

Even if you can get past Turnstile, then you’ll need to supply the correct URL parameters and headers, and execute JavaScript, to be served the malicious page. This means that a defender who knows the domain name can’t discover the malicious behavior just by making a simple HTTP(S) request to the domain.

And if all this wasn’t enough, [they’re also obfuscating both visual and DOM elements to prevent signature-based detections from picking them up](https://pushsecurity.com/blog/how-aitm-phishing-kits-evade-detection-p2/?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article) — so even if you can land on the page, there’s a high chance that your detections won’t trigger.

## Phishing attacks are novel because phishing detection is post mortem

The result of these detection evasion and obfuscation techniques is that real-time phishing detection is basically nonexistent.

At best, your proxy-based solution might be able to detect malicious behavior via the network traffic generated by your user interacting with the page. But because of the complexity of reconstructing network requests post-TLS-encryption, this typically happens on a time delay and is not entirely reliable.

If a page is flagged, it usually requires further investigation by a security team to rule out any false positives and kick off an investigation. This can take hours at best, probably days. Then, once a page is identified as malicious and IoCs are created, it can take days or even weeks before the information is distributed, TI feeds are updated, and ingested into blocklists.

The result? Most phishing attacks are entirely novel because phishing detection is inherently post mortem — it relies on known-bads. How does something become known-bad? When a user is phished…

## To fix phishing detection, we need real-time analysis

It’s clear that how we detect and block phishing attacks is fundamentally flawed. The good news is, we’ve been here before.

When endpoint attacks skyrocketed in the late 2000s / early 2010s, they took advantage of the fact that defenders were trying to detect malware with primarily network-based detections, signature-based analysis of files, and running files in sandboxes (which was reliably defeated with sandbox-aware malware and using things as simple as putting an execution delay in the code). But this gave way to EDR, which presented a better way of observing and intercepting malicious software in real-time.

**EDR enabled real-time detection and response at the OS level rather than relying on traffic to and from the endpoint.**

The key here was getting inside the data stream to be able to observe activity in real-time on the endpoint.

We’re in a similar position today. Modern phishing attacks are happening on web pages accessed via the browser, and the tools we’re relying on — email, network, even endpoint — don’t have the required visibility. They’re looking from the outside-in.

In many ways, the browser is the new Operating System. It’s where modern work predominantly takes place — and where attacks are happening too.

**Current phishing detection isn’t in the right place to observe and stop malicious activity in real time.**

To stop phishing attacks as they happen, we need to be able to observe the page in real-time, as the user sees it from inside the browser. Not in a sandbox — seeing the real page, at the same time as the user. Only then can we build the detection and containment controls required to move phishing beyond the current cat-and-mouse game, where attackers are always two steps ahead.

**Getting real-time visibility of page/user behavior and malicious toolkits running on the page is key to moving to TTP-based detections, rather than chasing quickly-changing IoCs**

## The future of phishing detection and response is browser based

[Push Security](https://pushsecurity.com/?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article) provides a browser-based identity security solution that intercepts phishing attacks as they happen — in employee browsers. Being in the browser delivers a lot of advantages when it comes to detecting and intercepting phishing attacks. You see the live webpage that the user sees, as they see it, meaning you have much better visibility of malicious elements running on the page. It also means that you can implement real-time controls that kick in when a malicious element is detected.

There’s a clear difference when you compare a phishing attack with and without Push.

Here, an attacker hacks a WordPress blog to get a reputable domain and then runs a phishing toolkit on the webpage. They email one of your employees a link to it. Your SWG or email scanning solution inspects it in a sandbox but the phish kit detects this and redirects to a benign site so that it passes the inspection.

Your user gets the email with the link and is now free to interact with the phishing page. They enter their credentials plus MFA code into the page and voila! The attacker steals the authenticated session and takes over the user’s account.

But with Push, our browser extension inspects the webpage running in the user's browser. Push observes that the webpage is a login page and the user is entering their password into the page, detecting that:

* The password the user is entering into the phishing site has been used to log into another site previously. This means that the password is being reused (bad) or the user is being phished (even worse).
* The web page is cloned from a legitimate login page that has been fingerprinted by Push.
* A phishing toolkit is running on the web page.

As a result, the user is blocked from interacting with the phishing site and prevented from continuing.

These are good examples of detections that are difficult (or impossible) for an attacker to evade — you can’t phish a victim if they can’t enter their credentials into your phishing site!

**[Find out more about how Push detects and blocks phishing attacks here.](https://pushsecurity.com/blog/detecting-and-blocking-phishing-attacks-in-the-browser/?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article)** 

## Learn more

It doesn’t stop there — Push provides comprehensive identity attack detection and response capabilities against techniques like credential stuffing, password spraying and session hijacking using stolen session tokens. You can also use Push to find and fix identity vulnerabilities across every app that your employees use like: ghost logins; SSO coverage gaps; MFA gaps; weak, breached and reused passwords; risky OAuth integrations; and more.

If you want to learn more about how Push helps you to detect and defeat common identity attack techniques, [book some time with one of our team for a live demo](https://pushsecurity.com/demo?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article) — or register an account to try it for free.

**[Check out our quick-start guide here](https://pushsecurity.com/help/audience/administrators/docs/getting-started/?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article).**

_Sponsored and written by [Push Security](https://pushsecurity.com/demo?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article)._