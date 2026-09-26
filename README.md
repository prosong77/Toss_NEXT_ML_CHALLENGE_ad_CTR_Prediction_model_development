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
│   ├── 01.eda.ipynb
│   └── 02_preprocessing.ipynb
│
├── src/                     # 모듈화된 파이썬 스크립트
│   ├── data_loader.py       # 데이터 로드 및 전처리 모듈
│   ├── utils.py             # 평가 지표 및 모델 저장/로드 유틸리티
│   └── train.py             # 메인 학습 실행 파이프라인
│
└── models/                  # 학습된 모델 가중치 저장 폴더 (.pkl 등)
```

## EDA 및 전처리

원본 Parquet 데이터는 `data/raw/`에 둡니다. `notebooks/01.eda.ipynb`는 청크 단위 전체 데이터 집계와 샘플 시각화를 수행하고, `notebooks/02_preprocessing.ipynb`는 고정 시드의 train/validation 분할 및 학습 데이터 기준 결측값 처리를 수행합니다.

전처리 결과는 `data/processed/` 아래 `train.parquet`, `validation.parquet`, `test.parquet`으로 저장됩니다. 숫자형 결측은 train 표본 중앙값으로 대체하고, 범주형 결측은 `__MISSING__` 값으로 보존합니다. 테스트 `ID`는 출력에 남기되 모델 특징에서는 제외합니다.

```bash
jupyter lab
```

두 노트북은 프로젝트 루트에서 순서대로 실행합니다. 데이터는 저장소에서 제외되므로 실행 전에 원본 데이터를 `data/raw/`에 준비해야 합니다.
