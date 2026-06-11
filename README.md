# The ghost in the machine
*Securing AI agent skills*
<br/><br/>
This was created for **Workshop #4** of PlatformCon: <br/>
[Link to the PlatformCon session](https://platformcon.com/sessions/the-ghost-in-the-machine-securing-ai-agent-skills)

<img width="50%" height="653" alt="Screenshot 2026-06-06 at 22 24 45" src="https://github.com/user-attachments/assets/85e8eedc-b7ed-4339-aaf6-6068c88e54d9" />

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


## PlatformCon 2026 Workshops

1. [Hunting compromised software dependencies inside Kubernetes workloads](https://github.com/ndouglas-cloudsmith/compromised-dependencies-kubernetes/tree/main)
2. [AI agents & platform engineering: Efficiency boost or new source of trouble?](https://github.com/ndouglas-cloudsmith/AI-agents-platform-engineering)
3. [Audit-ready Kubernetes: How to leverage policy-as-code for continuous compliance](https://github.com/ndouglas-cloudsmith/audit-ready-kubernetes/tree/main)
4. **[The ghost in the machine: Securing AI agent skills](https://github.com/ndouglas-cloudsmith/ghost-in-the-machine/tree/main)**
