# 🧰 자료 총정리 — 강의·책·코드·블로그·커뮤니티

> 원칙: **적게 골라서 끝까지.** 아래는 이미 엄선된 목록이니 "더 좋은 강의 찾아 헤매기" 금지.

## 🎬 영상 강의 (우선순위순)

| 자료 | 분량 | 용도 |
|---|---|---|
| ⭐ **Andrej Karpathy — Neural Networks: Zero to Hero** | ~16h | Phase 04–07의 등뼈. micrograd→makemore→GPT→토크나이저→GPT-2 재현 |
| ⭐ Karpathy — Deep Dive into LLMs / Intro to LLMs | 3.5h/1h | Phase 00 예고편 |
| ⭐ **Stanford CS336 — Language Modeling from Scratch** (강의+과제 공개) | 1학기 | Phase 07–10의 대학원 수업. 과제가 진국 (직접 BPE, 트랜스포머, 분산학습, 데이터, RL) |
| 3Blue1Brown — Neural networks 시리즈 | ~4h | Phase 00/01/04/06 시각적 직관 |
| Stanford CS224n (NLP with DL) | 1학기 | Phase 05–06 보조 |
| Stanford CS25 (Transformers United) | 게스트 강연 | Phase 11+ 교양 — 각 분야 1저자들의 토크 |
| Andrew Ng — ML Specialization | ~60h | Phase 03 |
| GPU Mode (YouTube 채널) | 시리즈 | Phase 10 커널/성능 심화 |

## 📚 책

| 책 | 용도 |
|---|---|
| ⭐ Sebastian Raschka, *Build a Large Language Model (From Scratch)* | Phase 05–08을 책으로 — 코드 전부 수록 (한국어판 有) |
| *밑바닥부터 시작하는 딥러닝* 1·2 (사이토 고키) | Phase 04–05 한국어 최강 입문 |
| *Mathematics for Machine Learning* (무료 PDF) | Phase 01 |
| ⭐ Nathan Lambert, *RLHF Book* (rlhfbook.com, 무료) | Phase 08–09 유일무이한 교과서 |
| *Dive into Deep Learning* (d2l.ai, 무료, 한국어 일부) | Phase 02–06 코드 중심 레퍼런스 |
| Chip Huyen, *AI Engineering* | Phase 12 실무 관점 |
| *Understanding Deep Learning* (Prince, 무료 PDF) | 이론 깊이 보강용 |

## 💻 코드 레포 (직접 뜯어볼 것들)

| 레포 | 무엇 | Phase |
|---|---|---|
| ⭐ karpathy/**micrograd** | 100줄 autograd | 04 |
| ⭐ karpathy/**minbpe** | BPE 토크나이저 | 05 |
| ⭐ karpathy/**nanoGPT** | GPT 학습 최소 구현 | 06–07 |
| KellerJordan/**modded-nanogpt** | 스피드런 (Muon 등 최신 트릭 집합소) | 07 |
| ⭐ karpathy/**nanochat** | $100 풀스택 ChatGPT 클론 — **M6 졸업작품** | 07–10 |
| huggingface/**transformers** | 산업 표준 (모델 구현 원전 대조용) | 06+ |
| huggingface/**trl** | SFT/DPO/GRPO 학습 | 08–09 |
| volcengine/**verl** | 대규모 RL (R1 재현 계열 표준) | 09 |
| Jiayi-Pan/**TinyZero** | $30으로 aha moment 재현 | 09 |
| huggingface/**open-r1** | R1 공개 재현 프로젝트 | 09 |
| vllm-project/**vllm**, sgl-project/**sglang** | 서빙 엔진 | 10 |
| ggml-org/**llama.cpp** + **ollama** | 로컬 실행 | 10 |
| EleutherAI/**lm-evaluation-harness** | 평가 표준 | 13 |
| **ARENA** (callummcdougall) | 해석가능성 실습 커리큘럼 | 13 |

## ✍️ 블로그·뉴스레터 (흐름 따라가기)

- ⭐ **Interconnects** (Nathan Lambert) — 정렬·RL·오픈모델 분석 최고봉
- ⭐ **Ahead of AI** (Sebastian Raschka) — 월간 연구 정리, 구현자 시점
- Lilian Weng — 주제별 서베이 블로그의 전설 (agents, RLHF, diffusion...)
- Simon Willison — 도구·보안(prompt injection) 실전 감각
- HuggingFace Blog — FineWeb, Ultra-Scale Playbook 등 기술 심층
- Anthropic — transformer-circuits.pub (해석가능성), Engineering 블로그 (에이전트)
- Chris Olah — colah.github.io (정보이론·신경망 시각화 고전)
- AI News (smol.ai) — 매일 전체 요약 (바쁠 때 이것만)

## 🌐 사이트·도구

- [tiktokenizer.vercel.app](https://tiktokenizer.vercel.app) — 토큰화 놀이터
- [bbycroft.net/llm](https://bbycroft.net/llm) — GPT 3D 시각화 (06 필수 체험)
- [Neuronpedia](https://neuronpedia.org) — SAE 피처 탐험 (13)
- 리더보드: [LMArena](https://lmarena.ai), [Artificial Analysis](https://artificialanalysis.ai), [llm-stats.com](https://llm-stats.com/), [Vellum 리더보드](https://www.vellum.ai/llm-leaderboard), [OpenRouter 랭킹](https://openrouter.ai/rankings)(실사용량)
- 논문: arXiv (cs.CL/cs.LG), [HF Daily Papers](https://huggingface.co/papers), alphaxiv
- 모델 동향 추적: [felloai 월간 정리](https://felloai.com/best-ai-models/), [오픈소스 지형도](https://codersera.com/blog/open-source-llms-landscape-2026/), [HF 오픈 LLM 정리](https://huggingface.co/blog/daya-shankar/open-source-llms)

## 🇰🇷 한국어 자료

- 위키독스 — *딥 러닝을 이용한 자연어 처리 입문* (무료, Phase 05)
- 《밑바닥부터 시작하는 딥러닝》 시리즈 (한빛미디어)
- 모두의연구소 / 가짜연구소 — 스터디 그룹 (14의 "랩 동료" 대체재)
- 업스테이지·네이버·LG AI 기술 블로그 — 한국어 LLM 학습 사정 (토크나이저, 한국어 벤치마크 KMMLU 등)

## 👥 커뮤니티

- **EleutherAI Discord** — 오픈 LLM 연구의 본진 (질문 수준 높음)
- HuggingFace Discord / 포럼
- r/LocalLLaMA — 로컬 모델·양자화 실전 정보 최속
- X(트위터) — 연구자 직접 팔로우 (논문 저자들이 스레드로 해설하는 시대)

## 💸 GPU 예산 가이드 (2026)

| Phase | 필요 | 비용 |
|---|---|---|
| ~06 | Colab/Kaggle 무료 | $0 |
| 07 (M3) | H100 1장 × 수십 시간 (RunPod/Lambda/Vast) | $30–100 |
| 08–09 (M4–M5) | 24–80GB 1장 × 수십 시간 | $50–150 |
| 10 (M6 nanochat) | 8×H100 × 4시간급 | ~$100 |
| 14 연구 | 과제 따라 | 월 $100–500 (작은 스케일 프록시 설계가 실력) |

> 총 ~$300–500이면 "박사급 실습 전 과정"이 가능한 시대. 10년 전엔 수억 원이었습니다.
