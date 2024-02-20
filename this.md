# This

## 1

What will be the output of the following code?

```js
// global scope
console.log(this);
```

<details>
  <summary>Answer</summary>

### In Browser

`window`

### In NodeJS

`{}`

</details>

---

## 2

What will be the output of the following code?

```js
// global scope
"use strict";

console.log(this);
```

<details>
  <summary>Answer</summary>

### In Browser

`window`

### In NodeJS

`{}`

</details>

---

## 3

What will be the output of the following code?

```js
// global scope
this.name = "Gor";

console.log(this.name);
```

<details>
  <summary>Answer</summary>

`"Gor"`

</details>

---

## 4

What will be the output of the following code?

```js
// global scope
"use strict";

this.name = "Gor";

console.log(this.name);
```

<details>
  <summary>Answer</summary>

`"Gor"`

</details>

---

## 5

What will be the output of the following code?

```js
// global scope
this = {
  name: "Ruben"
}

this.name = "Gor";

console.log(this.name)
```

<details>
  <summary>Answer</summary>

`SyntaxError: Invalid left-hand side in assignment`

</details>

## 6

What will be the output of the following code?

```js
const foo = function () {
  console.log(this);
};

foo();
```

<details>
  <summary>Answer</summary>

### In Browser
- Non-Strict Mode: `window`
- Strict Mode: `undefined`

### In NodeJs
- Non-Strict Mode: `global`
- Strict Mode: `undefined`


</details>

## 7

What will be the output of the following code?

```js
"use strict";

const foo = function () {
  console.log(this);
};

foo();
```

<details>
  <summary>Answer</summary>

`undefined`

</details>

## 8

What will be the output of the following code?

```js
const foo = () => {
  console.log(this);
};

foo();
```

<details>
  <summary>Answer</summary>

### In Browser

`window`

### In NodeJS

`{}`

</details>

## 9

What will be the output of the following code?

```js
const THIS = this

if (true) {
  console.log(this === THIS)
}
```

<details>
  <summary>Answer</summary>

`true`

</details>

## 10

What will be the output of the following code?

```js
const THIS = this

const foo =  () => {
  console.log(this === THIS)
}

foo();
```

<details>
  <summary>Answer</summary>

`true`

</details>

## 11

What will be the output of the following code?

```js
const foo =  () => {
  const THIS = this
  return () => {
    console.log(this === THIS)
  }
}

foo()();
```

<details>
  <summary>Answer</summary>

`true`

</details>

---

## 12

What will be the output of the following code?

```js
function foo() {
  console.log(this.abcdef)
}

const obj = {
  abcdef: 123,
  goo: foo,
}

obj.goo();

```

<details>
  <summary>Answer</summary>

`123`

</details>

---

## 13

What will be the output of the following code?

```js
function foo() {
  console.log(this.abcdef)
}

const obj = {
  abcdef: 123,
  goo: foo,
}

const getGoo = () => obj.goo

getGoo()();

```

<details>
  <summary>Answer</summary>

### Non-Strict Mode
`undefined`

### Strict Mode
`TypeError: Cannot read properties of undefined (reading 'abcdef')`

</details>

---

## 14

What will be the output of the following code?

```js
function foo() {
  console.log(this.abcdef)
};

const obj_1 = {
  abcdef: 123,
  goo: foo,
};

const obj_2 = {
  abcdef: 456,
  goo: foo,
};

(obj_1.goo === obj_2.goo ? obj_1.goo : obj_2.goo)();

```

<details>
  <summary>Answer</summary>

### Non-Strict Mode
`undefined`

### Strict Mode
`TypeError: Cannot read properties of undefined (reading 'abcdef')`

</details>

---

## 15

What will be the output of the following code?

```js
function foo() {
  console.log(this.abcdef)
};

const obj_1 = {
  abcdef: 123,
  goo: foo,
};

const obj_2 = {
  abcdef: 456,
  goo: foo,
};

(obj_1.goo === obj_2.goo ? obj_1 : obj_2).goo();

```

