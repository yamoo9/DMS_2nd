###### DMS(Digital Marketing School), Fast Campus
# Front-End Develop Course

### 테스트

- [디마스 『 프론트엔드 웹 2일차 』 TEST](http://goo.gl/forms/vKj8mTWcbGA9JqJ03)

-

### 웹 서비스 제작자가 고려해야 할 3가지

1. 사용성(`Usability`)
1. 접근성(`Accessibility`)
1. 성능(`Performance`)

-

### 텍스트 에디터 설정

- [에디터, Sublime Text](http://www.sublimetext.com/3)
- [패키지 컨트롤, Sublime Text Package Manager](https://packagecontrol.io/)
- [Emmet, 빠른 코딩을 위한 도구](http://emmet.io/)
- [IMESupport, Windows 환경 한글 입력 문제 해결 플러그인](https://packagecontrol.io/packages/IMESupport)
- [SideBarEnhancements, 사이드바 강화 플러그인](https://packagecontrol.io/packages/SideBarEnhancements)
- [ColorPicker, 컬러 선택 플러그인](https://packagecontrol.io/packages/ColorPicker)

-

### 참고 자료

- [브런치, 글이 작품이 되는 공간](https://brunch.co.kr/)
- [W3C(World Wide Web Consortium): 웹 표준 제정 기관](https://www.w3.org)
- [W3C 미션(Mission)](https://www.w3.org/Consortium/mission)
- [w3schools.com](http://w3schools.com)
- [생활코딩, HTML](http://opentutorials.org/course/2039)
- [생활코딩, CSS](http://opentutorials.org/course/45)

-

### 1일차

#### 1-1. HTML 문서 기본형

```html
<!DOCTYPE html>
<html lang="ko-KR" dir="ltr">
<head>
  <meta http-equiv="X-UA-Compatible" content="IE=Edge">
  <meta charset="UTF-8">
  <title>문서 제목</title>
</head>
<body>

</body>
</html>
```

-

#### 1-2. HTML 문서 단락 / 줄 바꿈

- 단락 (Paragraph, `<p>`)
- 줄바꿈 (Line Break, `<br>`)

```html
<p>
용서에 관한<br>
두 가지 이야기를<br>
하려고 한다.
</p>

<p>돈암동 시장 사거리를 지나던 밤. 장맛비는 차창에 빗금을 그으며 도심에 생채기를 냈으며, 물컹해진 신호등에선 과즙이 흘러내렸다. 아리랑 고개를 잔뜩 구부린 채 오르던 차량은 중턱에서 속도를 줄이곤, 허리를 한껏 폈다. 나도 하늘을 바라보았다. 기압골끼리 충돌한 자리엔 환란이 분분하게 떨어져, 세계는 물러지고 조금씩 삭아갔다. 비 오는 밤 상념이 짙어지는 것은, 세상이 발효된 때문은 아닐까.</p>

<p>그때였다. '쿵-'하는 소리와 함께 몸이 들썩였다. 뒤따르던 차 한 대가 꽁무니를 박은 것이다. 놀랄 것 없이 현장을 찍을 휴대폰만 챙겨 차에서 내렸다. 그리곤 허리에 손을 얹은 채 혀를 깨물어 난감한 표정을 취했다. 앞 유리창에 비친 또래의 남성은 하얀 셔츠를 말끔하게 입고 있었다. 그러나 운전석 문을 반쯤 열어둔 채 번잡스러운 몸짓을 이어갔고, 그것은 빗소리만큼 요란했다. 누군가 고삐 풀린 그의 시선을 봤다면, 분명 사건의 피해자로 여겼을 터이다.</p>
```

-

#### 1-3. HTML 문서 제목

- 대제목 (Heading1, `<h1>`)
- 중제목 (Heading2, `<h2>`)
- 중중제목 (Heading3, `<h3>`)
- 소제목 (Heading4, `<h4>`)
- 소소제목 (Heading5, `<h5>`)
- 소소소제목 (Heading6, `<h6>`)

```html
<h1>언제 어디서든 브런치를 만나보세요.</h1>
<h2>달콤한 오후의 팝콘</h2>
<h3>길게 내려다 본 골목길</h3>
<h4>영화와 우리들의 삶</h4>
<h5>빛과 그림자 교차하는 노래</h5>
<h6>당신을 용서합니다, 놓아줍니다.</h6>
```

-

#### 1-4. 웹 폰트

##### 무료 웹 폰트 글꼴

- [스포카 한 산스](http://spoqa.github.io/spoqa-han-sans/)
- [구글 웹폰트 - 한글](http://deminoth.github.io/google-font-kor/)

```html
<!-- Spoqa Han Sans 웹폰트 호출 -->
<link href="http://spoqa.github.io/spoqa-han-sans/css/SpoqaHanSans-kr.css" rel="stylesheet">

<!-- 문서 스타일링 -->
<style>
  body {
    /**
     * 폰트 이름 사이에 공백이 있을 경우, 폰트 이름을 쌍 따옴표로 감싼다.
     * 왼쪽에서 오른쪽으로 배치된 순서로 우선 적용된다.
     */
    font-family: "Spoqa Han Sans", "Nanum Gothic", Dotum, Gulim, Sans-Serif;
  }
</style>
```

-

#### 1-5. HTML 문서 디비전

- 디비전 (Division, `<div>`)

```html
<!-- 디비전 Division -->
<div>
  <p>일본 취업준비 어떻게 하고 계신가요? 단순히 기업에 대한 정보를 알아보고 자소서, 필기, 면접준비.. 여기서 그치는게 대부분 아닐까요? 그러나, 일본에 있는 학생들은 취업준비에 있어서 가장 중요한게 무엇이냐 물어 봤을때 절반 이상의 학생들은 자기분석(自己分析)라 대답할 거에요. 처음에 저는 오그라들게 무슨 자기분석이냐 라고 생각 했었지만, 실제로 취직 준비하면서 자기분석 없이는 자소서, 면접 등 어느 한군데에서 계속 구멍이 생겨 버리더라고요.</p>
</div>
```

-

#### 1-6. HTML 문서 이미지

- 이미지 (Image, `<img src="" alt="">`)

```html
<img src="http://ncc.phinf.naver.net/20160523_115/1463981683061mAPho_JPEG/4.jpg?type=w646" alt="덕혜옹주 돌사진">
<img src="http://dbscthumb.phinf.naver.net/4076_000_1/20151020150408491_JCO0BBK6U.jpg/ja85_19_i1.jpg?type=w276_fst_n&amp;wm=Y" alt="손목 터널 증후군">
```

-

#### 1-7. CSS 속성

수업 시간에 다룬바 있는 속성들.

- **Font**
  - 글꼴 ━ `font-family`
  - 글자 크기 ━ `font-size`
  - 글자 두께 ━ `font-weight`
  - 행간 ━ `line-height`

- **Color**
  - 글자 색상 ━ `color`

- **Margin**
  - 외부 여백 공간 (↑) ━ `margin-top`
  - 외부 여백 공간 (→) ━ `margin-right`
  - 외부 여백 공간 (↓) ━ `margin-bottom`
  - 외부 여백 공간 (←) ━ `margin-left`