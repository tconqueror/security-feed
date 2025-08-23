# New PumaBot botnet brute forces SSH credentials to breach devices

![Botnet](https://www.bleepstatic.com/content/hl-images/2022/11/30/botnet.jpg)

A newly discovered Go-based Linux botnet malware named PumaBot is brute-forcing SSH credentials on embedded IoT devices to deploy malicious payloads.

The targeted nature of PumaBot is also evident by the fact it targets specific IPs based on lists pulled from a command-and-control (C2) server instead of broader scanning of the internet.

## Targeting surveillance cams

Darktrace documented PumaBot in [a report](https://www.darktrace.com/blog/pumabot-novel-botnet-targeting-iot-surveillance-devices) providing an overview of the botnet's attack flow, indicators of compromise (IoCs), and detection rules.

The malware receives a list of target IPs from its C2 (ssh.ddos-cc.org) and attempts to perform brute-force login attempts on port 22 for open SSH access.

During this process, it checks for the presence of a "Pumatronix" string, which Darktrace believes could correspond to the targeting of surveillance and traffic camera systems by the vendor.

Once the targets have been established, the malware receives credentials to test against them.

If successful, it runs 'uname -a' to get environment information and verify the targeted device is not a honeypot.

Next, it writes its main binary (jierui) to /lib/redis and installs a systemd service (redis.service) to secure persistence across device reboots.

Finally, it injects its own SSH into the 'authorized_keys' file to maintain access, even in the case of a cleanup that removes the primary infection.

Where the infection stays active, PumaBot can receive commands to attempt data exfiltration, introduce new payloads, or steal data useful in lateral movement.

Example payloads seen by Darktrace include self-updating scripts, PAM rootkits that replace the legitimate 'pam_unix.so', and daemons (binary file "1").

The malicious PAM module harvests local and remote SSH login details and stores them in a text file (con.txt). The "watcher" binary (1) constantly looks for that text file and then exfiltrates it to the C2.

![Writing credentials on a text file](https://www.bleepstatic.com/images/news/u/1220909/2025/May/credentials.jpg)

**Writing credentials on a text file**  
_Source: Darktrace_

After the exfiltration, the text file is wiped from the infected host to delete any traces of the malicious activity.

The size and success of PumaBot are currently unknown, and Darktrace does not mention how extensive the target IP lists are.

This new botnet malware stands out for launching targeted attacks that could open the way to deeper corporate network infiltration instead of using the infected IoTs directly for lower-grade cybercrime, such as distributed denial of service (DoS) attacks or proxying networks.

To defend against botnet threats, upgrade IoTs to the latest available firmware version, change default credentials, put them behind firewalls, and keep them in separate networks isolated from valuable systems.