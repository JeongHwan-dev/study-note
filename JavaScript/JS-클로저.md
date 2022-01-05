# 클로저(Closure)

## 클로저란?

**클로저(Closure)** 는 함수가 선언된 환경의 스코프를 기억하여 함수가 스코프 밖에서 실행될 때에도 기억한 스코프에 접근할 수 있게 만드는 문법입니다.

```javascript
function makeGreeting(name) {
  const greeting = 'Hello, ';

  return function () {
    console.log(greeting + name);
  };
}

const world = makeGreeting('World!');
const jeonghwan = makeGreeting('Jeong-hwan');

world();
jeonghwan();
```

<br />

## 은닉화

클로저를 유용하게 사용할 수 있는 방법 중 하나는 **은닉화**입니다.  
클로저를 이용하여 내부 변수와 함수를 숨길 수 있습니다.

```javascript
function Counter() {
  let privateCounter = 0;

  function changeBy(value) {
    privateCounter += value;
  }

  return {
    increment: function () {
      changeBy(1);
    },
    decrement: function () {
      changeBy(-1);
    },
    getValue: function () {
      return privateCounter;
    },
  };
}

const counter = Counter();

console.log(counter.getValue()); // 0

counter.increment();
counter.increment();

console.log(counter.getValue()); // 2

counter.decrement();

console.log(counter.getValue()); // 1
```

<br />

## 클로저를 잘 알아야 하는 이유?

유용하게 사용하기보단 알기 힘든 버그를 잘 수정하기 위해서입니다.

```javascript
function counting() {
  let i = 0;

  for (i = 0; i < 5; i += 1) {
    setTimeout(() => {
      console.log(i);
    }, i * 100);
  }
}

counting(); // 5 5 5 5 5
```

> 만약 0 1 2 3 4 와 같이 출력을 원한다면 아래와 같은 해결법이 있습니다.

- 루프에 let과 const같은 블록 수준 스코프 사용

```javascript
function counting() {
  // let은 블록 수준 스코프기 때문에 매 루프마다 클로저가 생성됩니다.
  for (let i = 0; i < 5; i += 1) {
    setTimeout(() => {
      console.log(i);
    }, i * 100);
  }
}

counting(); // 0 1 2 3 4
```

- 즉시실행함수(Immediately-invoked function expression) 사용

```javascript
function counting() {
  let i = 0;

  for (i = 0; i < 5; i += 1) {
    (function (number) {
      setTimeout(() => {
        console.log(number);
      }, i * 100);
    })(i);
  }
}

counting(); // 5 5 5 5 5
```

<br />

## 참고 자료

> https://programmers.co.kr/learn/courses/13213

> 새 창 열기 방법 : CTRL+click (on Windows and Linux) | CMD+click (on MacOS)
