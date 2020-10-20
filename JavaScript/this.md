## this

this의 값은 함수가 호출되는 방식에 따라 달라진다.

### 1. this의 규칙

1. 함수를 호출할 때 `new` 키워드를 사용하는 경우, 함수 내부에 있는 `this`는 완전히 새로운 객체다.

```javascript
function ConstructorExample() {
    console.log(this);
    this.value = 10;
    console.log(this);
}

new ConstructorExample();
// -> {}
// -> { value: 10 }
```

2. `apply`, `call`, `bind`가 함수의 호출/생성에 사용되는 경우, 함수 내의 `this`는 인수로 전달된 객체다.

```javascript
function fn(){
    console.log(this);
}

var obj = {
    value : 5
}

var boundFn = fn.bind(obj);

boundFn();    // -> {value: 5}
fn.call(obj)  // -> {value: 5}
fn.apply(obj) // -> {value: 5}
```

3. `obj.method()`와 같이 함수를 메서드로 호출하는 경우, `this`는 함수가 프로퍼티인 객체다.

```javascript
var obj = {
	value: 5,
    printThis: function(){
        console.log(this);
    }
};

obj.printThis(); // -> {value: 5, printThis: ƒ}
```

4. 함수가 자유함수로 호출되는 경우, 즉, 위의 조건 없이 호출되는 경우 `this`는 전역 객체다. 
   브라우저에서는 `window` 객체다.
   엄격 모드(`'use strict'`) 일 경우, `this`는 전역 객체 대신 `undefined`가 된다.

```javascript
function fn() {
    console.log(this);
}

// If called in browser:

fn(); // -> Window {stop: ƒ, open: ƒ, alert: ƒ, ...}
```

```javascript
console.log(fn === window.fn); // -> true
```

5. 위의 규칙 중 다수가 적용되면 **더 상위 규칙이 승리하고 `this`값을 설정**한다.

6. 함수가 ES2015 화살표 함수인 경우 위의 모든 규칙을 무시하고 생성된 시점에서 주변 스코프의 `this`값을 받는다.

```javascript
const obj = {
    value: 'abc',
    createArrowFn: function() {
        return () => console.log(this);
    }
};

const arrowFn = obj.createArrowFn();

arrowFn(); // -> { value: 'abc', createArrowFn: ƒ }
```

### 2. 참조

- [The Simple Rules to 'this' in Javascript](https://codeburst.io/the-simple-rules-to-this-in-javascript-35d97f31bde3)
- [javascript-questions-this](https://github.com/yangshun/front-end-interview-handbook/blob/master/contents/kr/javascript-questions.md)