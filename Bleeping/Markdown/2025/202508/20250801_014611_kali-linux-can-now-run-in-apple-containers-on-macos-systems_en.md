# Kali Linux can now run in Apple containers on macOS systems

![Kali Linux](https://www.bleepstatic.com/content/hl-images/2022/02/14/kali-bright.jpg)

Cybersecurity professionals and researchers can now launch Kali Linux in a virtualized container on macOS Sequoia using Apple's new containerization framework.

During WWDC 2025, [Apple announced](http://www.apple.com/newsroom/2025/06/apple-supercharges-its-tools-and-technologies-for-developers/) a new containerization framework that allows Apple Silicon hardware to run isolated Linux distros in its virtualized environment, similar to Microsoft Windows Subsystem for Linux 2 (WSL2).

To get started, users on macOS Sequoia with Apple Silicon can install the [container CLI ](https://github.com/apple/container?utm%5Fsource=chatgpt.com)via Homebrew and initialize Apple's container framework:

```
brew install --cask container
container system start
```

You can then launch Kali Linux using the following command, which loads the container from the [DockerHub container library](https://hub.docker.com/r/kalilinux/kali-rolling) and executes inside a macOS VM.

```
container run --rm -it kalilinux/kali-rolling
```

You can also use a container to mount a local directory into the Kali VM with a command like:

```
container run --remove --interactive --tty --volume $(pwd):/mnt --workdir /mnt docker.io/kalilinux/kali-rolling:latest
```

This command allows you to access files on the host device from within the container.

However, there are some limitations to the new feature, as it's only available on Apple Silicon and does not support Intel Macs.

Also, the Kali team reports that there are some bugs with the new implementation around networking.

"Currently there are a [few known limitations of Containerization, especially using macOS "Sequoia" 15](https://github.com/apple/container/blob/main/docs/technical-overview.md#macos-15-limitations), such as [container's network access not getting an IP address or no network access](https://github.com/apple/container/blob/main/docs/technical-overview.md#container-ip-addresses)," reads [Kali's announcement](https://www.kali.org/blog/kali-apple-container-containerization/).

"We recommend reading and following Apple's advice if you run into these issues."

Cybersecurity professional Taha Ex [also warns](https://medium.com/%40e3x3e/integrating-kali-linux-with-macos-using-apples-new-containerization-feature-2025-ef645ba51671) that some Kali use cases that require hardware passthrough will not work due to the container being isolated from hardware.

The ability to quickly launch Kali Linux in macOS, even if in a virtualized environment, and with some limitations, makes it easier for Mac users to perform security testing.