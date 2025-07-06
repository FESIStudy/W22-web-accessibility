## 웹 접근성

웹 접근성(Web Accessibility)은 장애 여부, 신체 조건, 기술 환경에 관계없이 누구나 웹사이트나 웹 앱을 이용할 수 있도록 만드는 것을 말합니다.

솔직히 처음듣고 뭔지 잘 몰랐는데 생각해보니 이미지 태그에 alt속성값 넣어주던게 생각이 났음.
그리고 MUI쓰면서 팝오버나 다이얼로그 컴포넌트 쓸 때 aria~ 속성에 값을 줘야했던것도 기억이 남.

```tsx
export default function Dialog(props: DialogProps) {
  return <StyledDialog {...props} aria-labelledby="dialog-title" aria-describedby="dialog-description" />;
}
```

그럼 aria가 무엇인가.

ARIA는 Accessible Rich Internet Applications의 약자로,
웹 접근성을 높이기 위한 추가적인 속성들을 말한다.

즉,
스크린 리더(화면 낭독기) 같은 보조 기술이 요소의 역할이나 상태를 이해할 수 있도록 정보를 추가하는 속성들을 의미함.

저 속성값의 의미는 다음과 같다고 한다

aria-labelledby id="dialog-title"인 요소가 이 다이얼로그의 제목이라는 것을 알려줌
aria-describedby id="dialog-description"인 요소가 이 다이얼로그의 설명이라는 것을 알려줌

중간에 스크린 리더라는게 나오는데 이건 무엇이냐

화면의 텍스트, 버튼, 이미지 같은 정보를 소리로 읽어주는 소프트웨어야.

주로 시각장애인이나 저시력자가 사용하고,
웹사이트나 앱의 내용을 음성으로 들으면서 사용하는 거지.

가끔 웹서핑하다가 버튼 잘못 누르면 나오는 그게 이거였음.

이런 웹접근성의 표준을 정해주는 데가 WCAG라고 한다.

이번주는 쓸만한게없네요 :(
