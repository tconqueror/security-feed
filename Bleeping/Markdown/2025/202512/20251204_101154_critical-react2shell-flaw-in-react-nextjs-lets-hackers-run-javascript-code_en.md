# Critical React, Next.js flaw lets hackers execute code on servers

![Critical React, Next.js flaw lets hackers execute code on servers](https://www.bleepstatic.com/content/hl-images/2025/12/04/react.jpg)

A maximum severity vulnerability, dubbed 'React2Shell', in the React Server Components (RSC) 'Flight' protocol allows remote code execution without authentication in React and Next.js applications.

The security issue stems from insecure deserialization. It received a severity score of 10/10 and has been assigned the identifiers CVE-2025-55182 for React and CVE-2025-66478 (CVE rejected in the National Vulnerability Database) for Next.js.

Security researcher [Lachlan Davidson](https://www.linkedin.com/in/lachlan-s-davidson/) discovered the flaw and reported it to React on November 29\. He found that an attacker could achieve remote code execution (RCE) by sending a specially crafted HTTP request to React Server Function endpoints.

"Even if your app does not implement any React Server Function endpoints, it may still be vulnerable if your app supports React Server Components \[RCS\]," warns the [security advisory](https://react.dev/blog/2025/12/03/critical-security-vulnerability-in-react-server-components) from React.

The following packages in their default configuration are impacted:

* react-server-dom-parcel
* react-server-dom-turbopack
* and react-server-dom-webpack

React is an open-source JavaScript library for building user interfaces. It's maintained by Meta and widely adopted by organizations of all sizes for front-end web development.

Next.js, maintained by [Vercel](https://github.com/vercel/next.js/security/advisories/GHSA-9qr9-h5gf-34mp), is a framework built on top of React that adds server-side rendering, routing, and API endpoints.

Both solutions are widely present in cloud environments through front-end applications that help scale and deploy architectures faster and easier.

Researchers at Wiz cloud security platform [warn](http://www.wiz.io/blog/critical-vulnerability-in-react-cve-2025-55182) that the vulnerability is easy to exploit and exists in the default configuration of the affected packages. 

### Impact and fixes

According to React, the vulnerability is present in versions 19.0, 19.1.0, 19.1.1, and 19.2.0\. Next.js is impacted in experimental canary releases starting with 14.3.0-canary.77, and all releases of the 15.x and 16.x branches below the patched versions.

The flaw exists in the 'react-server' package used by React Server Components (RSC), but Next.js inherits it through its implementation of the RSC "Flight" protocol.

Wiz researchers say that 39% of all cloud environments where they have visibility contain instances of Next.js or React running versions vulnerable to CVE-2025-55182, CVE-2025-66478, or both.

The same vulnerability likely exists in other libraries that implement React Server, including the Vite RSC plugin, Parcel RSC plugin, React Router RSC preview, RedwoodSDK, and Waku.

Software supply-chain security company Endor Labs [explains](https://www.endorlabs.com/learn/critical-remote-code-execution-rce-vulnerabilities-in-react-and-next-js) that the React2Shell "is a logically insecure deserialization vulnerability where the server fails to properly validate the structure of incoming RSC payloads."

There is a validation failure when receiving the malformed data from the attacker, which results in executing privileged JavaScript code in the context of the server.

Davidson created a [React2Shell website](http://react2shell.com/), where he will publish technical details. The researcher is also warning that there are proof-of-concept (PoCs) exploits that are not genuine.

These PoCs invoke functions like _vm#runInThisContext_, _child\_process#exec_, and _fs#writeFile,_ but a genuine exploit does not need this, the researcher says.

"This would only be exploitable if you had consciously chosen to let clients invoke these, which would be dangerous no matter what," Davidson notes.

He further explained that these fake PoCs would not work with Next.js since these functions are not present due to the list of server functions being managed automatically.

Developers are strongly advised to apply the fixes available in React versions 19.0.1, 19.1.2, and 19.2.1, and Next.js versions 15.0.5, 15.1.9, 15.2.6, 15.3.6, 15.4.8, 15.5.7, and 16.0.7.

Organizations should audit their environments to determine if they use a vulnerable version and take the appropriate action to mitigate the risk.

The popularity of the two solutions is reflected in the number of weekly downloads, as React counts [55.8 million](https://www.npmjs.com/package/react) on the Node Package Manager (NPM), and Next.js has [16.7 million](https://www.npmjs.com/package/next) on the same platform.