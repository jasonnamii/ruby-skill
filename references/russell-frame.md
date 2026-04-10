# Russell's Philosophical Framework for Code/Content Decomposition

**러비스킬**: 코딩·문서·콘텐츠 분해→평가→아름다운 상위 설계로 올려주는 도구의 철학적 근거

---

## 1. 논리적 원자론 (Logical Atomism)

### 핵심 원리
복합 명제(complex proposition)는 모두 **원자 명제(atomic propositions)**로 환원 가능하다. 원자적 사실(atomic fact)은 "개별자 a가 성질 F를 가진다" 또는 "개별자 a, b가 관계 R을 맺는다"는 형태의 기본 단위.

### 코드/문서/콘텐츠 적용
```
복합한 함수     → 원자적 책임 단위로 분해
복합한 문장     → 주어·술어·목적어·의존절로 분해
복합한 설계     → 기본 데이터 흐름(atomic transaction)으로 분해
```

### 실무 체크리스트
- [ ] 이 함수/문단/기능은 하나의 원자적 역할만 하는가?
- [ ] 분해하면 더 이상 나눌 수 없는 단위에 도달했는가?
- [ ] 각 원자 단위가 독립적으로 이해·테스트·재사용 가능한가?
- [ ] 복잡성이 원자 단위들의 **조합**에서만 나오는가, 아니면 원자 단위 자체에서 나오는가?

---

## 2. 유형론 (Theory of Types)

### 핵심 원리
자기참조(self-reference)는 금지된다. 집합은 원소들의 유형과 다른 유형이어야 한다.
- 유형 0: 개별자(individuals)
- 유형 1: 개별자들의 집합
- 유형 2: 유형 1의 집합
- ...

### 코드/문서/콘텐츠 적용
```
코드층위 혼동           → 데이터·함수·클래스·모듈 간 경계 불명확
문서층위 혼동           → 용어 정의·사용·메타설명 구분 부재
설계층위 혼동           → 비즈니스 로직·UI·인프라 엮임
자기참조 버그           → 순환 의존성, 클로저의 closure capture 문제
```

### 실무 체크리스트
- [ ] 이 코드에서 "데이터", "함수", "설정"이 명확히 구분되는가?
- [ ] 문서의 각 절이 **같은 추상 수준**에 있는가?
- [ ] 순환 참조(A→B→A)가 없는가?
- [ ] 변수/함수가 자신을 참조하고 있지는 않은가?
- [ ] 메타 수준(규칙 자체)과 기본 수준(규칙 적용)이 혼동되지 않았는가?

---

## 3. 기술이론 (Theory of Descriptions)

### 핵심 원리
"The present King of France is bald" → ∃x(Kx ∧ ∀y(Ky→y=x) ∧ Bald(x))

표면상 단순한 주어-술어 구조는 실제로 **세 가지 논리적 주장**을 숨기고 있다:
1. **존재**: 대상이 존재하는가?
2. **유일성**: 그것이 유일한가?
3. **속성**: 그것이 그 속성을 가지는가?

### 코드/문서/콘텐츠 적용
```
함수명 "getUserData"        → 실제로는:
                             1. user가 존재하는가?
                             2. userData가 데이터베이스에 있는가?
                             3. 권한이 있는가?

문서 "고객 정의"             → 실제로는:
                             1. 고객이 존재하는가?
                             2. 하나인가 여럿인가?
                             3. 어떤 조건인가?

설계 "캐시 전략"            → 실제로는:
                             1. 캐시 대상이 명확한가?
                             2. 캐시 유효성 판정이 유일한가?
                             3. 오래됨 판정 방식이 명확한가?
```

### 실무 체크리스트
- [ ] 이 함수/개념의 "존재 조건"이 문서화되어 있는가?
- [ ] 유일성(uniqueness)이 보장되는가? (예: 한 번에 하나의 active instance?)
- [ ] 모호한 대명사(this, it, that)를 모두 명사로 교체할 수 있는가?
- [ ] 부정 표현("is not", "doesn't have") 뒤의 논리 구조를 재분석했는가?
- [ ] 함수명/변수명이 "존재를 가정"하고 있지는 않은가?

---

## 4. Principia Mathematica의 공리적 접근

### 핵심 원리
- **최소 공리**: 필요한 최소한의 기초 명제(axiom)만 설정
- **명시적 추론 규칙**: 모든 추론 단계를 논리적 규칙으로 명시
- **계층 구조**: 공리 → 정리(theorem) → 보조정리(lemma)의 엄격한 위계

