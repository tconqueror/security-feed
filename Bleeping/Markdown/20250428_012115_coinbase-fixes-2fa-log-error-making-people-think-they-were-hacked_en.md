# Coinbase fixes 2FA log error making people think they were hacked

![Coinbase](https://www.bleepstatic.com/content/hl-images/2021/08/31/Coinbase.jpg)

Coinbase has fixed a confusing bug in its account activity logs that caused users to think their credentials were compromised.

As [BleepingComputer first reported](https://www.bleepingcomputer.com/news/security/coinbase-to-fix-2fa-account-activity-entry-freaking-out-users/) earlier this month, Coinbase had mistakenly labeled failed login attempts with incorrect passwords as two-factor authentication failures in the Account Activity logs.

When a threat actor attempted to access someone's account and used the wrong password, error messages stating "second_factor_failure" or "2-step verification failed" would be shown instead.

These entries imply that a valid username and password were entered, but the login was blocked by 2-factor authentication, such as entering the wrong one-time passcode from an authenticator app.

Numerous Coinbase users contacted BleepingComputer with concerns that Coinbase had been breached as their passwords were unique to the site, there was no sign of malware, and no other accounts were affected.

![Incorrect 2FA error message in Coinbase Account Activity logs](https://www.bleepstatic.com/images/news/cryptocurrency/2fa/incorrect-2fa-error-message/coinbase-account-activity-message.jpg)

**Incorrect 2FA error message in Coinbase Account Activity logs**

However, Coinbase confirmed to BleepingComputer that its logging system was incorrectly attributing login attempts with incorrect passwords as "2FA failures," even though the attackers had not successfully reached the 2FA stage.

Coinbase has now pushed an update to fix this incorrect labeling so that "Password attempt failed" logs are shown in Account Activity instead.

Bugs like this are essential to fix as they cause unnecessary panic, with users telling BleepingComputer that they had reset all of their passwords and spent hours trying to determine if their devices were compromised due to this bug.

These mislabeled entries could have also been used in social engineering attacks to convince users their account credentials were compromised, potentially allowing threat actors to gain sensitive information.

Threat actors commonly [target Coinbase customers in social engineering attacks](https://krebsonsecurity.com/2021/10/how-coinbase-phishers-steal-one-time-passwords/) to gain access to their accounts and drain the stored cryptocurrency.

BleepingComputer was told that threat actors used these mislabeled error messages as part of such attacks but could not independently verify if that was true.

However, ongoing campaigns use automated SMS phishing (smishing) attacks and voice calls to impersonate Coinbase and attempt to steal 2FA tokens or credentials, so all users should be wary.

Coinbase has [said in the past](https://www.bleepingcomputer.com/news/security/coinbase-to-fix-2fa-account-activity-entry-freaking-out-users/) that they will never call customers or send text messages requesting they change passwords or reset two-factor authentication and that customers should treat all such messages as scams.