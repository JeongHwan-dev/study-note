# JavaScript 식별자

## 식별자의 정의와 규칙

**식별자**는 코드 내의 변수, 함수, 혹은 속성을 식별하는 문자입니다.

**JavaScript의 식별자**는 대소문자를 구별하며 `유니코드 글자`, `$`, `_`, `숫자(0-9)`로 구성할 수 있지만, 숫자로 시작할 수 없고 공백을 포함할 수 없습니다.

> 숫자로 시작 ✖️  
> 공백 포함 ✖️

**식별자**는 코드의 일부이지만 문자열은 데이터이기 때문에, 식별자와 문자열은 다릅니다.  
JavaScript에서 식별자를 문자열로 변환하는 방법은 없지만, 어떤 경우 문자열을 분석해 식별자로 사용할 수 있습니다.

> 식별자 ➜ 문자열 ✖️  
> 문자열 ➜ 식별자 ◯

```javascript
// age : 식별자
// 10 : 데이터
let age = 10;
```

```javascript
// person, name : 식별자
// 'Park JeongHwan': 데이터

const student = {
  name: 'Park JeongHwan',

  // 아래와 같은 경우는 데이터가 코드화, 식별자화가 될 수 있는 예시입니다. 그렇기에 식별자 규칙을 따르지 않아 숫자로 시작하거나 공백을 포함할 수 있습니다.
  ['studentAge']: 28,
  ['1-Math score']: 90,
  ['2-Eng score']: 100,
};

// 아래와 같은 방법으로 student 객체 속성에 접근할 수 있습니다.
console.log(student.studentAge);
console.log(student['1-Math score']);
console.log(student['2-Eng score']);
```

<br />

## 관습적인 컨벤션

**상수**는 대문자로 이름을 짓는 것을 선호합니다.

**이름이 길게되면** 단어와 단어의 구분 방법을 둡니다.  
대표적인 방법으로 `카멜 케이스(Camel case)`와 `스네이크 케이스(Snake case)`가 있습니다.

> 보통은 `카멜 케이스(Camel case)`를 더 많이 사용합니다.

- **카멜 케이스(Camel case)**

  ```javascript
  function setName(name) {}
  function getName() {}
  ```

- **스네이크 케이스(Snake case)**

  ```javascript
  function set_name(name) {}
  function get_name() {}
  ```

<br />

## 참고 자료

> https://developer.mozilla.org/ko/docs/Glossary/Identifier

> https://fastcampus.co.kr/dev_academy_kmt1

> 새 창 열기 방법 : CTRL+click (on Windows and Linux) | CMD+click (on MacOS)
