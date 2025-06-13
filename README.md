# 🧠 LLM 연구

이 프로젝트는 NVIDIA A100 80GB GPU 7번을 활용한 **LLM 연구**입니다. 데이터 전처리, 파인 튜닝 등을 포함합니다.

&nbsp;

# 🖥️ 서버 정보

- **GPU**: NVIDIA A100(80GB)
- **OS**: Ubuntu 20.04.6 LTS
- **CUDA**: 11.4
- **NVIDIA Driver**: 470.256.02
- **Python**: 3.8.10
- **환경 관리**: Container

&nbsp;

# 📂 프로젝트 구조

```bash

coding
├── part 1
│   ├── baseline_llm.ipynb
│   └── data
└── part 2
    ├── baseline_llm.ipynb
    └── data
        └── grit_all_1.csv

```

`part 1`은 연구원에서 사용하는 주간 업무를 요약하기 위해 설계된 LLM 기반 시스템의 코드 모음입니다.

`part 2`는 연구원 내부 NAS 서버의 문서 검색을 위해 설계된 LLM 기반 시스템의 코드 모음입니다.

```bash

docker
├── docker-compose.yml
├── Dockerfile
└── requirements.txt

```
