# Analysis Scripts

## 1) 메타데이터 수집
```powershell
python .\analysis\fetch_openaccess_papers.py --venues CVPR2024 CVPR2025 ICCV2025 ECCV2024
```

## 2) taxonomy 분류
```powershell
python .\analysis\classify_with_taxonomy.py
```

## 3) 자동 리포트 생성
```powershell
python .\analysis\build_trend_report.py
```
