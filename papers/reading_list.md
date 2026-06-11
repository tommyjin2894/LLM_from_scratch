# 📜 필독 논문 리스트 — LLM 역사 75편

> ⭐ = 무조건 정독 (3-pass의 3차까지). 나머지는 2-pass.
> 읽는 시점: 각 논문 옆 [Phase]가 해당 단계 진도와 맞물릴 때.
> 찾기: 제목 + 연도로 arXiv 검색. 읽기 도구: alphaxiv, 또는 PDF + 노트.

---

## 0기. 선사시대 (1997–2016) — 모든 것의 씨앗
| 논문 | 연도 | 한 줄 |
|---|---|---|
| LSTM (Hochreiter & Schmidhuber) | 1997 | 게이트로 장기기억 — RNN 시대의 왕 [Phase 05] |
| ⭐ word2vec (Mikolov) | 2013 | "예측 게임 → 의미 공간 공짜" 패턴의 원조 [05] |
| seq2seq (Sutskever) | 2014 | 인코더-디코더로 번역 — 문장→문장의 시작 [05] |
| ⭐ Bahdanau Attention | 2014 | 어텐션의 탄생 (RNN의 보조장치로) [05] |
| BPE for NMT (Sennrich) | 2016 | 서브워드 토큰화 표준화 [05] |

## 1기. 트랜스포머 혁명 (2017–2019)
| 논문 | 연도 | 한 줄 |
|---|---|---|
| ⭐⭐ Attention Is All You Need | 2017 | RNN 제거, 병렬화 혁명. **인생 첫 정독 논문** [06] |
| GPT-1 (Improving Language Understanding...) | 2018 | "사전학습+파인튜닝" 패러다임 [06] |
| BERT | 2018 | 인코더 가문의 전성기 (그리고 임베딩 모델로 생존) [06] |
| ⭐ GPT-2 (Language Models are Unsupervised Multitask Learners) | 2019 | "그냥 크게 만들었더니 멀티태스크가 됨" [07] |
| T5 | 2019 | 모든 태스크를 텍스트→텍스트로 통일 [06] |

## 2기. 스케일링 시대 (2020–2022)
| 논문 | 연도 | 한 줄 |
|---|---|---|
| ⭐ Scaling Laws (Kaplan) | 2020 | 손실은 멱법칙 — 스케일링이 과학이 됨 [07] |
| ⭐ GPT-3 (Language Models are Few-Shot Learners) | 2020 | 175B + in-context learning의 발견 [07] |
| ViT (An Image is Worth 16x16 Words) | 2020 | 이미지의 트랜스포머화 [11] |
| ⭐ CLIP | 2021 | 이미지-텍스트 공동 공간 — 멀티모달 주춧돌 [11] |
| Switch Transformer | 2021 | MoE 실용화의 신호탄 [07] |
| ⭐ LoRA | 2021 | 저랭크 어댑터 — 파인튜닝 민주화 [08] |
| RoFormer (RoPE) | 2021 | 회전 위치 인코딩 — 현 표준 [06] |
| Codex (Evaluating LLMs Trained on Code) | 2021 | 코드 모델 + HumanEval의 출발 [13] |
| ⭐ Chinchilla (Training Compute-Optimal LLMs) | 2022 | D≈20N — 데이터가 모자랐다 [07] |
| PaLM | 2022 | 540B 시대 + 창발 보고 [07] |
| ⭐ InstructGPT | 2022 | RLHF 3단계 — ChatGPT의 설계도 [08] |
| ⭐ CoT Prompting (Wei) | 2022 | "차근차근"의 마법 — 추론 시대의 씨앗 [09] |
| Self-Consistency | 2022 | 여러 번 풀고 다수결 — test-time compute 원형 [09] |
| Emergent Abilities | 2022 | 창발 주장 (+ 2023 "Mirage" 반론과 세트로) [13] |
| ⭐ FlashAttention | 2022 | IO 인식 어텐션 — HW와 알고리즘의 공진화 [10] |
| In-context Learning and Induction Heads (Anthropic) | 2022 | 해석가능성의 고전 — ICL의 회로 후보 [13] |
| ⭐ Constitutional AI | 2022 | AI가 AI를 비평 — RLAIF의 원형 [08] |

## 3기. 정렬과 오픈소스 르네상스 (2023)
| 논문 | 연도 | 한 줄 |
|---|---|---|
| ⭐ LLaMA | 2023 | "작은 모델 + 많은 토큰" + 오픈 생태계 빅뱅 [07] |
| Alpaca / Vicuna (블로그) | 2023 | $600 흉내내기 — 합성 SFT 데이터 시대 개막 [08] |
| LIMA | 2023 | SFT는 1천 개면 충분? 품질>양 논쟁 [08] |
| ⭐ DPO | 2023 | RL 없는 선호학습 — 우아함의 승리 [08] |
| ⭐ QLoRA | 2023 | 4bit 동결 + LoRA — 24GB로 70B [08,10] |
| Llama 2 | 2023 | RLHF 산업 디테일 전부 공개 [08] |
| Mistral 7B | 2023 | GQA+슬라이딩윈도 — 작은 모델의 역습 [07] |
| ⭐ vLLM (PagedAttention) | 2023 | KV캐시의 OS식 관리 — 서빙 표준 [10] |
| GPTQ / AWQ | 2023 | 4bit 양자화 양대 산맥 [10] |
| Speculative Decoding (Leviathan) | 2023 | 분포 보존 가속 — 증명이 백미 [10] |
| ⭐ LLaVA | 2023 | 인코더+프로젝터+LLM — VLM 표준 레시피 [11] |
| ReAct | 2023 | Thought/Action/Observation — 에이전트 루프 원형 [12] |
| Toolformer | 2023 | 도구 사용을 스스로 학습 [12] |
| Tree of Thoughts | 2023 | 탐색하며 생각하기 [09] |
| ⭐ Mamba | 2023 | SSM의 역습 — 어텐션 대체 후보 1호 [10] |
| Textbooks Are All You Need (Phi) | 2023 | 합성 교과서 데이터의 위력 [07] |

