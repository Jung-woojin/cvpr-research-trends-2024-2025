# CVPR 2024-2025 연구 트렌드 분석 (ICCV/ECCV 확장 준비 버전)

이 레포는 단순 요약 문서가 아니라,  
`논문 메타데이터 수집 -> 주제 분류 -> 집계 -> 리포트 생성`까지 재현 가능한 분석 레포를 목표로 합니다.

## 왜 개편했는가
기존 트렌드 문서는 인사이트는 있었지만, 아래가 부족했습니다.
- 분류 기준(taxonomy) 공개
- 원천 데이터(raw metadata) 구조
- 재실행 가능한 집계 스크립트
- ICCV/ECCV로 확장 가능한 동일 파이프라인

이번 개편은 위 4가지를 채우는 데 초점을 뒀습니다.

## 핵심 질문
1. 2024->2025에서 실제로 증가한 주제는 무엇인가?
2. 증가/감소 추세가 과대해석인지(샘플링/분류 편향) 어떻게 검증할까?
3. CVPR에서 보인 변화가 ICCV/ECCV에서도 재현되는가?
4. 단순 "핫키워드"가 아니라 연구 투자 가치가 높은 축은 무엇인가?

## 현재 구성
```text
analysis/
  fetch_openaccess_papers.py
  classify_with_taxonomy.py
  build_trend_report.py

taxonomy/
  cv_taxonomy_v1.yaml

data/
  raw/
  processed/
  reports/

docs/
  methodology.md

reports/
  2024-2025/deep-dive-ko.md
```

## 빠른 실행
```powershell
python -m pip install -r requirements.txt
python .\analysis\fetch_openaccess_papers.py --venues CVPR2024 CVPR2025
python .\analysis\classify_with_taxonomy.py
python .\analysis\build_trend_report.py
```

생성 파일 예시:
- `data/raw/papers_openaccess.csv`
- `data/processed/papers_tagged.csv`
- `data/reports/trend_summary_by_theme.csv`
- `reports/auto-trend-report-ko.md`

## 확장 계획 (ICCV/ECCV)
1. `fetch_openaccess_papers.py`에 `ICCV2025`, `ECCV2024` 추가 실행
2. taxonomy 키워드 보강 (3D/agent/robust perception 세분화)
3. venue별 normalization 지표 추가
4. CVPR vs ICCV/ECCV 교차 비교 리포트 생성

## 읽기 권장 순서
1. [docs/methodology.md](./docs/methodology.md)
2. [reports/2024-2025/deep-dive-ko.md](./reports/2024-2025/deep-dive-ko.md)
3. `analysis/` 스크립트 실행 후 자동 보고서 확인
