# HCU Risk Audit – Screaming Frog + GPT

A Python/Google Colab notebook to **score and prioritize URLs** for Google's *Helpful Content Update (HCU)* risk using exports from Screaming Frog.  
Designed for SEOs who want a **quick, data-driven way to identify and fix** potentially unhelpful content at scale.

---

## 🚀 Features
- **CSV/XLSX input** from Screaming Frog (Internal_All.csv or custom export).
- Calculates an **HCU Risk Score** (0–100) per URL based on multiple on-page & technical factors.
- Flags key content quality issues:
  - Thin content
  - Orphaned pages
  - Missing headings
  - Weak meta descriptions
  - Duplicate or missing canonicals
- **Visual distribution chart** of HCU risk.
- Exports a **prioritized list** of URLs for remediation.
- Includes a **prompt template** to push the top 50 URLs into GPT for qualitative review.

---

## 📂 Input Requirements
Export from Screaming Frog containing at least these columns:
- `Address`
- `Word Count`
- `Inlinks`
- `Indexability`
- `Meta Description 1`
- `Canonical Link Element 1`
- `H1-1`
- `H2-1`

**Accepted formats:** `.csv` or `.xlsx`

---

## 📤 Output
- **Dataframe** with all URLs and their `HCU_Risk` score.
- **Shortlist** of top-priority URLs to fix.
- CSV file `hcu_scored_urls.csv` with full results.
- GPT prompt template for qualitative review.

---

## 📊 Example Output

| Address                                | HCU_Risk | Word Count | Inlinks | H1 | H2 | Notes                          |
|----------------------------------------|----------|------------|---------|----|----|--------------------------------|
| https://example.com/thin-page          | 92       | 120        | 2       | ✅  | ❌  | Thin + low inlinks + no H2     |
| https://example.com/duplicate-content  | 85       | 400        | 10      | ✅  | ✅  | Duplicate canonical detected   |

---

## ▶️ Run in Google Colab

Click the badge below to open and run the notebook directly in Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jorgejrolo/hcu-risk-audit/blob/main/hcu_risk_audit_screamingfrog.ipynb)

---

## 🛠️ How to Use
1. Open the notebook in Colab.
2. Upload your Screaming Frog export (`.csv` or `.xlsx`).
3. Run all cells.
4. Review the **HCU Risk Distribution** chart.
5. Download the prioritized list of URLs for fixes.
6. Optionally, send the top 50 to GPT for qualitative content review.

---

## 📦 Requirements
> No local setup needed if using Colab.

If running locally:
```bash
pip install pandas matplotlib openpyxl

