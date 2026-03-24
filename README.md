# CV Research Trends (2024-2025) with Reproducible Pipeline

This repository tracks CVPR 2024-2025 trends and prepares expansion to ICCV/ECCV.

## What Changed
This repo is now organized as an analysis pipeline, not only a text summary.

- collect paper metadata
- classify papers with a taxonomy
- aggregate trend statistics
- generate reports

## Structure
```text
analysis/      # scripts: fetch, classify, report
taxonomy/      # category taxonomy + keyword rules
data/          # raw/intermediate/final outputs
docs/          # methodology and assumptions
reports/       # generated reports
README-korean.md
```

## Quick Start
```powershell
python -m pip install -r requirements.txt
python .\analysis\fetch_openaccess_papers.py --venues CVPR2024 CVPR2025
python .\analysis\classify_with_taxonomy.py
python .\analysis\build_trend_report.py
```

## Main Korean Entry
- [README-korean.md](./README-korean.md)

## Methodology
- [docs/methodology.md](./docs/methodology.md)
