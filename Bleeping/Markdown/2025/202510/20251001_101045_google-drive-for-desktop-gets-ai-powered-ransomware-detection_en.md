# Google Drive for desktop gets AI-powered ransomware detection

![Google Drive](https://www.bleepstatic.com/content/hl-images/2025/10/01/Google-Drive.jpg)

Google has begun rolling out a new AI-powered security feature for Google Drive desktop, which will automatically pause file syncing when it detects a ransomware attack to minimize impact.

While this will not block ransomware from encrypting files on the infected computer, users' documents stored in Google Drive will be protected and can be easily restored on a different device or on the compromised computer after the malware infection has been resolved.

The company stated that the feature utilizes a "specialized AI model" trained on "millions of real-world ransomware samples" to rapidly identify and respond to signs that a file has been maliciously altered.

The anti-ransomware engine is also capable of adapting to new ransomware strains by incorporating new threat intelligence from online malware scanning service VirusTotal and continuously analyzing file changes.

"When Drive detects unusual activity that suggests a ransomware attack, it automatically pauses syncing of affected files, helping to prevent widespread data corruption across an organization's Drive and the disruption of work," [Google said](https://workspace.google.com/blog/product-announcements/ai-ransomware-detection-in-google-drive) on Tuesday.

"Users then receive an alert on their desktop and via email, guiding them to restore their files. Unlike traditional solutions that require complex re-imaging or costly third-party tools, the intuitive web interface in Drive allows users to easily restore multiple files to a previous, healthy state with just a few clicks."

![Google Drive ransomware notification](https://www.bleepstatic.com/images/news/u/1109292/2025/Google%20Drive%20ransomware%20notification.webp)

_Google Drive ransomware notification (Google)_

This new capability is [toggled on by default](https://workspaceupdates.googleblog.com/2025/09/ransomware-detection-file-restoration-google-drive.html#:~:text=Ransomware%20detection%20will%20be%20on%20by%20default%20for%20users%20in%20your%20organization) for all Google Drive users on Windows and macOS systems, but IT administrators can turn off ransomware detection (from _Admin console > Apps > Google Workspace > Settings for Drive and Docs > Malware and Ransomware)_ and file restoration (from _Admin console > Apps > Google Workspace > Settings for Drive and Docs > Drive file restoration)_ capabilitiesif needed.

Also, while syncing will be paused automatically on older versions, those who also want to enable ransomware detection alerts must install Google Drive version 114 or later on their computers.

The new ransomware detection feature is available to Google Workspace users with Business Standard/Plus, Enterprise Starter/Standard/Plus, Education Standard/Plus, and Frontline Standard/Plus subscriptions. File restoration is available to all Google Workspace customers, Workspace Individual Subscribers, and users with personal Google accounts.

Google added that it doesn't use the customers' data, such as prompts and generated outputs, to train and fine-tune its generative AI models or for advertising purposes without permission.

Microsoft also provides [ransomware detection and recovery](https://support.microsoft.com/en-gb/office/ransomware-detection-and-recovering-your-files-0d90ec50-6bfd-40f4-acc7-b8c12c73637f) for Microsoft 365 subscribers who use OneDrive to store and sync their files in the cloud. Dropbox, another popular cloud storage service, [has a similar feature](https://help.dropbox.com/security/ransomware-detection) available to teams with Standard, Business, Advanced, or Enterprise subscriptions.