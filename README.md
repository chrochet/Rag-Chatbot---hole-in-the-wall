# 🍽️ Rag-Chatbot-find-good-restaurant
**Streamlit 기반 RAG 맛집 판별 AI Chatbot**

---

## 🖥️ 프로젝트 소개
본 프로젝트는 사용자가 입력한 **가게명/후기 정보**를 바탕으로  
**RAG(Retrieval-Augmented Generation)** 기반으로 데이터를 검색하고,  
LLM이 근거 기반으로 맛집 여부를 판단해주는 **맛집 판별 AI 챗봇**이다.

---

## 🕰️ 개발 기간
- 2025.10.16 ~ 2025.11.7

---

## 🧑‍🤝‍🧑 멤버 구성
- 개인 프로젝트 (1인 개발)
- 아이디어보조 

---

## 🏆 수상
명지대학교 2025 경영대학 학술제 학장상 대상(1위) 
---

## ⚙️ 개발 환경
- **Python** 3.11+  
- **IDE** : VSCode
- **Frontend** : Streamlit  
- **Vector DB** : ChromaDB  
- **LLM API** : OpenAI API  

---

## 📁 프로젝트 구조
```bash
.
├── app_streamlit4.py          # Streamlit UI 실행 파일
├── main_v4.py                 # RAG 로직 (Retriever + LLM)
├── big_data_collector.py      # Naver API 기반 데이터 수집
├── preprocess_data.py         # 데이터 전처리
├── embed_to_chroma.py         # Embedding + ChromaDB 생성
├── config.py                  # 설정값 관리
├── requirements.txt
├── runtime.txt
├── .gitignore
├── .env.example
└── (vectordb4 / vectordb5)    # 로컬에서 생성되는 ChromaDB (Git 제외)
```
---
## 📌 주요 기능

### 01 Streamlit UI (app_streamlit4.py)
[상세보기 · WIKI](https://github.com/chrochet/Rag-Chatbot-find-good-restaurant/wiki/01-Streamlit-UI)
- 사용자 입력(가게명/지점명) 기반으로 판별을 실행하고 결과를 Streamlit 화면에 출력

### 02 RAG 판별 로직 (main_v4.py)
[상세보기 · WIKI](https://github.com/chrochet/Rag-Chatbot-find-good-restaurant/wiki/02-RAG-%ED%8C%90%EB%B3%84-%EB%A1%9C%EC%A7%81)
- ChromaDB에서 관련 리뷰 문서를 검색하고, 점수 기반 판별 + LLM 근거 요약을 생성

### 03 Naver API 데이터 수집 (big_data_collector.py)
[상세보기 · WIKI](https://github.com/chrochet/Rag-Chatbot-find-good-restaurant/wiki/03-Naver-API-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%88%98%EC%A7%91)
- 네이버 OpenAPI로 블로그 리뷰 데이터를 수집하여 RAG 학습용 원천 데이터 구축

### 04 전처리 파이프라인 (preprocess_data.py)
[상세보기 · WIKI](https://github.com/chrochet/Rag-Chatbot-find-good-restaurant/wiki/04-%EC%A0%84%EC%B2%98%EB%A6%AC-%ED%8C%8C%EC%9D%B4%ED%94%84%EB%9D%BC%EC%9D%B8)
- 리뷰 텍스트 정제/가게명 추출/점수화 및 라벨링으로 검색 품질 향상

### 05 Embedding & ChromaDB (embed_to_chroma.py)
[상세보기 · WIKI](https://github.com/chrochet/Rag-Chatbot-find-good-restaurant/wiki/05-Embedding-&-ChromaDB)
- 전처리 데이터를 임베딩하여 ChromaDB(VectorDB)에 저장하고 유사도 기반 검색 환경 구성

### 06 설정 및 판별 기준 (config.py)
[상세보기 · WIKI](https://github.com/chrochet/Rag-Chatbot-find-good-restaurant/wiki/06-%EC%84%A4%EC%A0%95-%EB%B0%8F-%ED%8C%90%EB%B3%84-%EA%B8%B0%EC%A4%80)
- 모델, DB 경로, 판별 기준(Threshold), 가중치/불용어 등 핵심 설정을 config로 통합 관리

