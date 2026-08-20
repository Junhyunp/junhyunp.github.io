---
title: "[Policy] 책을 파쇄해 AI를 학습시키는 일 — 법원은 이미 판단했습니다"
excerpt: "Destructive book scanning for AI training, and what a US court actually ruled by Junhyun"
description: "AI 학습을 위해 책을 파쇄 스캔하는 관행을 다룹니다. 미국 법원이 무엇을 공정 이용으로 보고 무엇에 15억 달러를 물렸는지, 늘 뒤섞여 인용되는 두 갈래를 갈라 정리합니다."

categories:
    - Trend
tags:
    - [Policy, training data, copyright, ethics]

toc: true
toc_sticky: true

date: 2026-08-20
last_modified_at: 2026-08-20

math: true
---

이 블로그는 모델과 도구를 주로 다뤄왔습니다. 이번에는 **그 모델이 무엇을 먹고 자랐는가** 쪽입니다.

계기는 지난주 보도였는데, 찾아보니 정작 중요한 건 그 보도가 아니었습니다. **이 관행에 대해 미국 법원이 이미 판단을 내려뒀습니다.** 그리고 그 판단이 대부분의 기사에서 뒤섞여 인용되고 있습니다.

## 계기가 된 보도

404 Media 가 2026-08-17 에 낸 기사입니다. 헌책 대량 주문을 수상히 여긴 서점 쪽과 협력해, **추적기를 넣은 책이 어디로 가는지** 따라갔습니다.

도착지는 라스베이거스의 Amazon 창고(시설 코드 VGT3)였고, 그곳 직원들의 말로는 대량으로 들어온 인쇄본의 **제본을 뜯어 빠르게 스캔하며, 그 과정에서 인쇄본은 파괴된다**는 것입니다.

> 이 기사는 **유료 구독 벽 뒤에 있어 미리보기까지만 확인했습니다.** 추적 규모나 기간, 그리고 **Amazon 측 입장이 실렸는지**를 확인하지 못했습니다. 그래서 이 글은 Amazon 이 무엇을 하고 있는지 단정하지 않습니다.
{: .prompt-warning }

여기까지 읽으면 반응은 대개 하나입니다. "그래도 되나?"

## 그런데 이건 새로운 일이 아닙니다

같은 일이 이미 법정에서 다뤄졌습니다. **Bartz v. Anthropic** 입니다.

작가 세 명이 Anthropic 을 상대로 낸 저작권 소송인데, 2025년에 세 가지가 연달아 나왔습니다.

![img_file](/assets/img/post/ai-training-data-books/two-tracks.svg){: .align-center}*판결과 합의 내용을 갈래별로 정리해 직접 그렸습니다*

## 법원이 가른 두 갈래

핵심은 **책을 어디서 구했느냐** 였습니다.

| | 행위 | 판단 |
|---|---|---|
| ① | 중고·절판본을 **사서** 제본을 뜯고 스캔한 뒤 원본을 버리고 학습에 사용 | **공정 이용** |
| ② | 해적 사이트(LibGen·PiLiMi)에서 내려받아 **보관** | **침해** |

2025년 6월 Alsup 판사는 ①에 대해 **"본질적으로 변형적(quintessentially transformative)"** 이라며 공정 이용으로 판단했습니다.

**파쇄 자체는 문제가 되지 않았습니다.** 산 책을 어떻게 처리하든 그건 소유자의 몫이라는 쪽에 가깝습니다.

반면 ②는 다르게 봤습니다. 해적판을 내려받아 **"중앙 도서관(central library)"** 으로 쌓아둔 행위는 변형적이지 않고 침해라고 판단했습니다.

## 15억 달러는 무엇에 대한 값인가

여기서 숫자가 자주 틀리게 인용됩니다.

| 숫자 | 무엇인가 |
|---|---|
| **약 700만 권** | 2025년 7월 인증된 **집단(class)의 범위** — LibGen·PiLiMi 다운로드분의 저작권자 |
| **482,460권** | **합의가 실제로 다룬 저작물 수** — ISBN/ASIN 이 있고 저작권 등록 요건을 충족한 것 |
| **15억 달러** | 그 482,460권에 대한 합의금. 비용을 제하면 권당 약 **$3,100** |

**700만과 482,460은 다른 숫자입니다.** 앞은 소송에 참여할 수 있는 범위이고, 뒤는 돈이 지급되는 대상입니다. 이걸 뭉개면 "책 한 권당 얼마"가 완전히 달라집니다.

그리고 **이 돈은 ②에 대한 것입니다.** ①, 즉 사서 파쇄한 책에 대해서는 배상이 없습니다. 공정 이용이었으니까요.

합의는 2025년 8월 26일 기본 합의서, 9월 초 예비 승인 절차를 거쳤고, **2025년 8월 25일 이전의 행위**에 대한 면책입니다.

## "Project Panama" — 찾을 수 없는 인용

이 주제를 검색하면 Anthropic 내부 문서 인용이라며 이런 문장이 반복해서 나옵니다.

