# Chatbot Deep Learning

## 개요

챗봇의 언어 모델 학습 및 추론 파이프라인입니다.
텍스트 데이터 전처리, 토크나이징, 모델 학습 및 평가, 추론 스크립트를 포함합니다.

## 주요 기능

* **데이터 전처리 및 토크나이징**: Pandas, NumPy 기반 데이터 처리 및 전처리 스크립트
* **모델 정의 및 학습**: TensorFlow (Keras API) 및 PyTorch 양쪽 지원
* **사전학습 모델 활용**: Hugging Face Transformers와 Hugging Face Hub 연동
* **안전한 모델 저장**: safetensors 포맷 지원
* **학습 모니터링**: TensorBoard를 통한 학습 로그 시각화
* **평가 스크립트**: 학습된 모델에 대한 성능 평가
* **추론 스크립트**: 학습된 모델을 이용한 텍스트 생성/응답

## 기술 스택

* Python `>=3.8`
* **TensorFlow** `2.19.0` (`tensorflow`, `tf_keras`)
* **Keras** `3.10.0`
* **PyTorch** `2.7.1`
* **Hugging Face Transformers** `4.53.1`
* **Hugging Face Hub** `0.33.2`
* **safetensors** `0.5.3`
* **데이터 처리**: `numpy`, `pandas`
* **유틸리티**: `tqdm`, `requests`, `python-dateutil`
* **학습 모니터링**: `tensorboard`, `tensorboard-data-server`

## 설치 및 실행

```bash
# 저장소 클론 후 이동
git clone <repository-url> chatbot_dl
cd chatbot_dl

# 가상환경 생성 및 활성화
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 의존성 설치
pip install -r requirements.txt
```

### 데이터 준비

```bash
python data/download_data.py
python data/prepare_data.py --input-dir data/raw --output-dir data/processed
```

### 모델 학습

```bash
python train.py \
  --data-dir data/processed \
  --model-dir checkpoints/ \
  --epochs 10 \
  --batch-size 32
```

### 평가

```bash
python evaluate.py \
  --model-dir checkpoints/ \
  --data-dir data/processed
```

### 추론

```bash
python serve.py --port 8501
```

## 디렉터리 구조

```
```
<!--
chatbot_dl/
├── data/
│   ├── raw/               # 원본 텍스트 데이터
│   └── processed/         # 전처리된 데이터
├── notebooks/             # Jupyter 노트북 실험
├── src/                   # 파이썬 모듈 및 스크립트
│   ├── data/              # 데이터 처리 모듈
│   ├── model/             # 모델 정의 및 학습 스크립트
│   └── utils/             # 유틸리티 함수
├── checkpoints/           # 학습된 모델 가중치
├── requirements.txt       # 의존성 목록
└── README.md
-->



