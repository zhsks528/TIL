## ES6 (ECMAScript 2015)

### 1. let

`let` 키워드를 사용하여 변수를 선언한다.

블록스코프를 지원하고 호이스팅을 방지한다.

```js
var x = 10;
// Here x is 10
{  
  let x = 2;
  // Here x is 2
}
// Here x is 10
```



### 2. const

`const` 키워드를 사용하여 변수를 선언한다.

블록스코프를 지원하고 호이스팅을 방지한다.

`let`과 비슷하게 작동하지만, 재할당이 불가능하다.

```js
var x = 10;
// Here x is 10
{  
  const x = 2;
  // Here x is 2
}
// Here x is 10
```

```js
var x = 10;
// Here x is 10
{  
  const x = 2;
  x = 10;  // Assignment to constant variable
}
```



### 3. 기본 매개 변수 (Default Parameters)

function의 **parameters에 기본값을 설정**한다.

```js
function myFunction(x, y = 10) {
  // y is 10 if not passed or undefined
  return x + y;
}

console.log(myFunction(5)); // 15
console.log(myFunction(5, 20)); // 25
```



### 4. 템플릿 리터럴 (Template Literals)

"`" (back-ticked) 문자열 안에 **${NAME}**라는 새로운 구문을 사용해서 아래와 같이 간단히 처리할 수 있다.

```js
// ES5
var name = 'Your name is ' + first + ' ' + last + '.'
var url = 'http://localhost:3000/api/messages/' + id

// ES6
var name = `Your name is ${first} ${last}.`
var url = `http://localhost:3000/api/messages/${id}`
```



### 5. 화살표 함수 (Arrow Functions)

함수 표현시 짧은 문법을 제공한다.

화살표 함수는 항상 익명 함수이며 `this`의 값을 현재 문맥에 바인딩 시킨다.

`function` , `return` 키워드가 필요하지 않는다.

```js
// ES5
var x = function(x, y) {
   return x * y;
}

// ES6
const x = (x, y) => x * y;
```



### 6. 클래스 (Classes)

`class` keyword를 이용하여 class를 생성한다.

`constructor()`가 항상 필요하다.

**javascript의 class는 object가 아니고 javascript objects의 template 라는 것을 인지해야한다.**

```js
// ES5
var Car = function(name, year){
    this.name = name;
    this.year = year;
};

Car.prototype.print = function(){
    return "이름 : " + this.name + " 출시년도 : " + this.year
}

var car_name = new Car("Ford", 2014)

console.log(car_name.print()) // 이름 : Ford 출시년도 : 2014
```

```js
// ES6
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
    
  print(){
      return "이름 : " + this.name + " 출시년도 : " + this.year
  }
}

myCar = new Car("Ford", 2014);

console.log(myCar.print()); // 이름 : Ford 출시년도 : 2014
```

### 7. Promise

```js
let myPromise = new Promise(function(myResolve, myReject) {
// "Producing Code" (May take some time)

  myResolve(); // 성공할 시 실행
  myReject();  // 실패할 시 실행
});

// "Consuming Code" (Must wait for a fulfilled Promise).
myPromise.then(
  function(value) { /* code if successful */ },
  function(error) { /* code if some error */ }
);
```



### 8. rest 매개인자 (Function Rest Parameter)

arguments보다 직관성을 제공한다.

```js
// ... : rest parameter

function sum(...args) {
  let sum = 0;
  for (let arg of args) sum += arg;
  return sum;
}

let x = sum(4, 9, 16, 25, 29, 100, 66, 77);
```



### 9. Array.find()

Array를 순환하면서 **조건을 만족하는 첫번째 element를 반환**한다.

```js
var numbers = [4, 9, 16, 25, 29];
var first = numbers.find(myFunction);

// value : 배열 안의 element
// index : 배열의 index
// array : 배열
function myFunction(value, index, array) {
  return value > 18;
}

console.log(first) // 25
```



### 10. Array.findIndex()

Array를 순환하면서 **조건을 만족하는 첫번째 element의 index를 반환**한다.

```js
var numbers = [4, 9, 16, 25, 29];
var first = numbers.find(myFunction);

// value : 배열 안의 element
// index : 배열의 index
// array : 배열
function myFunction(value, index, array) {
  return value > 18;
}

console.log(first) // 3
```



### 11. 모듈

```js
// ES5 , Node.js

// 불러오기 format
const fs1 = require('./fs1');
const fs2= require('./fs2');
const createFile = () => {
 ...
}

// 내보내기 format
module.exports = { createFile }

// ES6
    
// lib.js
// 내보내기 format
export function hello(){
...
}

// 불러오기 format
import { hello } from './lib';
hello();
```



### 12. 비동기화 할당

추가예정



### 참조

- [Javascript ES6 정리](https://k39335.tistory.com/83?category=699283)
- [W3Schools JS ES5](https://www.w3schools.com/js/js_es6.asp)
- [개발자가 필히 알아야할 ES6 10가지 기능](https://blog.asamaru.net/2017/08/14/top-10-es6-features/)