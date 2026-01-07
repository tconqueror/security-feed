# Critical jsPDF flaw lets hackers steal secrets via generated PDFs

![Critical jsPDF flaw lets hackers steal secrets via generated PDFs](https://www.bleepstatic.com/content/hl-images/2024/12/10/hacker-box.jpg)

The jsPDF library for generating PDF documents in JavaScript applications is vulnerable to a critical vulnerability that allows an attacker to steal sensitive data from the local filesystem by including it in generated files.

The flaw is a local file inclusion and path traversal that allows passing unsanitized paths to the file loading mechanism (loadFile) in jsPDF versions before 4.0\. It is tracked as [CVE-2025-68428](https://nvd.nist.gov/vuln/detail/CVE-2025-68428) and received a severity score of 9.2.

The jsPDF library is a widely adopted package with more than [3.5 million weekly downloads](https://www.npmjs.com/package/jspdf) in the npm registry.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

In jsPDF’s Node.js builds, the 'loadFile' function is used for reading the local filesystem. The problem arises when user-controlled input is passed as the file path, causing jsPDF to incorporate into the generated PDF output the content of the file.

![Exploitation example](https://www.bleepstatic.com/images/news/u/1100723/jsPDF_CVE-2025-68428_attack.png)

**Exploitation example**  
_Source: Parallax_

Other file loading methods are also affected, including 'addImage', 'html', and 'addFont', as all can call the loadFile function.

According to the [jsPDF security bulletin](http://github.com/parallax/jsPDF/security/advisories/GHSA-f8cm-6447-x5h2), the issue only affects the Node.js builds of the library, namely the _dist/jspdf.node.js_ and _dist/jspdf.node.min.js_ files.

In a detailed technical report, application security company Endor Labs says that the exploitation risk is low or nonexistent if file paths are hardcoded, come from a trusted configuration, or strict allowlists are used for inputs.

CVE-2025-68428 was fixed in version 4.0.0 of jsPDF by restricting filesystem access by default and relying instead on Node.js permission mode.

However, Endor Labs [researchers note](https://www.endorlabs.com/learn/cve-2025-68428-critical-path-traversal-in-jspdf) that this mode is experimental in Node 20, so versions 22.13.0, 23.5.0, or 24.0.0 and later are recommended.

Another caveat to consider is that enabling the ‘--permission’ flag, a workaround suggested by the developers, affects the entire Node.js process, not just jsPDF.

Endor Labs also underlines that overly broad filesystem permissions added to the '--allow-fs-read' configuration flag negate the fix.

**Overly permissive configuration**  
_source: Endor Labs_

The jsPDF team recommends that older Node versions sanitize user-provided paths before passing them to jsPDF.

Given the broad deployment of jsPDF on numerous projects, CVE-2025-68428 is a good candidate for active exploitation.