# 리서치 스윕 로그

blog-post 스킬이 글감을 찾으러 웹을 훑을 때마다 여기에 기록한다.
같은 걸 두 번 조사하지 않기 위한 로그이고, 사용자에게 보고한 내역도 남긴다.

- **검증**: 스타 수·논문 ID·저자를 `gh api` / arxiv 원문으로 직접 확인했는지
- 검증 안 된 항목은 `refs.yml` 로 승격하지 않는다
- Jekyll 빌드 제외 디렉토리 (사이트 노출 없음)

---

## 2026-08-07 — 1차 스윕 (프롬프트 / 에이전트 / 컨텍스트 엔지니어링)

### 레포

| 레포 | ★ | 검증 | 판단 |
|---|---|---|---|
| [openclaw/openclaw](https://github.com/openclaw/openclaw) | 385,447 | ✅ gh api | **글감 승격** — 2026년 최대 화제. 메신저 UI 기반 개인 AI 비서 |
| [ollama/ollama](https://github.com/ollama/ollama) | 177,991 | ✅ gh api | refs 등록 — 토픽 #18 의 1차 출처 |
| [langflow-ai/langflow](https://github.com/langflow-ai/langflow) | 152,923 | ✅ gh api | 보류 — 노코드 에이전트 빌더. 우리 톤(코드 중심)과 거리 |
| [langgenius/dify](https://github.com/langgenius/dify) | 151,695 | ✅ gh api | 보류 — 위와 동일 |
| [x1xhlol/system-prompts-and-models-of-ai-tools](https://github.com/x1xhlol/system-prompts-and-models-of-ai-tools) | 142,641 | ✅ gh api | refs 등록 — 실제 도구의 시스템 프롬프트 실물 |
| [anthropics/claude-code](https://github.com/anthropics/claude-code) | 140,571 | ✅ gh api | 토픽 #21, #22 의 1차 출처 |
| [microsoft/generative-ai-for-beginners](https://github.com/microsoft/generative-ai-for-beginners) | 116,903 | ✅ gh api | refs 등록 — 입문 시리즈 구성 참고 |
| [dair-ai/Prompt-Engineering-Guide](https://github.com/dair-ai/Prompt-Engineering-Guide) | 77,329 | ✅ gh api | refs 등록 — 프롬프트 표준 레퍼런스 |
| [anthropics/claude-cookbooks](https://github.com/anthropics/claude-cookbooks) | 51,092 | ✅ gh api | refs 등록 — **실행 가능한 검증 코드** 확보처 |
| [anthropics/prompt-eng-interactive-tutorial](https://github.com/anthropics/prompt-eng-interactive-tutorial) | 37,569 | ✅ gh api | refs 등록 |
| [humanlayer/12-factor-agents](https://github.com/humanlayer/12-factor-agents) | 25,116 | ✅ gh api | refs 등록. ⚠️ 2025-09 이후 푸시 없음 |
| [VoltAgent/awesome-ai-agent-papers](https://github.com/VoltAgent/awesome-ai-agent-papers) | 1,661 | ✅ gh api | refs 등록 — 논문 스윕 시작점 |
| [caramaschiHG/awesome-ai-agents-2026](https://github.com/caramaschiHG/awesome-ai-agents-2026) | 1,547 | ✅ gh api | 보류 — 링크 나열 위주, 깊이 부족 |
| [natnew/Awesome-Prompt-Engineering](https://github.com/natnew/Awesome-Prompt-Engineering) | 105 | ✅ gh api | 제외 — 검색 상위에 떴으나 스타 105. 검색 순위 ≠ 품질의 사례 |

### 논문

| 논문 | 날짜 | 검증 | 판단 |
|---|---|---|---|
| [TokenPilot: Cache-Efficient Context Management for LLM Agents](https://arxiv.org/abs/2606.17016) | 2026-06-15 | ✅ arxiv 원문 (Xu 외, Ningyu Zhang 그룹) | **글감 승격** — 컨텍스트 압축으로 비용 56~87% 절감 |
| [The Missing Memory Hierarchy: Demand Paging for LLM Context Windows](https://arxiv.org/abs/2603.09023) | 2026-03-09 | ✅ arxiv 원문 (Tony Mason, 단독) | 토픽 #2 의 비유 소재. 컨텍스트 최대 93% 감축 주장 |
| Zhang 외, "Agentic Context Engineering" (ACE), ICLR 2026 | ? | ❌ 미검증 | 2차 출처에서만 언급됨. arxiv ID 확인 필요 |
| "Evaluating AGENTS.md" | ? | ❌ 미검증 | 사람이 쓴 컨텍스트 파일은 +4%, 자동 생성은 -3% 주장. 원문 확인 필요 |
| ContextBench | ? | ❌ 미검증 | LLM 이 precision 보다 recall 을 선호 (과다 검색) 주장. 원문 확인 필요 |

### 개념 트렌드

- **prompt engineering → context engineering 으로 용어 이동.** 프롬프트 문장 다듬기가 아니라 컨텍스트 창에 무엇을 넣을지 설계하는 문제로 재정의됨.
- LangChain 의 4전략 프레이밍: **write / select / compress / isolate**. (원글 URL 재확인 필요)
- "추론 성능이 약 3,000 토큰부터 저하" 류의 수치가 여러 블로그에 돌아다님 — **원 논문 미확인, 인용 금지**.

### 이번 스윕에서 얻은 교훈

검색 1페이지 상위 = 품질 보장 아님. `natnew/Awesome-Prompt-Engineering`(★105)이 ★77,329 짜리 `dair-ai` 보다 위에 뜬 사례.
→ **레포는 반드시 `gh api` 로 스타·최근 푸시 확인 후 등록.**

---

## 2026-08-09 — 2차 스윕 (토큰 절약 / 프롬프트 압축)

### 레포

| 레포 | ★ | 검증 | 판단 |
|---|---|---|---|
| [microsoft/LLMLingua](https://github.com/microsoft/LLMLingua) | 6,533 | ✅ gh api | **refs 등록** — EMNLP'23·ACL'24 논문 뒷받침, 2026-04 푸시. 이 주제의 유일한 신뢰 출처 |
| [vaibkumr/prompt-optimizer](https://github.com/vaibkumr/prompt-optimizer) | 312 | ✅ gh api | 제외 — 2024-02 이후 방치 |
| [pleasedodisturb/awesome-llm-token-optimization](https://github.com/pleasedodisturb/awesome-llm-token-optimization) | 51 | ✅ gh api | 제외 — 링크 나열, 깊이 부족 |
| [base76-research-lab/token-compressor](https://github.com/base76-research-lab/token-compressor) | 9 | ✅ gh api | 제외 |
| maheshmakvana/llm-token-optimizer | **0** | ✅ gh api | 제외 — "LLM 지출 최대 60% 절감" 홍보 문구로 검색 상위 노출. 스타 0, 포크 0 |

### 논문

| 논문 | 날짜 | 검증 | 판단 |
|---|---|---|---|
| [LLMLingua](https://arxiv.org/abs/2310.05736) | 2023-10-09 | ✅ arxiv 원문 (Jiang 외, EMNLP 2023) | refs 등록 — 최대 20배 압축, 성능 손실 적음 |
| [Subword Units (BPE)](https://arxiv.org/abs/1508.07909) | 2015-08-31 | ✅ arxiv 원문 (Sennrich·Haddow·Birch, ACL 2016) | refs 등록 — 토크나이저 정본 |

### 인용 거부한 수치

블로그들이 반복하는 **"토큰 비용 최대 80% 절감", "63% 절감", "95~99% 절감"** 류는 전부 출처가 서로를 가리키는 SEO 양산글이라 인용하지 않음.
대신 **Anthropic 공식 문서에 명시된 수치만** 사용 (캐시 읽기 ≈ 입력가의 1/10, 배치 50%).

### 교훈 (1차 스윕의 강화판)

★0 / 포크 0 레포가 "60% 절감" 마케팅 문구만으로 검색 1페이지에 올라옴.
→ **절감률·성능 수치를 내세운 도구일수록 `gh api` 검증을 먼저.** 수치가 자극적일수록 출처가 없을 확률이 높다.

---

> ⚠️ **기록 공백: 2026-08-10 ~ 2026-08-12.**
> 이 기간에 5편(`prime-agent`, `continual-harness`, `tokenpilot`, `harness-engineering`, `claude-watermark`, `llm-hallucination`)이 나갔는데 스윕 기록이 없습니다.
> 각 글의 `## 참고` 절에 출처가 남아 있으니 재조사가 필요하면 거기서 출발하면 됩니다.
> **추측으로 채우지 않았습니다** — 직접 확인하지 않은 것을 검증된 것처럼 적으면 이 로그의 쓸모가 사라집니다.

---

## 2026-08-14 — 출처 검증 (하네스 탐색 / RAG / 임베딩)

글감 스윕이 아니라 **발행 전 1차 출처 검증** 기록입니다. 이날 3편이 나갔습니다.

### 논문 — 전부 arXiv 원문 확인

| 논문 | 날짜 | 검증 | 쓰인 곳 |
|---|---|---|---|
| [AutoDesign: Meta-Harness Optimization for Long-Horizon Agentic Design](https://arxiv.org/abs/2608.13560) | 2026-08-13 | ✅ arxiv 초록 **+ 본문** (Luo 외) | `harness-search` |
| [DarwinX: Evolving Agent Harnesses Through Natural Selection](https://arxiv.org/abs/2608.07545) | 2026-07-31 | ✅ arxiv 초록 **+ 본문** (Zhang 외) | `harness-search` |
| [Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks](https://arxiv.org/abs/2005.11401) | 2020-05-22 | ✅ arxiv 초록 (Lewis 외) | `rag-basics` — 파라메트릭/비파라메트릭 구분 |
| [Lost in the Middle](https://arxiv.org/abs/2307.03172) | 2023-07-06 | ✅ arxiv 초록 (Liu 외, TACL 2023) | `rag-basics` — 중간 손실 인용문 |
| [Searching for Best Practices in RAG](https://arxiv.org/abs/2407.01219) | 2024-07-01 | ✅ arxiv 초록 **+ 본문** (Wang 외) | `rag-basics` — 청크 512·하이브리드·리랭커 |
| [Efficient Estimation of Word Representations in Vector Space](https://arxiv.org/abs/1301.3781) | 2013-01-16 | ✅ arxiv 초록 **+ 본문** (Mikolov 외) | `embedding-basics` — King/Queen, 65.6% |
| [Sentence-BERT](https://arxiv.org/abs/1908.10084) | 2019-08-27 | ✅ arxiv 초록 (Reimers·Gurevych, EMNLP 2019) | `embedding-basics` — 65시간 → 5초 |
| [MTEB: Massive Text Embedding Benchmark](https://arxiv.org/abs/2210.07316) | 2022-10-13 | ✅ arxiv 초록 (Muennighoff 외) | `embedding-basics` — 지배적 모델 없음 |

### 초록에 없어 본문까지 열어야 했던 수치

초록만 읽고 인용하면 틀렸을 것들입니다. **2차 출처가 흔히 인용하는 숫자일수록 본문에 있습니다.**

| 수치 | 원문 |
|---|---|
| 253 도구 호출 / 11 편집턴 | `executes 253 tool calls and 11 editing turns within 40 minutes for under $3` |
| 조합 7종 | `Across the seven completed configurations…` |
| PosterBench 100편·5분야 + mini 10편 | `a 100-paper Main Track spanning five disciplines and PosterBench-mini, a shared 10-paper subset` |
| 동일 베이스 +7.7 → 83.2% | `lifts base Monet from 75.5% to 83.2% (+7.7 points)` |
| `audit-clean` 단서 | `We report audit-clean pass@1 throughout…` |
| 청크 512 · 하이브리드 · 리랭커 | `we recommend Hybrid Search with HyDE as the default retrieval method` / `The absence of a reranking module led to a noticeable drop in performance` |
| King/Queen · 유추 65.6% | `vector("King") - vector("Man") + vector("Woman") results in a vector that is closest to … Queen` / Skip-gram 1000차원·60억 단어 |

### 인용 거부

| 대상 | 이유 |
|---|---|
| Meilisearch / StackAI / FloTorch 블로그 | RAG 동향 파악용으로만 읽음. 2차 출처이고 수치 근거 불명확 → **본문 인용 안 함** |
| 초보자 글의 벤치마크 점수 | 의도적 제외. 설정 의존적 숫자는 입문자에게 오해가 더 큼 |
| WebArena-Infinity 43.5% → 93.0% | 인용하되 논문 자신의 `audit-clean` 단서를 붙이고 "이 숫자만 떼어 인용하지 말 것"을 본문에 명시 |

### 검증으로 잡아낸 오류 2건

- **`harness-search`** — 초안이 "DarwinX 의 마지막 문장"이라 한 인용문은 실제로 **초록의** 마지막 문장. 결론 마지막 문장은 따로 있음(`The harness is the surface that can still move…`). 발행 전 정정
- **`embedding-basics`** — King/Queen 예시는 word2vec 논문의 발견이 아니라 **선행 연구 인용**(`it was shown for example that`). "논문 서두가 인용한 예"로 표기

### 교훈

**초록 검증은 검증의 절반이다.** 널리 인용되는 숫자일수록 본문에 있고, 초록만 보고 "확인했다"고 적으면 실제로는 2차 출처를 믿은 것과 같아진다.
→ 본문 수치를 쓸 거면 **전문을 연다.** 열 수 없으면 그 수치를 뺀다.

**유명한 예시는 출처가 한 단계 더 있을 수 있다.** King/Queen 처럼 어디서나 인용되는 예는 그 논문의 발견이 아닐 수 있으니, "누가 처음 보였나"를 문장 형태(`it was shown that`)로 확인한다.

### 도구 함정 (GOTCHAS 후보)

`WebFetch` 로 **`arxiv.org/pdf/<id>` 를 열면 압축 바이너리라 본문을 못 읽는다.** 대신:

- 최신 논문(2024~) → `arxiv.org/html/<id>v1` — ⚠️ **버전 번호를 맞춰야 한다.** `v3` 은 404 인데 `v1` 은 열린 사례 있음
- 오래된 논문(2013 등) → `ar5iv.labs.arxiv.org/html/<id>` 로 우회 성공
