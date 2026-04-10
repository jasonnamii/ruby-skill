# Wittgenstein Philosophical Frame
비트겐슈타인의 철학을 실무 의미검증 도구로 변환한 프레임

## I. 그림이론 (Picture Theory) — 명제와 현실의 동형성

### 비트겐슈타인의 주장
**Tractatus 4.01**: "A sentence is a picture of reality"
- 명제의 의미는 그것이 현실의 어떤 상태(state of affairs)를 그리고 있다는 데서 비롯된다
- 명제와 사실은 **구조적 동형성(isomorphism)**을 가진다
- 마치 "gramophone record, musical thought, musical notation, sound waves"가 서로 내적 관계를 가지듯이 언어와 현실도 같은 방식으로 연결된다

### 실무 적용: 코드/문서의 "정확도" 검증
**질문**:
- 함수명이 실제 동작을 정확히 그리고 있는가? (예: `getUserData()`가 정말 user data만 반환하는가?)
- 다이어그램의 상자와 화살표가 실제 시스템 흐름과 1:1 대응되는가?
- 문서의 구조(챕터→섹션→항목)가 독자의 이해 과정(전체→세부→사례)과 동형인가?
- 설정값이 실제 런타임 동작을 반영하는가?

**의미**: 코드/문서가 현실을 거짓말 없이 정확히 표현하고 있는지 체크

---

## II. 말할 수 있는 것과 말할 수 없는 것

### 비트겐슈타인의 주장
**Tractatus 7**: "Whereof one cannot speak, thereof one must be silent"
- 형식(form)으로 표현 가능한 명제만 의미가 있다
- 행간, 맥락, 암묵적 지식은 "보여질 수" 있지만 "말해질" 수는 없다

### 실무 적용: 명시 vs 암묵의 균형
**질문**:
- 이 코드의 제약은 타입 시스템에 명시되어 있는가, 아니면 개발자 관례일 뿐인가?
- 문서가 "왜"를 설명하려 애쓰고 있는가? (설명 불가능한 직관을 억지로 표현하려는 시도)
- 복잡한 알고리즘을 말로 설명하는 것보다 시각화(다이어그램)가 더 효과적인가?
- 일부 지식은 코드 리뷰/페어프로그래밍 같은 실천(practice)으로만 전수되어야 하는가?

**의미**: 무리하게 명시화하려는 것이 무엇인지 구분. "침묵"하는 것도 설계 선택

---

## III. 논리적 형식 (Logical Form) — 조건부와 진리함수

### 비트겐슈타인의 주장
**Tractatus**: 명제는 진리함수로 분해된다
- 원자 명제(atomic proposition)와 논리 연산(AND, OR, NOT)으로만 의미가 결정된다
- 모든 가능한 진리값 조합에 대해 명제의 진리성이 결정되어야 한다

### 실무 적용: 조건문과 분기 로직의 완전성
**질문**:
- 이 if-else 체인이 모든 경우를 (중복 없이, 빠짐 없이) 다루는가?
- 중첩된 조건문을 진리표로 펼쳐보면 실제 의도한 로직과 일치하는가?
- 불가능한 상태(dead code)가 남아 있는가?
- API의 에러 처리가 모든 실패 케이스를 명시적으로 다루는가?

**의미**: 로직의 "틈새"를 찾는 도구. 완전성과 명확성 검증

---

## IV. 언어게임 (Language Games) — 의미는 사용에 있다

### 비트겐슈타인의 주장
**Philosophical Investigations 23, 43**: 
- "The meaning of a word is its use in the language"
- 같은 단어도 다른 "게임"(문맥)에서는 완전히 다른 의미를 갖는다
- 의미는 사전 정의가 아니라 **실제 사용 관례(practice)**로 결정된다

### 실무 적용: 용어와 함수명의 맥락 일관성
**질문**:
- "User"가 이 파일에서는 "등록한 사람", 저 파일에서는 "로그인한 세션"을 뜻하는가? (게임 혼동)
- 함수 `process()`가 동사로 너무 추상적이지 않은가? (사용 맥락을 읽어야 의미를 알 수 있다)
- 팀 내에서 같은 단어를 다르게 사용하고 있는가? (예: "request"는 HTTP, 비즈 요청, 사용자 요청?)
- 독자(개발자/사용자)가 이 용어를 "어떻게 사용"해야 하는지 예시가 있는가?

**의미**: 용어의 일관성과 맥락 적절성 검증. "사전"이 아니라 "실제 사용"이 표준

---

## V. 가족유사성 (Family Resemblance) — 경계 없는 분류

