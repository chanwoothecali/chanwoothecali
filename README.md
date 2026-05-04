<div align="center">

### Hi there, I'm Chanwoo 👋

**Backend Developer · Building AI on top of production systems**

운영형 백엔드 위에 AI 파이프라인을 얹는 일에 관심이 많습니다.

[![Gmail](https://img.shields.io/badge/Gmail-jungcali94@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:jungcali94@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-chanwoothecali-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/chanwoothecali)

</div>

---

### 🧭 About Me

```yaml
name:        정찬우 (Jung Chanwoo)
role:        Backend Developer @ KoreaEDS
focus:       AI Backend · LLM Pipelines · Production Reliability
location:    Seoul, Korea
education:   M.S. in Computer Software Engineering, Yonsei University (2026)
```

- 일평균 **657만+ 호출** 규모의 리테일 앱/웹 서비스에서 쿠폰·이벤트·쇼핑맵·관리자·배치 영역을 5년간 운영해왔습니다.
- 실무와 병행한 공학대학원 과정에서 LLM·RAG·QLoRA 파인튜닝 기반 AI 백엔드 파이프라인을 직접 설계·구현했습니다.
- 운영 안정성, 데이터 정합성, AI 응답 신뢰도를 함께 고려하는 백엔드를 지향합니다.

---

### 🛠 Tech Stack

**Backend**
<p>
  <img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white"/>
  <img src="https://img.shields.io/badge/Spring-6DB33F?style=flat-square&logo=spring&logoColor=white"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white"/>
  <img src="https://img.shields.io/badge/SQLAlchemy-D71F00?style=flat-square&logo=sqlalchemy&logoColor=white"/>
</p>

**Database**
<p>
  <img src="https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white"/>
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white"/>
  <img src="https://img.shields.io/badge/PGVector-336791?style=flat-square&logo=postgresql&logoColor=white"/>
</p>

**AI / LLM**
<p>
  <img src="https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white"/>
  <img src="https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=ollama&logoColor=white"/>
  <img src="https://img.shields.io/badge/HuggingFace-FFD21E?style=flat-square&logo=huggingface&logoColor=black"/>
  <img src="https://img.shields.io/badge/PEFT-FF6B00?style=flat-square&logoColor=white"/>
  <img src="https://img.shields.io/badge/QLoRA-9B59B6?style=flat-square&logoColor=white"/>
  <img src="https://img.shields.io/badge/RAG-2E86C1?style=flat-square&logoColor=white"/>
</p>

**Infra & Tools**
<p>
  <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white"/>
  <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white"/>
</p>

---

### 💼 Experience

**🏢 한국이디에스 (KoreaEDS)** · *Backend Developer* · `2019.12 — Present`

```
📌 롯데백화점 운영 (2021.01 — Present)
   └ 일평균 657만+ 호출 / 최대 일일 1,021만+ 호출 / 누적 2.03억+ 호출
   └ 쿠폰 · 모바일 이벤트 · 쇼핑맵 · 예약 · 관리자 · 배치 · 외부 연동
   └ 데이터 정합성 추적, 장애 대응, 외부 API 연동, 운영 배포

📌 NS홈쇼핑 제휴 시스템 고도화 (2020.01 — 2020.09)
   └ 제휴사 ↔ NS홈쇼핑 주문 · 배송 · CS · 정산 데이터 연동
   └ JMS 비동기 처리, PostgreSQL JSON Operator 활용
```

---

### 🚀 Featured Project

#### [HrAutoFlow](https://github.com/ctccts22/HrAutoFlow) — AI-powered Resume Analysis System

이력서 업로드부터 텍스트 추출 · 임베딩 · 벡터 검색 · LLM 분석 · RAG 질의응답까지 이어지는 **end-to-end AI 백엔드 파이프라인**을 직접 설계·구현한 대학원 졸업 프로젝트입니다.

**🔧 Backend Pipeline**
- `extracting → chunking → embedding → analyzing → completed/failed` 6단계 상태 머신 기반 처리
- `asyncio.gather` + `return_exceptions=True` 로 5개 LLM 분석 task 병렬 실행 및 부분 실패 격리
- LangChain LCEL 체인 패턴 (`prompt | llm | StrOutputParser`) 기반 프롬프트 모듈화
- PGVector + NumPy 코사인 유사도 직접 구현으로 `doc_id` 필터링 RAG 검색

**🤖 LLM Fine-tuning (Model Compression)**
- **Llama 3.1 8B Instruct** 베이스 모델 위에 **4bit QLoRA SFT** 학습
- `bnb_4bit_quant_type=nf4` · `bf16` compute · `paged_adamw_8bit` · gradient checkpointing
- 직무별 평가 어댑터 분리 학습 (`team_backend` / `team_frontend`)
- target_modules: `q/k/v/o_proj` + `gate/up/down_proj` 전체 어댑팅
- SFT 데이터셋 **14,000건 자체 설계** (tech / experience / impact / growth 4축 평가)

**⚙️ LLMOps Design**
- LLM Provider 추상화 (Ollama / OpenAI / Upstage SOLAR)
- Human-in-the-loop 평가 모델 — AI 점수와 평가자 점수 분리 저장
- QA History + Good-case Vector — RAG 응답 품질 피드백 누적 구조

```
Tech: FastAPI · PostgreSQL · PGVector · LangChain · Ollama
      Llama 3.1 8B · QLoRA · PEFT · TRL · Transformers · Next.js
```

---

### 🌱 Currently Learning

- **LangGraph** — Agent 기반 제품 설계 및 multi-step reasoning
- **vLLM · TensorRT-LLM** — Production-grade LLM serving (PagedAttention, continuous batching)
- **MSA · Kubernetes** — AI 서비스의 확장성과 운영 자동화

---

### 🎓 Education

- **M.S.** Computer Software Engineering, **Yonsei University** Graduate School of Engineering (2024 — 2026)
- **B.S.** Food and Nutrition, **The Catholic University of Korea** (2012 — 2019)

---

### 📊 GitHub Stats

<div align="center">

![Chanwoo's GitHub stats](https://github-readme-stats.vercel.app/api?username=chanwoothecali&show_icons=true&theme=default&hide_border=true&count_private=true)
![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=chanwoothecali&layout=compact&theme=default&hide_border=true&langs_count=8)

</div>

---

<div align="center">

*"안정적인 백엔드 위에, 신뢰할 수 있는 AI를 얹습니다."*

</div>
