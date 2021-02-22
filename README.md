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
