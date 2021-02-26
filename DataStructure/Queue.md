## 큐 (Queue)

### 1. 개념

먼저 집어 넣은 데이터가 먼저 나오는 `FIFO` 형식의 자료구조입니다.

![img](https://media.vlpt.us/images/sbinha/post/dbc199b3-6959-464e-872d-39c503fa0b1b/Screenshot%202020-04-20%2019.19.59.png)

출처 : [sbinha.log](https://velog.io/@sbinha/%EC%8A%A4%ED%83%9D-%ED%81%90)

### 2. 코드

- Enqueue: 큐에 데이터를 넣는 기능입니다.
- Dequeue: 큐에서 데이터를 꺼내는 기능입니다.

```js
class Queue {
    // Initialize
    constructor() {
      this.arr = [];
    }
     
    // enqueue
    enqueue(item) {
      this.arr.push(item);
    }

    // dequeue
    dequeue() {
      return this.arr.shift();
    }
  }
  
const queue = new Queue();
```

### 3. 사용하는 경우

- 너비 우선 탐색(BFS, Breadth-First Search) 구현
- 캐시 (Cache) 구현
- 우선순위가 같은 작업 예약 (인쇄 대기열)
- 선입선출이 필요한 대기열 (티켓 카운터)
- 콜센터 고객 대기시간
- 프린터의 출력 처리
- 윈도우 시스템의 메시지 처리기
- 프로세스 관리

### 4. 시간복잡도

- Insertion : O(1)
- Deletion: O(1)
- Search : O(n)

### 5. 참조

- [큐, 스택, 트리](https://helloworldjavascript.net/pages/282-data-structures.html)
- [[자료구조] 스택(stack)이란](https://gmlwjd9405.github.io/2018/08/03/data-structure-stack.html)

- [자료구조 기본 개념](https://velog.io/@dnjscksdn98/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0%EB%A5%BC-%EC%99%9C-%EB%B0%B0%EC%9B%8C%EC%95%BC%ED%95%98%EB%8A%94%EA%B0%80)