### 코드/문서/콘텐츠 적용
```
소프트웨어 설계에서:
- 공리       = 피할 수 없는 기본 가정 (예: DB 시간은 단조증가)
- 추론 규칙  = 설계 원칙 (예: "모든 상태 변화는 audit log를 남긴다")
- 정리       = 파생 속성 (예: "시간순으로 정렬하면 순서는 유일하다")
```

### 실무 체크리스트
- [ ] 이 시스템의 **기초 가정(axioms)**을 리스트할 수 있는가?
- [ ] 각 규칙이 공리로부터 논리적으로 도출 가능한가?
- [ ] "항상 그렇다"는 명제는 최소화되어 있는가?
- [ ] 추론 단계가 암묵적이지 않은가? (예: "당연히 user는 authenticated")
- [ ] 공리를 위반하는 코드/문서가 남아있지는 않은가?

---

## 5. Russell's Razor: 논리적 구성으로 대체하라

### 핵심 원리
> "Whenever possible, substitute constructions out of known entities for inferences to unknown entities"

"깔끔한 속성"을 가진 새로운 개념을 가정하기보다, **기존 원소들의 논리적 조합**으로 그것을 정의하라.

```
나쁜 설계:                   좋은 설계:
- user.isAdmin (추론)       - user ∈ admins (구성)
- data.isCached (추론)      - data ∈ cacheLayer (구성)
- status.isPending (추론)   - status ∈ {pending, approved, rejected} (구성)
```

### 코드/문서/콘텐츠 적용
| 추론된 개념(나쁨) | 논리적 구성(좋음) | 이점 |
|---|---|---|
| `is_valid` 플래그 | `value in valid_range & schema_matches` | 재계산 불필요, 검증 로직 명시적 |
| `boolean enabled` | `role in allowed_roles & subscription_active` | 변경 시점 명확, 디버깅 쉬움 |
| `computed property` | `derived_from(base_data)` | 소스 추적 가능, 캐시 전략 결정 가능 |

### 실무 체크리스트
- [ ] boolean 플래그를 모두 찾아, 그 정의를 논리식으로 바꿀 수 있는가?
- [ ] "derived" 또는 "computed"로 표시된 것들이 실제로 어떤 기본 요소에서 도출되는가?
- [ ] 새로운 클래스/함수/개념을 추가하려 할 때, 기존 요소의 조합으로 표현할 수는 없는가?
- [ ] 상태 관리 라이브러리에서 "derived state"가 명시적으로 정의되어 있는가?
- [ ] 문서에서 "이런 경우", "특수한 경우" 같은 예외 설명이 패턴화되어 있는가?

---

## 실전: Decomposition Checklist

### Phase 1: 원자적 단위 찾기
1. 가장 복잡한 함수/문단/기능을 선택
2. Russell's atomism: "이것을 더 나눌 수 있는가?" 반복
3. 각 원자 단위의 책임을 한 문장으로 표현

### Phase 2: 층위 구분 (Types)
1. 각 원자 단위가 어떤 "유형"인가? (data/logic/config/test)
2. 유형 간 경계가 명확한가?
3. 자기참조 또는 순환 의존성이 있는가?

### Phase 3: 숨겨진 복잡성 드러내기 (Descriptions)
1. 모호한 표현을 모두 찾기 ("it", "this", "status", "valid")
2. 각각을 세 부분으로 분해: **존재 조건**, **유일성**, **속성**
3. 함수명/변수명을 다시 쓰기

### Phase 4: 공리 명시하기 (Principia)
1. "이것이 작동하려면 다음이 참이어야 한다"는 모든 가정 리스트
2. 각 공리가 코드/문서에 반영되어 있는가 확인
3. 공리 위반 케이스 처리

### Phase 5: 불필요한 추상화 제거 (Russell's Razor)
1. boolean 플래그 → 조합 논리식으로 변환
2. 새로운 타입 → 기존 요소 조합으로 재정의 가능?
3. 특수 경우 → 공통 패턴으로 일반화 가능?

---

## 참고 자료
- [Russell's Logical Atomism (Stanford Encyclopedia of Philosophy)](https://plato.stanford.edu/entries/logical-atomism/)
- [Russell's Paradox & Theory of Types (Stanford Encyclopedia)](https://plato.stanford.edu/entries/russell-paradox/)
- [Theory of Descriptions (Stanford Encyclopedia)](https://plato.stanford.edu/entries/descriptions/)
- [Logical Constructions (Stanford Encyclopedia)](https://plato.stanford.edu/entries/logical-construction/)