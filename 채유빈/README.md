## 1. 웹 접근성의 철학과 기본 개념

### 웹 접근성이란?

웹 접근성은 **어떠한 사용자(장애인, 노인 등), 어떠한 기술환경에서도 웹 사이트가 제공하는 모든 정보에 전문적 능력 없이 접근할 수 있도록 보장하는 것**을 말한다.

- **정의:** 정보에 대한 물리적·기술적 장벽 제거
- **목적:** 모두에게 동등한 정보 접근 기회 제공
- **대상:** 시각·청각·지체·인지 등 모든 유형의 장애인뿐 아니라 일시적·상황적 제약 환경 사용자

<br/>

### 비장애인 개발자가 접근성을 공부해야 하는 이유

- 약 10억 명의 잠재 사용자 확보
- 법적·규제적 의무 준수: ADA, EN 301 549, 장애인차별금지법 등
- 검색 최적화 및 SEO 향상
- 유지보수 비용 절감 및 브랜드 평판 강화

<br/>

### 접근성과 유니버설 디자인, 사용성(Usability)의 관계

- **유니버설 디자인:** 모든 사용자가 나이·성별·능력 불문하고 쾌적히 이용할 수 있는 환경 설계
- 접근성 vs 포용성 vs 사용성
    - **접근성(A11y)**: 장애 유무와 관계없이 웹 콘텐츠에 접근 가능
    - **포용성(Inclusivity)**: 다양한 사용 사례 포괄
    - **사용성(Usability)**: 특정 사용자·환경 목표 달성의 편의성
- 접근성 준수만으로 충분치 않으며, 사용성 향상을 목표로 설계해야 진정한 접근성 보장이라고 할 수 있다.

<br/>

### 주요 용어 및 기관 개요

- **WCAG (Web Content Accessibility Guidelines):** W3C/WAI 주관, 콘텐츠 접근성 국제 표준
- **POUR 원칙:** 인식 가능(Perceivable), 운용 가능(Operable), 이해 가능(Understandable), 견고성(Robust)
- **WAI-ARIA:** 동적 콘텐츠 및 커스텀 컴포넌트 접근성 향상을 위한 역할(role), 속성(state) 프레임워크
- **ATAG, UAAG:** 저작도구 및 사용자 에이전트 접근성 표준

<br/>

## 2. WCAG 핵심 원칙과 기준

### POUR 원칙

1. **Perceivable(인지):** 모든 사용자는 서비스 콘텐츠를 인식할 수 있어야 한다.
    - 대체 텍스트·자막·명도 대비 제공
2. **Operable(운용):** 모든 사용자는 서비스의 기능을 운용할 수 있어야 한다.
    - 키보드 내비게이션·충분한 시간·비발작성 보장
3. **Understandable(이해)**: 모든 사용자가 서비스의 콘텐츠, 기능 사용법 등을 이해하기 쉬워야 한다.
    - 언어 표기·일관된 인터페이스·입력 오류 수정 지원
4. **Robust(견고):** 사용자가 이용하는 모든 기기 및 브라우저에서 접근, 사용할 수 있어야 한다.
    - 시맨틱 HTML 및 ARIA로 보조 기술과 호환

<br/>

### WCAG 규정 준수 수준

- **Level A:** 최소 준수 (본질적으로 웹사이트에 액세스할 수 없게 만드는 요소를 금지)
- **Level AA:** 허용 가능한 보편적인 규정 준수 (전 세계 대부분의 접근성 규칙 및 규정에서 사용됨)
- **Level AAA:** 최적의 규정 준수 (거의 모든 사용자가 사이트에 접속하여 모든 기능을 경험하는 데 무리가 없음)

<br/>

### KWCAG (한국형 웹 콘텐츠 접근성 지침)

- WCAG를 국내 웹 환경을 고려하여 제작한 우리나라만의 접근성 준수 지침
- 주요 차이점
    1. 문화적 및 법적 조정
        - 예) 한국어의 특성상 텍스트 가독성에 관한 추가적인 지침이 포함될 수 있음
        - 한국의 장애인차별금지법 및 웹 접근성 관련 법규와의 일치를 보장
    2. 세부 지침 및 예시
        - 한국 사용자를 위한 구체적인 예시와 지침 제공
    3. 용어와 표현
        - 한국어로 작성되어 있어 한국어 사용자가 더 쉽게 접근할 수 있음

