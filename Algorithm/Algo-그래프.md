# 그래프(Graph)

## 그래프란?

**그래프(Graph)** 는 정점과 정점 사이를 연결하는 간선으로 이루어진 비선형 자료구조입니다.  
정점 집합과 간선 집학으로 표현할 수 있습니다.

<img src="../images/Algorithm/graph.png" alt="그래프(Graph)" />

<br />

## 그래프의 특징

- 정점은 여러 개의 간선을 가질 수 있습니다.
- 크게 방향 그래프와 무방향 그래프로 나눌 수 있습니다.
- 간선은 가중치를 가질 수 있습니다.
- 사이클이 발생할 수 있습니다.

<br />

## 무방향 그래프

**무방향 그래프**는 간선에 방향성이 존재하지 않는 그래프입니다. 간선으로 이어진 정점끼리는 양방향으로 이동이 가능합니다.

> ex) 양방향 통행 도로

<br />

## 방향 그래프

**방향 그래프**는 간선에 방향성이 존재하는 그래프입니다.

> ex) 일방 통행

<br />

## 연결 그래프

**연결 그래프**는 모든 정점이 서로 이동이 가능한 상태인 그래프입니다.

<br />

## 비연결 그래프

**비연결 그래프**는 특정 정점쌍 사이에 간선이 존재하지 않는 그래프입니다.

<br />

## 완전 그래프

**완전 그래프**는 모든 정점끼리 연결된 상태인 그래프입니다.

<br />

## 사이클

**사이클**은 그래프의 정점과 간선의 부분 집합에서 순환이 되는 부분입니다.

<br />

## JavaScript에서 사용법

### 인접 행렬

```javascript
const graph = Array.from(Array(5), () => Array(5).fill(false));

graph[0][1] = true;
graph[0][3] = true;
graph[1][2] = true;
graph[2][0] = true;
graph[2][4] = true;
graph[3][2] = true;
graph[4][0] = true;
```

### 인접 리스트

```javascript
const graph = Array.from(Array(5), () => []);

graph[0].push(1);
graph[0].push(3);
graph[1].push(2);
graph[2].push(0);
graph[2].push(4);
graph[3].push(2);
graph[4].push(0);
```

<br />

## 참고 자료

> https://ko.wikipedia.org/wiki/%EA%B7%B8%EB%9E%98%ED%94%84_(%EC%9E%90%EB%A3%8C_%EA%B5%AC%EC%A1%B0)

> https://programmers.co.kr/learn/courses/13213

> 새 창 열기 방법 : CTRL+click (on Windows and Linux) | CMD+click (on MacOS)
