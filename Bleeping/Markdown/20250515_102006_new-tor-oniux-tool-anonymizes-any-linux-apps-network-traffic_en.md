# New Tor Oniux tool anonymizes any Linux app's network traffic

![Linux Onion](https://www.bleepstatic.com/content/hl-images/2025/05/15/clean.jpg)

Tor has announced Oniux, a new command-line tool for routing any Linux application securely through the Tor network for anonymized network connections.

Unlike classic methods like torsocks, which rely on user-space tricks, Oniux uses Linux namespaces to create a fully isolated network environment for each application, preventing data leaks even if the app is malicious or misconfigured.

Linux namespaces are a kernel feature that allows processes to run in isolated environments, each with its own view of specific system resources like networking, processes, or file mounts.

Oniux uses Linux namespaces to isolate apps at the kernel level, so all their traffic is forced through Tor.

"We are excited to introduce _oniux_: a small command-line utility providing Tor network isolation for third-party applications using Linux namespaces," reads a [Tor blog post](https://blog.torproject.org/introducing-oniux-tor-isolation-using-linux-namespaces/).

"Built on Arti, and onionmasq, oniux drop-ships any Linux program into its own network namespace to route it through Tor and strips away the potential for data leaks."

It achieves this by placing each app in its own network namespace with no access to the host's interfaces, and instead attaching a virtual interface (onion0) that routes through Tor using onionmasq. 

It also uses mount namespaces to inject a custom /etc/resolv.conf for Tor-safe DNS, and user/PID namespaces to safely set up the environment with minimal privileges.

This setup ensures leak-proof, kernel-enforced Tor isolation for any Linux app.

On the other hand, Torsocks works by using an 'LD_PRELOAD' hack to intercept network-related function calls in dynamically linked Linux applications and redirect them through a Tor SOCKS proxy.

The problem with this approach is that raw system calls aren't caught by Torsocks, and malicious apps can avoid using libc functions to cause leaks.

Moreover, Torsocks doesn't work with static binaries at all, and doesn't offer true isolation, as apps still access the host's real network interfaces.

The Tor project published a comparison table highlighting the qualitative differences between the two solutions.

| **oniux**                         | **torsocks**                                                                |
| --------------------------------- | --------------------------------------------------------------------------- |
| Standalone application            | Requires running Tor daemon                                                 |
| Uses Linux namespaces             | Uses an ld.so preload hack                                                  |
| Works on all applications         | Only works on applications making system calls through libc                 |
| Malicious application cannot leak | Malicious application can leak by making a system call through raw assembly |
| Linux only                        | Cross-platform                                                              |
| New and experimental              | Battle-proven for over 15 years                                             |
| Uses Arti as its engine           | Uses CTor as its engine                                                     |
| Written in Rust                   | Written in C                                                                |

Despite the obvious advantages of Oniux, Tor highlights that the project is still experimental and hasn't been tested extensively under multiple conditions and scenarios.

That said, the tool may not work as expected, so its use in critical operations is discouraged.

Instead, Tor calls for enthusiasts who can test Oniux and report any problems they encounter so the tool can reach maturity quickly and become ready for broader deployment.

The Tor Project has published the [source code](http://gitlab.torproject.org/tpo/core/oniux), and those interested in testing Oniux must first ensure they have Rust installed on their Linux distribution, and then install the tool using the command:

`cargo install --git https://gitlab.torproject.org/tpo/core/oniux oniux@0.4.0`

Tor gives some usage examples like accessing an .onion site (oniux curl http://example.onion), "torifying" the shell session (oniux bash), or running a GUI app over Tor in the desktop environment (oniux hexchat).