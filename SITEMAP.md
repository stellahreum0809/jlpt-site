# 사이트 구조 설계

## 왜 목적별인가

학습자가 검색해서 들어오는 의도는 네 가지뿐이다.

1. 내 레벨을 모르겠다 → **진단**
2. 레벨은 알았는데 뭘 외워야 하지 → **학습**
3. 개념은 알겠는데 손에 안 익는다 → **연습**
4. 시험을 언제 어떻게 치지 → **시험 정보**

레벨(N5~N1)은 대분류가 아니라 **학습 안의 중분류**로 들어간다. 레벨을 모르는 사람이 주 타깃인데 입구에서 레벨을 고르게 하면 그 사람이 막힌다.

---

## 전체 지도

### 대분류 1 — 진단
| 페이지 | 파일 | 상태 |
|---|---|---|
| 레벨 진단 테스트 | `level-test.html` | 완료 |
| 한자 레벨 테스트 | `kanji-test.html` | 예정 |
| 어느 급수를 봐야 할까 | `guide/which-level.html` | 예정 |

### 대분류 2 — 학습

**중분류 A. 레벨별** (검색 유입 주력)

| 레벨 | 단어 | 문법 | 한자 |
|---|---|---|---|
| N5 | `guide/n5-words.html` | `guide/n5-grammar.html` | `guide/n5-kanji.html` |
| N4 | `guide/n4-words.html` | `guide/n4-grammar.html` | `guide/n4-kanji.html` |
| N3 | `guide/n3-words.html` | `guide/n3-grammar.html` | `guide/n3-kanji.html` |
| N2 | `guide/n2-words.html` | `guide/n2-grammar.html` | `guide/n2-kanji.html` |
| N1 | `guide/n1-words.html` | `guide/n1-grammar.html` | `guide/n1-kanji.html` |

단어 페이지는 한 장에 몰지 말고 품사별로 쪼갠다.
예: `guide/n3-words-verb.html`, `guide/n3-words-adj.html`
검색어가 "N3 동사"처럼 세분화돼 있고, 한 장에 500개를 넣으면 읽히지 않는다.

**중분류 B. 주제별** (레벨을 가로지르는 개념)

| 주제 | 파일 |
|---|---|
| 히라가나·가타카나 | `guide/kana.html` |
| 조사 총정리 | `guide/particles.html` |
| 동사 활용 총정리 | `guide/verb-conjugation.html` |
| 형용사 활용 | `guide/adjectives.html` |
| 수수동사 (あげる·くれる·もらう) | `guide/giving-receiving.html` |
| 경어 (존경어·겸양어) | `guide/keigo.html` |
| 조수사 세는 법 | `guide/counters.html` |
| 자동사·타동사 짝 | `guide/transitivity.html` |

### 대분류 3 — 연습
| 도구 | 파일 | 상태 |
|---|---|---|
| 동사 변형 사전 | `verb-dict.html` | 예정 |
| 동사 변형 퀴즈 | `verb-quiz.html` | 예정 |
| 오늘의 문법 | `daily-grammar.html` | 예정 |

### 대분류 4 — 시험 정보
| 페이지 | 파일 |
|---|---|
| 시험 일정과 접수 기간 | `guide/schedule.html` |
| 접수 방법과 준비물 | `guide/apply.html` |
| 합격 기준과 점수 계산 | `guide/score.html` |
| 시험 당일 안내 | `guide/exam-day.html` |

### 기본 페이지 (애드센스 필수)
| 페이지 | 파일 | 상태 |
|---|---|---|
| 소개 | `about.html` | 완료 |
| 문의 | `contact.html` | 완료 |
| 개인정보처리방침 | `privacy.html` | 완료 |

**총 페이지 수: 약 40개** — 애드센스 심사 기준(15~20개)을 충분히 넘긴다.

---

## 메뉴 배치

상단에 4개만 둔다. 대분류가 그대로 메뉴가 된다.

```
[로고]   진단   학습   연습   시험정보
```

- 메뉴를 4개로 제한한 이유: 5개가 넘으면 모바일에서 줄바꿈이 생기고, 선택 부담이 커진다.
- 레벨(N5~N1)은 메뉴에 넣지 않는다. 넣으면 항목이 9개가 되고, 레벨을 모르는 사람이 막힌다.
- 메인 페이지에서 각 대분류를 섹션으로 한 번씩 더 펼쳐 보여준다. 메뉴는 재방문자용, 메인 섹션은 첫 방문자용이다.

---

## 파일 이름 규칙

| 종류 | 위치 | 예시 |
|---|---|---|
| 도구 페이지 | 루트 | `verb-dict.html` |
| 도구 데이터 | 루트 | `verb-dict-data.json` |
| 글 | `guide/` | `guide/n5-words.html` |
| 기본 페이지 | 루트 | `about.html` |
| 공통 스타일 | 루트 | `style.css` |

---

## 만드는 순서

콘텐츠를 한 번에 다 쓰면 전부 얇아진다. 이 순서로 간다.

1. **뼈대** — 메인, 소개, 문의, 개인정보처리방침, 공통 스타일 ← 오늘
2. **N5·N4 학습 자료** — 방문자가 가장 많이 몰리는 구간
3. **시험 정보 4종** — 검색량이 꾸준하고 쓰기 쉽다
4. **애드센스 신청** — 여기서 이미 20페이지가 넘는다
5. **N3 이상, 주제별 글, 나머지 도구** — 반응을 보면서

전부 만들고 공개하는 것보다, N5·N4만 채워서 먼저 공개하는 편이 낫다.
실제 방문자 데이터를 보고 나머지를 만들면 헛수고가 줄어든다.
