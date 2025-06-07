# Malicious npm packages posing as utilities delete project directories

![NPM](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_logo_headpic.jpg)

Two malicious packages have been discovered in the npm JavaScript package index, which masquerades as useful utilities but, in reality, are destructive data wipers that delete entire application directories.

The data wiper packages are 'express-api-sync' and 'system-health-sync-api,' and pose as database syncing and system health monitoring Tools.

According to open-source software security firm Socket, they both contain backdoors that enable remote data-wiping actions at the infected host.

The packages were published on npm in May 2025 and have been removed from npm following their reporting by Socket.

The firm's historic stats show that express-api-sync was downloaded by unsuspecting developers [855 times](https://socket.dev/npm/package/system-health-sync-api), while express-api-sync had [104 downloads](https://socket.dev/npm/package/express-api-sync).

The first package, express-api-sync, registers a hidden POST endpoint (/api/this/that) and waits for requests that contain the secret key 'DEFAULT\_123.'

Once it receives it, it executes "rm -rf \*" in the application's directory, deleting all files.

"Once triggered, the rm -rf \* command executes in the application's working directory, deleting all files, including source code, configuration files, uploaded assets, and any local databases," explains the [Socket report](http://socket.dev/blog/destructive-npm-packages-enable-remote-system-wipe).

"The endpoint returns status messages to the attacker indicating success ({"message":"All files deleted"}) or failure of the destruction."

The second package, 'system-health-sync-api,' is more sophisticated.

It registers multiple backdoor endpoints at:

* GET /\_/system/health → returns server status
* POST /\_/system/health → primary destruction endpoint
* POST /\_/sys/maintenance → backup destruction endpoint

In this case, the secret key is 'HelloWorld,' triggering reconnaissance followed by remote, OS-specific destruction.

The wiper supports both Linux ('rm -rf \*') and Windows ('rd /s /q .') deletion commands, so it uses the right one depending on the detected architecture.

![Multi-platform destruction](https://www.bleepstatic.com/images/news/u/1220909/2025/June/winlinux.jpg)

**Multi-platform destruction**  
_Source: Socket_

Once the action is complete, the wiper emails the attacker to ‘anupm019@gmail.com' with the backend URL, the system fingerprint, and the result of the file wipe.

The attacker also receives more immediate feedback to their original request via an HTTP response, which confirms whether the destructive command succeeded in real time.

Cases of data wipers in npm are unusual, as they serve no financial gain or data theft purpose, which is the typical case when malware slips onto software distribution platforms.

Socket comments on this by characterizing the two packages as "a concerning addition to npm's threat landscape," which could signify state-level or sabotage activity creeping into the ecosystem.

"These packages don't steal cryptocurrency or credentials—they delete everything," concludes Socket.

"This suggests attackers motivated by sabotage, competition, or state-level disruption rather than being solely financially motivated."