## ES5 (ECMAScript 2009)

### 1. 'use strict'

- 'strict mode' 에서 Javascript code를 실행한다.
- 선언하지 않은 variable, object를 사용 / 수정 / 삭제 할 수 없다.
- 함수 호이스팅이 제한된다.
- script나 function 시작 부분에 'use strict'; 을 선언함으로써 사용한다.
- IE9에서는 지원하지 않는다.

```js
"use strict";
x = 3.14;       // This will cause an error because x is not declared
```

```js
"use strict";
myFunction();

function myFunction() {
  y = 3.14;   // This will also cause an error because y is not declared
}
```

함수 내에   "use strict"; 선언할 경우 error가 발생한다.

```js
x = 3.14;       // This will not cause an error.
myFunction();

function myFunction() {
  "use strict";
  y = 3.14;   // This will cause an error
}
```



### 2. String.trim()

문자열에 존재하는 공백을 제거한다.

```js
var str = "       Hello World!        ";
console.log(str.trim());  // "Hello World!"
```



### 3. Array.isArray()

Object가 Array인지 검사한다.

```js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(Array.isArray(fruits));  // true
```



### 4. Array.forEach()

Array의 element들을 하나씩 호출한다.

```js
var numbers = [45, 4, 9, 16, 25];
numbers.forEach(myFunction);

function myFunction(value) {
  console.log(value);
}

// 45, 4, 9, 16, 25
```



### 5. Array.map()

Array를 순회하면서 새로운 Array를 생성한다. 

기존에 있던 Array는 변경되지 않는다.

```js
var numbers1 = [45, 4, 9, 16, 25];
var numbers2 = numbers1.map(myFunction);

function myFunction(value) {
  return value * 2;
}

console.log(numbers2); // [90, 8, 18, 32, 50]
```



### 6. Array.filter()

Array를 순회하면서 조건에 맞는 새로운 Array를 생성한다.

기존에 있던 Array는 변경되지 않는다.

```js
var numbers = [45, 4, 9, 16, 25];
var over18 = numbers.filter(myFunction);

function myFunction(value) {
  return value > 18;
}

console.log(over18); // [45, 25]
```



### 7. Array.reduce()

각 element를 순회하면서 새로운 value를 생성한다.

기존에 있던 Array는 변경되지 않는다.

```js
var numbers1 = [45, 4, 9, 16, 25];
var sum = numbers1.reduce(myFunction);

function myFunction(total, value) {
  console.log(total); // 45 -> 49 -> 58 -> 74
  return total + value;
}

console.log(sum) // 99
```



### 8. Array.reduceRight()

Array.reduce()와 같은 기능이지만, 오른쪽부터 순회한다.

기존에 있던 Array는 변경되지 않는다.

```js
var numbers1 = [45, 4, 9, 16, 25];
var sum = numbers1.reduceRight(myFunction);

function myFunction(total, value) {
  console.log(total); // 25 -> 41 -> 50 -> 54
  return total + value;
}

console.log(sum) // 99
```



### 9. Array.every()

Array의 **모든 element들이 주어진 조건을 만족하는지 검사**한다.

```js
var numbers = [45, 4, 9, 16, 25];
var allOver18 = numbers.every(myFunction);

function myFunction(value) {
  return value > 18;
}

console.log(allOver18) // false
```



### 10. Array.some()

Array의 **element 중에 주어진 조건을 만족하는 element가 있는지 검사**한다.

```js
var numbers = [45, 4, 9, 16, 25];
var allOver18 = numbers.every(myFunction);

function myFunction(value) {
  return value > 18;
}

console.log(allOver18) // true
```



### 11. Array.indexOf()

Array의 element 중 주어진 value와 같은 element의 위치를 반환한다.

```js
var fruits = ["Apple", "Orange", "Apple", "Mango"];
var a = fruits.indexOf("Apple");

console.log(a); // 0
```



### 12. Array.lastIndexOf()

Array.indexOf()와 같지만, Array의 뒷 쪽부터 순회한다.

```js
var fruits = ["Apple", "Orange", "Apple", "Mango"];
var a = fruits.indexOf("Apple");

console.log(a); // 2
```



### 13. JSON.parse()

웹 서버로부터 데이터를 받았을 때 string 타입의 데이터를 javascript의 object 타입으로 바꿔준다.

데이터는 JSON의 형태를 가진다.

```js
var txt = '{"name":"John", "age":30, "city":"New York"}' 
console.log(typeof txt) // type : string

var obj = JSON.parse(txt);
console.log(typeof obj) // type : object
```



### 14. JSON.stringify()

JSON 형태의 데이터를 웹 서버로 전송할 때 string 타입으로 바꿔준다.

```js
var obj = { name: "John", age: 30, city: "New York" };
console.log(typeof obj) // type : object

var myJSON = JSON.stringify(obj);
console.log(typeof myJSON) // type : string
```



### 참조

- [Javascript ES5 정리](https://k39335.tistory.com/81?category=699283)
- [W3Schools JS ES5](https://www.w3schools.com/js/js_es5.asp)