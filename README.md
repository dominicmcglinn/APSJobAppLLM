# APS JobAppLLM
### End-to-End APS Job Application AI Assistant

**APS JobAppLLM** is a multi-agent large-language-model workflow that guides APS candidates through every phase of a government job application — from job description analysis to interview reflection — aligned with APS recruitment methodology, merit principles, and values.

---

## 🧩 Workflow Overview

| Stage | Agent | Purpose |
|-------|--------|----------|
| 1 | Job-Alignment & Resume Optimizer | Analyse JD + resume for APS alignment |
| 2 | Application Drafting Agent | Generate APS-style cover letter or pitch |
| 2.5 | Output Handover | Standardise data for STAR input |
| 3 | STAR / Mock Interview Agent | Create STAR responses & simulate panel interview |
| 4 | Reflection & Alignment Agent | Analyse transcript + feedback vs JD |
| 5 | Multi-Agent Coordinator | Orchestrate all stages and generate L&D plan |

---

## 🧠 APS Methodology

This system is based on the official APSC frameworks:
- *Recruitment in the APS (2024)*  
- *Cracking the Code – Applying for an APS Job*  
- *APS Work Level Standards (APS–EL–SES)*  
- *APS Values and Code of Conduct in Practice (2023)*  
- *Secretaries’ Charter of Leadership Behaviours (2022)*  

Each stage ensures compliance with the **APS Merit Principle (PS Act s10A)** and the **APS Employment Principles** of fairness, transparency, and inclusion.

---

## ⚙️ Installation & Setup

```bash
# Clone repository
git clone https://github.com/<your-org>/APS-JobAppLLM.git
cd APS-JobAppLLM

# Copy environment template
cp .env.template .env
