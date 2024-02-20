# Hoisting

## 1

What will be the output of the following code?

```js
console.log(func());

function func() {
  return "JS";
}
```

<details>
  <summary>Answer</summary>

`"JS"`

</details>

---


## 2

What will be the output of the following code?

```js
function func() {
  console.log(test);
  var test = "JS";
}

func();
```

<details>
  <summary>Answer</summary>

`undefined`

</details>

---



## 3

What will be the output of the following code?

```js
var test = "JS";
function func() {
  console.log(test);
  var test = "React";
}

func();
```

<details>
  <summary>Answer</summary>

`undefined`

</details>

---



## 4

What will be the output of the following code?

```js
console.log(test);
if (false) {
  var test = "JS";
}

console.log(test);
```

<details>
  <summary>Answer</summary>

```
undefined
undefined
```

</details>

---



## 5

What will be the output of the following code?

```js
var test = "JS";

function test() {
  return "React";
}

console.log(test);
```

<details>
  <summary>Answer</summary>

`"JS"`

</details>

---



## 6

What will be the output of the following code?

```js
function func() {
  var test = "JS";
  return "React";
}

func();
console.log(test);
```

<details>
  <summary>Answer</summary>

`ReferenceError: test is not defined`

</details>

---



## 7

What will be the output of the following code?

```js
console.log(test);
if (true) {
  var test = "JS";
}
console.log(test);
```

<details>
  <summary>Answer</summary>

```
undefined
JS
```

</details>

---



## 8

What will be the output of the following code?

```js
function test() {
  return "React";
}

var test;

console.log(test);
```

<details>
  <summary>Answer</summary>

`[Function: test]`

</details>

---



## 9

What will be the output of the following code?

```js
console.log(test);
test = "JS";
```

<details>
  <summary>Answer</summary>

`ReferenceError: test is not defined`

</details>

---



## 10

What will be the output of the following code?

```js
console.log(test);
window.test = "JS";
```

<details>
  <summary>Answer</summary>

`ReferenceError: test is not defined`

</details>

---



## 11

What will be the output of the following code?

```js
function test() {
  return "JS";
}

var test = undefined;

console.log(test);
```

<details>
  <summary>Answer</summary>

`undefined`

</details>

---



## 12

What will be the output of the following code?

```js
console.log(func);

var func = function () {
  return "JS";
};
```

<details>
  <summary>Answer</summary>

`undefined`

</details>

---



## 13

What will be the output of the following code?

```js
var func = function test() {
  return "JS";
};

console.log(test());
```

<details>
  <summary>Answer</summary>

`ReferenceError: test is not defined`

</details>

---



## 14

What will be the output of the following code?

```js
console.log(Test);

var Test = class {};
```

<details>
  <summary>Answer</summary>

`undefined`

</details>

---



## 15

What will be the output of the following code?

```js
console.log(test());
function test() {
  return "First";
}
console.log(test());
function test() {
  return "Second";
}
console.log(test());
```

<details>
  <summary>Answer</summary>

```
Second
Second
Second
```

</details>

---



## 16

What will be the output of the following code?

```js
console.log(test);
var test = "JS";
console.log(test);
var test = "REACT";
console.log(test);
```

<details>
  <summary>Answer</summary>

```
undefined
JS
REACT
```

</details>

---



## 17

What will be the output of the following code?

```js
if (true) {
  console.log(test);
  let test = "JS";
}
```

<details>
  <summary>Answer</summary>

`ReferenceError: Cannot access 'test' before initialization`

</details>

---



## 18

What will be the output of the following code?

```js
console.log(test);
let test = "JS";
console.log(test);
let test = "REACT";
console.log(test);
```

<details>
  <summary>Answer</summary>

`SyntaxError: 'test' has already been declared`

</details>

---



## 19

What will be the output of the following code?

```js
let test;
function test() {
  return "React";
}

console.log(test);
```

<details>
  <summary>Answer</summary>

`SyntaxError: 'test' has already been declared`

</details>

---



## 20

What will be the output of the following code?

```js
console.log(Test);

class Test {}
```

<details>
  <summary>Answer</summary>

`ReferenceError: Cannot access 'Test' before initialization`

</details>

---



## 21

What will be the output of the following code?

```js
if (true) {
  const func = function () {
    console.log(test);
  };

  let test = "JS";
  func();
}
```

<details>
  <summary>Answer</summary>

`JS`

</details>

---



## 22

What will be the output of the following code?

```js
console.log(test);
if (true) {
  let test = "JS";
}
console.log(test);
```

<details>
  <summary>Answer</summary>

`ReferenceError: test is not defined`

</details>

---



## 23

What will be the output of the following code?

```js
if (true) {
  class Test {}
}

console.log(Test);
```

<details>
  <summary>Answer</summary>

`ReferenceError: Test is not defined`

</details>

---


