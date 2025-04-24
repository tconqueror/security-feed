# Linux 'io_uring' security blindspot allows stealthy rootkit attacks

![Linux](https://www.bleepstatic.com/content/hl-images/2024/11/27/Linux-bootkit.jpg)

A significant security gap in Linux runtime security caused by the 'io\_uring' interface allows rootkits to operate undetected on systems while bypassing advanced Enterprise security software.

The flaw was [discovered by ARMO](https://www.armosec.io/blog/io%5Furing-rootkit-bypasses-linux-security/) security researchers who developed a proof-of-concept rootkit called "Curing" to demonstrate the practicality and feasibility of attacks leveraging io\_uring for evasion.

io\_uring is a Linux kernel interface for efficient, asynchronous I/O operations. It was introduced in 2019 with Linux 5.1 to address performance and scalability issues with the traditional I/O system.

Instead of relying on system calls that cause a lot of overhead and process hangs, io\_uring uses ring buffers shared between programs and the system kernel to queue up I/O requests that will be processed asynchronously, allowing the program to keep running.

![io_uring task submission and completion rings](https://www.bleepstatic.com/images/news/u/1220909/2025/April/circles.jpg)

**io\_uring task submission and completion rings**  
_Source: Donald Hunter_

The problem, according to ARMO, arises from the fact that most security tools monitor for suspicious syscalls and hooking (like 'ptrace' or 'seccomp'), completely ignoring anything that involves the io\_ring, creating a very dangerous blindspot.

The researchers explain that io\_uring supports a [wide range of operations](https://developers.redhat.com/articles/2023/04/12/why-you-should-use-iouring-network-io) through 61 ops types, including file read/writes, creating and accepting network connections, spawning processes, modifying file permissions, and reading directory contents, making it a powerful rootkit vector.

Such is the risk that Google decided to [turn it off by default](https://security.googleblog.com/2023/06/learnings-from-kctf-vrps-42-linux.html) on Android and ChromeOS, which use the Linux kernel and inherit many of its underlying vulnerabilities.

To put theory into testing, ARMO created Curing, a special-purpose rootkit that abuses io\_uring to pull commands from a remote server and execute arbitrary operations without triggering syscall hooks.

Testing Curing against several well-known runtime security tools demonstrated that most couldn't detect its activity.

Specifically, Falco was found to be entirely blind even when custom detection rules were used, while Tetragon showed an inability to flag malicious activity under the default configuration.

Tetragon, though, does not consider its platform vulnerable as monitoring can be enabled to detect this rootkit.

"We reported this to the Tetragon team and their response was that from their perspective Tetragon is not 'vulnerable' as they provide the flexibility to hook basically anywhere," explains the researchers.

"They pointed out a good [blog post](https://isovalent.com/blog/post/file-monitoring-with-ebpf-and-tetragon-part-1/) they wrote about the subject."

Testing against commercial tools, ARMO further confirmed the inability to detect io\_uring-based malware and kernel interactions that don't involve syscalls. However, ARMO did not share what commercial programs they tested again.

For those who want to test their environments against this threat, ARMO has made Curing [available for free on GitHub](https://github.com/armosec/curing).

ARMO suggests that the problem can be solved with the adoption of Kernel Runtime Security Instrumentation (KRSI), which allows eBPF programs to be attached to security-relevant kernel events.