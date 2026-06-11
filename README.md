# 🚼→🎓 LLM 박사 만들기 (From Scratch to PhD)

> "다음 단어 맞히기 기계"가 어떻게 세상을 바꾸는지 —
> 유치원생 비유에서 시작해 진짜 박사과정 수준 연구까지 가는 풀코스 커리큘럼.
>
> **기준 시점: 2026년 6월** (최신 모델·기법 반영). 모든 단계는
> ① 🍼 유치원 비유 → ② 🧠 제대로 된 이론 → ③ 🧪 코드 실습 → ④ 🔬 최신 논문, 4층 구조로 배웁니다.

---

## 공부 철학 5계명

1. **구현 못 하면 이해 못 한 것이다.** 모든 핵심 개념은 내 손으로 다시 만든다.
   (파인만: *"What I cannot create, I do not understand"* — 이 커리큘럼의 헌법)
2. **비유 → 수식 → 코드 순서로 세 번 배운다.** 비유로 감을 잡고, 수식으로 정확해지고, 코드로 확인한다.
3. **원전(논문)을 직접 읽는다.** 블로그 요약은 입구일 뿐, Phase 6부터는 논문 PDF가 주식(主食)이다.
4. **단계마다 산출물을 남긴다.** "공부했다"가 아니라 "만들었다"가 진도의 단위다.
5. **최신 모델은 암기 대상이 아니라 사례다.** 원리를 알면 신모델은 테크리포트만 훑어도 보인다.

---

## 전체 지도

| 레벨 | 단계 | 주제 | 기간(풀타임) | 핵심 산출물 |
|------|------|------|------------|------------|
| 🍼 유치원 | [00](curriculum/00_orientation.md) | LLM이 뭐야? 큰 그림 | 1주 | 내 언어로 그린 LLM 개념 지도 |
| 🎒 기초체력 | [01](curriculum/01_math_foundations.md) | 수학 (선형대수·미적분·확률·정보이론) | 4–6주 | 손으로 푼 역전파 유도 |
| | [02](curriculum/02_programming.md) | Python·NumPy·PyTorch·GPU | 2–4주 | PyTorch MNIST 분류기 |
| | [03](curriculum/03_ml_basics.md) | 머신러닝 기초 | 2–3주 | 경사하강법 from scratch |
| 🎓 학부 | [04](curriculum/04_deep_learning.md) | 딥러닝 (역전파·최적화·정규화) | 4주 | micrograd 재구현 |
| | [05](curriculum/05_nlp_tokenization.md) | NLP·토크나이저·임베딩 | 3주 | BPE 토크나이저 from scratch |
| | [06](curriculum/06_transformer.md) | **트랜스포머 완전 해부** ⭐ | 4–6주 | GPT from scratch (셰익스피어 생성) |
| 🧑‍🔬 석사 | [07](curriculum/07_pretraining.md) | 사전학습·스케일링 법칙·데이터 | 4–6주 | GPT-2(124M) 재현 |
| | [08](curriculum/08_finetuning_alignment.md) | 파인튜닝·정렬 (SFT/RLHF/DPO/GRPO) | 4–6주 | 나만의 챗봇 (SFT+DPO) |
| | [09](curriculum/09_reasoning.md) | 추론 모델 (o1/R1, test-time compute) | 3–4주 | GRPO로 미니 추론모델 |
| | [10](curriculum/10_efficiency_inference.md) | 효율화 (양자화·KV캐시·서빙) | 3–4주 | vLLM 서빙 + QLoRA 파인튜닝 |
| 👨‍🏫 박사 코스웍 | [11](curriculum/11_multimodal.md) | 멀티모달 (비전·오디오) | 2–3주 | VLM 아키텍처 해부 노트 |
| | [12](curriculum/12_agents_rag.md) | 에이전트·RAG·도구사용·MCP | 3–4주 | 100줄 에이전트 + MCP 서버 |
| | [13](curriculum/13_evaluation_safety.md) | 평가·안전·해석가능성 | 3–4주 | lm-eval 실행 + SAE 탐험 |
| 🔬 박사 | [14](curriculum/14_phd_research.md) | 연구하는 법 + 2026 열린 문제들 | 6개월–∞ | 논문 재현 → 나의 첫 연구 |

**총 소요**: 풀타임(주 30–40h) 약 10–14개월 + 연구 기간 / 파트타임(주 10–15h) 약 2년.
진짜 박사처럼 5년 잡고 천천히 가도 됩니다 — 이 분야는 마라톤이에요.

---

## 7개의 마일스톤 (졸업시험)

| # | 시험 | 통과 기준 | 단계 |
|---|------|----------|------|
| M1 | 역전파 자격시험 | 2층 신경망 그래디언트 손으로 유도 + MNIST 97%+ | 01–04 |
| M2 | 트랜스포머 백지시험 | 아무것도 안 보고 어텐션+GPT 블록 구현, 셰익스피어 텍스트 생성 | 06 |
| M3 | 사전학습 실전 | GPT-2 124M을 FineWeb으로 재현 (클라우드 GPU, ~$100 이하) | 07 |
| M4 | 정렬 실전 | 베이스 모델 → SFT → DPO로 "말 잘 듣는 챗봇" 완성 | 08 |
| M5 | 추론 실전 | 작은 모델에 GRPO 돌려서 수학 점수 오르는 것 직접 관측 | 09 |
| M6 | 풀스택 종합시험 | Karpathy **nanochat** 풀파이프라인 1회전 (토크나이저→사전학습→SFT→RL→서빙) | 07–10 |
| M7 | 박사 자격시험 | 논문 1편 완전 재현 + 자기 연구 질문 1개로 ablation 실험 | 14 |

---

## 디렉토리 구조

```
study_llm/
├── README.md                 ← 지금 이 파일 (로드맵)
├── curriculum/               ← 단계별 교재 (00~14)
├── papers/
│   └── reading_list.md       ← 필독 논문 80편 (시대순 + 한 줄 요약)
└── appendix/
    ├── glossary.md           ← 용어집 (유치원 버전 + 정확한 정의)
    └── resources.md          ← 강의·책·코드·블로그 총정리
```

---

## 하루 루틴 (추천)

- **오전 (2–3h)**: 이론 — 강의 시청 또는 논문 읽기
- **오후 (3–4h)**: 코드 — 그날 배운 것을 직접 구현
- **저녁 (30m)**: 흐름 따라잡기 — 뉴스레터/X/HuggingFace 트렌딩 (Phase 7부터 시작해도 됨)
- **주말**: 그 주 배운 것을 글로 정리 (블로그/노트). 설명 못 하면 모르는 것.

## 건너뛰기 규칙

각 단계 첫머리에 **"건너뛰기 시험"**이 있습니다. 풀 수 있으면 그 단계는 스킵.
예: 수학 전공자는 01을, 백엔드 개발자는 02를 건너뛰고 바로 다음으로.

## 지금 당장 시작하기 (오늘 할 일 3개)

1. [`curriculum/00_orientation.md`](curriculum/00_orientation.md) 읽기 (30분)
2. Karpathy **"Deep Dive into LLMs like ChatGPT"** (YouTube, 3.5h) 보기 시작 — 전체 숲을 한 번에 보여주는 최고의 영상
3. [tiktokenizer.vercel.app](https://tiktokenizer.vercel.app)에서 아무 문장이나 쳐보고 토큰이 쪼개지는 모습 구경하기
