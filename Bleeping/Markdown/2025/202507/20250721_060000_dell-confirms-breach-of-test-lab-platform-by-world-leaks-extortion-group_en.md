# Dell confirms breach of test lab platform by World Leaks extortion group

![Dell logo](https://www.bleepstatic.com/content/hl-images/2024/05/09/Dell-headpic.jpg)

A newly rebranded extortion gang known as "World Leaks" breached one of Dell's product demonstration platforms earlier this month and is now trying to extort the company into paying a ransom.

Dell acknowledged the incident to BleepingComputer, confirming that the threat actor had breached its [Customer Solution Centers](https://www.dell.com/en-us/lp/dt/customer-solution-centers) platform, which is used to demonstrate Dell products and solutions to customers.

"A threat actor recently gained access to our Solution Center, an environment designed to demonstrate our products and test proofs-of-concept for Dell's commercial customers," Dell told BleepingComputer.

"It is intentionally separated from customer and partner systems, as well as Dell's networks and is not used in the provision of services to Dell customers."

"Data used in the solution center is primarily synthetic (fake) data, publicly available datasets used solely for product demonstration purposes or Dell scripts, systems data, non-sensitive information and testing outputs. Based on our ongoing investigation, the data obtained by the threat actor is primarily synthetic, publicly available or Dell systems/test data."

World Leaks stole data from the environment during the attack, but BleepingComputer has learned that this data is believed to be synthetic test data used in product demonstrations and trials.

While the threat actors likely believe it contains valuable data, as it includes sample medical data and financial information, this data is reportedly entirely fabricated. BleepingComputer has learned that the only legitimate data stolen in the attack is a very outdated contact list.

The Dell Customer Solution Centers are partitioned from the rest of Dell's customer-facing network and internal systems, with customers shown multiple warnings not to upload private data to the labs.

BleepingComputer asked Dell how the company was breached, but was told it would not share this information as the breach is still under investigation. When asked about the ransom demand, Dell said it had nothing further to share.

World Leaks is [a rebrand of the Hunters International ransomware](https://www.bleepingcomputer.com/news/security/hunters-international-rebrands-as-world-leaks-in-shift-to-data-extortion/), which shifted its focus away from file encryption toward pure data extortion.

Hunters International was launched in late 2023 as a ransomware operation and was flagged as a [possible rebrand of Hive](https://www.bleepingcomputer.com/news/security/new-hunters-international-ransomware-possible-rebrand-of-hive/) due to code similarities. 

Since then, the threat actors have claimed over 280 attacks against organizations worldwide.

In January 2025, Hunters International rebranded as World Leaks, citing concerns that ransomware is no longer profitable and risky.

Instead, the threat actors now focus on stealing data in extortion attacks, utilizing a custom-made data exfiltration tool.

Since its launch, World Leaks has published data from 49 organizations on its data leak site. They have not listed Dell at this time.

World Leaks affiliates are also [linked to the recent exploitation](https://www.bleepingcomputer.com/news/security/sonicwall-sma-devices-hacked-with-overstep-rootkit-tied-to-ransomware/) of end-of-life SonicWall SMA 100 devices, where threat actors installed a custom OVERSTEP rootkit.

Yutaka Sejiyama, a threat researcher at Macnica, told BleepingComputer that 10 out of the 46 companies posted on World Leaks' data leak site had been using an SMA 100.