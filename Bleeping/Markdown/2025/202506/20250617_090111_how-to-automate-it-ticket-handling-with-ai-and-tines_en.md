# How to automate IT ticket handling with AI and Tines

![Tines header](https://www.bleepstatic.com/content/posts/2025/06/11/tines-header.jpg)

Run by the team at workflow orchestration and AI platform Tines, the Tines library features pre-built workflows shared by IT and security practitioners from across the community - all free to import and deploy through the platform’s [Community Edition](https://www.tines.com/community-edition/?utm%5Fsource=BleepingComputer&utm%5Fmedium=paid%5Fmedia&utm%5Fcontent=article-1706).

A recent standout is a ticket-handling workflow developed by Connor Brewer, Principal Solutions Architect at Uzado Inc., a Canadian IT and security service provider.

Built with Tines Pages and powered by AI, the workflow invites employees to submit common IT issues through a simple form, then automatically responds or routes the ticket to the right practitioner, reducing manual triage and speeding up resolution.

“At Uzado, these types of requests account for roughly 20% of IT tickets,” Connor explains. “We estimate that 10% of these could be resolved automatically, representing significant time savings and enabling analysts to focus on more complex challenges. The benefits extend to end users as well, who often prefer instant, AI-guided troubleshooting over waiting for IT responses.”

In this guide, we’ll share an overview of the workflow and walk you through setting it up in your own environment.

## The problem – manual ticket handling that drains time and focus

IT teams deal with a steady stream of support tickets, many of which are simple and repetitive, like audio issues or password resets. These low-effort tasks consume a disproportionate amount of practitioner time and introduce challenges like:

* Alert fatigue from high ticket volumes
* Context switching that interrupts deeper project work
* Slow response times for end users who need quick resolutions

Uzado wanted to streamline how their team handled routine requests, without sacrificing service quality or analyst control.

## [What Will You Automate? The Top Ways IT Teams are Modernizing Their Operations](https://www.tines.com/access/guide/unlocking-it-agility-with-automation-patch-management/?utm%5Fsource=BleepingComputer&utm%5Fmedium=paid%5Fmedia&utm%5Fcontent=article-intext-CTA)

With threat actors moving faster and CVEs hitting record highs, manual patching simply can’t keep up.

Discover how teams are taking the pain out of patch management. Learn how you can strengthen both IT operations and your organization’s security posture with automated, scalable workflows.

[Get the guide](https://www.tines.com/access/guide/unlocking-it-agility-with-automation-patch-management/?utm%5Fsource=BleepingComputer&utm%5Fmedium=paid%5Fmedia&utm%5Fcontent=article-intext-CTA)

## The solution – an AI-powered self-service IT help desk app

Connor’s workflow tackles the problem by giving users a simple self-service interface built with Tines Pages. It leverages AI to analyze and triage incoming requests, determining whether to auto-resolve or escalate them.

![A sample webpage with form, built using Tines Pages](https://www.bleepstatic.com/images/news/security/t/tines/automated-ticket-handling/sample-web-page.png)

**A sample webpage with form, built using Tines Pages**

Here’s how it works:

* User submission: A form powered by Tines Pages captures the request (e.g., "My Zoom audio isn't working").
* AI triage: The workflow uses AI to analyze the request, summarizing it and determining whether it’s user-actionable.
* Automated response: If the issue is simple (e.g., audio muted in Zoom), the app sends a helpful, step-by-step resolution. If it requires deeper investigation, it automatically escalates the issue to a support analyst.

![A sample response that the user might receive](https://www.bleepstatic.com/images/news/security/t/tines/automated-ticket-handling/sample-response.png)

**A sample response that the user might receive**

Key benefits of this workflow

* Time savings by eliminating manual triage for routine issues
* Better user experience with instant feedback and guidance
* Improved morale as analysts focus on more meaningful work
* Scalability without increasing headcount
* Customizable for teams in IT, security, DevOps, and more

## Workflow overview

### Tools used

* **Tines** – workflow orchestration and AI platform (Community Edition available)
* **Tines Pages** – a product feature that enables you to build interactive forms and apps
* **Large Language Model (LLM)** – powers triage and response logic; customers can choose their preferred AI model in Tines
* **Slack or other system integrations** for escalations

### Sample AI prompt

Here’s the LLM prompt Connor used to craft actionable responses:

_You are an expert helpdesk assistant who analyzes requests received by a support team in a Managed Service Provider company._

_Your responses are strictly JSON objects without any preamble text or summary text after the JSON._

_You create a title for the request, summarize the requests, recommend some actions as an array that could help solve the customer's problems, a polite response to acknowledge the user's request informing them a support agent will reach out to them shortly, and determine whether or not this problem is something a regular user could solve without any special technical knowledge._

_Please be very conservative with what you believe is end user actionable. Do not request they reach out to any IT support themselves. Do not request the requestor elaborates on their request._

_Analyze the following request and respond using the fields listed below:_

* _title_
* _summary_
* _recommended_action_
* _request_acknowledgement_
* _end_user_actionable_

_Some assumptions you should hold to be true:_

_The end user is asking about their personal device or a company-owned device unless otherwise stated._

_If this is end user actionable, the response you provide needs to be tailored to the requestor in a way that they can themselves solve the problem if you deem that it is a problem which can be resolved by a typical user. If it is not, please tailor the response to an IT professional._

## Configuring the workflow - step-by-step guide

**The Tines Community Edition sign-up form**

1\. Log into Tines or create a new account.

2\. Ensure AI is enabled on your tenant. For this, you need to be the tenant owner. Select the account settings drop-down in the top left of your screen, and check the box to turn AI on.

**The workflow on Tines’ drag-and-drop canvas**

3\. Navigate to the [pre-built workflow in the library](https://www.tines.com/library/stories/1270850/?name=self-service-helpdesk-with-ai-and-pages?utm%5Fsource=BleepingComputer&utm%5Fmedium=paid%5Fmedia&utm%5Fcontent=article-1706). Select import. This should take you straight to your new pre-built workflow.

**Adding a new credential in Tines**

4\. (Optional) Set up credentials for any additional tools you’d like to use.

While the core workflow uses Tines Pages and AI for triage and response, you can optionally integrate additional tools for escalations or notifications - for example, sharing unresolved tickets via Slack.

To connect these tools:

To create a new credential from the Storyboard, click the plus (+) icon beside Credentials on the storyboard to the right, then search for and select your credential from the list to get started. Follow the credential setup guides at explained.tines.com if you need help.

**Editing the Tines page**

5\. Configure your actions: Edit the layout of your Tines Page, adjust the AI prompt as needed, and configure any optional escalation or notification actions.

6\. Test the workflow: Submit a request via the form to test your workflow.

7\. Publish and operationalize: Publish your workflow and share the Page URL with your desired users.

**To try this workflow for yourself, you can sign up for a [free Tines account](https://www.tines.com/community-edition/?utm%5Fsource=BleepingComputer&utm%5Fmedium=paid%5Fmedia&utm%5Fcontent=article-1706).**

_Sponsored and written by [Tines](https://www.tines.com/community-edition/?utm%5Fsource=BleepingComputer&utm%5Fmedium=paid%5Fmedia&utm%5Fcontent=article-1706)._