## 3. 웹 접근성 보장을 위한 주요 항목 분석

### ARIA 속성

- ARIA(Accessible Rich Internet Applications) 속성은 기**본 HTML 태그만으로는 표현이 부족한 상호작용 요소나 동적 콘텐츠를 보완**하는 역할을 한다.
- 그러나 많은 속성이 HTML5로 통합되었으므로, 개발자는 되도록 시맨틱 HTML을 ARIA보다 먼저 적용해야 한다.
    - 예) 네이티브 요소는 키보드 접근성, 역할, 상태를 내장하고 있음
- 필수로 알아야 하는 속성
    - `aria-label`: 시각적으로 보이지 않지만 스크린 리더에게 요소의 이름을 제공
        
        ```html
        <button aria-label="장바구니에 추가">🛒</button>
        ```
        
        - 텍스트가 없거나 아이콘만 있는 버튼 등에 사용
        - 직접 텍스트 제공 → 간단한 경우에 적합
    - `aria-labelledby`: 스크린 리더가 요소의 레이블을 다른 요소의 텍스트로부터 가져오도록 연결
        
        ```html
        <h2 id="dialog-title">로그인 안내</h2>
        <div role="dialog" aria-labelledby="dialog-title">
          <p>로그인이 필요합니다.</p>
        </div>
        ```
        
        - 여러 요소를 묶여서 레이블로 지정 가능
        - `aria-label`보다 유지보수성이 높음
    - `aria-describedby`: 설명(보조 정보)이 있는 요소에 설명을 연결
        
        ```html
        <input type="text" aria-describedby="desc1" />
        <span id="desc1">비밀번호는 최소 8자 이상이어야 합니다.</span>
        ```
        
        - 스크린 리더가 읽어주는 부가 설명
        - 오류 메시지, 유효성 설명 등에 활용
    - `aria-hidden`: 접근성 트리에서 요소와 자식 요소 전체를 제외
        
        ```html
        <div aria-hidden="true">이 영역은 스크린 리더에서 무시됩니다</div>
        ```
        
        - 숨기려는 요소는 꼭 시각적으로 숨기기만 해서는 부족하므로 사용
        - 반대로 숨겼지만 읽히게 하고 싶을 땐 `aria-hiden="false"` 사용
    - `aria-expanded`: 요소가 열려 있는지(true) 닫혀 있는지(false)를 나타냄
        
        ```html
        <button aria-expanded="false" aria-controls="menu">메뉴</button>
        <ul id="menu" hidden>...</ul>
        ```
        
        - 아코디언, 드롭다운 메뉴, 모달 등에서 상태 표현
        - JS로 `aria-expanded` 값을 동적으로 변경해야 함
    - `aria-controls`: 어떤 요소가 어떤 다른 요소를 제어하는지 연결
        
        ```html
        <button aria-controls="menu">메뉴 열기</button>
        <div id="menu">메뉴 내용</div>
        ```
        
        - `aria-expanded`와 자주 함께 쓰임
        - 스크린 리더가 컨트롤 대상을 인식할 수 있게 도와줌
    - `aria-live`: 실시간으로 변화하는 콘텐츠를 스크린 리더에게 읽히도록 지정
        
        ```html
        <div aria-live="polite" id="cart-status">장바구니에 추가됨</div>
        ```
        
        - `polite`: 현재 읽는 내용을 다 읽은 후 읽음
        - `assertive`: 즉시 읽음(주의 필요)
        - 요청 결과, 알림, 상태 메시지 등에 활용
    - `role="alert"`: 자동으로 긴급 메시지를 스크린 리더가 즉시 읽음
        
        ```html
        <div role="alert">비밀번호가 일치하지 않습니다.</div>
        ```
        
        - 별도로 `aria-live="assertive"`를 지정하지 않아도 즉시 읽힘
    - `role="dialog"` + `aria-modal="true"`: 모달창 구조 정의
        
        ```html
        <div role="dialog" aria-modal="true" aria-labelledby="dialog-title">
          <h2 id="dialog-title">확인 필요</h2>
          <p>이 작업을 진행하시겠습니까?</p>
        </div>
        ```
        
        - 시맨틱 구조를 부여하고, 스크린 리더의 포커스를 제한하는 데 사용
        - 배경 요소에는 `aria-hidden="true"`도 적용해야 함
    - `aria-invalid`: 입력 필드가 유효하지 않음을 명시
        
        ```html
        <input type="email" aria-invalid="true" aria-describedby="error-msg" />
        <span id="error-msg">유효하지 않은 이메일입니다.</span>
        ```
        
        - 유효성 검사 실패 시 동적으로 속성을 추가해줘야 함
    - 그외 알아두면 좋은 속성들
        
        
        | 속성 | 설명 |
        | --- | --- |
        | `aria-checked` | 체크 상태 표현 (예: 커스텀 체크박스) |
        | `aria-selected` | 탭, 리스트 등에서 선택 여부 |
        | `aria-disabled` | 비활성 상태 표시 (`disabled` 속성이 없을 때) |
        | `aria-current` | 현재 페이지 또는 위치 표시 (`aria-current="page"`) |
        | `aria-busy` | 로딩 중임을 나타냄 |
        | `aria-role="presentation"` | 시맨틱 제거 (읽지 않도록 처리) |

