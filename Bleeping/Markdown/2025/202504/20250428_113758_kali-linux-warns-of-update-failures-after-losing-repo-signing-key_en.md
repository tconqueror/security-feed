# Kali Linux warns of update failures after losing repo signing key

![Kali](https://www.bleepstatic.com/content/hl-images/2025/04/28/KALI.jpg)

Offensive Security warned Kali Linux users to manually install a new Kali repository signing key to avoid experiencing update failures.

The announcement comes after OffSec lost the old repo signing key (ED444FF07D8D0BF6) and was forced to create a new one (ED65462EC8D5E4C5) signed by Kali Linux developers using signatures available on the [Ubuntu OpenPGP key server](https://keyserver.ubuntu.com/pks/lookup?search=827C8569F2518CC677FECA1AED65462EC8D5E4C5&fingerprint=on&op=index). However, since the key was not compromised, the old one was not removed from the keyring.

On systems still using the old key, users will see "Missing key 827C8569F2518CC677FECA1AED65462EC8D5E4C5, which is needed to verify signature" when trying to get the list of latest software packages.

While OffSec didn't share the date when it realized the key was lost, the company added that the Kali Linux repo was frozen on February 18th.

"In the coming day(s), pretty much every Kali system out there will fail to update. \[..\] This is not only you, this is for everyone, and this is entirely our fault. We lost access to the signing key of the repository, so we had to create a new one," the company [said](https://www.kali.org/blog/new-kali-archive-signing-key/).

"At the same time, we froze the repository (you might have noticed that there was no update since Friday 18th), so nobody was impacted yet. But we're going to unfreeze the repository this week, and it's now signed with the new key."

To avoid experiencing these update issues, OffSec advises users to manually download and install the new repository signing key using the following command:

```
sudo wget https://archive.kali.org/archive-keyring.gpg -O /usr/share/keyrings/kali-archive-keyring.gpg
```

OffSec also provides details on how to check that the checksum of the file matches and view the contents of the updated keyring. Those who don't trust manually updating the keyring can also reinstall Kali on their systems using images updated with the new keyring.

This isn't the first time Kali Linux users have had to manually update their keyring to avoid having update issues. In February 2018, Kali devs also [let the GPG key expire](https://x.com/kalilinux/status/959515084157538304) and asked users to update the new key manually.

"If you don't update Kali regularly (\*cough\*), then your archive-keyring package is outdated, and you'll get key mismatches when working with our repositories. Sucks for you, but at least you can manually update," the Kali team said at the time.