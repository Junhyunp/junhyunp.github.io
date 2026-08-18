---
title: "[Model] Gemini 3.7 Flash — 23일 만의 교체, 무엇이 달라졌나"
excerpt: "What actually changed in Gemini 3.7 Flash, and what did not by Junhyun"
description: "구글이 3.6 Flash 를 낸 지 23일 만에 3.7 Flash 로 교체했습니다. 공식 발표와 모델 카드를 근거로 벤치마크·가격·사양에서 무엇이 바뀌고 무엇이 그대로인지 정리합니다."

categories:
    - Trend
tags:
    - [Model, Gemini, benchmark, LLM]

toc: true
toc_sticky: true

date: 2026-08-18
last_modified_at: 2026-08-18

math: true
---

구글이 **Gemini 3.7 Flash** 를 냈습니다. 직전 모델인 3.6 Flash 가 나온 지 **23일** 만입니다.

숫자는 크게 올랐는데, 정작 컨텍스트와 지식 컷오프는 그대로입니다. 무엇이 바뀌고 무엇이 안 바뀌었는지 정리합니다.

## 사양

[DeepMind 모델 카드](https://deepmind.google/models/model-cards/gemini-3-7-flash/) 기준입니다.

| 항목 | 3.6 Flash | 3.7 Flash |
|---|---|---|
| 출시 | 2026-07-21 | **2026-08-13** |
| 입력 컨텍스트 | 1M | **1M** |
| 출력 | 64K | **64K** |
| 지식 컷오프 | 2026년 3월 | **2026년 3월** |
| 모델 ID | `gemini-3.6-flash` | `gemini-3.7-flash` |

**뒤의 셋이 전부 같습니다.** 입력·출력 한도도, 지식 컷오프도 움직이지 않았습니다.

입력은 텍스트·이미지·오디오·비디오를 받고 출력은 텍스트입니다. 지식 컷오프는 2026년 3월이지만 **일부 도메인은 2025년 1월까지**라고 모델 카드가 따로 적어두고 있습니다.

## 벤치마크

[공식 발표](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-3-7-flash/)가 내놓은 수치입니다. 전부 3.6 Flash 와의 비교입니다.

| 벤치마크 | 3.6 Flash | 3.7 Flash |
|---|---|---|
| DeepSWE v1.1 | 49.0% | **65.3%** |
| FrontierCode 1.1 Main | 34.4% | **43.6%** |
| GDP.pdf | 22.0% | **34.0%** |
| AutomationBench | 17.0% | **30.4%** |
| WebDev Arena (Elo) | 1538 | **1588** |

AutomationBench 가 17.0 에서 30.4 로, DeepSWE 가 49.0 에서 65.3 으로 올랐습니다. 23일 간격치고는 큰 폭입니다.

## 그래서 무엇이 좋아진 건가

여기가 이 소식에서 가장 읽을 만한 대목입니다.

**컨텍스트가 늘어난 게 아닙니다.** 1M 그대로입니다. **더 최신 데이터를 학습한 것도 아닙니다.** 지식 컷오프가 2026년 3월로 동일합니다.

즉 이번 개선은 **더 크게 만들거나 더 많이 먹여서 얻은 것이 아닙니다.** 같은 용량, 같은 지식 범위에서 코딩·에이전트 과제 점수만 올랐습니다.

구글은 이 모델을 **"복잡한 코딩, 에이전트 워크플로, 신뢰할 수 있는 다단계 실행"** 을 위해 만들었다고 적었습니다. 올라간 벤치마크들이 정확히 그 방향입니다.

## 가격 — 반값이지만 한시적입니다

| 기간 | 입력 | 출력 |
|---|---|---|
| ~2026-12-31 | **$0.75** | **$3.75** |
| 2027-01-01 ~ | $1.50 | $7.50 |

100만 토큰 기준입니다. 도입가가 절반이라 눈에 띄지만, **정가는 3.6 Flash 와 같은 값**으로 돌아갑니다.

"Flash 가 반값이 됐다"로 요약하면 틀립니다. **연말까지 할인**입니다. 이 가격을 전제로 원가를 계산하고 있다면 2027년 1월에 두 배가 된다는 걸 같이 잡아둬야 합니다.

## Flash 는 3.7, Pro 는 3.1 프리뷰

사양보다 눈에 띄는 게 하나 있습니다.

![img_file](/assets/img/post/gemini-37-flash/flash-vs-pro.svg){: .align-center}*2026-08-18 구글 공식 모델 목록 기준으로 직접 그렸습니다*

공식 모델 목록을 보면 Flash 계열은 3.5 → 3.6 → 3.7 로 안정판이 계속 나오는데, **Pro 계열의 최신은 `gemini-3.1-pro-preview`** 입니다. 아직 프리뷰이고, 안정판 Pro 중 가장 최신은 `gemini-2.5-pro` 입니다.

**Gemini 3.5 Pro 라는 모델은 목록에 없습니다.**

> 버전 번호는 계열별로 매겨집니다. Flash 3.7 과 Pro 3.1 을 같은 축 위의 세대 차이로 읽으면 안 됩니다. "Flash 가 Pro 를 앞질렀다"는 뜻이 아닙니다.
{: .prompt-warning }

말할 수 있는 건 **두 계열의 출시 속도가 다르다**는 것까지입니다. 왜 그런지는 구글이 설명하지 않았고, 저도 모릅니다.

## 읽을 때 붙여야 할 단서

**벤치마크는 전부 구글 자체 발표입니다.** 제3자 재현이나 독립 평가가 아닙니다. 비교 대상도 자사 직전 모델 하나뿐이라, 다른 회사 모델과의 상대적 위치는 이 숫자만으로 알 수 없습니다.

**모델 카드가 한계를 스스로 적어뒀습니다.** 환각 가능성, 탈옥 저항은 개선 진행 중, 느려지거나 타임아웃이 날 수 있음 — 발표 자료가 아니라 모델 카드 쪽에 있는 내용이라 그냥 지나치기 쉽습니다.

**지식 컷오프에 예외가 있습니다.** 2026년 3월이 기본이지만 일부 도메인은 2025년 1월입니다. 최신성이 중요한 용도라면 이 단서를 기억해야 합니다.

**23일이라는 간격 자체가 판단하기 이릅니다.** 이 속도가 유지될지, 이번이 예외인지는 몇 번 더 봐야 압니다.

## 정리

Gemini 3.7 Flash 는 3.6 Flash 가 나온 지 23일 만에 그 자리를 대신했습니다.

컨텍스트(1M)와 출력 한도(64K), 지식 컷오프(2026년 3월)는 **전부 그대로**입니다. 대신 코딩과 에이전트 벤치마크가 크게 올랐습니다. 용량이 아니라 모델 품질 쪽에서 얻은 개선입니다.

가격은 연말까지 절반이고, 2027년부터 3.6 Flash 와 같은 값으로 돌아갑니다.

그리고 Flash 가 빠르게 갱신되는 동안 Pro 계열의 최신은 아직 프리뷰입니다. 다음에 지켜볼 것은 3.8 Flash 가 아니라 **Pro 쪽이 언제 안정판으로 나오는가** 라고 봅니다.

## 참고

- [Gemini 3.7 Flash: our most intelligent workhorse model](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-3-7-flash/) — Tulsee Doshi, Google, 2026-08-13 (2026-08-18 확인). 벤치마크 5종과 가격은 여기서 가져왔습니다. **전부 구글 자체 발표 수치입니다**
- [Gemini 3.7 Flash 모델 카드](https://deepmind.google/models/model-cards/gemini-3-7-flash/) — Google DeepMind (2026-08-18 확인). 컨텍스트·지식 컷오프·한계 서술의 출처입니다
- [Gemini 3.6 Flash 모델 카드](https://deepmind.google/models/model-cards/gemini-3-6-flash/) — Google DeepMind (2026-08-18 확인). 2026-07-21 출시일과 비교 사양을 여기서 확인했습니다
- [Gemini API 모델 목록](https://ai.google.dev/gemini-api/docs/models) — Google (2026-08-18 확인). Pro 계열의 최신이 `gemini-3.1-pro-preview` 라는 것과 3.5 Pro 부재는 이 목록에서 확인했습니다
- [컨텍스트 윈도우 — 대화가 길어지면 앞을 잊는 이유](/posts/context-window/) — 1M 이 무슨 뜻인지
