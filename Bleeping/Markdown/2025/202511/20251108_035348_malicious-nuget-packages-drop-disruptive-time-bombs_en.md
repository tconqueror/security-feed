# Malicious NuGet packages drop disruptive 'time bombs'

![Malicious NuGet packages drop disruptive 'time bombs'](https://www.bleepstatic.com/content/hl-images/2023/08/11/industrial-control-system.jpg)

Several malicious packages on NuGet have sabotage payloads scheduled to activate in 2027 and 2028, targeting database implementations and Siemens S7 industrial control devices.

The embedded malicious code uses a probabilistic trigger, so it may or may not activate depending on a set of parameters on the infected device.

NuGet is an open-source package manager and software distribution system, enabling developers to download and include ready-to-run .NET libraries for their projects.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Researchers at code security company Socket found nine malicious packages on NuGet, all published under the developer name _shanhai666_, that featured legitimate functionality along with the harmful code.

The packages "strategically target all three major database providers used in .NET applications (SQL Server, PostgreSQL, SQLite)." However, the most dangerous of them is _Sharp7Extend,_ which targets users of the legitimate Sharp7 library for communicating over ethernet with Siemens programmable logic controllers (PLCs).

"By appending "Extend" to the trusted Sharp7 name, the threat actor exploits developers searching for Sharp7 extensions or enhancements," Socket researchers said.

Under the shanhai666 developer name, NuGet listed 12 packages, but only nine of them included malicious code:

1. SqlUnicorn.Core
2. SqlDbRepository
3. SqlLiteRepository
4. SqlUnicornCoreTest
5. SqlUnicornCore
6. SqlRepository
7. MyDbRepository
8. MCDbRepository
9. Sharp7Extend

At publishing time, there are no packages listed under that developer's name. But it should be noted that the delisting occurred after the download count almost reached 9,500.

## Sneaking a “bomb” for 2028

According to Socket researchers, the packages contain mostly (99%) legitimate code, creating a false sense of safety and trust, but include a small 20-line malicious payload.

"The malware exploits C# extension methods to transparently inject malicious logic into every database and PLC operation," Socket [explains](https://socket.dev/blog/9-malicious-nuget-packages-deliver-time-delayed-destructive-payloads) in a report this week.

The extension methods execute every time an application performs a database query or a PLC operation. There is also a verification for the current date on the compromised system against a hardcoded trigger date, which ranges from August 8, 2027, to November 29, 2028.

![Trigger date](https://www.bleepstatic.com/images/news/u/1220909/2025/November/triggerdate.png)

**Trigger date for November 2028**  
_Source: Socket_

If the date condition is a match, the code creates a ‘Random’ class to generate a number between 1 and 100, and if it’s higher than 80 (20% chance), calls ‘Process.GetCurrentProcess().Kill()’ for the immediate termination of the host process.

For typical PLC clients that call transactional or connection methods frequently, this would lead to an immediate stop of operations.

The Sharp7Extend package, which impersonates the legitimate Sharp7 library, a popular .NET communication layer for Siemens S7 PLCs, follows the opposite approach, immediately terminating PLC communications in 20% of cases. This mechanism is set to expire on June 6, 2028.

A second sabotage method in the Sharp7Extend package consists in code trying to read from an inexistent configuration value. As a result, the initialization always fails.

A second mechanism creates a filter value for internal PLC operations and sets a payload execution delay between 30 and 90 minutes.

After that time has elapsed, PLC writes that pass through the filter have an 80% chance to get corrupted, resulting in actuators not receiving commands, setpoints not being updated, safety systems not engaging, and production parameters not being modified.

**Corrupting PLC writes**  
_Source: Socket_

"The combination of immediate random process termination (_via BeginTran()_) and delayed write corruption (via _ResFliter_) creates a sophisticated multi-layered attack that evolves over time," Socket researchers say.

While the exact goals and origins of these extensions remain unclear, organizations potentially impacted are recommended to immediately audit their assets for the nine packages and assume compromise if any are present.

For industrial environments running Sharp7Extend, audit PLC write operations for integrity, check safety system logs for missed commands or failed activations, and implement write-verification for critical operations.