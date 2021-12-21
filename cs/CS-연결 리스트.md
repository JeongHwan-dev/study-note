# 연결 리스트(Linked List)

## 연결 리스트란?

**연결 리스트**는 각 요소를 포인터로 연결하여 관리하는 선형 자료구조입니다.  
각 요소를 노드라고 부르며 데이터 영역과 포인터 영역으로 구성됩니다.

<br />

## 연결 리스트의 특징

- 메모리가 허용하는한 요소를 제한없이 추가할 수 있습니다.
- 탐색은 O(n)이 소요됩니다.
- 요소를 추가하거나 제거할 때는 O(1)이 소요됩니다.
- 단일 연결 리스트(Singly Linked List), 이중 연결 리스트(Doubly Linked List), 단순 원형 연결 리스트(Circular Linked List)가 존재합니다.

### 단일 연결 리스트(Singly Linked List)

<img src="../images/CS/singly-linked-list.png" alt="단일 연결 리스트(Singly Linked List)" />

> Head에서 Tail까지 단방향으로 이어지는 연결 리스트이며 가장 단순한 형태인 연결 리스트입니다.

```javascript
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

class SinglyLinkedList {
  constructor() {
    this.head = null;
    this.tail = null;
  }

  find(value) {
    let currNode = this.head;

    while (currNode.value !== value) {
      currNode = currNode.next;
    }

    return currNode;
  }

  append(newValue) {
    const newNode = new Node(newValue);

    if (this.head === null) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      this.tail.next = newNode;
      this.tail = newNode;
    }
  }

  insert(node, newValue) {
    const newNode = new Node(newValue);

    newNode.next = node.next;
    node.next = newNode;
  }

  remove(value) {
    let prevNode = this.head;

    while (prevNode.next.value !== value) {
      prevNode = prevNode.next;
    }

    if (prevNode.next !== null) {
      prevNode.next = prevNode.next.next;
    }
  }

  display() {
    let currNode = this.head;
    let displayString = '[';

    while (currNode != null) {
      displayString += `${currNode.value}, `;
      currNode = currNode.next;
    }

    displayString = displayString.substring(0, displayString.length - 2);
    displayString += ']';

    console.log(displayString);
  }
}

const linkedList = new SinglyLinkedList();
```

### 이중 연결 리스트

<img src="../images/CS/doubly-linked-list.png" alt="이중 연결 리스트(Double Linked List)" />

> 양방향으로 이어지는 연결 리스트입니다. 이중 연결 리스트는 포인터 변수가 하나 더 추가되기 때문에 단일 연결 리스트(Singly Linked List)보다 자료구조의 크기가 조금 더 큽니다.

### 단순 원형 연결 리스트

<img src="../images/CS/circular-linked-list.png" alt="단순 원형 연결 리스트(Circular Linked List" />

> 단일(Singly) 혹은 이중(Dobuly) 연결 리스트에서 Tail이 Head로 연결되는 연결 리스트 메모리를 아껴쓸 수 있습니다. 원형 큐 등을 만들 때도 사용합니다.

<br />

## 배열과의 차이점

|           자료구조           | 요소 추가 또는 삭제 |                          요소 찾기                          |
| :--------------------------: | :-----------------: | :---------------------------------------------------------: |
|       **배열(Array)**        |        O(n)         | O(n) <br /> ( 만약 원하는 원소의 index를 알고 있다면 O(1) ) |
| **연결 리스트(Linked List)** |        O(1)         |                            O(n)                             |

<br />

## 참고 자료

> https://ko.wikipedia.org/wiki/%EC%97%B0%EA%B2%B0_%EB%A6%AC%EC%8A%A4%ED%8A%B8

> 새 창 열기 방법 : CTRL+click (on Windows and Linux) | CMD+click (on MacOS)
