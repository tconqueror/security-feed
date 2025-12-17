# Amazon: Ongoing cryptomining campaign uses hacked AWS accounts

![Amazon: Ongoing cryptomining campaign uses hacked AWS accounts](https://www.bleepstatic.com/content/hl-images/2025/05/16/Cryptocurrency.jpg)

Amazon’s AWS GuardDuty security team is warning of an ongoing crypto-mining campaign that targets its Elastic Compute Cloud (EC2) and Elastic Container Service (ECS) using compromised credentials for Identity and Access Management (IAM).

The operation started on November 2nd and employed a persistence mechanism that extended mining operations and hindered incident responders.

The threat actor used a Docker Hub image that was created at the end of October and had more than 100,000 pulls.

[![Wiz](https://www.bleepstatic.com/content/webinar-images/Action1-970x250-watch-now.jpg)](/mgo/72/) 

The Amazon EC2 service lets users run virtual machines in AWS, while ECS allows running containerized applications (e.g., Docker apps) on the cloud platform.

Planting crypto-miners on these instances allows threat actors to profit financially at the expense of AWS customers and Amazon, who must bear the burden of computational resource exhaustion.

Amazon says that the attacker did not leverage a vulnerability but used valid credentials in customer accounts.

### Crypto-mining operations

AWS said in a report released today that the attacker started cryptomining within 10 minutes of initial access, following reconnaissance of EC2 service quotas and IAM permissions.

This was possible by registering a task definition pointing to the Docker Hub image _yenik65958/secret_, created on October 29, which included an SBRMiner-MULTI cryptominer and a startup script to launch it automatically when the container started.

Each task was configured with 16,384 CPU units and 32GB of memory, and the desired count for ECS Fargate tasks was set to 10.

![Cryptomining diagram](https://www.bleepstatic.com/images/news/u/1220909/2025/December/image-2-diagram.jpg)

**Cryptomining diagram**  
_Source: Amazon_

On Amazon EC2, the attacker created two launch templates with startup scripts that automatically initiated cryptomining, along with 14 auto-scaling groups configured to deploy at least 20 instances each, with a maximum capacity of up to 999 machines.

### Novel persistence method

Once the machines were running, the attacker enabled a setting that prevents administrators from remotely terminating them, forcing responders to explicitly disable the protection before shutting them down. This was likely introduced to delay response and maximize cryptomining profits.

"An interesting technique observed in this campaign was the threat actor’s use of _ModifyInstanceAttribute_ across all launched EC2 instances to disable API termination," Amazon [explains](https://aws.amazon.com/blogs/security/cryptomining-campaign-targeting-amazon-ec2-and-amazon-ecs/).

"Although instance termination protection prevents accidental termination of the instance, it adds an additional consideration for incident response capabilities and can disrupt automated remediation controls," the company says.

After identifying the campaign, Amazon alerted affected customers about the cryptomining activity and the need to rotate the compromised IAM credentials.

Also, the malicious Docker Hub image has been removed from the platform, but Amazon warns that the threat actor could deploy similar images under different names and publisher accounts.