# PhantomRaven attack floods npm with credential-stealing packages

![PhantomRaven attack floods npm with credential-stealing packages](https://www.bleepstatic.com/content/hl-images/2025/10/29/package-container.jpg)

An active campaign named ‘PhantomRaven’ is targeting developers with dozens of malicious npm packages that steal authentication tokens, CI/CD secrets, and GitHub credentials.

The activity started in August and deployed 126 npm packages that counted more than 86,000 downloads.

The Node Package Manager (NPM) is the default package manager for Node.js, used by JavaScript developers to share and install reusable code that comes in the form of distributed packages.

PhantomRaven was detected by researchers at [Koi Security](https://www.koi.ai/blog/phantomraven-npm-malware-hidden-in-invisible-dependencies) and includes packages that mimic legitimate projects, and many are the result of AI hallucinated recommendations (“slopsquatting”).

Slopsquatting occurs when developers ask LLMs to suggest packages for a project, and the AI assistants recommend non-existent package names that appear legitimate.

The researchers say that some malicious packages impersonate GitLab or Apache tools. Most of them are still present on the npm platform at the time of writing.

## Overview of the attack

The packages used in the PhantomRaven campaign leverage a remote dynamic dependencies (RDD) system where they declare zero dependencies, but automatically fetch payloads from external URLs during installation.

![Code declaring zero dependencies](https://www.bleepstatic.com/images/news/u/1220909/2025/October/dependency.jpg)

**Code declaring zero dependencies**  
_Source: Koi Security_

The mechanism fetches packages and executes them automatically when running ‘npm install’, and requires no user interaction.

The “side-loaded” payload profiles the infected device to determine the target’s value, and searches the victim’s environment variables for email addresses.

![Searching for the victim's email address](https://www.bleepstatic.com/images/news/u/1220909/2025/October/email(2).jpg)

**Searching for the victim's email address**  
_Source: Koi Security_

Most worryingly, the malware collects tokens for NPM, GitHub Actions, GitLab, Jenkins, and CircleCI, which could be used to introduce malicious changes into other projects and potentially launch [supply chain attacks](https://www.bleepingcomputer.com/news/security/hackers-steal-3-325-secrets-in-ghostaction-github-supply-chain-attack/).

**Secrets targeted in compromised environments**  
_Source: Koi Security_

According to Koi Security, the operators behind the PhantomRaven campaign use three data exfiltration methods: HTTP GET requests with data encoded in the URL, HTTP POST requests with JSON data, and through a WebSocket connection.

PhantomRaven evaded detection for an extended period due to remote dynamic dependencies, which are not visible through static analysis. Koi Security notes that this allows sophisticated threat actors to evade detection.

Software developers should make sure that they are using legitimate packages published by reputable vendors. They should avoid consulting LLMs for package suggestions and double-check search results to discern between authentic and typosquatted projects.

Koi Security's report includes indicators of compromise (IoCs) for the infrastructure used in PhantomRaven attacks and the complete list of malicious packages.