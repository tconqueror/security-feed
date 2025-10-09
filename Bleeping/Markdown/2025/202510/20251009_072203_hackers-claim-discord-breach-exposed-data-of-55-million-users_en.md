# Hackers claim Discord breach exposed data of 5.5 million users

![Discord](https://www.bleepstatic.com/content/hl-images/2021/03/05/discord-header-l.jpg)

Discord says they will not be paying threat actors who claim to have stolen the data of 5.5 million unique users from the company's Zendesk support system instance, including government IDs and partial payment information for some people.

The company is also pushing back on claims that 2.1 million photos of government IDs were disclosed in the breach, stating that approximately 70,000 users had their government ID photos exposed.

While the attackers claim the breach occurred through Discord's Zendesk support instance, the company has not confirmed this and only described it as involving a third-party service used for customer support.

"First, as stated in our blog post, this was not a breach of Discord, but rather a third-party service we use to support our customer service efforts," Discord told BleepingComputer in a statement.

"Second, the numbers being shared are incorrect and part of an attempt to extort a payment from Discord. Of the accounts impacted globally, we have identified approximately 70,000 users that may have had government-ID photos exposed, which our vendor used to review age-related appeals."

"Third, we will not reward those responsible for their illegal actions."

In a conversation with the hackers, BleepingComputer was told that Discord is not being transparent about the severity of the breach, stating that they stole 1.6 TB of data from the company's Zendesk instance.

According to the threat actor, they gained access to Discord’s Zendesk instance for 58 hours beginning on September 20, 2025\. However, the attackers say the breach did not stem from a vulnerability or breach of Zendesk but rather from a compromised account belonging to a support agent employed through an outsourced business process outsourcing (BPO) provider used by Discord.

As many companies have outsourced their support and IT help desks to BPOs, they have become a popular target for attackers to gain access to downstream customer environments.

The hackers allege that Discord's internal Zendesk instance gave them access to a support application, known as Zenbar, that allowed them to perform various support-related tasks, such as disabling multi-factor authentication and looking up users’ phone numbers and email addresses.

Using access to Discord's support platform, the attackers claimed to have stolen 1.6 terabytes of data, including around 1.5 TB of ticket attachments and over 100 GB of ticket transcripts.

The hackers say this consisted of roughly 8.4 million tickets affecting 5.5 million unique users, and that about 580,000 users contained some sort of payment information.

The threat actors themselves acknowledged to BleepingComputer that they are unsure how many government IDs were stolen, but they believe it is more than 70,000, as they say there were approximately 521,000 age-verification tickets.

The threat actors also shared a sample of the stolen user data, which can include a wide variety of information, including email addresses, Discord usernames and IDs, phone numbers, partial payment information, date of birth, multi-factor authentication related information, suspicious activity levels, and other internal information.

The payment information for some users was allegedly retrievable through Zendesk integrations with Discord's internal systems. These integrations reportedly allowed the attackers to perform millions of API queries to Discord's internal database via the Zendesk platform and retrieve further information.

BleepingComputer could not independently verify the hackers' claims or the authenticity of the provided data samples.

The hacker said the group demanded $5 million in ransom, later reducing it to $3.5 million, and engaged in private negotiations with Discord between September 25 and October 2.

After Discord ceased communications and released a public statement about the incident, the attackers said they were "extremely angry" and plan to leak the data publicly if an extortion demand is not paid.

BleepingComputer contacted Discord with additional questions about these claims, including why they retained government IDs after completing age verification, but did not receive answers beyond the above statement.