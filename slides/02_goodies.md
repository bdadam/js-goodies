# ES2015

--

# ES2016

--

# ES2017

--

# const and let vs. var

```js
const five = 5;
five = 6; // Uncaught TypeError: Assignment to constant variable.

function test() {
  const a = 'a';
}

console.log(a); // Uncaught ReferenceError: a is not defined
```

--

# Arrow functions
```js
const inc = num => { return num + 1; };
const add = (a, b) => a + b;
```

--

# Default parameters

```js
const inc = (x, y = 1) => x + y;
inc(5, 3); // 8
inc(5); // 6
```

--

# Spread operator
```js
const numbers = [1, 2, 3, 4, 5];
Math.max(...numbers); // same as: Math.max.apply(null, numbers);

const divs = [...document.querySelectorAll('div')];
```

--

# Template literals
- multiline strings
- string interpolation

```js
const name = 'Adam';
const hello = `Hello ${name}!
This is the ${ 1 + 1 }nd line.
/*
"Hello Adam!
This is the 2nd line.
"
*/
`;
```

--

# Array methods

```js
const fibnumbers = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55];
fibnumbers.find(x => x === 13); // 13
fibnumbers.findIndex(x => x === 13); // 6
```

--

# Object literals
### Computed keys

```js
const key = 'name';
const o1 = {
  title: 'JS Goodies',
  [key]: 'Adam'
}; // Object {title: "JS Goodies", name: "Adam"}
```

--

# Object literals
### Methods

```js
const key = 'name';
const person = {
  speak() { console.log('Blah blah'); },
  get age() { return Math.random() * 100 | 0; },
  get name() { return this._name; },
  set name(value) { this._name = value; }
};
person.speak();
person.name = 'Name';
console.log(person.name); // "Name"
```
