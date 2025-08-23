# Bluetooth 6.1 enhances privacy with randomized RPA timing

![Bluetooth](https://www.bleepstatic.com/content/hl-images/2025/05/09/bluetooth.jpg)

The Bluetooth Special Interest Group (SIG) has announced Bluetooth Core Specification 6.1, bringing important improvements to the popular wireless communication protocol.

One new feature highlighted in the latest release is the increased device privacy via randomized Resolvable Private Addresses (RPA) updates.

"Randomizing the timing of address changes makes it much more difficult for third parties to track or correlate device activity over time," [reads SIG's announcement](https://www.bluetooth.com/blog/delivering-on-the-bi-annual-release-schedule-bluetooth-core-6-1-is-here/).

A Resolvable Private Address (RPA) is a Bluetooth address created to look random and is used in place of a device's fixed MAC address to protect user privacy. It allows trusted devices to securely reconnect without revealing their true identity.

Currently, RPAs are updated at fixed intervals, usually every 15 minutes, which introduces a level of predictability. This predictability can be exploited in correlation attacks, making long-term tracking possible.

Bluetooth 6.1 improves privacy by randomizing the RPA updates between 8 and 15 minutes (default), while also allowing custom values between the range of 1 second to 1 hour.

The Controller picks a random value in the defined range using a NIST-approved random number generator, and updates the RPA. This makes tracking significantly harder, as there is no pattern in the value selection.

More details about how the new privacy feature works can be found in the [specification document](https://files.bluetooth.com/download/core%5Fv6-1/) published along with the announcement.

Another feature highlighted in the announcement is better power efficiency starting from Bluetooth 6.1, which stems from allowing the chip (Controller) to autonomously handle the randomized RPA updates.

Specifically, the Bluetooth chip will choose the randomized timing intervals and generate and update the RPA internally without waking the host device.

This saves CPU cycles and memory operations, so much power is saved when conditions are met. For smaller devices like fitness bands, earbuds, and IoT sensors, this could make a big difference in battery life.

While Bluetooth 6.1 has made exciting steps forward, it's important to underline that actual support in hardware and firmware may take years to arrive.

The first wave of chips with Bluetooth 6.1 should not be realistically expected before 2026, and even then, early implementations may not immediately expose all the newly available features, as testing and validation may be required.