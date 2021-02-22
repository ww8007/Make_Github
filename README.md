# Make_Github

### viewport

initial-scale 최초 화면 비율
user-scalable=no 사용자가 화면을 확대 축소를 막아놓음
기본 확대 축소 비율이 1로 고정이 되어있기 때문에 이는 신경쓰지 않아도 된다.

### og

이 사이트에서 사용하는 제목 대표 이미지등을 알려줌

### link

```html
<link rel="icon" href="favicon.png" /> <link rel="apple-touch-icon" href="" />
```

### font

```html
<link rel="preconnect" href="https://fonts.gstatic.com" />
<link
  href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&display=swap"
  rel="stylesheet"
/>
<link rel="stylesheet" href="css/main.css" />
```

### reset.css

초기화를 먼저 해주고 다른 것을 해주는 것이 중요함

- link 태그를 이용한 바로 링크로 받아오기도 가능

```html
<link
  rel="stylesheet"
  href="https://cdnjs.cloudflare.com/ajax/libs/meyer-reset/2.0/reset.min.css"
  integrity="sha512-NmLkDIU1C/C88wi324HBc+S2kLhi08PN5GDeUVVVC/BVt/9Izdsc9SVeVfA1UZbY3sHUlDSyRXhCzHfr6hmPPw=="
  crossorigin="anonymous"
/>
```

### 컨테이너 생성

body 태그를 직접적으로 모두 건드는 것 보다 react에서 사용 하듯이 컨테이너 생성해서 스타일 적용하는 것이 좋음

- BEM 작명 규칙
  block element css 작명 규칙

  - \_

  - (\_\_) 무엇의 일부분

버튼의 상태를 나타낼 때는 -- 하이픈 두 번 사용
\_\_ 두번 사용하는 것도 똑같은 느낌

toggle-btn -> 하나로 이루어 진다면 일반적인 작명 규칙느낌

### 반복적인 부분은 input 버튼 하나로 동일하게 적용

- 버튼 그라데이션
  linear-gradient(to bottom, red, blue);

### align-items

flex: 모든 내용을 다 차지 하게
수평 가운데 정렬

### inline-flex

요소를 block 처럼 전체를 사용하는 것이 아닌 요소의 내용 만큼만 사용하도록 함

### box-sizing: border box

padding 이나 margin이 들어 갔을 시 박스 사이즈가 커지는 것을 막아줌

### btn:hover

가상 선택자로 앞에 만들어줌
before를 사용하면 부모요소에 position 값이 있어야 하는데 없다면 relative를 사용한다.

position absoulte를 사용하더라도 top과 left는 0로 설정해줘야한다.

### input

Vendoer Prefix (브라우저 업체별 접두사)
.input--text::input-placeholder {color: red;}

### header section

하나의 섹션 안에서 content들을 두어서 container wrapper inner
하나의 inner 안에서 묶어서 내용들을 사용

왼쪽 메뉴 오른쪽 메뉴들 구분

로고와 메뉴들로 구성

ul 태그들을 사용해서 li로 사용

### 화면 가운데에 정렬

화면 가운데에 정렬 하려면 margin 값을 0 auto로 설정 할 시 위 아래는 0 auto로 하면
알아서 가운데 정렬이 된다.

- 주의 사항 : 특정 요소의 사이즈 값이 정해져 있어야 한다.

display: flex로 설정 되어있다면 align-items: center를 사용 가능 하고
이를 할 때는 부모 요소의 높이 값을 같이 따라가도록 height: 100%로 설정하여야 한다.

### 버튼의 크기를 늘리기

li 태그들의 크기가 너무 작기 때문에 a
margin으로 확보하는 것이 아닌 padding으로 확보해야 한다.

- 여기서 클릭 되는것은 li가 아닌 a 태그 이므로 a태그에 삽입 되도록 해야한다.

* a 태그는 inline 요소 이므로 display: block으로 설정
  범위를 가질 수 없으므로

* img 태그에서는 alt가 필수 요소로 대체 텍스트 속성으로 사용이 된다.
  css에 backgroun로 사용하면 대체 텍스트 속성은 사용 할 수 없다.

* text-indent 속성을 사용해서 대체 택스트 느낌으로 사용할 수 있다.
  -9999px 의 이유는 텍스트를 사라지게 하는 용도로 사용했구나를 명시한다.

### 반응형 웹페이지

크기가 달라지면 오른쪽 영역들은 버튼 하나에 들어가야 한다.

a 태그는 기본적으로 밑줄이 그어진 형식을 가지고 있음
-> 이를 방지하기 위해서 a태그를 컨테이너 부분에서 정의해줌

### form, input

고유한 값이라고 판단하여서 id값을 삽입

### float

float 속성이 들어가면 부모요소가 자식 요소를 올바르게 감싸지 못하게된다.

이를 해결 하기 위해서 clearfix class 를 만들어서 clear:both를 해주게 된다면
이를 해결 할 수 있다.

```css
.clearfix::after {
  content: "";
  clear: both;
  display: block;
}
```

- 매번 flaot left right 속성을 사용하는 것 보다 이를 common적인 요소로 사용하는 것이 더 효율 적

```css
/* FLOAT CLEARFIX  */

.clearfix::after {
  content: "";
  clear: both;
  display: block;
}

.float--left {
  float: left;
}

.float--right {
  float: right;
}
```
