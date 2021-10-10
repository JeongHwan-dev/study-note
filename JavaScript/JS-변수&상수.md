# JavaScript 변수&상수

## 선언 명령어

### `let`

`let` 선언은 블록 유효 범위의 지역 변수를 선언합니다.

> 선언과 동시에 임의의 값으로 초기화 할 수 있고 이후 값 변경도 가능합니다.

<br />

### `const`

`const` 선언은 블록 유효 범위의 상수를 선언합니다.

> 상수의 값은 재할당할 수 없으며 다시 선언할 수도 없습니다.

<br />

## 변수와 상수의 차이점

**변수**는 한번 만들어 놓은 이후에 그 변수가 가지고 있는 값을 다른 값으로 변경할 수 있습니다.

```JAVASCRIPT
let num = 10;

num = 20;
num = 30;
```

**상수**는 최초에 만들어질 때 단 한 번만 값을 넣을 수 있고 그 이후에는 값을 바꾸지 못합니다.

```JAVASCRIPT
const num = 10;

// ReferenceError 발생 (애플리케이션 종료)
num = 20;
```

하지만 object 타입의 'square'는 상수이지만 'square'의 속성 값인 'width'와 'height'의 값들은 변경이 가능합니다. 즉, 상수라고 하는 것의 영향 범위는 바로 바깥쪽 object 입니다. 그래서 이 object 자체를 다른 값으로 바꿀 수 없는 것이지 object 안의 내용물에 대해서는 변경이 가능합니다.

```JAVASCRIPT
const square = {
  width: 600,
  height: 300
}

// 정상 작동
square.width = 500;
square.hight = 1000;

// Error 발생
square = 200;
```

<br />

### 변수 선언과 상수 선언 중 어느 것을 더 많이 사용하는 것이 좋은 가?

상수 선언을 더 많이 사용하는 것이 더 좋습니다. 왜냐하면 변수라고 하는 것은 값이 변한다는 뜻인데 값 자체가 변화된다는 거 자체가 괸장히 많은 불안정성을 내포하고 있습니다. 그래서 변하지 않는 값을 갖는 구조로 프로그래밍을 하는 습관들, 혹은 그런 테크닉들을 연마하는 게 굉장히 좋습니다.

습관적으로 값이 전혀 변하지 않는 데도 `let`으로 선언하여 변수로 만들어서 다루는 것은 굉장히 나쁜 습관입니다.

코드 자체에서 한 번도 값이 세팅되고 나서 변하지 않는다면 항상 상수 `const`로 선언하고 값이 변한다고 할 때만 `let`으로 변수를 만들어서 사용해야 합니다.

<br />

## 참고 자료

> https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/let

> https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/const

> https://fastcampus.co.kr/dev_academy_kmt1

> 새 창 열기 방법 : CTRL+click (on Windows and Linux) | CMD+click (on MacOS)