<details>
  <summary>Answer</summary>

`123`

</details>

---

## 16

What will be the output of the following code?

```js
function foo() {
  console.log(this.abcdef)
};

const obj = {
  abcdef: 123,
  goo: foo,
};

obj["goo"]();

```

<details>
  <summary>Answer</summary>

`123`

</details>

---

## 17

What will be the output of the following code?

```js
function foo() {
  console.log(this.abcdef)
};

const obj = {
  abcdef: 123,
  goo: foo,
};

const getGooName = () => "goo";

obj[getGooName()]();

```

<details>
  <summary>Answer</summary>

`123`

</details>

---

## 18

What will be the output of the following code?

```js
function f() {
  const foo = () => {
    console.log(this.abcdef)
  };

  const obj = {
    abcdef: 456,
    goo: foo,
  };

  obj.goo();
}

const obj = {
  abcdef: 123,
  f,
}

obj.f();

```

<details>
  <summary>Answer</summary>

`123`

</details>

---

## 19

What will be the output of the following code?

```js
const obj = {
    abcdef: 123,
    foo() {
      return () => {
        console.log(this.abcdef)
      }
    },
};


const g = obj.foo();
g();
```

<details>
  <summary>Answer</summary>

`123`

</details>

---

## 20

What will be the output of the following code?

```js
const obj = {
    abcdef: 123,
    a: {
      foo() {
        console.log(this.abcdef)
      }
    },
};

obj.a.foo();
```

<details>
  <summary>Answer</summary>

`undefined`

</details>


---

## 21

What will be the output of the following code?

```js
const foo = (a, b) => {
  console.log(this.abcdef)
  console.log(a)
  console.log(b)
}

const obj = {
  abcdef: 1
}

foo.call(obj, 2, 3, 4)
```

<details>
  <summary>Answer</summary>

```
undefined
2
3
```

</details>


---

## 22

What will be the output of the following code?

```js
this.abcdef = 6

function foo(a, b) {
  console.log(this.abcdef)
  console.log(a)
  console.log(b)
}

const obj = {
  abcdef: 1
}

foo.call(obj, 2, 3, 4)
```

<details>
  <summary>Answer</summary>

```
1
2
3
```

</details>


---

## 23

What will be the output of the following code?

```js
const obj = {
  abcdef: 1,
  foo() {
    console.log(this.abcdef)
  },
}

obj.foo.call({
  abcdef: 2,
})
```

<details>
  <summary>Answer</summary>

`2`

</details>


---

## 24

What will be the output of the following code?

```js
function foo(a, b) {
  return 4
}

console.log(foo.call(1, 2, 3))

```

<details>
  <summary>Answer</summary>

`4`

</details>


---

## 25

What will be the output of the following code?

```js
function foo(a, b) {
  console.log(this.abcdef)
  console.log(a)
  console.log(b)
}

foo.apply({
  abcdef: 1,
}, [2, 3, 4])
```

<details>
  <summary>Answer</summary>

```
1
2
3
```
</details>


---

## 26

What will be the output of the following code?

```js
function foo(a, b) {
  console.log(this.abcdef)
  console.log(a)
  console.log(b)
}

foo.apply({
  abcdef: 1,
}, 2, 3)
```

<details>
  <summary>Answer</summary>

`TypeError: CreateListFromArrayLike called on non-object`

</details>


---

## 27

What will be the output of the following code?

```js
function foo(a, b) {
  console.log(this.abcdef)
  console.log(a)
  console.log(b)
}

foo.apply({
  abcdef: 1,
}, [2], [3])

```

<details>
  <summary>Answer</summary>

```
1
2
undefined
```

</details>


---

## 28

What will be the output of the following code?

```js
const foo = (a, b) => {
  console.log(this.abcdef)
  console.log(a)
  console.log(b)
}

foo.apply({
  abcdef: 1,
}, [1])
```

<details>
  <summary>Answer</summary>

