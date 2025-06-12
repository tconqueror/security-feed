# Microsoft Edge now offers secure password deployment for businesses

![Microsoft Edge](https://www.bleepstatic.com/content/hl-images/2025/06/12/Microsoft-Edge.jpg)

Microsoft announced that a new Edge feature allowing employees to share passwords more securely in enterprise environments has reached general availability.

Known as secure password deployment, this feature will be available to Microsoft Edge for Business users starting this week, minimizing the risk of unauthorized access by ensuring that employees don't accidentally share passwords with unintended recipients.

The feature is available for Microsoft 365 Business Premium, E3, and E5 subscriptions and requires the Edge admin or Global admin role.

"In many organizations today, employees often resort to sharing passwords via sticky notes or emails. This not only exposes sensitive credentials to unintended recipients, but also increases the risk of those passwords being forwarded or misused," [Microsoft said](https://blogs.windows.com/msedgedev/2025/06/11/introducing-secure-password-deployment-in-microsoft-edge-for-business/).

"Secure password deployment allows administrators to deploy encrypted shared passwords to a set of users within their organization. With this feature, users will receive the deployed passwords on their device and can seamlessly log into websites."

Secure password deployment is part of the Microsoft Edge management service within the Microsoft 365 admin center, allowing administrators to configure browser settings using policies to deploy encrypted passwords to specific user groups.

![Secure password deployment in M365 admin center](https://www.bleepstatic.com/images/news/u/1109292/2025/M365-admin-center-secure-password-deployment.jpg)

_Secure password deployment in M365 admin center (Microsoft)_

This feature expands on the built-in Autofill experience with an intuitive interface that allows admins to add, update, and revoke credentials.

Once deployed by admins, the passwords will automatically appear in the users' Edge work profiles on managed Windows devices, ready for autofill on the corresponding websites and allowing for a secure login experience.

Although accessible in Edge, these passwords cannot be viewed, edited, deleted (unless allowed by the website), or exported from the password manager.

While there are still ways to gain access to the passwords using the web browser's developer tools, admins can restrict access to them using the [DeveloperToolsAvailability policy](https://learn.microsoft.com/deployedge/microsoft-edge-browser-policies/developertoolsavailability).

![Edge password manager](https://www.bleepstatic.com/images/news/u/1109292/2025/Edge_password_manager.jpg)

_Edge password manager (Microsoft)_

The passwords are encrypted using the Microsoft Information Protection SDK, and this encryption is linked with Entra identities, ensuring that access is automatically enforced based on organizational policies without requiring manual key management.

"This integration brings the power of Microsoft's data protection platform directly into the Edge Management experience, giving administrators a seamless way to deploy credentials securely while aligning with Zero Trust principles and compliance requirements," Microsoft added.

"By embedding the Protection SDK directly into Edge for Business, we extend Microsoft's data protection capabilities all the way to the endpoint—ensuring that sensitive information is safeguarded from configuration to consumption."

To begin using secure password deployment, administrators must first access the [Edge management service](https://admin.microsoft.com/#/Edge/Overview) within the Microsoft 365 admin center and then select an existing configuration policy or create a new one.