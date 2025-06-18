# Asana warns MCP AI feature exposed customer data to other orgs

![Data leak](https://www.bleepstatic.com/content/hl-images/2024/08/16/data-leak.jpg)

Work management platform Asana is warning users of its new Model Context Protocol (MCP) feature that a flaw in its implementation potentially led to data exposure from their instances to other users and vice versa.

The data exposure was due to a logic flaw in the MCP system and not the result of a hack, but the risk that arises from the incident could still be significant in some cases.

Asana is a project and task management SaaS platform used by organizations to plan, track, and manage work, assign tasks to team members, set deadlines, and collaborate from a centralized interface.

As of last year, the platform had over 130,000 paying customers and millions of free-tier users across 190 countries.

On May 1, 2025, Asana introduced the MCP server feature with large language model (LLM) integration, enabling AI-powered capabilities such as summarization, smart replies, natural language queries, and more.

However, a software bug in the MCP server exposed data from Asana instances to other MCP users, with the data type being limited to each user's access scope.

This means that organizations did not have their entire Asana workspace leaked to the public. Still, other companies' users with access to MCP might have seen certain data from another domain, including chatbot-generated queries.

Depending on the integration type and engagement with the chatbots, the exposed data could include task-level information, project metadata, team details, comments and discussions, and any uploaded files.

Asana discovered the logic flaw that created this exposure on June 4, so these cross-organization data leaks occurred for over a month.

Given the functional role of Asana within organizations, it is possible that these leaks contained sensitive information that could create privacy or even regulatory complexities for impacted entities.

For this reason, it is recommended that admins review Asana logs for MCP access, review generated AI summaries or answers, and report it immediately if they see data that appears to have been pulled from another organization.

LLM integration should be set to restricted access, and auto-reconnections and bot pipelines should be paused until trust has been re-established and there are no residual exposure risks.

Asana sent notices with links to communication forms to each impacted organization but has not issued a public statement about the incident.

UpGuard, who informed BleepingComputer about the issue, [shared more details](https://www.upguard.com/blog/asana-discloses-data-exposure-bug-in-mcp-server) on its own blog space, including advice for potentially impacted users.

BleepingComputer has contacted Asana to ask about the scope of the exposure and the number of affected organizations/users, and a spokesperson has told us the incident impacts roughly 1,000 customers.

In the meantime, the MCP server has been taken offline, but Asana's [status page](https://status.asana.com/) indicates that it has returned to normal operational status as planned on June 17, 17:00 UTC.