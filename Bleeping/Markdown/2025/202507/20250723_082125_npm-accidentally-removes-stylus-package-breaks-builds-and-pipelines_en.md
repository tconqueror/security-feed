# npm 'accidentally' removes Stylus package, breaks builds and pipelines

![npm](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_logo_headpic.jpg)

npm has taken down all versions of the real Stylus library and replaced them with a "security holding" page, breaking pipelines and builds worldwide that rely on the package.

A security placeholder webpage is typically displayed when malicious packages and libraries are removed by the admins of npmjs.com, the world's largest software registry primarily used for JavaScript and Node.js development.

But that isn't quite the case for Stylus: a legitimate "revolutionary" library receiving 3 million weekly downloads and providing an expressive way for devs to generate CSS.

## Stylus 'accidentally banned by npmjs'

As of a few hours ago, npmjs has removed all versions of the Stylus package and published a "security holding package" page in its place.

![all versions of npm package 'stylus' removed and replaced with a 'security placeholder' page](https://www.bleepstatic.com/images/news/u/1164866/2025/Jul/npm-stylus-ban/placeholder-stylus.jpg)

**All versions of 'stylus' removed and replaced with a 'security placeholder' page**  
(npmjs.com)

"Stylus was accidentally banned by npmjs," [states](https://github.com/stylus/stylus/issues/2938) Stylus developer Lei Chen in a GitHub issue. The project maintainer is "currently waiting for npmjs to restore access to Stylus."

"I am the current maintainer of Stylus. The Stylus library has been flagged as malicious..., which has caused many \[libraries\] and frameworks that depend on Stylus to fail to install," also [posted](https://x.com/chenleidev/status/1947878300086624601) Chen on X (formerly Twitter). "Please help me retweet this msg in the hope that the npmjs official team will take notice of this issue."

Stylus' original npmjs page (shown below) indicates that the legitimate library is a "revolutionary new language" for CSS development and nets close to 3 million downloads weekly.

![Stylus package on npm receives millions of downloads](https://www.bleepstatic.com/images/news/u/1164866/2025/Jul/npm-stylus-ban/stylus-npm.jpg)

**Stylus package on npm receives millions of downloads** (BleepingComputer)

Surely enough, developers of different projects relying on Stylus chimed in:

"My builds are failing so my software updates don't publish because this administrative error," [posted](https://x.com/i%5Fw%5Fh%5Fo/status/1947939151841538404) one developer.

Packages like [typescript-plugin-css-modules](https://www.npmjs.com/package/typescript-plugin-css-modules) (downloaded up to 500,000 times weekly) also rely on Stylus, [noted](http://x.com/Seniya%5FS/status/1947926005328347377) full-stack developer Chanuka Asanka:

"Pipelines are failing. Does anyone know whether npm/yarn provides any early notice when they are going to do such thing?"

**Stylus is depended-upon by large projects** (BleepingComputer)

"I was deploying Frappe/ERPNext like I usually do with the CI/CD pipeline and it failed suddenly," [wrote](https://discuss.frappe.io/t/stylus-malicious-npm-package-removed-but-present-in-frappe-fails-to-build-docker/150549) a Docker developer in a Frappe forums thread.

## What _really_ happened?

Typically, packages are taken down on npm for violating one or more of their open source [terms of service](https://docs.npmjs.com/policies/open-source-terms), and fairly commonly for containing malicious code. But that is not the case for Stylus—all versions of which appear to be clean and functional.

Tom Abai, a security researcher at supply chain security firm Mend.io, has it figured out.

While investigating the development, Abai [confirmed](https://x.com/abai%5Ftom/status/1947933649577341062) that at least the most recent version (0.64.0) of Stylus was "clean," but something odd stood out in connection with the package:

**Mend.io researcher shedding light on the development** (Tom Abai via X)

"...one weird thing came \[up\] in our investigation, and that this owner _panyakor_..., that looks like he was part of the stylus npm package owners, published 3 malicious packages last week..." wrote Abai.

npmjs.com, like many open source development platforms, allows multiple maintainers to be listed for and contribute to a package. While Chen may be the primary developer of Stylus, there are other npm accounts listed under maintainers.

"Panya, who is one of the maintainers of the stylus package, published them, and because of that, his account was banned, and all the packages that were connected to him were yanked, including the Stylus one. So that's the story here. A big false alarm by NPM," states Abai.

BleepingComputer further confirmed that the npm account '[panya](https://www.npmjs.com/~panya)' was indeed listed among maintainers on npmjs.com for both Stylus and the 3 packages listed in Abai's post that are otherwise unrelated to Stylus.

The packages flagged by Abai: _@pwa-ib/eslint-plugin-compat_, _@blocks-shared/desktop-title_, _@tui-react-internal/select-account-icon_, published by 'panya', now require authentication to access on npmjs.com registry and therefore are restricted from the public view.

BleepingComputer was, however, able to obtain and peek into these packages, and we can confirm Abai's findings.

For example, the "extract.js" file in @blocks-shared/desktop-title contains a proof-of-concept [dependency confusion](https://www.bleepingcomputer.com/tag/dependency-confusion/) exploit that the industry has seen several times by now:

**Dependency confusion PoC code seen in a package published by a Stylus co-maintainer**  
(Bleeping Computer)

[According to](https://socket.dev/npm/user/panya) supply chain security firm Socket, npm account 'panya' had been a maintainer for (and/or published) at least 12 packages in the past:

**npm account panya has been associated with 12 packages** (Socket.dev)

At the time of writing, though, the account has no packages listed under it, indicating that the registry likely purged all of its PoC exploits and removed Stylus in the process, by accident.

BleepingComputer approached npm registry and its parent organization, GitHub, for comment on the matter before publishing.

## What can you do?

Luckily, the Stylus developer and the open source community members have [shared detailed tips in the meantime](https://github.com/stylus/stylus/issues/2938) for npm and yarn developers relying on Stylus to maintain access to the library and restore their builds.

npm developers can opt to reference the stylus package "dynamically by specifying a branch, tag, or commit hash in the `dependencies` section of `package.json`," states Chen, such as:

```json
{
  "dependencies": {
    "stylus": "github:stylus/stylus#version-you-need"
  }
}
```

Using overrides is another option for npm developers:

"You can override the `stylus` package version used by other dependencies by specifying it in the `overrides` section (supported in npm v8.3.0 and later)"

```json
{
  "overrides": {
    "stylus": "github:stylus/stylus#version-you-need"
  }
}
```

**"Note**: Ensure the specified tag, branch, or commit (e.g., `0.54.4`) exists in the `stylus/stylus` repository. Clear the npm cache (`npm cache clean --force`) if you encounter issues with outdated dependencies."

To summarize, Chen reiterates:

"Stylus does not contain malicious code; this has been confirmed. _npmmirror.com_ (a non-profit mirror sponsored by Alibaba) has resumed access \[to the library\]," [wrote](https://github.com/stylus/stylus/issues/2938#issue-3254793141) Lei Chen.  
  
It is unclear whether this is a coincidence, but a tool called Stylus Tools component has been [reported to have a CVE](https://nvd.nist.gov/vuln/detail/CVE-2025-6044).  
  
_Panya_ (the former maintainer of Stylus) used their own account to release a package containing malicious code (for security research purposes? I am unsure), but did not release a new version of Stylus containing malicious code.  
  
We are awaiting official action from npmjs. Yes, we are waiting for them to handle it.  
  
A workaround has been provided in the comments. Please apply it as needed."

In the past, open source developers have made headlines for breaking builds by [pulling their libraries](https://qz.com/646467/how-one-programmer-broke-the-internet-by-deleting-a-tiny-piece-of-code) from registries over disagreements or outright [corrupting their code in protest](https://www.bleepingcomputer.com/news/security/dev-corrupts-npm-libs-colors-and-faker-breaking-thousands-of-apps/).

This incident marks the first notable instance of a registry taking down an entire legitimate project in what appears to be an administrative error.