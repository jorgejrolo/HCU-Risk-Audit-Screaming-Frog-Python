# HCU Risk Audit – Screaming Frog + Python

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jorgejrolo/HCU-Risk-Audit-Screaming-Frog-Python/blob/main/hcu_risk_audit_screamingfrog.ipynb)

## Overview
This project scores and prioritizes website URLs for **Helpful Content Update (HCU) risk** using exports from **Screaming Frog SEO Spider**.  
It’s designed for SEOs who want to quickly identify pages that might be impacted by Google’s HCU and take **data-driven corrective action**.

**Author:** Jorge J. Rolo  
**Purpose:** Prioritize URLs by HCU risk using Screaming Frog exports.

---

## Features
- 📊 **Risk scoring (0–100)** based on thin content, orphaned pages, lack of structure, and more.
- 🔍 **High-impact fixes** list for immediate action.
- 🤖 **GPT prompt template** to review the top 50 risky URLs qualitatively.
- 📥 Supports **CSV and Excel** Screaming Frog exports.
- ⚡ Fast, reproducible workflow in **Google Colab** or locally.

---

## Input
Export from Screaming Frog in one of these formats:
- **Internal_All.csv**
- **Custom export** with these columns:
  - `Address`
  - `Title 1`
  - `Meta Description 1`
  - `Word Count`
  - `H1-1`
  - `H2-1`
  - `Status Code`
  - `Canonical Link Element 1`
  - `Inlinks`
  - `Outlinks`
  - `Indexability`
  - *(…other columns are optional but recommended)*

---

## Output
1. **Scored table** with `HCU_Risk` (0–100) and explanations.
2. **Shortlist** of high-priority URLs to fix.
3. **Prompt template** to send top 50 risky URLs to GPT for qualitative review.

---

## How to Run

### Option 1: Google Colab (Recommended)
1. Click the badge at the top of this README or [open this link](https://colab.research.google.com/github/jorgejrolo/HCU-Risk-Audit-Screaming-Frog-Python/blob/main/hcu_risk_audit_screamingfrog.ipynb)
2. Upload your Screaming Frog export (CSV or XLSX).
3. Run all cells and review the generated outputs.

### Option 2: Local Python Environment
```bash
git clone https://github.com/jorgejrolo/HCU-Risk-Audit-Screaming-Frog-Python.git
cd HCU-Risk-Audit-Screaming-Frog-Python
pip install -r requirements.txt
jupyter notebook hcu_risk_audit_screamingfrog.ipynb
Example Output
Address	HCU_Risk	Word Count	Inlinks	H1	H2	Notes
https://example.com/page-1	92	120	1	Yes	No	Thin + orphan + no structure
https://example.com/page-2	65	800	5	Yes	Yes	Solid but meta description missing

Notes
HCU Risk is a relative metric: higher scores = higher priority for review.

The script does not make changes to your site — it only analyzes and prioritizes.

You can tweak the scoring formula inside the notebook to fit your specific SEO context.

License
MIT License © 2025 Jorge J. Rolo

