# Cybersecurity Portfolio — Felix Githure

> **QA Engineer & Cybersecurity Analyst, open to entry-level QA and SOC Analyst roles.**
> I build, break, detect, and respond — all in one home lab, all with free tooling, all
> documented so you can see how I think.

This is the index to a **purple-team portfolio**: I stand up an Active Directory + SIEM
lab, attack it, detect my own attacks, then investigate and respond to them as
incidents. Every project ships a write-up mapped to **MITRE ATT&CK**, real screenshots,
and a quantified result.

---

## The one idea that ties it together

Most portfolios show *either* offense *or* defense. This one shows **both sides of the
same event** — the "purple-team" thinking that makes an entry-level candidate look a cut
above:

```
        ┌───────────────────────────────────────────────┐
        │        PROJECT 0 — The Home Lab (shared)        │
        │   AD (DC + Win client) · Linux victims · Kali   │
        │             · Wazuh SIEM · Sysmon               │
        └───────────────────────┬───────────────────────┘
             RED ▼                             ▼ BLUE
   ┌───────────────────────┐      ┌────────────────────────────┐
   │ P1 AD attack chain     │─────▶│ P2 Detection engineering    │
   │ recon→roast→DCSync→BH  │ logs │ Sigma + Wazuh, my attacks   │
   └───────────┬───────────┘      └──────────────┬─────────────┘
   ┌───────────▼───────────┐      ┌──────────────▼─────────────┐
   │ P3 Web-app pentest     │─────▶│ P4 IR & threat hunt         │
   │ Juice Shop/DVWA + PDF  │ logs │ timelines, triage, hunts    │
   └───────────────────────┘      └────────────────────────────┘
```

**P1's attacks generate the logs P2 detects; P3's attacks generate the incidents P4
investigates.** One coherent environment, not five disconnected tutorials.

---

## The projects

| # | Project | Team | What it proves | Repo |
|---|---------|------|----------------|------|
| 0 | **Home Lab foundation** | 🟣 Both | Build & document infrastructure on a 16 GB budget | [security-homelab](https://github.com/manlikefelo/security-homelab) |
| 1 | **AD attack chain** | 🔴 Red | Enumeration, Kerberoasting, AS-REP, DCSync, BloodHound → Domain Admin | [ad-attack-chain](https://github.com/manlikefelo/ad-attack-chain) |
| 2 | **Detection engineering** | 🔵 Blue | Sigma + Wazuh rules that detect the exact attacks I ran, tuned for false positives | [detection-engineering](https://github.com/manlikefelo/detection-engineering) |
| 3 | **Web-app pentest + report** | 🔴 Red | OWASP Top 10 testing, a chained exploit, a professional PDF report | [webapp-pentest-juiceshop](https://github.com/manlikefelo/webapp-pentest-juiceshop) |
| 4 | **Incident response + threat hunt** | 🔵 Blue | Timeline reconstruction, triage, hunting, IR process | [ir-threat-hunt](https://github.com/manlikefelo/ir-threat-hunt) |
| 5 | **Detection-as-code** | 🟣 Purple | Sigma rules under version control, unit tests, and CI that fails on a bad rule | [detection-as-code](https://github.com/manlikefelo/detection-as-code) |
| 6 | **Adversary emulation** | 🟣 Purple | Measured detection coverage (4 of 8 techniques), then a new rule to close a gap | [adversary-emulation](https://github.com/manlikefelo/adversary-emulation) |
| 7 | **SOC automation** | 🔵 Blue | A tested pipeline that enriches, scores, and tickets Wazuh alerts | [soc-automation](https://github.com/manlikefelo/soc-automation) |
| 8 | **sigmatest** | 🛠️ Tooling | A packaged CLI that lints and unit-tests Sigma rules with no live SIEM | [sigmatest](https://github.com/manlikefelo/sigmatest) |

Projects 5–8 turn the hand-built work above into tested, automated, repeatable work. That
draws on my QA engineering background; see my QA project,
[ruleguard](https://github.com/manlikefelo/ruleguard).

---

## By the numbers

- **6 ATT&CK techniques** detected end-to-end across **3 tactics**, via **6 custom Wazuh
  rules** backed by portable **Sigma**.
- **9 red-team actions** (4 AD techniques + 5 web findings), each mapped to ATT&CK, each
  with real evidence.
- **2 incident reports** on the NIST IR lifecycle with reconstructed attack timelines.
- **3 documented detection-tuning cases** (2 false positives + 1 false negative) — the
  part hiring managers ask about.
- **100% free/local tooling**, engineered to run on **16 GB of RAM** by phasing
  workloads.

---

## Where to start (a 3-minute tour for a hiring manager)

1. **The 90-second story:** [detection-engineering → one detection end to end](https://github.com/manlikefelo/detection-engineering#the-part-hiring-managers-ask-about) — attack → log → rule → alert.
2. **Red skill:** [ad-attack-chain → the BloodHound attack path + executive summary](https://github.com/manlikefelo/ad-attack-chain#read-next).
3. **Writing skill:** [webapp-pentest-juiceshop → the PDF report](https://github.com/manlikefelo/webapp-pentest-juiceshop#the-report-is-the-deliverable-).
4. **Investigative skill:** [ir-threat-hunt → the INC-001 timeline](https://github.com/manlikefelo/ir-threat-hunt#the-headline-artifact--the-timeline).

Each repo has a `docs/reviewer-path.md` with its own guided tour.

---

## What I want you to notice

- **I document the messy bits.** Where a tool failed (sqlmap said "not injectable"),
  where my evidence has limits (a headless XSS I couldn't screenshot), where a detection
  silently missed an encoded payload — I write it down. Honest work is more useful than
  tidy work.
- **Every attack has a defense, and every defense has a fix.** I don't just break
  things; I show the detection *and* the remediation.
- **Constraints drove the engineering.** The whole lab runs on 16 GB by phasing which
  VMs are on — a real limitation turned into a documented design decision.

---

*Built with free tooling in a home lab · all systems self-owned · [contact via GitHub](https://github.com/manlikefelo)*
