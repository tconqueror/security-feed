# Microsoft fixes highest-severity ASP.NET Core flaw ever

![Microsoft](https://www.bleepstatic.com/content/hl-images/2025/08/06/Microsoft.jpg)

Earlier this week, Microsoft patched a vulnerability that was flagged with the "highest ever" severity rating received by an ASP.NET Core security flaw.

This HTTP request smuggling bug ([CVE-2025-55315](https://nvd.nist.gov/vuln/detail/CVE-2025-55315)) was found in the Kestrel ASP.NET Core web server, and it enables authenticated attackers to smuggle another HTTP request to hijack other users' credentials or bypass front-end security controls.

"An attacker who successfully exploited this vulnerability could view sensitive information such as other user's credentials (Confidentiality) and make changes to file contents on the target server (Integrity), and they might be able to force a crash within the server (Availability)," Microsoft said in a [Tuesday advisory](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-55315).

To ensure that their ASP.NET Core applications are secured against potential attacks, Microsoft advises developers and users to take the following measures:

* If running .NET 8 or later, install the .NET update from Microsoft Update, then restart your application or reboot the machine.
* If running .NET 2.3, update the package reference for Microsoft.AspNet.Server.Kestrel.Core to 2.3.6, then recompile the application, and redeploy.
* If running a self-contained/single-file application, install the .NET update, recompile, and redeploy.

To address the vulnerability, Microsoft [has released security updates](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-55315#securityUpdates) for Microsoft Visual Studio 2022, ASP.NET Core 2.3, ASP.NET Core 8.0, and ASP.NET Core 9.0, as well as the Microsoft.AspNetCore.Server.Kestrel.Core package for ASP.NET Core 2.x apps.

As .NET security technical program manager Barry Dorrans explained, the impact of CVE-2025-55315 attacks would depend on the targeted ASP.NET application, and susccesful exploitation could allow the threat actors to log in as a different user (for privilege escalation), make an internal request (in server-side request forgery attacks), bypass cross-site request forgery (CSRF) checks, or perform injection attacks.

"But we don't know what's possible because it's dependent on how you've written your app. Thus, we score with the worst possible case in mind, a security feature bypass which changes scope," [Dorrans said](http://github.com/dotnet/aspnetcore/issues/64033#issuecomment-3403054914).

"Is that likely? No, probably not unless your application code is doing something odd and skips a bunch of checks that it ought to be making on every request. However please go update."

During this month's Patch Tuesday, Microsoft [released security updates for 172 flaws](https://www.bleepingcomputer.com/news/microsoft/microsoft-october-2025-patch-tuesday-fixes-6-zero-days-172-flaws/), including eight "Critical" vulnerabilities and six zero-day bugs (three of which were exploited in attacks).

This week, Microsoft also published KB5066791, a cumulative update that includes [the final Windows 10 security updates](https://www.bleepingcomputer.com/news/microsoft/final-windows-10-patch-tuesday-update-rolls-out-as-support-ends/) as the operating system reaches the end of its support lifecycle.