<br/>

### 대체 텍스트(alt)와 시맨틱 마크업

- 의미 있는 이미지는 `alt`로 설명, 장식 이미지에는 `alt=""`
    - 스크린 리더는 `alt=""`인 이미지를 접근성 트리에서 건너뛴다.
    - 만약 `alt` 속성이 없다면 오히려 이미지 경로나 파일명이 읽힐 수 있다.
    
    ```html
    <!-- 의미 있는 이미지 -->
    <img src="profile.jpg" alt="홍길동의 프로필 사진" />
    
    <!-- 장식용 이미지 -->
    <img src="decorative-line.png" alt="" />
    ```
    
- `<header>`, `<main>`, `<nav>` 등 HTML5 시맨틱 태그 사용
    
    ```html
    <header>
      <nav>
        <ul>
          <li><a href="/home">홈</a></li>
          <li><a href="/about">소개</a></li>
        </ul>
      </nav>
    </header>
    
    <main id="main-content">
      <h1>접근성 안내</h1>
      <p>모든 사용자가 이용할 수 있는 웹을 만들어요.</p>
    </main>
    ```
    
<br/>

### 이미지, SVG, 아이콘 폰트 처리

- SVG: `role="img"` + `aria-label` 또는 `title` 활용
- 아이콘 폰트: 텍스트 대체 수단 반드시 제공

```html
<!-- 접근 가능한 SVG 아이콘 -->
<svg role="img" aria-label="다운로드 아이콘" xmlns="http://www.w3.org/2000/svg" width="24" height="24">
  <title>다운로드</title>
  <path d="..." />
</svg>

<!-- 아이콘 폰트 (예: Font Awesome) + 텍스트 숨김 -->
<i class="fa fa-envelope" aria-hidden="true"></i>
<span class="sr-only">이메일 보내기</span>

<!-- 시각적으로 숨긴 텍스트 스타일 예시 -->
<style>
  .sr-only {
    position: absolute;
    width: 1px; height: 1px;
    padding: 0; margin: -1px;
    overflow: hidden;
    clip: rect(0,0,0,0);
    border: 0;
  }
</style>

```

<br/>

### aria-hidden vs role="presentation" 차이

- 두 속성은 모두 스크린 리더에게 무언가를 읽지 않게 하려는 목적으로 사용되지만, 역할과 적용 범위가 다르다.
- `aria-hidden="true"`: 접근성 트리에서 요소 및 자식 제거
    - 대표 용도: 모달 뒤 배경 숨기기, 중복 정보 숨기기
    
    ```html
    <div aria-hidden="true">
      <img src="decorative.png" alt="장식 이미지" />
    </div>
    ```
    
- `role="presentation"`: 요소를 트리에는 남기되 시맨틱 제거 (레이아웃만 유지)
    - 대표 용도: 시각적 표지만 의미 없는 `<tabe>`, `<img>` 등
    
    ```html
    <table role="presentation">
      <tr><td>데이터</td></tr>
    </table>
    ```
    
<br/>

### 키보드 내비게이션

- `tabindex="0"` 으로 포커스 가능, `-1`로 제외
- 모달 내 **포커스 트랩(Focus Trap)** 구현
- `aria-modal="true"` + `role="dialog"` 활용

