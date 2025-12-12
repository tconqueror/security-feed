# New Windows RasMan zero-day flaw gets free, unofficial patches

![Windows](https://www.bleepstatic.com/content/hl-images/2024/12/16/Windows.jpg)

Free unofficial patches are available for a new Windows zero-day vulnerability that allows attackers to crash the Remote Access Connection Manager (RasMan) service.

RasMan is a critical Windows system service that starts automatically, runs in the background with SYSTEM-level privileges, and manages VPN, Point-to-Point Protocol over Ethernet (PPoE), and other remote network connections.

ACROS Security (which manages the 0patch micropatching platform) discovered a new denial-of-service (DoS) flaw while looking into [CVE-2025-59230](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59230), a Windows RasMan privilege escalation vulnerability exploited in attacks that was [patched in October](https://www.bleepingcomputer.com/news/microsoft/microsoft-october-2025-patch-tuesday-fixes-6-zero-days-172-flaws/#:~:text=CVE%2D2025%2D59230).

The DoS zero-day has not been assigned a CVE ID and remains unpatched across all Windows versions, including Windows 7 through Windows 11 and Windows Server 2008 R2 through Server 2025.

As the researchers found, when combined with CVE-2025-59230 (or similar elevation-of-privileges flaws), it allows attackers to execute code by impersonating the RasMan service. However, that attack only works when RasMan is not running.

The new flaw provides the missing puzzle piece, enabling threat actors to crash the service at will and opening the door to privilege escalation attacks that Microsoft thought it had closed.

Unprivileged users can exploit the zero-day to crash the RasMan service due to a coding error in how it processes circular linked lists. When the service encounters a null pointer while traversing a list, it attempts to read memory from that pointer rather than exiting the loop, causing a crash.

ACROS Security now provides [free](https://blog.0patch.com/2025/12/free-micropatches-for-windows-remote.html)[, unofficial security patches](https://blog.0patch.com/2025/12/free-micropatches-for-windows-remote.html) for this Windows RasMan zero-day via its 0Patch micropatching service for all affected Windows versions until Microsoft releases an official fix.

To install the micropatch on your device, you have to create an account and install the 0Patch agent. Once launched, the agent will automatically apply the micropatch without requiring a restart unless a custom patching policy blocks it.

"We alerted Microsoft about this issue; they will likely provide an official patch for still-supported Windows versions in one of future Windows updates," ACROS Security CEO [Mitja Kolsek said](https://blog.0patch.com/2025/12/free-micropatches-for-windows-remote.html) today.

"As always, we included these 0day patches in our FREE plan until the original vendor has provided their official patch."

A Microsoft spokesperson was not immediately available for comment when contacted by BleepingComputer earlier today.