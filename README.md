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
python .\analysis\fetch_openaccess_papers.py --venues CVPR2024 CVPR2025 ICCV2025 ECCV2024
python .\analysis\enrich_abstracts.py --input data/raw/papers_openaccess.csv --output data/raw/papers_with_abstracts.csv --workers 12
python .\analysis\classify_with_abstract.py --input data/raw/papers_with_abstracts.csv
python .\analysis\build_trend_report.py --tagged data/processed/papers_tagged_abstract.csv --summary data/reports/trend_summary_by_theme_abstract.csv
python .\analysis\build_cross_venue_report.py --summary data/reports/trend_summary_by_theme_abstract.csv
```

Note:
- Abstract enrichment may take time for large venue sets.
- Use `--max-papers 1000` for a quick run and `--max-papers 0` for full enrichment.

## Main Korean Entry
- [README-korean.md](./README-korean.md)

## Methodology
- [docs/methodology.md](./docs/methodology.md)