```html
<!-- 키보드 포커스가 가능한 버튼 -->
<button tabindex="0">제출</button>

<!-- 포커스 제외 (비활성화) -->
<button tabindex="-1" disabled>비활성화됨</button>

<!-- 포커스트랩: 모달 내에서만 Tab 이동 가능 -->
<div role="dialog" aria-modal="true">
  <button id="first">첫 번째</button>
  <input type="text" />
  <button id="last">마지막</button>
</div>

<!-- JS로 Focus Trap 구현 (단순 예시) -->
<script>
  const first = document.getElementById('first');
  const last = document.getElementById('last');

  document.addEventListener('keydown', (e) => {
    if (e.key === 'Tab') {
      if (document.activeElement === last && !e.shiftKey) {
        e.preventDefault();
        first.focus();
      } else if (document.activeElement === first && e.shiftKey) {
        e.preventDefault();
        last.focus();
      }
    }
  });
</script>

```

<br/>

### Skip Navigation 구현

- skip navigation: 화면 맨 위에 반복적으로 나타나는 내비게이션 링크, 메뉴, 광고 등을 건너뛰고 바로 본문으로 이동할 수 있게 해주는 숨겨진 링크
- 화면을 키보드 또는 스크린 리더로 탐색하는 사용자는 웹 페이지에 들어갈 때마다 매번 헤더, 내비게이션, 로그인 버튼 등 반복적인 요소들을 모두 거쳐야 본문에 도달할 수 있다. 이런 반복을 줄이기 위해 사용자가 "본문으로 건너뛰기" 링크를 먼저 눌러서 바로 이동할 수 있도록 하는 것이다.

```html
<!-- 스킵 링크 -->
<a href="#main-content" class="skip-link">본문 바로가기</a>

<!-- 본문 시작 지점 -->
<main id="main-content">
  <h1>뉴스 기사</h1>
  <p>오늘의 주요 뉴스는...</p>
</main>
```

- 시각적으로 숨기고 키보드 포커스 시 노출

<br/>

### Modal/Dialog 접근성

- `role="dialog"` + `aria-labelledby` 적용
- 오픈 시 배경 내용 `aria-hidden="true"` 설정
- 닫을 땐 포커스 복원

```html
<!-- 모달 구조 -->
<div role="dialog" aria-modal="true" aria-labelledby="modal-title">
  <h2 id="modal-title">로그인 필요</h2>
  <p>서비스를 이용하려면 로그인이 필요합니다.</p>
  <button>로그인</button>
  <button>닫기</button>
</div>

<!-- 모달 외 영역을 aria-hidden -->
<main aria-hidden="true">...</main>
```

<br/>

### 폼 접근성

- `<label for>` 연결 또는 `aria-labelledby`
- 오류 필드에 `aria-invalid="true"` + `aria-describedby`(오류 메시지)

```html
<!-- label 연결 -->
<label for="email">이메일</label>
<input type="email" id="email" name="email" />

<!-- 오류 메시지 -->
<input type="email" aria-invalid="true" aria-describedby="email-error" />
<span id="email-error">이메일 형식이 올바르지 않습니다.</span>
```

<br/>

### 색상 대비 및 시각 요소

- 명도 대비 4.5:1(AA), 7:1(AAA)
- 색맹 대응: 패턴·텍스트·모양으로 구분
- 대비 검사 도구: Lighthouse, Contrast Checker

<br/>

## 4. 동적 UI 구성요소의 접근성

### SPA(React/Vue) 접근성 고려사항

SPA에서는 화면 전환이 DOM 재조합을 통해 이뤄지기 때문에, 전통적인 웹의 `<title>`, `<h1>` 업데이트, 페이지 화면 전환 감지가 **스크린 리더에게 자동으로 전달되지 않는다.**

1. `document.title` 업데이트
    - `react-helmet`, `vue-meta`, `document.title = '...'` 등 사용
2. 커스텀 컴포넌트의 역할 제공
    - `<div>`로만 구성된 컴포넌트에는 `role`, `aria-` 속성을 적절히 부여해야 의미 전달 가능
3. 라우팅 시 상태 알림 (`aria-live`)
    - 라우터 전환 후, 현재 위치나 제목을 스크린 리더에 읽히게 하려면 `aria-live` 영역 사용

<br/>

### 토스트, 팝업, 드롭다운, 툴팁, 스크롤 영역

1. 토스트 알림: 화면에 자동으로 뜨는 알림 → `role="alert"` 또는 `status`로 스크린 리더에게 즉시 읽힘
2. 툴팁: `aria-describedby`로 툴팁 내용 연결 + `role="tooltip"`
    
    ```html
    <button aria-describedby="tooltip1">도움말</button>
    <span role="tooltip" id="tooltip1">이 버튼은 저장 기능입니다.</span>
    ```
    
