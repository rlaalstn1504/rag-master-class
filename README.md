# rag-master-class

LLM은 학습하지 않은 정보를 모릅니다. 이 저장소는 LLM이 외부 문서를 검색해 근거 있는 답변을 하도록 만드는 RAG(Retrieval-Augmented Generation)를 원리부터 고도화 기법까지 실습하는 노트북 모음입니다.

유튜브 강의: [RAG 마스터 클래스: 원리와 수학부터 최신 고도화 기법까지](https://www.youtube.com/playlist?list=PLW2PVYDtwkCw)

## 구성

| 파일 | 내용 |
|---|---|
| [01_RAG_기초와_Naive_RAG.ipynb](01_RAG_기초와_Naive_RAG.ipynb) | RAG가 필요한 이유, 임베딩과 벡터 유사도, 벡터 DB, 청킹, LCEL로 만드는 기본 RAG 체인, Naive RAG의 한계 |
| [02_Advanced_RAG와_평가_모니터링.ipynb](02_Advanced_RAG와_평가_모니터링.ipynb) | 쿼리 리라이팅, HyDE, 하이브리드 검색(BM25 + 벡터), RRF, 리랭크, 문맥 압축, Recall@K·Precision@K 평가, Langfuse 모니터링 |
| [03_RAG_실전_과제.ipynb](03_RAG_실전_과제.ipynb) | 직접 RAG 파이프라인을 설계해 정답률을 겨루는 실전 과제 (자동 채점: grading_utils.py) |

## 실행 환경

- Python 3.10에서 테스트했습니다.
- 라이브러리 버전에 따라 결과가 달라질 수 있으니 `requirements.txt`로 설치하는 것을 권장합니다.

```bash
python -m venv .venv            # 또는 conda create -n rag-master-class python=3.10
pip install -r requirements.txt
```

- `requirements.txt`의 PyTorch는 CUDA 12.1 버전입니다. GPU가 없거나 다른 CUDA 버전을 쓰면 https://pytorch.org 에서 환경에 맞는 설치 명령을 확인하세요.

## API 키 설정

`.env.example`을 복사해 `.env` 파일을 만들고 값을 채우세요. `.env`는 깃허브에 올라가지 않도록 `.gitignore`에 들어 있습니다.

```bash
cp .env.example .env
```


## 참고

- 02 노트북은 01 노트북에서 만든 벡터 DB(`faiss_index_minsu`)를 불러옵니다. 01을 먼저 실행하세요.
- 리랭크 실습은 허깅페이스 모델을 내려받으므로 처음 실행할 때 시간이 걸릴 수 있습니다.

## 문의

강의 문의: rlaalstn1504@naver.com
