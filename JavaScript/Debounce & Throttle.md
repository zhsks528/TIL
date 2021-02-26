## Debounce & Throttle

### 1. 등장배경

스크롤 막대를 드래깅함으로써 매번 스크롤 이벤트에 대한 콜백(callback)이 발생하고 그 콜백이 수행하는 일이 매우 큰 리소스를 잡아먹게 됩니다.

다시말해, 과도한 이벤트 횟수의 실행으로 이벤트 핸들러가 무거운 계산 및 기타 DOM 조작과 같은 작업을 수없이 많이 수행하는 경우 성능 문제가 발생하고 이는 사용자 경험까지 떨어뜨리게 될 것입니다.

이러한 문제를 해결하기위해 `Throttle`, `Debounce`가 등장했습니다.

### 2. 사용사례

1. 사용자가 창 크기 조정을 멈출 때까지 기다렸다가 resizing event 사용하기 위해
2. 사용자가 키보드 입력을 중지(예: 검색창) 할 때까지 ajax 이벤트를 발생시키지 않기 위해
3. 페이지의 스크롤 위치를 측정하고 최대 50ms 마다 응답하기를 바랄 경우에
4. 앱에서 요소를 드래그 할 때 좋은 성능을 보장하기 위해

### 3. Debounce

`Debounce`는 이벤트를 그룹화하여 특정시간이 지난 후 하나의 이벤트만 발생하도록 하는 기술입니다.

즉, 순차적 호출을 하나의 그룹으로 "그룹화"할 수 있습니다.

- 연이어 호출되는 함수들 중 마지막 함수(또는 제일 처음)만 호출하도록 하는 것

```javascript
function debounce(callback, milliseconds) {
  let timeout;

  return function (...args) {
    clearTimeout(timeout);
    timeout = setTimeout(() => {
      callback.apply(this, args);
    }, milliseconds);
  };
}
```

#### 4. Throttle

`Throttle`은 이벤트를 일정한 주기마다 발생하도록 하는 기술입니다.

- 마지막 함수가 호출된 후 일정 시간이 지나기 전에 다시 호출되지 않도록 하는 것

```js
function throttle(callback, milliseconds = 100) {
  let wating = null;
  
  return function(...args) {
    if (wating === null) {
      wating = setTimeout(() => {
        callback.apply(this, args);
        wating = null;
      }, milliseconds); 
    }
  };
}
```

### 5. 참조

- [쓰로틀링과 디바운싱](https://www.zerocho.com/category/JavaScript/post/59a8e9cb15ac0000182794fa)
- [디바운스와 스로틀 그리고 차이점](https://webclub.tistory.com/607)