3. 드롭다운
    - 버튼이 리스트를 여는 구조라면
        
        ```html
        <button aria-haspopup="listbox"
          aria-expanded="true"
          aria-controls="dropdown1"
        >
          옵션 선택
        </button>
        <ul id="dropdown1" role="listbox">
          <li role="option">옵션 1</li>
        </ul>
        ```
        
4. 가상 스크롤 영역
    - 스크롤 가능한 영역은 `role="region"` 또는 `aria-labelledby` 사용
        
        ```html
        <div role="region" aria-labelledby="scroll-title" tabindex="0">
          <h2 id="scroll-title">공지사항</h2>
          <div style="max-height: 300px; overflow: auto;">...</div>
        </div>
        ```

<br/>        

### 애니메이션, 로딩 상태 처리

1. 로딩 상태
    - `aria-busy="true"`: 콘텐츠가 아직 로딩 중임을 의미
    - `aria-live`: 상태가 바뀔 때 스크린 리더에게 전달
    
    ```html
    <div aria-busy="true" aria-live="polite">로딩 중입니다...</div>
    ```
    
2. 모션 제한 설정 (`prefers-reduced-motion`)
    - 시각 민감 사용자 배려
    
    ```css
    @media (prefers-reduced-motion: reduce) {
      * {
        animation: none !important;
        transition: none !important;
      }
    }
    ```
    
<br/>

## 5. 자동화 도구와 테스트 전략

### 자동 검사 도구

| 도구 | 특징 |
| --- | --- |
| **Axe DevTools** | 가장 인기 있는 브라우저 확장 도구. 오류 위치 + 수정 제안 |
| **Lighthouse** | Chrome DevTools 내장. 접근성 점수 제공 |
| **WAVE** | 시각적 오버레이 기반 검사. 누락된 label 등 탐지 |
| **tota11y** | 마우스오버 방식의 시각적 접근성 디버깅 툴 |

> 자동 도구는 전체 이슈 중 약 20~30%만 검출되므로, **반드시 수동 테스트와 병행**해야 한다.
> 

<br/>

### 수동 테스트 기준

| 항목 | 확인 방법 |
| --- | --- |
| **키보드 전용 탐색** | Tab / Shift+Tab / Enter / Space만으로 모든 기능 가능해야 |
| **포커스 순서** | 논리적이고 예측 가능해야 함 |
| **포커스 표시** | outline 등으로 현재 위치 시각화 |
| **화면 리더 사용 테스트** | NVDA/VoiceOver 등으로 실제 읽힘 확인 |

<br/>

### 주요 스크린 리더 종류 및 특징

| 이름 | 플랫폼 | 특징 |
| --- | --- | --- |
| **NVDA** | Windows | 무료/가볍고 정확함. 실무에서 자주 사용 |
| **VoiceOver** | macOS, iOS | 시스템 내장. Safari와 호환성 높음 |
| **TalkBack** | Android | 안드로이드 기본. 모바일 테스트에 필수 |

<br/>

## 6. 최신 동향과 정책 이슈

### 공공·국방·금융권 법적 기준

| 구분 | 내용 |
| --- | --- |
| **장애인차별금지법** (국내) | 공공기관, 민간기관(교육, 의료 등) 및 일정 규모 이상의 민간 서비스에 대해 **웹 접근성 준수 의무 부여** |
| **전자정부법** | 정부 및 지자체 사이트는 **웹 접근성 인증마크 획득 의무화** |
| **금융기관** | 대국민 서비스 웹/앱은 **시각·지체장애 사용자**를 고려해 설계해야 함. 주요 은행 및 보험사는 WCAG 준수 권장. |
| **미국 Section 508** | 연방정부 및 수탁기관은 **접근 가능한 정보 시스템 제공 필수**. WCAG 2.0 AA 이상 요구. |
| **EU 접근성 법(AAD)** | 2025년부터 **민간 기업에도 접근성 준수 법적 의무화 예정** (모바일 앱 포함) |

> 실무에서는 특히 공공/금융 프로젝트에서 **접근성 테스트 항목 및 문서화 요구**가 많다.
> 

<br/>

### 접근성 인증마크 획득 프로세스

1. **사전 자가진단**
    - 내부적으로 Axe, Lighthouse 등 도구 활용
    - K-WCAG 기준에 따라 24개 항목 체크리스트 작성
