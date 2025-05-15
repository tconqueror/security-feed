# Windows 11 and Red Hat Linux hacked on first day of Pwn2Own

![Pwn2Own Berlin](https://www.bleepstatic.com/content/hl-images/2025/05/15/Pwn2Own_Berin.jpg)

On the first day of Pwn2Own Berlin 2025, security researchers were awarded $260,000 after successfully demonstrating zero-day exploits for Windows 11, Red Hat Linux, and Oracle VirtualBox.

Red Hat Enterprise Linux for Workstations was the first to fall in the local privilege escalation category after DEVCORE Research Team's Pumpkin exploited an integer overflow vulnerability to earn $20,000.

Hyunwoo Kim and Wongi Lee also got root on a Red Hat Linux device by chaining a use-after-free and an information leak, but one of the exploited flaws was an N-day, which [led to a bug collision](https://x.com/thezdi/status/1922988072142000509).

Next, Chen Le Qi of STARLabs SG was awarded $30,000 for an exploit chain combining a use-after-free and an integer overflow to escalate privileges to SYSTEM on a Windows 11 system.

Windows 11 was hacked twice more to gain SYSTEM privileges by Marcin Wiązowski, who exploited an out-of-bounds write vulnerability, and Hyeonjin Choi, who demoed a type confusion zero-day.

Team Prison Break earned $40,000 after demoing an exploit chain that used an integer overflow to escape Oracle VirtualBox and execute code on the underlying operating system.

Summoning Team's Sina Kheirkhah was awarded another $35,000 for a Chroma zero-day and an already known vulnerability in Nvidia's Triton Inference Server, while STARLabs SG's Billy and Ramdhan earned $60,000 for escaping Docker Desktop and executing code on the underlying OS using a use-after-free zero-day.

![Pwn2Own Berlin 2025 1st day leaderboard](https://www.bleepstatic.com/images/news/u/1109292/2025/Pwn2Own%20Berlin%202025%201st%20day%20leaderboard.jpg)

_Pwn2Own Berlin 2025 1st day leaderboard ([Trend Zero Day Initiative](https://x.com/thezdi/status/1923034127759970639))_

​​The [Pwn2Own Berlin 2025](http://www.zerodayinitiative.com/blog/2025/2/24/announcing-pwn2own-berlin-2025) hacking competition, which focuses on enterprise technologies and introduces an AI category, takes place in Berlin between May 15 and May 17, during the [OffensiveCon](https://www.offensivecon.org/) conference.

[On the second day](https://www.zerodayinitiative.com/blog/2025/5/14/pwn2own-berlin-the-full-schedule#day2), security researchers will try to exploit zero-days in Microsoft SharePoint, VMware ESXi, Mozilla Firefox, Red Hat Enterprise Linux for Workstations, and Oracle VirtualBox.

After the zero-day vulnerabilities are demoed and disclosed during Pwn2Own, vendors have 90 days to release security fixes for their software and hardware products.

Pwn2Own contestants will target fully patched products in the AI, web browser, virtualization, local privilege escalation, servers, enterprise applications, cloud-native/container, and automotive categories, and will be able to earn over $1,000,000 in cash and prizes.

However, while the 2024 Tesla Model 3 and the 2025 Tesla Model Y bench-top units were also available as targets, no attempts have been registered before the competition started.