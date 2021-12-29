# 소수 구하기

## 소수란?

**소수**는 1 또는 자기 자신만을 약수로 가지는 수를 의미합니다.

<br />

## 소수를 구하는 가장 효율적인 방법은?

### 가장 직관적인 방법

2부터 (N - 1)까지 루프를 돌며 나눠보기

```javascript
function isPrimeNumber(num) {
  for (let i = 2; i < num; i++) {
    if (num % i = 0) {
      return false;
    }
  }

  return true;
}
```

> 시간 복잡도 O(n) 소요

### 효율성을 개선한 방법

그 어떤 소수도 N의 제곱근보다 큰 수로 나눠지지 않는 다는 점을 이용하는 방법

```javascript
function isPrimeNumber(num) {
  for (let i = 2; i * i <= num; i++) {
    if (num % i === 0) {
      return false;
    }
  }

  return true;
}
```

> 시간 복잡도 O(sqrt(n))

### 에라토스테네스의 체를 이용한 방법

고대 그리스 수학자 에라토스테네스가 발견한 소수를 찾는 방법

- N이하의 소수인 수 구하기

```javascript
function getPrimeNumbers(num) {
  const numbers = [false, false, ...Array(num - 1).fill(true)];
  const primeNumbers = [];

  for (let i = 2; i * i <= num; i++) {
    if (numbers[i]) {
      for (let j = i * 2; j <= num; j += i) {
        numbers[j] = false;
      }
    }
  }

  numbers.forEach((value, index) => value && primeNumbers.push(index));

  return primeNumbers;
}
```

- N이하의 소수 개수 구하기

```javascript
function getPrimeNumberCount(num) {
  const numbers = [false, false, ...Array(num - 1).fill(true)];

  for (let i = 2; i * i <= num; i++) {
    if (numbers[i]) {
      for (let j = i * 2; j <= num; j += i) {
        numbers[j] = false;
      }
    }
  }

  const primeNumberCount = numbers.filter(Boolean).length;

  return primeNumberCount;
}
```

> 시간 복잡도 O(n log log n)

<br />

## 참고 자료

> https://programmers.co.kr/learn/courses/13213

> 새 창 열기 방법 : CTRL+click (on Windows and Linux) | CMD+click (on MacOS)