2. **웹 접근성 개선 작업**
    - 문제 발생 영역 수동 수정
    - 스크린리더/키보드 테스트 병행
3. **본심사(웹접근성 인증기관 평가)**
    - (사)한국웹접근성인증평가원, 한국지능정보사회진흥원(NIA) 등 기관에서 심사
    - 성공 시 **WA 인증마크** 부여 (1년 유효)

<br/>

### WCAG 3.0 동향

| 항목 | 설명 |
| --- | --- |
| 현재 상태 | WCAG 3.0은 **Working Draft 단계** (2021~현재) |
| 주요 변화 | 기존 이분법 평가(준수/비준수) → **점수 기반의 유연한 평가 모델** 도입 예정 |
| 새 기준 | 시각뿐 아니라 **인지적 장애, 감각 민감도**, **사용성 경험 중심** 접근 확대 |
| 명칭 변화 | "Guideline → Outcome", "Success Criterion → Method" 등 구조 변경 중 |

<br/>

### AI 기반 접근성 보조 도구 사례

| 도구 | 설명 |
| --- | --- |
| **Be My Eyes** | 시각장애인과 자원봉사자를 연결해 **실시간 도움 제공** (AI + 사람 병행) |
| **Microsoft Seeing AI** | OCR, 얼굴 인식, 바코드 인식 등을 통해 **환경을 음성으로 설명** |
| **VoiceOver 자동화 스크립트** | 웹 테스트에서 **스크린 리더 시뮬레이션 자동화** |
| **AI 대체 텍스트 생성** | 이미지 분석 후 자동 `alt` 생성 (주의: 완전 신뢰 X) |
| **axe-core + Jest** | 접근성 단위 테스트 자동화 (CI 파이프라인 통합 가능) |

<br/>

### Lottie 애니메이션 접근성 처리

- Lottie는 JSON 기반 벡터 애니메이션으로 React/Vue 앱에서 자주 사용됨
- 그러나 **canvas 내부이므로 스크린 리더가 인식하지 못함**
- 처리 방법
    1. 장식용일 경우
        
        ```jsx
        <Lottie animationData={data} aria-hidden="true"
        ```
        
    2. 정보 전달 목적일 경우
        
        ```jsx
        <Lottie animationData={data} role="img" aria-label="성공적으로 업로드됨" />
        ```
        
    3. 사용자 설정 고려
        
        ```css
        @media (prefers-reduced-motion: reduce) {
          .lottie-animation {
            display: none;
          }
        }
        ```
        
<br/>

### 🤔 컴포넌트 라이브러리를 사용하는 이유에 접근성도 있지 않나?

핵심 이유 중 하나이다. 개발자가 일일이 모든 접근성 세부사항을 구현하는 건 복잡하고, 실수하기 쉬우며, 일관성 유지도 어렵기 때문이다.

[접근성 기반 UI 라이브러리]

| 라이브러리 | 접근성 수준 | 스타일 분리 | 프레임워크 | 비고 |
| --- | --- | --- | --- | --- |
| **Radix UI** | 🟢 매우 높음 | ✅ 완전 분리 | React | 실무 1위 |
| **Reach UI** | 🟢 높음 | ✅ | React | 유지보수 ↓ |
| **Headless UI** | 🟢 높음 | ✅ | React, Vue | Tailwind 친화 |
| **MUI** | 🟡 중간 | ❌ | React | 빠른 프로토타이핑 |
| **Chakra UI** | 🟢 높음 | ❌ | React | DX 우수 |
| **Spectrum** | 🟢 매우 높음 | ❌ | React | 기업용 |
| **Ark UI** | 🟢 높음 | ✅ | React, Vue | Radix 대안 |

<br/>

### 참고 자료

- [아는 만큼 보이는 웹접근성 WCAG 2.2](https://www.books.weniv.co.kr/accessibility)
- [국내 접근성과 국제 접근성은 어떻게 다를까?](https://aoa.gitbook.io/skymimo/undefined)
- [[웹접근성] WCAG와 KWCAG의 가장 큰 차이](https://webmini.tistory.com/1188)
- [ARIA - mdn](https://developer.mozilla.org/ko/docs/Web/Accessibility/ARIA)
- [W3C Web Accessibility Initiative (WAI)](https://www.w3.org/WAI/)
- [Google Web Fundamentals - Accessibility](https://web.dev/accessibility?hl=ko)