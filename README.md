# The ghost in the machine
*Securing AI agent skills*
<br/><br/>
This was created for **Workshop #4** of PlatformCon: <br/>
[Link to the PlatformCon session](https://platformcon.com/sessions/the-ghost-in-the-machine-securing-ai-agent-skills)

<img width="50%" height="653" alt="ghost" src="https://github.com/user-attachments/assets/af1d48a8-c03b-4844-8b0d-a114d62a3299" />


### Learning Outcomes
As agent skills emerge as a pivotal mechanism for extending AI capabilities in platform engineering, they offer significant productivity gains alongside critical supply chain vulnerabilities. By enabling agents to execute modular instructions, these tools help platform teams scale

- Public repositories like ```ClawHub``` mirror the security risks of traditional open-source ecosystems.
- This talk explores the tension between agentic innovations and an expanding attack surface, emphasising the need to integrate security scanning into golden path initiatives.
- It proposes leveraging databases like ```Open Source Malware``` to detect Agentic IoCs, arguing that proactive, API-driven defenses are essential for adopting autonomous workflows today.

## Part 1: ClawHub

In January, the first AI skills registries launched. Paul McCarty of **[Open Source Malware](https://opensourcemalware.com/?type=package&ecosystem=skills)** foresaw that this new ecosystem would be quickly exploited by threat actors, and unfortunately he was right. Between January 27-February 22, he discovered **386 malicious skills** in **[ClawHub](https://clawhub.ai)** (OpenClaw’s skill registry). By the end of March, that number **topped 700**.
<br/><br/>
While the malware itself was unsophisticated (either the payload was directly in the skill, or in a typosquatted domain), the victims tell an interesting story.
<br/><br/>
Jenn Gile analysed **707 malicious skills** published in this period, and found they could be grouped into five clear target groups:
1. **32%:** Crypto / finance, such as ```polymarketbtcskill```
2. **19%**: Social media / marketing, such as ```klaviyoapi```
3. **17%**: CLI impersonations, such as ```openclaw-git```
4. **16%**: Productivity, such as ```gmail-client```
5. **12%**: Developers, such as ```n8nsk```

The remaining 4% they were unable to classify into the above groups.
<br/><br/>
Most of the categories weren’t terribly surprising: we know that most malicious open source targets crypto and software developers. And it’s not shocking that loads of CLI impersonators would flood the registry, since threat actors commonly target new technologies. Even productivity-related skills are logical since OpenClaw was designed to be a personal assistant.
<br/><br/>
But what surprised us was that nearly 1/5th of skills that seemed to target people in marketing roles. Non-engineers are a mostly untapped but attractive target for threat actors. After all, people in marketing (as well as sales, finance, etc) also have credentials. But unlike engineers, often security teams pay less attention to their access and blast radius.

<img width="1920" height="1080" alt="malicious_skills" src="https://github.com/user-attachments/assets/62375704-f309-494f-83f2-32cef21e31ac" />

**Source:**
https://opensourcemalware.com/blog/software-supply-chain-malware-landscape


## Part 2: Godel's Sieve

Scan documents and media for threats targeting AI Agents: <br/>
https://sieve.godel-labs.ai

- ```finance-crypto-agent.md```: https://sieve.godel-labs.ai/scan/4o3g1r435d1r0n5m520z0z
- ```SKILL.md```: https://sieve.godel-labs.ai/analysis/181c7ad5-2d5b-4b10-8b78-5b5b1c87308d
- ```trading-skill.md```: https://sieve.godel-labs.ai/analysis/750be001-7d46-4827-8c06-c8d218d0980e

<img width="1138" height="512" alt="skills-infra" src="https://github.com/user-attachments/assets/cdc3ae0e-8ebf-4e2b-92e7-839a8ac14408" />

#### Backstage AI Skills
Backstage publishes a set of curated AI skills — self-contained guidance files that teach an AI coding assistant how to perform common Backstage engineering tasks. Skills are published to a **[well-known endpoint](https://backstage.io/.well-known/skills/)** on ```backstage.io``` and can be installed into your repository with the **[skills.sh](https://www.skills.sh/)** tool.<br/><br/>
https://backstage.io/docs/ai/skills

<img width="1200" height="476" alt="Screenshot 2026-06-11 at 12 50 06" src="https://github.com/user-attachments/assets/2a23ba79-eefb-4c0c-b754-d5d4105d66d6" />

#### Backstage Agent Skills
Claude skills for building Backstage plugins with the New Frontend and Backend Systems. <br/>
https://github.com/rothenbergt/backstage-agent-skills/tree/main
<br/><br/>

```
wget https://raw.githubusercontent.com/rothenbergt/backstage-agent-skills/refs/heads/main/backstage-backend-plugin/SKILL.md
```

```backstage-backend-plugin``` - https://sieve.godel-labs.ai/analysis/45763adc-f55b-40af-8953-33749d6145a7

- Server-side request forgery (SSRF) to internal/metadata endpoint detected
- Sensitive Data: **US BANK NUMBER**
- OwaspAgenticThreats": "```ASI01```", "```ASI02```", and "```ASI03```"

<img width="1113" height="678" alt="Screenshot 2026-06-11 at 12 59 52" src="https://github.com/user-attachments/assets/ff89f555-e366-4112-b5a8-e6b0cfae8359" />


#### OWASP Top 10 for Agentic Systems
OWASP Agentic Skills Top 10: <br/>
https://owasp.org/www-project-agentic-skills-top-10
<br/><br/>
OWASP Top 10 for Agentic Applications for 2026<br/>
https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/

## Part 3: Caterpillar

Before you install, make sure it's safe. Caterpillar scans every skill before it can cause any harm. <br/>
https://caterpillar.alice.io 
<br/><br/>
Install with ```curl``` on Linux/Mac:
```
curl -fsSL caterpillar.alice.io/d/i.sh | sh
```
Scan any skill like ```Claude``` Skills, ```Cursor``` Skills, and more..
```
caterpillar scan
```

<img width="648" height="782" alt="Screenshot 2026-06-11 at 15 44 05" src="https://github.com/user-attachments/assets/fca9c6fa-3589-4c46-ae80-d7165a5fe5ae" />


----

#### Miscellaneous
- Snyk Agent Scan: https://github.com/snyk/agent-scan


## PlatformCon 2026 Workshops

1. [Hunting compromised software dependencies inside Kubernetes workloads](https://github.com/ndouglas-cloudsmith/compromised-dependencies-kubernetes/tree/main)
2. [AI agents & platform engineering: Efficiency boost or new source of trouble?](https://github.com/ndouglas-cloudsmith/AI-agents-platform-engineering)
3. [Audit-ready Kubernetes: How to leverage policy-as-code for continuous compliance](https://github.com/ndouglas-cloudsmith/audit-ready-kubernetes/tree/main)
4. **[The ghost in the machine: Securing AI agent skills](https://github.com/ndouglas-cloudsmith/ghost-in-the-machine/tree/main)**
