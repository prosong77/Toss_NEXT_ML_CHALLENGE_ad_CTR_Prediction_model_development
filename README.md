## 📂 Project Directory Structure

```text
data_project/
├── .gitignore               # Git 추적 제외 설정 파일
├── README.md                # 프로젝트 설명서 (가장 중요)
├── environment.yml          # 아나콘다 가상환경 설정 파일
│
├── data/                    # 데이터 저장소 (.gitignore로 관리)
│   ├── raw/                 # 원본 데이터 (.gitkeep으로 폴더 구조 유지)
│   └── processed/           # 전처리 완료된 데이터
│
├── notebooks/               # EDA 및 실험용 주피터 노트북
│   ├── 01_eda.ipynb
│   └── 02_preprocessing.ipynb
│
├── src/                     # 모듈화된 파이썬 스크립트
│   ├── data_loader.py       # 데이터 로드 및 전처리 모듈
│   ├── utils.py             # 평가 지표 및 모델 저장/로드 유틸리티
│   └── train.py             # 메인 학습 실행 파이프라인
│
└── models/                  # 학습된 모델 가중치 저장 폴더 (.pkl 등)