```
undefined
1
undefined
```

</details>


---

## 29

What will be the output of the following code?

```js
function foo() {
  console.log(this)
}

new foo()
```

<details>
  <summary>Answer</summary>

`{}`

</details>


---

## 30

What will be the output of the following code?

```js
function foo(a, b) {
  console.log(this)
  console.log(a)
  console.log(b)
}

new foo(1, 2, 3)
```

<details>
  <summary>Answer</summary>

```
{}
1
2
```

</details>


---

## 31

What will be the output of the following code?

```js
function foo(a, b) {
  console.log(this)
  console.log(a)
  console.log(b)
}

new foo
```

<details>
  <summary>Answer</summary>

```
{}
undefined
undefined
```

</details>


---

## 32

What will be the output of the following code?

```js
function foo() {}

const obj = new foo()
console.log(obj)
```

<details>
  <summary>Answer</summary>

`{}`

</details>


---

## 33

What will be the output of the following code?

```js
function foo() {
  this.name = "Gor"
}

const obj = new foo()
console.log(obj)

```

<details>
  <summary>Answer</summary>

`{ name: 'Gor' }`

</details>


---

## 34

What will be the output of the following code?

```js
function foo() {
  this.name = "Gor"
  return "Hello"
}

const obj = new foo()
console.log(obj)
```

<details>
  <summary>Answer</summary>

`{ name: 'Gor' }`

</details>


---

## 35

What will be the output of the following code?

```js
function foo() {
  this.name = "Gor"
  return {
    name: "Ruben"
  }
}

const obj = new foo()
console.log(obj)
```

<details>
  <summary>Answer</summary>

`{ name: 'Ruben' }`

</details>


---

## 36

What will be the output of the following code?

```js
function foo() {
  this.name = "Gor"
  return []
}

const obj = new foo()
console.log(obj)
```

<details>
  <summary>Answer</summary>

`[]`

</details>


---

## 37

What will be the output of the following code?

```js
const foo = () => {
  console.log(this)
}

new foo()
```

<details>
  <summary>Answer</summary>

`TypeError: foo is not a constructor`

</details>


---

## 38

What will be the output of the following code?

```js
const obj = {
  abcdef: 1,
  foo() {
    console.log(this.abcdef)
  }
}

new obj.foo();
```

<details>
  <summary>Answer</summary>

`TypeError: obj.foo is not a constructor`

</details>

---

## 39

What will be the output of the following code?

```js
const obj = {
  abcdef: 1,
  foo() {
    console.log(this.abcdef)
  }
}

const foo = obj.foo
new foo();
```

<details>
  <summary>Answer</summary>

`TypeError: foo is not a constructor`

</details>

---

## 40

What will be the output of the following code?

```js
const obj = {
  abcdef: 1,
  foo: function () {
    console.log(this.abcdef)
  }
}

new obj.foo();
```

<details>
  <summary>Answer</summary>

`undefined`

</details>

---

## 41

What will be the output of the following code?

```js
function foo() {
  console.log(this)
}

new foo.call({name: "Gor"})
```

<details>
  <summary>Answer</summary>

`TypeError: foo.call is not a constructor`

</details>

---

## 42

What will be the output of the following code?

```js
function foo() {
  this.name = "Gor"
}

const obj = foo();

console.log(obj)
```

<details>
  <summary>Answer</summary>

### Non-Strict Mode
`undefined`

### Strict Mode
`TypeError: Cannot set properties of undefined (setting 'name')`

</details>

---

## 43

What will be the output of the following code?

```js
function foo() {
  if (new.target) {
    console.log(1)
  } else {
    console.log(2)
  }
}

foo();
new foo();
```

<details>
  <summary>Answer</summary>

```
2
1
```

</details>


---

## 44

What will be the output of the following code?

```js
function foo() {
  return foo;
}


const obj = new new new foo();
console.log(obj)
```

<details>
  <summary>Answer</summary>

`[Function: foo]`

</details>

