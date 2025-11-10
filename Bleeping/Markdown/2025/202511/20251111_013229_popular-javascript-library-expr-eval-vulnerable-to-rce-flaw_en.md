# Popular JavaScript library expr-eval vulnerable to RCE flaw

![Popular JavaScript library expr-eval vulnerable to RCE flaw](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_headpic.jpg)

A critical vulnerability in the popular _expr-eval_ JavaScript library, with over 800,000 weekly downloads on NPM, can be exploited to execute code remotely through maliciously crafted input.

The security issue was discovered by security researcher Jangwoo Choe and is tracked as [CVE-2025-12735](https://nvd.nist.gov/vuln/detail/CVE-2025-12735). According to the U.S. Cybersecurity and Infrastructure Security Agency (CISA), the severity rating is critical, with a score of 9.8.

Originally developed by Matthew Crumley, [expr-eval](https://www.npmjs.com/package/expr-eval) is a small JavaScript expression parser and evaluator, used in projects that require safe parsing and computation of user-supplied mathematical expressions at runtime.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Examples include online calculators, educational suites, simulation tools, financial tools, and, more recently, AI and natural language processing (NLP) systems that parse mathematical expressions from text prompts.

In an advisory over the weekend, the CERT Coordination Center (CERT-CC) for Carnegie Mellon's Software Engineering Institute (SEI) says that the vulnerability is due to the library’s failure to validate the variables/context object passed into the _Parser.evaluate()_ function, which allows an attacker to supply malicious function objects that the parser invokes during evaluation.

"The vulnerability gives the adversary total control over the behavior of the software or total disclosure of all information on the affected system" - [CERT-CC](https://kb.cert.org/vuls/id/263614) 

CVE-2025-12735 affects both the original expr-eval, with a stable version released 6 years ago, and its currently actively maintained fork, _expr-eval-fork_, which has over 80,000 weekly downloads on the NPM package registry for Node.js.

Based on data from npmjs.com, the library is used in more than 250 projects. A security fix for CVE-2025-12735 is present in the [expr-eval-fork version 3.0.0](https://www.npmjs.com/package/expr-eval-fork), with the recommendation that impacted projects switch to it as soon as possible.

The patch enforces an allowlist of safe functions for evaluation, a registration system for custom functions, and improved test coverage for these constraints.

For users of expr-eval, there is a [pull request](https://github.com/silentmatt/expr-eval/pull/288) that implements the fix; however, due to the project maintainers being unresponsive, it is unknown when it will be merged into a new release.

Impacted software developers are advised to migrate immediately to expr-eval-fork v3.0.0 and republish their libraries so users receive the fix.