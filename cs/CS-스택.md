# 스택(Stack)

## 스택이란?

스택(Stack)은 LIFO(Last In First Out)이라는 개념을 가진 선형 자료구조입니다.

<img src="../images/CS/stack.png" alt="스택(Stack)" width="300px" />

<br />

## Javascript에서 사용하기

### 배열(Array)로 구현

```javascript
const stack = [];

// Push
stack.push(1);
stack.push(2);
stack.push(3);

console.log(stack); // [1, 2, 3]

// Pop
stack.pop();

console.log(stack); // [1, 2]
```

### 연결 리스트(Linked List)로 구현

```javascript
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

class Stack {
  constructor() {
    this.top = null;
    this.size = 0;
  }

  push(value) {
    const node = new Node(value);

    node.next = this.top;
    this.top = node;
    this.size += 1;
  }

  pop() {
    const value = this.top.value;

    this.top = this.top.next;
    this.size -= 1;

    return value;
  }

  size() {
    return this.size;
  }
}

const stack = new Stack();
```

<br />

## 참고 자료

> https://ko.wikipedia.org/wiki/%EC%8A%A4%ED%83%9D

> 새 창 열기 방법 : CTRL+click (on Windows and Linux) | CMD+click (on MacOS)
