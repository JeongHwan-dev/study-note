# 해시 테이블 (Hash Table)

## 해시 테이블이란?

**해시 테이블(Hash Table)** 이란 키와 값을 받아 키를 해싱(Hashing)하여 나온 index에 값을 저장하는 선형 자료구조입니다.  
삽입은 O(1)이며 키를 알고 있다면 삭제, 탐색도 O(1)로 수행합니다.

<img src="../images/CS/hash-table.png" alt="해시 테이블(Hash Table)" width="350px" />

<br />

## 해시 함수란?

**해시 함수**는 입력받은 값을 특정 범위 내 숫자로 변경하는 함수입니다.

<br />

## 해시 충돌(Hash Collision)을 해결할 수 있는 방법

### 선형 탐사법

충돌이 발생하면 옆으로 한 칸 이동하는 방법입니다.

### 제곱 탐사법

충돌이 발생하면 충돌이 발생한 횟수의 제곱만큼 옆으로 이동하는 방법입니다.

### 이중 해싱

충돌이 발생하면 다른 해시 함수를 이용하는 방법입니다.

### 분리 연결법

버킷의 값을 연결 리스트로 사용하여 충돌이 발생하면 리스트에 값을 추가하는 방법입니다.

<br />

## 해시 테이블은 언제 사용하는 것이 좋은가?

빠르게 값을 찾아야 하는 경우 해시 테이블을 사용하는 것이 좋습니다.

<br />

## JavaScript에서 사용하기

### 배열(Array)로 구현

```javascript
const hashTable = [];

hashTable['key1'] = 100;
hashTable['key2'] = 'David';

console.log(hashTable['key1']); // 100

delete hashTable['key2'];

console.log(hashTable['key2']); // undefined
```

### 객체(Object)로 구현

```javascript
const hashTable = {};

hashTable['key1'] = 100;
hashTable['key2'] = 'David';

console.log(hashTable['key1']); // 100

delete hashTable['key2'];

console.log(hashTable['key2']); // undefined
```

### Map 객체로 구현

```javascript
const hashTable = new Map();

hashTable.set('key1', 100);
hashTable.set('key2', 'David');

console.log(hashTable.get('key1')); // 100

const object = { name: 'John' };

hashTable.set(object, 'A1'); // Map은 Object도 Key로 쓸 수 있습니다.

hashTable.delete(object);

console.log(hashTable.keys()); // { 'key1', 'key2' }

console.log(hashTable.values()); // { 100, 'David' }

hashTable.clear();

console.log(hashTable.values()); // {}
```

### Set 객체로 구현

```javascript
const hashTable = new Set();

hashTable.add('key1'); // Key와 Value가 동일하게 들어갑니다.
hashTable.add('key2');

console.log(hashTable.has('key1')); // true
console.log(hashTable.has('key3')); // false

hashTable.delete('key2');

console.log(hashTable.size); // 1

table.clear();

console.log(hashTable.size); // 0
```

<br />

## 참고 자료

> https://programmers.co.kr/learn/courses/13213

> https://velog.io/@chjh121/Hash-Table

> 새 창 열기 방법 : CTRL+click (on Windows and Linux) | CMD+click (on MacOS)
