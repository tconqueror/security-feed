# Hackers target misconfigured proxies to access paid LLM services

![Hackers target misconfigured proxies to access paid LLM services](https://www.bleepstatic.com/content/hl-images/2025/10/23/ai-1.jpg)

Threat actors are systematically hunting for misconfigured proxy servers that could provide access to commercial large language model (LLM) services.

In an ongoing campaign that started in late December, the attackers have probed more than 73 LLM endpoints and generated over 80,000 sessions.

According to threat monitoring platform GreyNoise, the threat actors use low-noise prompts to query endpoints in an attempt to determine the accessed AI model without triggering a security alert.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

### Grey-hat operation

GreyNoise says in a report that over the past four months, its Ollama honeypot caught a total of 91,403 attacks that are part of two distinct campaigns.

One operation started in October and is still active, with a spike of 1,688 sessions over 48 hours around Christmas. It exploits server-side request forgery (SSRF) vulnerabilities that allow the actor to force a server to connect to an attacker-controlled external infrastructure.

According to the researchers, the attacker behind this operation achieved its goals by using Ollama's model pull functionality to inject malicious registry URLs and Twilio SMS webhook integrations through the MediaURL parameter.

However, based on the tools used, GreyNoise points out that the activity likely originates from security researchers or bug bounty hunters, as they used ProjectDiscovery's OAST (Out-of-band Application Security Testing) infrastructure, which is typically used in vulnerability assessments.

"OAST callbacks are standard vulnerability research techniques. But the scale and Christmas timing suggest grey-hat operations pushing boundaries" - [GreyNoise](https://www.greynoise.io/blog/threat-actors-actively-targeting-llms)

Telemetry data revealed that the campaign originated from 62 IP addresses across 27 countries that exhibit VPS-like characteristics rather than signs of botnet operation.

![Activity timeline](https://www.bleepstatic.com/images/news/u/1220909/2026/January/diagram(3).jpg)

**Activity timeline**  
_Source: GreyNoise_

### Threat actor activity

GreyNoise observed a second campaign starting on December 28 and detected a high-volume enumeration effort to identify exposed or misconfigured LLM endpoints.

Over 11 days, the activity generated 80,469 sessions, with two IP addresses systematically probing over 73 model endpoints using both OpenAI-compatible and Google Gemini API formats.

The list of targeted models included those from all major providers, including: 

* OpenAI (GPT-4o and variants)
* Anthropic (Claude Sonnet, Opus, Haiku)
* Meta (Llama 3.x)
* DeepSeek (DeepSeek-R1)
* Google (Gemini)
* Mistral
* Alibaba (Qwen)
* xAI (Grok)

To avoid security alerts when testing access to an LLM service, the attacker used harmless queries such as short greetings, empty inputs, or factual questions.

GreyNoise says that the scanning infrastructure has been previously associated with widespread vulnerability exploitation activity, which suggests that the enumeration is part of an organized reconnaissance effort to catalog accessible LLM services.

The GreyNoise report does not claim observed exploitation after discovery, data theft, or model abuse, but the activity is still indicative of malicious intentions.

"Eighty thousand enumeration requests represent investment," warn the researchers, adding that "threat actors don't map infrastructure at this scale without plans to use that map."

To defend against this activity, it is recommended to restrict Ollama model pulls to trusted registries, apply egress filtering, and block known OAST callback domains at the DNS level.

Measures against enumeration include rate-limiting suspicious ASNs and monitoring for JA4 network fingerprints linked to automated scanning tools.