> 세상의 모든 책을 파괴적으로 스캔하려는 우리의 노력

찾아봤는데 **출처를 추적할 수 없었습니다.** 제가 열 수 있었던 기사는 이것을 직접 인용이 아니라 "내부 기획 문서에 대한 서술"이라고 스스로 밝히고 있었고, 어느 제출 문서의 몇 번 증거인지는 아무도 적지 않습니다. 함께 도는 벤더 이름과 수량도 다른 매체 재인용이었습니다.

**그래서 이 글에는 넣지 않았습니다.** 사실이 아니라는 뜻이 아니라, 제가 확인하지 못했다는 뜻입니다.

## 이 글의 출처 한계

명시해둡니다.

**판결문 원문을 직접 읽지 못했습니다.** 법원 문서 사이트 두 곳과 원 보도 매체가 모두 접근을 차단했습니다. 대신 **법률 전문 매체와 로펌 분석 두 곳**을 통해 확인했고, 둘이 서로 독립적으로 같은 표현("quintessentially transformative")을 따옴표로 인용한 점을 근거로 삼았습니다.

**404 Media 기사는 미리보기까지만 봤습니다.**

**이 글은 미국 판결에 대한 정리입니다.** 한국 저작권법에서 같은 결론이 나오는지는 다른 문제이고, 저는 그 판단을 할 위치에 있지 않습니다.

## 그래서 무엇을 생각해야 하나

**"불법인가"라는 질문은 이미 답이 나왔습니다.** 적어도 미국에서, 산 책을 파쇄해 스캔하고 학습에 쓰는 것은 공정 이용입니다. 분노하든 아니든 그게 현재의 법적 상태입니다.

그래서 남는 질문은 다른 것입니다.

**되돌릴 수 없다는 점.** 절판본이나 희귀본은 스캔되고 나면 그 물리적 사본이 사라집니다. 디지털 사본은 스캔한 회사가 갖습니다. 법이 허용하는 것과 그것이 남기는 결과는 별개입니다.

**규모가 다르다는 점.** 도서관도 오래 책을 디지털화해 왔습니다. 다른 것은 목적과 속도입니다.

**우리가 쓰는 모델도 여기서 왔다는 점.** 이 블로그에서 다루는 모델들이 이 과정을 거친 데이터 위에 서 있습니다. 그걸 알고 쓰는 것과 모르고 쓰는 것은 다릅니다.

## 정리

AI 학습을 위해 책을 사서 제본을 뜯고 스캔한 뒤 버리는 일은 **미국 법원이 공정 이용으로 판단했습니다.** 파쇄가 문제가 된 게 아니라, 갈린 것은 그 책을 어디서 구했느냐였습니다.

15억 달러가 나온 쪽은 **해적 사이트에서 받아 보관한 책**입니다. 대상은 482,460권이고, 집단 범위로 인증된 700만 권과는 다른 숫자입니다.

지난주 보도는 이 관행이 2026년에도 이어지고 있다는 정황입니다. 다만 유료 벽 때문에 저는 그 기사를 끝까지 읽지 못했고, 반론이 실렸는지도 모릅니다.

**분노할 지점과 법이 허용하는 지점이 어긋나 있다는 것**, 그게 이 사안에서 가장 중요한 부분이라고 생각합니다.

## 참고

- [The Bartz v. Anthropic Settlement: Understanding America's Largest Copyright Settlement](https://legalblogs.wolterskluwer.com/copyright-blog/the-bartz-v-anthropic-settlement-understanding-americas-largest-copyright-settlement/) — Kluwer Copyright Blog (2026-08-20 확인). 판시 내용, 482,460권, 권당 약 $3,100, 면책 범위의 출처입니다
- [Bartz v. Anthropic: Settlement reached after landmark summary judgment and class certification](https://www.insidetechlaw.com/blog/2025/09/bartz-v-anthropic-settlement-reached-after-landmark-summary-judgment-and-class-certification) — Norton Rose Fulbright (2026-08-20 확인). "중앙 도서관" 판단과 합의 일정의 출처입니다. 위 항목과 **독립적으로 같은 표현을 인용**합니다
- [Bartz v. Anthropic: Judge Alsup certifies class for rightsholders of 7 million books](https://authorsalliance.substack.com/p/bartz-v-anthropic-judge-alsup-certifies) — Authors Alliance (2026-08-20 확인). 집단 인증 범위와 요건의 출처입니다
- [We Tracked a Shipment of Rare Books. It Ended at an Amazon AI Training Facility](https://www.404media.co/we-tracked-a-shipment-of-rare-books-it-ended-at-an-amazon-ai-training-facility/) — Emanuel Maiberg, 404 Media, 2026-08-17 (2026-08-20 확인). **유료 구독 기사로 미리보기까지만 확인했습니다**
- [Simon Willison 의 소개 글](https://simonwillison.net/2026/Aug/17/we-tracked-a-shipment-of-rare-books-it-ended-at-an-amazon-ai-tra/) — 2026-08-17. 이 보도를 알게 된 경로입니다
