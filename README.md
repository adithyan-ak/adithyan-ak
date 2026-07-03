<div align="center">

# Adithyan Arun Kumar

### Offensive Security Researcher | AI · LLM · Agent Security

Security Engineer (AI) at Salesforce &nbsp;·&nbsp; M.S. Information Security, Carnegie Mellon<br/>
OSCP · OSEP · OSWE · CRTP · CREST CRT · CEH (Master)

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-akinfosec-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/akinfosec)
[![Blog](https://img.shields.io/badge/Blog-adithyanak.com-1F6FEB?style=flat-square&logo=googlechrome&logoColor=white)](https://adithyanak.com)

![Coordinated Disclosures](https://img.shields.io/badge/Coordinated_Disclosures-7-4B0000?style=flat-square)
![Severity](https://img.shields.io/badge/Severity-1_Critical_%C2%B7_5_High_%C2%B7_1_Medium-b31b1b?style=flat-square)
![CVE-2025-45691](https://img.shields.io/badge/CVE--2025--45691-RAGAS-8B0000?style=flat-square)
![Focus](https://img.shields.io/badge/Focus-AI_%C2%B7_LLM_%C2%B7_Agent_Security-6f42c1?style=flat-square)

</div>

---

## $whoami

I break AI systems for a living. I'm a product security engineer and offensive researcher focused on the security of **LLMs, autonomous agents, and the infrastructure around them**: MCP, A2A, gateways, and RAG pipelines.

My open-source work centers on finding and fixing high-impact vulnerabilities in the tools the AI ecosystem is being built on: evaluation frameworks, agent runtimes, and AI assistants used by hundreds of thousands of developers. Below is a record of my public security research, responsible disclosures, and open-source contributions.

---

## Security Research & Responsible Disclosures

Coordinated-disclosure vulnerabilities I discovered and reported in widely-used open-source AI/ML projects, spanning codebases with a **combined ~625k GitHub stars**. Every entry links to a public, verifiable reference.

| Project | Reach | Vulnerability | Severity | Reference |
|---|---:|---|:--:|---|
| **openclaw** (personal AI assistant) | ~381k★ | LLM-driven gateway config-injection: bypass exec approvals, disable auth, and inject MCP servers via `config.patch` | ![Critical](https://img.shields.io/badge/CRITICAL-4B0000?style=flat-square) | <sub>GHSA-xmjq-5cvf-v7gj<br/>(coordinated)</sub> |
| **hermes-agent** (agent runtime) | ~208k★ | Unauthenticated plugin code execution via dashboard loader | ![High](https://img.shields.io/badge/HIGH-C62828?style=flat-square) `7.8` | [Report #46435](https://github.com/NousResearch/hermes-agent/issues/46435)<br/><sub>GHSA-mcfc-hp25-cjv7</sub> |
| **hermes-agent** | ~208k★ | Authorization bypass via spoofed `From:` header (email gateway) | ![High](https://img.shields.io/badge/HIGH-C62828?style=flat-square) `7.0` | [Report #46434](https://github.com/NousResearch/hermes-agent/issues/46434)<br/><sub>GHSA-rxqh-5572-8m77</sub> |
| **promptfoo** (LLM eval / red-team toolkit) <br/><sub>used by OpenAI & Anthropic</sub> | ~23k★ | Second-order Nunjucks SSTI → Remote Code Execution in `renderPrompt` | ![High](https://img.shields.io/badge/HIGH-C62828?style=flat-square) `8.3` | [Fix PR #9693](https://github.com/promptfoo/promptfoo/pull/9693)<br/><sub>GHSA-7x7g-w3q4-fv98</sub> |
| **promptfoo** | ~23k★ | RCE via `storeOutputAs` register collapse (`file://` dynamic import) | ![High](https://img.shields.io/badge/HIGH-C62828?style=flat-square) `8.3` | [Fix PR #9693](https://github.com/promptfoo/promptfoo/pull/9693)<br/><sub>GHSA-f5hv-jrwp-gh59</sub> |
| **RAGAS** (LLM evaluation framework) | ~15k★ | Arbitrary File Read in multimodal prompt handling | ![High](https://img.shields.io/badge/HIGH-C62828?style=flat-square) `7.5` | [CVE-2025-45691](https://nvd.nist.gov/vuln/detail/CVE-2025-45691) · [GHSA](https://github.com/advisories/GHSA-v2xr-wvrv-p969) |
| **openclaw** | ~381k★ | Server-Side Request Forgery on all bot media-fetch paths | ![Medium](https://img.shields.io/badge/MEDIUM-EF6C00?style=flat-square) | [GHSA-3fv3-6p2v-gxwj](https://github.com/advisories/GHSA-3fv3-6p2v-gxwj) |

---

## Open-Source Contributions

Pull requests to major open-source projects: security fixes, hardening, and disclosure infrastructure.

| Project | Reach | Contribution |
|---|---:|---|
| [tensorflow/tensorflow](https://github.com/tensorflow/tensorflow/pull/115326) | ~196k★ | Fix out-of-bounds write in `MaxPoolGradWithArgmax` GPU kernel (CWE-787) |
| [promptfoo/promptfoo](https://github.com/promptfoo/promptfoo/pull/9693) | ~23k★ | Harden eval template rendering to close RCE sinks |
| [vibrantlabsai/ragas](https://github.com/vibrantlabsai/ragas/pull/1991) | ~15k★ | Patch CVE-2025-45691 + add security controls |
| [vibrantlabsai/ragas](https://github.com/vibrantlabsai/ragas/pull/1987) | ~15k★ | Add responsible-disclosure policy (`SECURITY.md`) |
| [github/advisory-database](https://github.com/github/advisory-database/pull/7317) | n/a | Publish RAGAS advisory `GHSA-v2xr-wvrv-p969` |
| [OWASP/www-chapter-coimbatore](https://github.com/OWASP/www-chapter-coimbatore) | n/a | OWASP chapter website & content |

I also file detailed reliability reports in high-traffic projects, e.g. openclaw [#55330](https://github.com/openclaw/openclaw/issues/55330) and [#55410](https://github.com/openclaw/openclaw/issues/55410).

---

## Security Tooling

Open-source offensive-security and AI-security tools I build and maintain.

| Tool | Stack | Description |
|---|---|---|
| [AgentHound](https://github.com/adithyan-ak/AgentHound) | Go | Offensive security framework for AI-agent infrastructure: recon, credential looting, model exfiltration, poisoning, and attack-path analysis across MCP, A2A, gateways, and AI services. *"BloodHound for the agentic stack."* |
| [AgentMask](https://github.com/adithyan-ak/agentmask) | TypeScript | Context-level secret isolation for AI coding agents (Claude Code, Copilot). Keeps secrets out of the LLM context window with sub-50ms hook latency. |
| [PixelPoison](https://github.com/adithyan-ak/pixelpoison) | Python | Adversarial image generation for Vision-Language Model (VLM) security testing. |
| [WAVE](https://github.com/adithyan-ak/WAVE) | Python | Web Application Vulnerability Exploiter: automated web vulnerability scanner. |
| [BufferSploit](https://github.com/adithyan-ak/BufferSploit) | Python | Semi-automated CLI for stack-based buffer-overflow exploitation. |
| [Slacksploit](https://github.com/adithyan-ak/Slacksploit) | Python | Forensic framework for enumerating Slack artifacts on a host. |

More on my [repositories](https://github.com/adithyan-ak?tab=repositories) · [talk decks](https://github.com/adithyan-ak/Slides).

---

## Publications

Full list on [ORCID](https://orcid.org/0000-0001-9790-2657).

- A Comprehensive Approach for Enhancing OSINT through Leveraging LLMs
- Diminishing Popularity of Encoder-Only Architectures in Machine Learning Models
- LSAF: A Novel Comprehensive Application and Network Security Framework for Linux
- Reverse Engineering and Backdooring Router Firmwares

---

## Certifications

`OSEP` · `OSWE` · `OSCP` · `CRTP` · `CREST CRT` · `CREST CPSA` · `GCCEP` · `CEH (Master)` · `ICSI CNSS` · `Fortinet NSE`

---

<div align="center">

**Let's talk security:** [LinkedIn](https://www.linkedin.com/in/akinfosec) · [Blog](https://adithyanak.com) · [adioffsec@gmail.com](mailto:adioffsec@gmail.com)

</div>

