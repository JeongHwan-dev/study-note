# 이진 탐색(Binary Search)

## 이진 탐색이란?

**이진 탐색(Binary Search)** 정렬 되어있는 요소들을 반씩 제외하며 찾는 알고리즘입니다.

> O(log n) 만큼 시간 복잡도가 걸립니다.

<img src="../images/Algorithm/binary-search.gif" alt="이진 탐색(Binary Search)" />

<br />

## 이진 탐색의 특징

- 반드시 정렬이 되어있어야 사용할 수 있습니다.
- 배열 혹인 이진 트리를 이용하여 구현할 수 있습니다.
- O(log n) 시간복잡도인 만큼 상당히 빠릅니다.
- 이진 탐색은 배열과 트리를 이용해 구현할 수 있습니다.

<br />

## 이진 탐색 트리의 문제점

- 최악의 경우 한쪽으로 편향된 트리가 될 수 있습니다.
- 그런 경우 순차 탐색과 동일한 시간복잡도를 가집니다.
- 이를 해결하기 위해 다음과 같은 자료구조를 이용할 수 있습니다.
  - AVL 트리
  - 레드-블랙 트리

<br />

## JavaScript에서 사용법

### 배열(Array)로 구현

```javascript
function binarySearch(array, findValue) {
  let left = 0;
  let right = array.length - 1;
  let mid = Math.floor((left + right) / 2);

  while (left <= right) {
    if (array[mid] === findValue) {
      return mid;
    }

    array[mid] < findValue ? (left = mid + 1) : (right = mid - 1);
    mid = Math.floor((left + right) / 2);
  }

  return -1;
}

const array = [1, 2, 5, 124, 400, 599, 1004, 2876, 8725];

console.log(binarySearch(array, 2876)); // 7
console.log(binarySearch(array, 1)); // 0
console.log(binarySearch(array, 500)); // -1
console.log(binarySearch(array, 2)); // 1
console.log(binarySearch(array, 1004)); // 6
```

### 트리(Tree)로 구현

```javascript
class Node {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

class BinarySearchTree {
  constructor() {
    this.root = null;
  }

  insert(value) {
    const newNode = new Node(value);

    if (this.root === null) {
      this.root = newNode;
      return;
    }

    let currentNode = this.root;

    while (currentNode !== null) {
      if (currentNode.value < value) {
        if (currentNode.right === null) {
          currentNode.right = newNode;
          break;
        }

        currentNode = currentNode.right;
      } else {
        if (currentNode.left === null) {
          currentNode.left = newNode;
          break;
        }

        currentNode = currentNode.left;
      }
    }
  }

  has(value) {
    let currentNode = this.root;

    while (currentNode !== null) {
      if (currentNode.value === value) {
        return true;
      }

      if (currentNode.value < value) {
        currentNode = currentNode.right;
      } else {
        currentNode = currentNode.left;
      }
    }

    return false;
  }
}

const tree = new BinarySearchTree();

tree.insert(5);
tree.insert(4);
tree.insert(7);
tree.insert(8);
tree.insert(5);
tree.insert(6);
tree.insert(2);

console.log(tree.has(8)); // true
console.log(tree.has(1)); // false
```

<br />

## 참고 자료

> https://programmers.co.kr/learn/courses/13213

> https://blog.penjee.com/binary-vs-linear-search-animated-gifs/

> 새 창 열기 방법 : CTRL+click (on Windows and Linux) | CMD+click (on MacOS)
