# 02. 프로그래밍 — Python, PyTorch, 그리고 GPU

> **기간**: 2–4주 (01과 병행 가능) | **선행**: 없음 | **산출물**: PyTorch로 MNIST 분류기 (정확도 97%+)
>
> **건너뛰기 시험**: ① 파이썬 클래스/데코레이터/제너레이터를 씀 ② NumPy 브로드캐스팅 규칙 설명 가능 ③ `nn.Module` 상속해서 모델 짜고 학습 루프 작성 가능 — 셋 다 되면 03으로 (③만 안 되면 PyTorch 절만).

### 🍼 유치원 버전
요리사(나)에게 필요한 것: **칼질(Python)**, **만능 조리기구(PyTorch)**, **초강력 화력(GPU)**.
GPU는 곱셈을 한 번에 수만 개씩 하는 기계야. CPU가 셰프 1명이라면 GPU는 단순 작업 알바 1만 명.
행렬곱은 단순 작업이 수억 개라서 알바 군단이 압승.

---

## 1. Python 핵심 (아는 사람은 스킵)

LLM 코드 읽기에 필요한 것만: 자료구조, 함수/클래스, 컴프리헨션, 제너레이터(`yield` — 데이터로더가 이것),
컨텍스트 매니저(`with torch.no_grad()`), 타입힌트, `dataclass`, f-string.
- 자료: 공식 튜토리얼 또는 *점프 투 파이썬* (한국어 무료)

## 2. NumPy — 텐서 감각 키우기

| 개념 | 핵심 | 왜 중요 |
|---|---|---|
| ndarray, shape, dtype | 모든 데이터는 다차원 배열 | LLM 코드의 모국어 |
| **브로드캐스팅** | (8,1024,768) + (768,) 가 되는 규칙 | 버그의 80%가 여기서 나옴. 규칙을 외울 것: 뒤에서부터 맞추고, 1은 늘어난다 |
| 인덱싱/슬라이싱/마스킹 | `a[a > 0]`, `a[:, -1, :]` | causal mask 만들 때 |
| `einsum` | `np.einsum('bij,bjk->bik', A, B)` | 어텐션 구현이 우아해짐. 미리 친해지기 |
| 벡터화 | for문 금지 정신 | 1000배 속도 차이 |

**실습**: for문으로 짠 행렬곱 vs `@` 연산자 속도 비교 (1000×1000) — GPU가 왜 필요한지 몸으로 느끼기.

## 3. PyTorch — 이 커리큘럼의 주력 무기

### 🍼 PyTorch가 뭐가 좋아?
NumPy랑 거의 똑같이 생겼는데 두 가지 마법이 있어:
① 계산 과정을 **자동으로 기억**했다가 "누구 탓인지"(그래디언트)를 거꾸로 계산해줘 (**autograd**)
② `.cuda()` 한 줄이면 알바 1만 명(GPU)에게 일을 넘겨줘.

### 🧠 꼭 익힐 것 (이 순서대로)
1. **Tensor 기본**: 생성, shape 조작 (`view/reshape`, `transpose`, `unsqueeze`, `cat`, `stack`)
2. **autograd**: `requires_grad=True`, `loss.backward()`, `tensor.grad`, `torch.no_grad()`
   - 미니 실험: `y = x**2`에서 `y.backward()` 후 `x.grad == 2x` 확인 — 01의 미분이 코드가 되는 순간
3. **nn.Module**: `__init__`에 레이어, `forward`에 계산. `nn.Linear`, `nn.Embedding`, `nn.LayerNorm`
4. **학습 루프 5단계 의식(ritual)** — 평생 수천 번 쓸 패턴:
   ```python
   for x, y in dataloader:
       optimizer.zero_grad()     # 1. 이전 그래디언트 지우기
       pred = model(x)           # 2. 순전파
       loss = criterion(pred, y) # 3. 손실 계산
       loss.backward()           # 4. 역전파 (자동!)
       optimizer.step()          # 5. 다이얼 돌리기
   ```
5. **Dataset/DataLoader**: 배치, 셔플, `collate_fn`
6. **GPU**: `model.to('cuda')`, 텐서도 같은 디바이스로. `torch.cuda.is_available()`
7. (예고) `torch.compile`, mixed precision(`bf16`) — Phase 07에서 본격 사용

### 📚 자료
- 공식 "PyTorch 60 Minute Blitz" → "Learning PyTorch with Examples" (NumPy→Tensor→autograd 진화 과정이 백미)
- 책: *Deep Learning with PyTorch* 또는 d2l.ai (한국어판 있음)

## 4. GPU와 개발 환경

| 항목 | 추천 (2026) |
|---|---|
| 무료 GPU | Google Colab (T4), Kaggle (T4/P100 주 30h) — Phase 06까지 충분 |
| 유료 (Phase 07+) | RunPod, Lambda, Vast.ai에서 A100/H100 시간당 임대. GPT-2 재현 ~$30–100 |
| 환경 관리 | `uv` (2026 표준, pip보다 100배 빠름) 또는 conda |
| 실험 기록 | `wandb` 무료 계정 — 손실 곡선 추적 습관은 지금부터 |
| 코드 관리 | git + GitHub. 모든 실습은 커밋으로 남기기 |
| VRAM 감각 | 파라미터 1B ≈ FP16으로 2GB. 학습은 그 ~8배(그래디언트+옵티마이저+활성값). "7B 모델 추론 = 14GB+" 암산 가능해야 |

## 🧪 실습 과제

1. **[필수]** NumPy로 선형회귀: y=3x+2+노이즈 데이터 생성 → 경사하강법 직접 구현 → w≈3, b≈2 수렴 확인
2. **[필수]** 같은 문제를 PyTorch autograd로 다시 (손 미분 vs 자동 미분 비교)
3. **[필수: 졸업작품]** MNIST 손글씨 분류기: `nn.Linear` 2~3층, 97%+ 달성, wandb에 손실곡선 기록
4. **[심화]** einsum으로 배치 행렬곱, 내적, 트레이스 각각 구현
5. **[심화]** Colab에서 GPU/CPU 행렬곱(4096×4096) 시간 비교 — 몇 배 빠른지 기록

## ✅ 졸업 조건
- [ ] 학습 루프 5단계를 안 보고 작성
- [ ] `view(B, T, H, D).transpose(1, 2)` 가 무슨 shape을 만드는지 즉답 (Phase 06 멀티헤드에서 매일 봄)
- [ ] MNIST 97%+ 스크린샷
- [ ] "7B 모델을 BF16으로 추론하면 VRAM 몇 GB?" 즉답 (~14GB + KV캐시)
- [ ] git에 커밋 10개 이상 쌓임
