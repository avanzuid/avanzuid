# Security Engineering, AI & Cybersecurity Research

A collection of practical cybersecurity projects, experiments, and technical research focused on applying automation and AI to enterprise security challenges.

The repositories cover application security, threat modeling, security operations, vulnerability management, Continuous Threat Exposure Management (CTEM), endpoint security, and SIEM/XDR integration.

> **Scope:** These repositories are separate projects and research examples. They are not presented as one integrated product or as production-ready security controls. Review each project's documentation, prerequisites, limitations, and validation requirements before using it in a live environment.

## Repository overview

| Project | Area | Description |
|---|---|---|
| [CTEM: The Role of AI](https://github.com/avanzuid/CTEM-The-Role-of-AI) | Exposure management | Demonstrates a deterministic-first CTEM pipeline correlating devices, identities, access mappings, installed software, and vulnerabilities to prioritize exposure and explain candidate attack paths. |
| [AI-assisted Vulnerability Management / CTEM](https://github.com/avanzuid/ai-vm-ctem) | Vulnerability management | Demonstrates correlating vulnerability advisories with device and software inventory to identify potentially affected assets and support CTEM prioritization. |
| [Advanced Security Notification](https://github.com/avanzuid/advanced-security-notification) | Threat intelligence | Explores using Tavily Search to discover vendor security advisories, emergency updates, out-of-band patches, hardening releases, and product security announcements. |
| [Threat Modeling with AI](https://github.com/avanzuid/Threat-modeling-with-AI) | Security architecture | A Mistral-powered command-line application that turns an application story into a structured STRIDE threat model, with JSON Schema validation and Markdown/JSON output. |
| [SAST-AI](https://github.com/avanzuid/SAST-AI) | Application security | A Python SAST command-line tool that uses AST analysis to identify security-sensitive code and Mistral AI for semantic vulnerability analysis. |
| [AI Dependency Auditor](https://github.com/avanzuid/AI-Dependency-Auditor) | Software supply chain security | Audits Python requirements using PEP 508 parsing, PyPI metadata, and OSV.dev vulnerability data. Mistral AI provides a separate reasoning and recommendation layer. |
| [AI Security Analyst](https://github.com/avanzuid/AI-Security-Analyst) | Security operations | Analyzes local security logs with Mistral AI and produces structured findings, severity, evidence, confidence, and recommendations. The included log data is simulated. |
| [Endpoint Privilege Management (EPM)](https://github.com/avanzuid/EPM) | Endpoint security | Research notes and a test approach for validating EPM controls, with particular attention to Windows Registry permissions and DLL loading behavior. |
| [SIEM-XDR](https://github.com/avanzuid/SIEM-XDR) | SIEM / XDR integration | Describes using Splunk to run targeted Microsoft Defender Advanced Hunting KQL queries and index selected results, rather than continuously ingesting all Defender telemetry. |

## Focus areas


### 1. Vulnerability and exposure management

- **AI-assisted Vulnerability Management:** Compares vulnerability advisories with an existing asset and software inventory to identify systems that may require investigation.
- **CTEM: The Role of AI:** Correlates technical exposure, asset criticality, identity context, and candidate attack paths. Deterministic Python logic handles verifiable matching and scoring; AI is reserved for selected interpretation and security reasoning.


### 2. Security operations and threat intelligence

- **Advanced Security Notification:** Explores collecting security announcements from vendor and other relevant sources.
- **AI Security Analyst:** Uses AI to summarize and assess security log data while retaining evidence from the original input.
- **SIEM-XDR:** Explores a selective-hunting integration pattern between Splunk and Microsoft Defender Advanced Hunting.

### 3. Application security and secure development

- **SAST-AI:** Combines Python AST-based code analysis with AI-assisted semantic review.
- **Threat Modeling with AI:** Uses the STRIDE methodology to structure threats, trust boundaries, assumptions, and security considerations.
- **AI Dependency Auditor:** Checks Python dependency metadata and known vulnerability records using PyPI and OSV.dev.

### 4. Endpoint security

- **EPM:** Examines whether endpoint privilege controls account for registry configuration and DLL search/loading behavior, in addition to the primary executable and elevation policy.

## Design principles

Across these projects, several engineering principles are useful:

- **Prefer verifiable data for security facts.** Use authoritative vulnerability and package sources where available; use AI to interpret and explain rather than invent facts.
- **Keep deterministic checks deterministic.** Version matching, input validation, scoring, and evidence checks should be performed in code wherever practical.
- **Validate AI output.** Use structured output, schema validation, and cross-checks before accepting generated findings.
- **Preserve evidence.** Findings should include traceable source material, affected assets, or exact log evidence where applicable.
- **Treat input as untrusted.** Logs, source code, dependency files, advisories, and external content may contain malformed or adversarial data.
- **Keep humans in the decision loop.** AI-generated analysis is advisory and must be checked before remediation or production security decisions.

## Technologies and security concepts

The repositories include work with:

- Python and command-line tooling
- Mistral AI
- Tavily Search API
- Python Abstract Syntax Trees (AST)
- STRIDE threat modeling
- JSON and JSON Schema validation
- PyPI package metadata
- OSV.dev vulnerability data
- Continuous Threat Exposure Management (CTEM)
- Vulnerability management and asset inventory correlation
- Microsoft Defender Advanced Hunting and Kusto Query Language (KQL)
- Splunk search and investigation workflows
- Endpoint Privilege Management, Windows Registry, and DLL loading

The technologies listed above are drawn from the individual project documentation. They are not necessarily shared dependencies across all repositories.

## Getting started

Each project has its own setup and usage instructions. Start with the README or main documentation in the relevant repository:

1. Open the project link in the repository overview.
2. Review its requirements and configuration.
3. Configure API credentials using the method documented by that project. Do not commit secrets or API keys.
4. Run the supplied example or tests where available.
5. Validate findings independently before acting on them.

Some projects require external API access or credentials. Others are research documents or test guidance rather than executable applications.

## Safety and limitations

These projects are intended for learning, research, and security engineering experimentation unless an individual repository explicitly documents a validated production deployment.

- AI-generated findings can be incomplete, inaccurate, or misleading.
- A potential vulnerability match is not proof that an asset is exploitable or compromised.
- Sample data may be simulated and must not be treated as live telemetry.
- External APIs have coverage, rate limits, and availability constraints.
- Test endpoint security controls only in authorized, isolated environments.
- Validate product versions, API permissions, integrations, and vendor documentation before deployment.
- Do not use generated recommendations as the sole basis for security or remediation decisions.

## About

This portfolio documents practical exploration of cybersecurity engineering, AI-assisted analysis, vulnerability management, and enterprise security operations.

For questions, suggestions, or collaboration, please use the issue or discussion facilities available in the relevant repository.

---

**GitHub:** [@avanzuid](https://github.com/avanzuid)
