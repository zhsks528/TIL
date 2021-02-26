## 스택 (Stack)

### 1. 개념

한 쪽 끝에서만 자료를 넣고 뺼 수 있는 `LIFO `형식의 자료구조입니다.

![img](https://media.vlpt.us/images/sbinha/post/17a3cf61-fb95-4970-b66c-92a71b99846b/Screenshot%202020-04-20%2019.07.55.png)

출처 : [sbinha.log](https://velog.io/@sbinha/%EC%8A%A4%ED%83%9D-%ED%81%90)

### 2. 코드

- push(item) : 스택의 가장 윗 부분에 item을 추가합니다.
- pop() : 스택에서 가장 위에 있는 항목을 제거합니다.
- top() : 스택의 가장 위에 있는 항목을 반환합니다.
- isEmpty() : 스택이 비어있을 때에 true를 반환합니다.

```js
class Stack{
    // Initialize
    constructor(){
        this.arr = [];
    }

    // push
    push(item){
        this.arr.push(item);
    }

    // pop
    pop(){
        if (this.arr.length === 0){
            return "스택이 비어있습니다.";
        }
        else{
            return this.arr.pop();
        }
    }

    // top
    top(){
        if (this.arr.length === 0){
            return "스택이 비어있습니다."
        }else{
            return this.arr[this.arr.length - 1];
        }
    }
	
    // isEmpty
    isEmpty(){
        if (this.arr.length === 0){
            return "스택이 비어있습니다."
        }
        else{
            return "스택안에 원소가 있습니다."
        }
    }
    
}

const stack = new Stack();
```

### 3. 사용하는 경우

- 함수의 콜스택
- 재귀 알고리즘
- 문자열 역순 출력
- 연산자 후위표기법
- 웹 브라우저 방문기록(뒤로가기)
- 실행 취소
- 수식의 괄호 검사

### 4. 시간복잡도

삭제나 삽입시 맨 위에 데이터를 삽입하거나 삭제하기 때문에 시간복잡도는 늘 **O(1)**의 시간복잡도를 가집니다. 하지만 특정 데이터를 찾을 때는 특정 데이터를 찾을 때까지 수행을 해야하므로 **O(n)**의 시간복잡도를 가집니다.

- Insertion : O(1)
- Deletion : O(1)
- Search : O(n)

### 5. 참조

- [큐, 스택, 트리](https://helloworldjavascript.net/pages/282-data-structures.html)
- [[자료구조] 스택(stack)이란](https://gmlwjd9405.github.io/2018/08/03/data-structure-stack.html)

- [자료구조 기본 개념](https://velog.io/@dnjscksdn98/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0%EB%A5%BC-%EC%99%9C-%EB%B0%B0%EC%9B%8C%EC%95%BC%ED%95%98%EB%8A%94%EA%B0%80)