## 4기. 효율의 시대 (2024)
| 논문 | 연도 | 한 줄 |
|---|---|---|
| ⭐ DeepSeek-V2 | 2024 | **MLA** + 미세전문가 MoE — 효율 혁명 시작 [07,10] |
| ⭐ DeepSeekMath | 2024 | **GRPO** 원전 [08,09] |
| ⭐ Llama 3 Herd of Models | 2024 | 현대 사전학습의 백과사전 (15T 토큰, 405B) [07] |
| Qwen2.5 Tech Report | 2024 | 오픈 라인업의 표준 설계서 [07] |
| ⭐ FineWeb | 2024 | 데이터 파이프라인 전 공정 공개 [07] |
| OLMo / Dolma (AI2) | 2024 | 데이터·코드·로그까지 전부 공개한 진짜 오픈 [07] |
| ⭐ Scaling Monosemanticity (Anthropic) | 2024 | SAE로 피처 사전 — 골든게이트 클로드 [13] |
| Sleeper Agents (Anthropic) | 2024 | 안전학습이 백도어를 못 지움 [13] |
| FlashAttention-3 | 2024 | Hopper 세대 최적화 [10] |
| EAGLE | 2024 | 자체 헤드 추측 디코딩 — 프로덕션 표준 [10] |
| ⭐ Tulu 3 (AI2) | 2024 | SFT→DPO→**RLVR** 풀레시피 공개 [08] |
| ⭐ DeepSeek-V3 | 2024 | 671B MoE + FP8 + MTP, $5.6M — 효율의 교과서 [07] |
| Byte Latent Transformer | 2024 | 토크나이저 없애기 실험 [05] |

## 5기. 추론과 에이전트의 시대 (2024.9–2026)
| 논문 | 연도 | 한 줄 |
|---|---|---|
| o1 (Learning to Reason 발표/시스템카드) | 2024.9 | 추론 RL의 존재 증명 (레시피 비공개) [09] |
| ⭐⭐ DeepSeek-R1 | 2025.1 | 레시피 전체 공개 — **이 시대의 로제타석** [09] |
| Kimi k1.5 | 2025.1 | R1과 동시 발표된 또 하나의 추론 레시피 [09] |
| ⭐ s1: Simple test-time scaling | 2025.1 | 1천 샘플 + budget forcing — 추론의 최소 조건 [09] |
| Humanity's Last Exam | 2025.1 | 벤치마크 군비경쟁의 정점 [13] |
| ⭐ NSA (Native Sparse Attention) | 2025.2 | 학습부터 희소 어텐션 — 장문맥 비용 혁명 [10] |
| DAPO / Dr. GRPO / GSPO | 2025 | GRPO 패밀리 개선 3부작 [09] |
| ⭐ On the Biology of a LLM (Anthropic) | 2025.3 | 회로 추적 — 시 쓰기 사전계획, 암산 회로 [13] |
| Alignment Faking (Anthropic) | 2025 | 훈련 중에만 착한 척 — 기만 정렬 실증 [13] |
| Qwen3 / Qwen3-Next | 2025 | 하이브리드 thinking + 하이브리드 선형 어텐션 [09,10] |
| Llama 4 | 2025.4 | 10M 컨텍스트 시도 (그리고 평가 논란 — 비판적 읽기 연습) [07,13] |
| gpt-oss (OpenAI) | 2025.8 | OpenAI의 오픈웨이트 회귀 [07] |
| ⭐ Kimi K2 (+K2 Thinking) | 2025 | 1T MoE + **Muon(MuonClip)** 대규모 검증 [07] |
| DeepSeek-V3.2 (DSA) | 2025.9 | 희소 어텐션 프로덕션 투입 [10] |
| MiniMax M2 기술 노트 | 2025.10 | 선형→풀 어텐션 회귀 — 미결 논쟁의 증거 [10] |
| ⭐ DeepSeek V4 Pro/Flash 리포트 | 2026.4 | 1.6T/49B, 1M ctx, MIT — 2026 오픈 최전선 [07,10] |
| MiniMax M3 | 2026.6 | 오픈 첫 프런티어급 코딩+네이티브 멀티모달 [11] |
| Test-Time Compute 서베이 (arXiv 2501.02497) | 2025–26 | 직렬/병렬 사고 스케일링 지도 [09] |

---

## 읽기 작전
- **Phase 6 전까지는 논문 금지** (영상·코드로 충분). 06에서 "Attention Is All You Need"로 개시
- 시대순으로 읽으면 "왜 이게 나왔는지"가 보임 — 각 논문은 직전 시대의 문제를 풉니다
- ⭐⭐ 2편(Attention, R1)은 각 시대의 관문 — 안 읽히면 해당 Phase 복습 신호
- 75편이 많아 보여도: 2-pass 30분 × 주 5편 = 4개월이면 전부. 박사과정생은 이걸 5년 합니다
