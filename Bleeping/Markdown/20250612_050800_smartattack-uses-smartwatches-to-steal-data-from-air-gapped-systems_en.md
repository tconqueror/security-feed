# SmartAttack uses smartwatches to steal data from air-gapped systems

![Air-gapped](https://www.bleepstatic.com/content/hl-images/2024/09/05/Airgapped.jpg)

A new attack dubbed 'SmartAttack' uses smartwatches as a covert ultrasonic signal receiver to exfiltrate data from physically isolated (air-gapped) systems.

Air-gapped systems, commonly deployed in mission-critical environments such as government facilities, weapons platforms, and nuclear power plants, are physically isolated from external networks to prevent malware infections and data theft.

Despite this isolation, they remain vulnerable to compromise through insider threats such as rogue employees using USB drives or state-sponsored supply chain attacks.

Once infiltrated, malware can operate covertly, using stealthy techniques to modulate the physical characteristics of hardware components to transmit sensitive data to a nearby receiver without interfering with the system's regular operations.

SmartAttack was devised by Israeli university researchers led by [Mordechai Guri](https://arxiv.org/html/2506.08866v1), a specialist in the field of covert attack channels who previously presented methods to leak data using [LCD screen noise](https://www.bleepingcomputer.com/news/security/new-pixhell-acoustic-attack-leaks-secrets-from-lcd-screen-noise/), [RAM modulation](https://www.bleepingcomputer.com/news/security/new-rambo-attack-steals-data-using-ram-in-air-gapped-computers/), [network card LEDs](https://www.bleepingcomputer.com/news/security/etherled-air-gapped-systems-leak-data-via-network-card-leds/), [USB drive RF signals](https://www.bleepingcomputer.com/news/security/new-software-bridges-an-air-gap-using-an-unmodified-usb/), [SATA cables](https://www.bleepingcomputer.com/news/security/air-gapped-systems-leak-data-via-sata-cable-wifi-antennas/), and [power supplies](https://www.bleepingcomputer.com/news/security/air-gapped-pcs-vulnerable-to-data-theft-via-power-supply-radiation/).

While attacks on air-gapped environments are, in many cases, theoretical and extremely difficult to achieve, they still present interesting and novel approaches to exfiltrate data.

## How SmartAttack works

SmartAttack requires malware to somehow infect an air-gapped computer to gather sensitive information such as keystrokes, encryption keys, and credentials. It can then use the computer's built-in speaker to emit ultrasonic signals to the environment.

By using a binary frequency shift keying (B-FSK), the audio signal frequencies can be modulated to represent binary data, aka ones and zeroes. A frequency of 18.5 kHz represents "0," while 19.5 kHz denotes "1."

![The covert channel and interference from keyboard typing](https://www.bleepstatic.com/images/news/u/1220909/2025/June/inter.jpg)

**The covert channel and interference from keyboard typing**  
_Source: arxiv.org_

Frequencies at this range are inaudible to humans, but they can still be caught by a smartwatch microphone worn by a person nearby.

The sound monitoring app in the smartwatch applies signal processing techniques to detect frequency shifts and demodulate the encoded signal, while integrity tests can also be applied.

The final exfiltration of the data can take place via Wi-Fi, Bluetooth, or cellular connectivity.

The smartwatch can either be purposefully equipped with this tool by a rogue employee, or outsiders may infect it without the wearer's knowledge.

## Performance and limitations

The researchers note that smartwatches use small, lower-SNR microphones compared to smartphones, so signal demodulation is quite challenging, especially at higher frequencies and lower signal intensities.

Even wrist orientation was found to play a crucial role in the feasibility of the attack, working best when the watch has "line-of-sight" with the computer speaker.

Depending on the transmitter (speaker type), the maximum transmission range is between 6 and 9 meters (20 – 30 feet).

![Transmitter type performance](https://www.bleepstatic.com/images/news/u/1220909/2025/June/transmitter.jpg)

**Transmitter type performance**  
_Source: arxiv.org_

The data transmission rate ranges from 5 bits per second (bps) to 50 bps, reducing reliability as the rate and distance increase.

**Performance measurements (Signal to Noise Ratio, Bit Error Rate)**  
_Source: arxiv.org_

The researchers say the best way to counter the SmartAttack is to prohibit using smartwatches in secure environments.

Another measure would be to remove in-built speakers from air-gapped machines. This would eliminate the attack surface for all acoustic covert channels, not just SmartAttack.

If none of this is feasible, ultrasonic jamming through the emission of broadband noise, software-based firewalls, and audio-gapping could still prove effective.