### 비트겐슈타인의 주장
**Philosophical Investigations 66-71**:
- 범주는 하나의 본질적 특성으로 정의되지 않는다
- "게임"이 무엇인지 정의할 수 없는 것처럼, 범주는 **중첩된 유사성 네트워크**를 가진다

### 실무 적용: 상속 vs 컴포지션, 분류의 재설계
**질문**:
- 상속 계층을 강제하려 애쓰고 있지 않은가? (유사한 클래스들이 공통 기본클래스를 못 찾음)
- 문서의 분류 체계(카테고리)가 독자의 다양한 진입점을 모두 지원하는가?
- 과도한 상속/분류 vs 명확함의 트레이드오프는?

**의미**: "완벽한 분류"를 버리고 "실용적 유사성"으로 설계 재검토

---

## VI. 규칙 따르기 (Rule Following) — 해석 아닌 관행

### 비트겐슈타인의 주장
**Philosophical Investigations 201**:
- "No course of action could be determined by a rule, because any course of action can be made out to accord with the rule"
- 규칙의 의미는 추상적 정의가 아니라 **공동체의 관행(practice)**에서 비롯된다

### 실무 적용: 컨벤션과 가이드의 실효성
**질문**:
- 코딩 가이드가 있지만, 팀의 실제 코드는 다르게 작성되는가?
- 규칙을 "해석"하는 데 시간을 쓰고 있는가? (모호한 규칙)
- 새 팀원이 규칙을 명시적으로 배워야 하는가, 아니면 코드를 읽고 보고 따라하면 되는가?

**의미**: 규칙은 종이가 아니라 **실천 공동체의 습관**이어야 한다

---

## VII. 삶의 형식 (Form of Life) — 맥락이 의미를 결정한다

### 비트겐슈타인의 주장
**Philosophical Investigations 19, 23**:
- "To imagine a language means to imagine a form of life"
- 언어는 추상적 시스템이 아니라 **구체적 삶의 실천**에 뿌리박혀 있다

### 실무 적용: 맥락의 재검증
**질문**:
- 독자/사용자의 실제 업무 흐름을 반영하고 있는가?
- 기술 결정이 회사 규모, 팀 구성, 배포 문화와 맞는가?
- "논리적으로 완벽하지만" 현장에서 안 쓰이는 산출물은 없는가?

**의미**: 맥락(팀, 사용자, 조직 문화)을 우선하는 재검토

---

## VIII. 사적 언어 논증 (Private Language Argument) — 가독성과 공유성

### 비트겐슈타인의 주장
**Philosophical Investigations 243-315**:
- 오직 자신만이 이해할 수 있는 언어는 불가능하다
- 의미의 기준은 **공동체의 동의**에서 비롯되므로, 개인 단독으로는 정확성/틀림을 판단할 수 없다

### 실무 적용: 코드 가독성과 문서 명확성
**질문**:
- 이 코드는 저자 외에는 읽을 수 없을 정도로 암호화되어 있는가?
- 변수명, 함수명, 용어가 팀 외 사람도 이해할 수 있는가?
- 기술 결정의 "왜"가 기록되어 있는가?

**의미**: 공유 불가능한 산출물은 실질적으로 무의미하다

---

## 실무 검증 체크리스트

각 산출물(코드/문서/콘텐츠)에 대해:

1. **그림이론**: 표현이 현실과 구조적으로 일치하는가?
2. **말할 수 있는 것**: 필수 정보는 명확하되, 모든 것을 억지로 명시하지 않는가?
3. **논리적 형식**: 모든 경우의 수가 빠짐없이 다루어지는가?
4. **언어게임**: 용어의 의미가 사용 맥락 내에서 일관적인가?
5. **가족유사성**: 불필요하게 강압적인 분류를 강요하고 있지 않은가?
6. **규칙 따르기**: 가이드/컨벤션이 실제 관행과 일치하는가?
7. **삶의 형식**: 팀/사용자/조직의 실제 맥락을 반영하는가?
8. **사적 언어**: 팀 외 누구나 읽고 이해할 수 있는가?

---

## 참고 자료
- [Tractatus Logico-Philosophicus - Britannica](https://www.britannica.com/topic/Tractatus-Logico-Philosophicus)
- [Ludwig Wittgenstein - Stanford Encyclopedia of Philosophy](https://plato.stanford.edu/entries/wittgenstein/)
- [Language game (philosophy) - Wikipedia](https://en.wikipedia.org/wiki/Language_game_(philosophy))
- [Private language argument - Stanford Encyclopedia of Philosophy](https://plato.stanford.edu/entries/private-language/)
