# Concentration risk: cloud outages, Binance and the case for distributed resilience

**13 November 2026 · Ventus Ltd · Fact-checked commentary**

## Public-facing statement

First Google Cloud's London-region outage disrupted major UK banking services, and now a Microsoft 365 outage has affected organisations worldwide. In between came the largest cryptocurrency theft reported to date: approximately $6.3 billion stolen from Binance, with a compromised DevOps engineer's laptop identified in Binance's preliminary investigation. The incidents had different causes, but all expose the consequences of concentrated dependencies.

This is why open-source tools need to replace critical closed dependencies wherever practical, with genuine portability, independent recovery and proper security oversight.

I've always been fascinated that a Finnish 🇫🇮 guy, Linus Torvalds, created the Linux kernel and then Git. Git is distributed, so no single central machine has to hold the only copy of a project's history. Computers can work in isolation, commit changes locally, and verify the integrity of the histories they exchange. It is free to learn; and what you build can run locally without the internet if you design it to do so.

AI is heading the same way as enterprise email and video calls: a few major providers, operating across a few major clouds. Claude is offered through Amazon, Google and Microsoft cloud platforms. OpenAI remains closely tied to Microsoft, although its 2026 agreement also permits service across other cloud providers. Meanwhile, the UK's Competition and Markets Authority is examining Microsoft's business software ecosystem, including bundling, interoperability and customer choice.

There's a familiar fix. Just as special-purpose vehicles are used to ring-fence project liabilities, critical digital services should isolate their failure domains. R&D and key procurement should be spread beyond the largest firms, with proper oversight, independently usable alternatives and tested recovery arrangements, so one provider's failure stays contained.

## Evidence and qualifications

| Topic | Verified position as at 13 November 2026 | Caution |
| --- | --- | --- |
| Google Cloud, 20 October | A power supply fault affected the London-region availability zone `europe-west2-b`. Google's post-incident report identifies a PLC voltage-sensing/control configuration that prevented generators starting; UPS reserves were depleted. Broad service impact lasted about 6 hours 8 minutes. Lloyds, HSBC and Revolut reported customer disruption. | Not evidence of a cyberattack or the collapse of all London banking. Distinguish an affected zone from the whole region and the banking system. |
| Binance, 29 October | The FBI attributed the theft of more than US$6 billion to North Korean TraderTraitor activity. Binance estimated about US$6.3 billion and preliminarily said an attacker may have compromised a DevOps engineer's laptop. | Say 'largest reported cryptocurrency theft', not an unqualified 'largest heist in history'. The laptop pathway was preliminary, not a completed forensic finding. |
| Microsoft 365, 12–13 November | Outlook / Exchange Online, Teams, Copilot and other dependent services suffered widespread disruption, including effects on businesses and government users internationally. Microsoft's reported investigation focused on server health and capacity issues. | No established malicious cyberattack; initial technical explanations are subject to the final post-incident report. |
| Linux and Git | Linus Torvalds, a Finnish software developer, initiated the Linux kernel (1991) and Git (2005). Git is distributed, tracks content by hashes and allows local commits while offline. | Git detects content differences; it does **not** automatically prove an external peer is trustworthy, authenticate every author, or make deployment infrastructure independent of a hosting platform. Use signed commits/tags and independently controlled mirrors when provenance matters. |
| Anthropic / Claude | Claude is available via AWS, Google Cloud and Microsoft Azure; Anthropic describes major compute arrangements with AWS. | Availability on three clouds does not by itself demonstrate three operationally independent backends for every product or workload. |
| OpenAI / Microsoft | Under the April 2026 amended agreement, Microsoft remained OpenAI's primary cloud partner, but OpenAI could serve products across other providers and Microsoft's IP licence became non-exclusive. | Avoid implying OpenAI exclusively runs on Microsoft or that regulators have found the partnership unlawful. |
| Microsoft competition oversight | The UK CMA opened a strategic-market-status investigation in May 2026 and proposed designation in October; bundling, interoperability, AI choice and licensing are within its stated areas of concern. | The designation and any future remedies were provisional at this date; an investigation is not a finding of misconduct. |

## Practical resilience principles

1. **Architect for supplier loss:** define and exercise provider, region, network and identity-service failure scenarios; test actual restoration times, not just failover diagrams.
2. **Keep recoverable local copies:** local source code, build instructions, configuration, verified backups and offline procedures where the mission permits.
3. **Mirror across independent control planes:** repositories, secrets recovery and backups must not all depend on one identity provider, cloud account or shared administrator.
4. **Use open standards and inspectable components where suitable:** this can reduce vendor lock-in, but an open-source licence alone does not ensure security, maintainership or operational independence.
5. **Check provenance:** content hashes detect alteration relative to known references; trusted signatures, access controls, patch review and reproducible builds address different supply-chain threats.
6. **Diversify procurement deliberately:** challenge exclusive dependencies, establish credible smaller suppliers, and include independent technical checks and exit/portability obligations.
7. **Separate kinds of risk:** outages caused by electricity, control logic or resource exhaustion are different from theft by hostile operators; both require containment, but different controls.

## Sources (retrieved 13 November 2026)

1. [Google Cloud — official London-region incident report, 20 October 2026](https://status.cloud.google.com/incidents/Xs2XTHzAVC9YnafnPyzj)
2. [Euronews / AFP — banks affected by Google Cloud disruption, 20 October 2026](https://www.euronews.com/2026/10/20/power-outage-hits-google-cloud-services-disrupting-uk-banks)
3. [FBI — North Korea responsible for $6 billion-plus Binance attack, 31 October 2026](https://www.fbi.gov/investigate/cyber/alerts/2026/north-korea-responsible-for-6-billion-binance-attack/layout_view)
4. [Binance — preliminary security incident update, 30 October 2026](https://www.binance.com/en/square/post/382718392937002)
5. [Chainalysis — Binance exploit findings, 30 October 2026](https://www.chainalysis.com/blog/binance-exploit-latest-findings-and-response/)
6. [Reuters — Microsoft 365 outage, 12–13 November 2026](https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/)
7. [BleepingComputer — Microsoft advisory MO1550821 and service impacts, 12 November 2026](https://www.bleepingcomputer.com/news/microsoft/massive-microsoft-365-outage-disrupts-outlook-teams-copilot-worldwide/)
8. [Git documentation — a short history of Git](https://git-scm.com/book/en/v2/Getting-Started-A-Short-History-of-Git)
9. [Git documentation — distributed version control](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)
10. [Git documentation — integrity and offline operation](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git)
11. [Anthropic — Amazon collaboration and Claude across three clouds, 20 April 2026](https://www.anthropic.com/news/anthropic-amazon-compute)
12. [OpenAI — next phase of Microsoft partnership, 27 April 2026](https://openai.com/index/next-phase-of-microsoft-partnership/)
13. [UK CMA — Microsoft's business software ecosystem case, May–October 2026](https://www.gov.uk/cma-cases/microsofts-business-software-ecosystem)
14. [UK CMA — proposed designation and areas for intervention, 16 October 2026](https://www.gov.uk/government/news/cma-takes-first-steps-to-ensure-choice-in-business-software)

**Method:** Reported incidents are sourced; assessments and diversification proposals are policy and engineering judgements, not a claim of proven causation between the incidents. This is a research note, not an audit or legal opinion.
