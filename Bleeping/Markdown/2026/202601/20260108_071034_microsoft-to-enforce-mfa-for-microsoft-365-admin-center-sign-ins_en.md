# Microsoft to enforce MFA for Microsoft 365 admin center sign-ins

![Microsoft](https://www.bleepstatic.com/content/hl-images/2025/08/06/Microsoft.jpg)

Microsoft will start enforcing multi-factor authentication (MFA) for all users accessing the Microsoft 365 admin center starting next month.

While MFA requirements for the admin center began rolling out in February 2025, Microsoft will now enforce this for all users and block those without MFA enabled from signing in to the Microsoft 365 administrative portal after the change goes live on February 9th, 2026.

This will affect the portal.office.com/adminportal/home, admin.cloud.microsoft, and admin.microsoft.com admin center URLs used by IT administrators to manage Microsoft 365 accounts and services.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Microsoft said that enforcing MFA for all admin center sign-ins adds critical protection beyond standard password security, making it significantly harder for attackers to compromise accounts.

"Implementing MFA in the Microsoft 365 admin center significantly reduces the risk of account compromise, prevents unauthorized access, and safeguards sensitive data," [Microsoft said](https://admin.microsoft.com/#/MessageCenter/:/messages/MC1215070).

"By adding an extra layer of protection beyond standard username and password authentication, MFA makes it harder for attackers to steal data and prevents unauthorized access from phishing, credential stuffing, brute force, or password reuse attacks."

Microsoft also urged admins to take immediate action to avoid interruptions to IT operations and administrative functions, as organizations that fail to enable MFA before the February deadline will experience access disruptions when administrators start experiencing sign-in failures.

Global administrators can configure MFA using [Microsoft's setup wizard](https://aka.ms/MFAWizard) or by following the [official documentation](https://learn.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide). Individual users can check their verification methods and add authentication options through [Microsoft's MFA setup portal](https://aka.ms/mfasetup).

Microsoft has also been enforcing MFA for Azure Portal sign-ins across all tenants since March 2025, a change announced [in May 2024,](https://www.bleepingcomputer.com/news/microsoft/microsoft-will-start-enforcing-azure-multi-factor-authentication-MFA-in-july-2024/) when it began requiring MFA for all users signing in to Azure to administer resources. It also [started enforcing MFA](https://www.bleepingcomputer.com/news/microsoft/microsoft-to-enforce-mfa-for-azure-resource-management-in-october/) on Azure CLI, PowerShell, SDKs, and APIs in October 2025 to protect users' accounts against attacks.

A [Microsoft study](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/final/en-us/microsoft-brand/documents/MFA-Microsoft-Research-Paper-update.pdf) from November 2023 found that 99.99% of MFA-protected accounts successfully block hacking attempts, and that MFA also reduced the chance of account compromise by 98.56% even when the credentials are compromised.