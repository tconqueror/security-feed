# New 'CoPhish' technique wraps OAuth phishing in Microsoft Copilot

![New 'CoPhish' technique wraps OAuth phishing in Microsoft Copilot](https://www.bleepstatic.com/content/hl-images/2025/10/24/Microsoft_Copilot.jpg)

A new phishing technique dubbed 'CoPhish' weaponizes Microsoft Copilot Studio agents to deliver fraudulent OAuth consent requests via legitimate and trusted Microsoft domains.

The technique was developed by researchers at Datadog Security Labs, who warned in a report earlier this week that Copilot Studio's flexibility introduces new, undocumented phishing risks.

Although CoPhish relies on social engineering, Microsoft has confirmed to BleepingComputer that it plans on fixing the underlying causes in a future update.

"We've investigated this report and are taking action to address it through future product updates," a Microsoft spokesperson told BleepingComputer.

"While this technique relies on social engineering, we remain committed to hardening our governance and consent experiences and are evaluating additional safeguards to help organizations prevent misuse."

## Copilot agents and OAuth phishing

Copilot Studio agents are chatbots hosted on _copilotstudio.microsoft.com_ that users can create and customize through "topics," which are workflows that automate specific tasks.

Agents can be shared on Microsoft's domain by enabling the "demo website" feature. Because the URL is a legitimate one, it is easier for a user to fall for the trick and log in.

The Login topic, which authenticates the user when starting a conversation with the chatbot, can be configured for specific actions, like requesting a verification code or redirecting to another location or service.

![](https://www.bleepstatic.com/images/news/u/1100723/MaliciousCopilot_SignInTopic_Datadog.png)

**Customizable sign-in topic in malicious agent**  
_source: Datadog_

Katie Knowles, senior security researcher at Datadog, says that an attacker can customize the Login button with a malicious application that can be "either internal or external to the target environment," and could target an application admin even they don have access to the environment.

Targeting an unprivileged user in the tenant is currently possible if the threat actor is already present in the environment. However, when Microsoft's default policy changes, the attack would be limited only to OneNote read/write permissions and close the gap for email, chat, and calendar services.

Knowles says that even after Microsoft's update, it is still possible for an external attacker to "target an Application Administrator with an externally registered application," because the changes do not apply to high-privileged roles.

Users with administrator privileges in the tenant can approve permissions requested by internal or external applications, even if they are not verified (e.g. are marked as not being published by Microsoft or their organization).

The Datadog researcher says that a CoPhish attack starts with the threat actor creating a malicious multi-tenant app with the sign-in topic configured to direct to the authentication provider and to collect the session token.

Getting the session token is possible by configuring an HTTP request to a Burp Collaborator URL and deliver the access token variable in a "token" header.

![Adding the required actions to the sign-in topic](https://www.bleepstatic.com/images/news/u/1220909/2025/October/forwarding.jpg)

**Adding the required actions to the sign-in topic**  
_Source: Datadog_

"The application ID (or client ID), secret, and authentication provider URLs are used to configure the agent's sign-in settings," Knowles says in a [report](https://securitylabs.datadoghq.com/articles/cophish-using-microsoft-copilot-studio-as-a-wrapper/) this week.

It should be noted that the redirect action when the victim user clicks on the Login button can be configured to redirect to any malicious URL, and the application consent workflow URL is just one possibility for the attacker.

## CoPhish attack on Admins

After activating the malicious agent's demo website, an attacker can distribute it to targets in email phishing campaigns or over Team messages.

Since the URL is legitimate and the design of the page, users may think that it is just another Microsoft Copilot service. Knowles says that one clue that could raise suspicions is the "Microsoft Power Platform" icon, which is easy to miss.

**The Microsoft-hosted page and Login button**  
_Source: Datadog_

An admin falling for the trick and accepting the malicious app's permisssions, are taken to the OAuth redirect URL \[token.botframework.com\] to validate the bot connection.

"This may seem atypical, but it’s a standard part of the Copilot Studio authentication process using a valid domain," the Datadog researchers says.

After completing the authentication process, the user will receive no notification about their session token being forwarded to Burp Collaborator and their session being hijacked, but they will be able to chat with the agent.

Furthermore, because the token was sent from Copilot using Microsoft's IP addresses, the connection to the attacker will not show in the user's web traffic.

Below is a visual overview of how the CoPhish attack works and the steps from the victim user accessing the malicious app to the attacker receiving the token.

**Cophish attack flow diagram**  
_Source: Datadog_

Microsoft told BleepingComputer that customers can protect against CoPhish attacks by limiting administrative privileges, reducing application permissions, and enforcing governance policies.

Datadog provides a set of security considerations that include implementing a strong application consent policy that would cover any gaps in Microsoft's default baseline configuration.

The cloud monitoring and security company also advises organizations to disable user application creation defaults, and closely monitor application consent via Entra ID and Copilot Studio agent creation events.