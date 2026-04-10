# 러비스킬 (러셀 + 비트겐슈타인)

> 🇺🇸 [English README](./README.md)

**논리적 분해 및 의미 검증: 코드, 문서, 콘텐츠를 아름다운 상위 설계로 리팩토링**

## 사전 요구사항

- **Claude Cowork 또는 Claude Code** 환경

## 목적

ruby-skill은 설계 기술채무와 불명확한 사고의 문제를 해결합니다. Russell (구조적 분해 — 원자 요소로 절단)과 Wittgenstein (의미 검증 — 각 부분이 해야 할 말을 하는가?)을 사용하여 엉킨 구현을 명확화된 아키텍처로, 불명확한 문서를 정밀한 문장으로, 흐릿한 콘텐츠를 선명한 내러티브로 변환합니다.

## 사용 시점 및 방법

코드 리팩토링, 문서 재작성, 기존 작업의 명확성 향상이 필요할 때 배치하세요. 초안 후 다듬기로 가장 강력합니다. TRIZ (모순)와 달리 ruby-skill은 일관성과 우아함에 초점합니다. 코드, 마크다운, 콘텐츠 전반에 작동합니다.

## 사용 예시

| 상황 | 프롬프트 | 결과 |
|---|---|---|
| 지저분한 코드베이스 | `"Decompose this 500-line module into atomic functions"` | Russell 분해→Wittgenstein 검증→명확한 계층, 최소 결합 |
| 조밀한 문서 | `"Refactor this 20-section guide into precise atomic sections"` | 원자적 주장→각 섹션이 한 개 포인트 증명→통일된 내러티브 |
| 방향 없는 콘텐츠 | `"Elevate: decompose arguments, verify claims, resurface with arc"` | 주장 추출→증거 검증→일관된 내러티브로 재구성 |

## 핵심 기능

- Russell 분해: 가장 작은 의미 있는 원자 단위로 절단
- Wittgenstein 검증: 각 요소가 정확히 명시된 기능을 수행
- 이중 프레임 사이클: 분해 → 검증 → 통일된 설계로 재표면화
- 다중 도메인: 코드, 문서, 콘텐츠, 데이터 구조, 프로세스 흐름


## 연관 스킬

- **[deliverable-engine](https://github.com/jasonnamii/deliverable-engine)** — ruby-skill은 명확성 향상, deliverable-engine은 포맷팅 적용
- **[trigger-dictionary](https://github.com/jasonnamii/trigger-dictionary)** — 구조화된 리팩토링 프로토콜로 접근 가능

## 설치

```bash
git clone https://github.com/jasonnamii/ruby-skill.git ~/.claude/skills/ruby-skill
```

## 업데이트

```bash
cd ~/.claude/skills/ruby-skill && git pull
```

`~/.claude/skills/`에 배치된 스킬은 Claude Code 및 Cowork 세션에서 자동으로 사용할 수 있습니다.

## Cowork 스킬 생태계

25개 이상의 커스텀 스킬 중 하나입니다. 전체 카탈로그: [github.com/jasonnamii/cowork-skills](https://github.com/jasonnamii/cowork-skills)

## 라이선스

MIT 라이선스 — 자유롭게 사용, 수정, 공유하세요.
