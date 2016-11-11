# ES2015

--

# ES2016

--

# ES2017

--

### const and let vs. var

```js
const five = 5;
five = 6; // Uncaught TypeError: Assignment to constant variable.

function test() {
  const a = 'a';
}

console.log(a); // Uncaught ReferenceError: a is not defined
```

--

```js
for (var i = 0; i < 3; i++) {
  setTimeout(function() { console.log(i); }, 1);
}
// 3, 3, 3

for (let i = 0; i < 3; i++) {
  setTimeout(function() { console.log(i); }, 1);
}
// 0, 1, 2
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

# String Methods

```js
'asdfghjkl'.startsWith('asdf'); // true
'asdfghjkl'.endsWith('kl'); // true
'asdfghjkl'.includes('fg'); // true
'ha '.repeat(3); // "ha ha ha "
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
fibnumbers.includes(8); // true
```

--

# Object literals

### superset of JSON

```js
const obj = {
  "key": "value",
  or_key: 'value',
  no_quotes_needed: true,
  regex: /asdf/ig,
  fn: x => x + 1
};
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

# Properties

```js
const obj = {};
Object.defineProperty(obj, 'key', {
  enumerable: false,
  configurable: false,
  writable: false,
  value: 'value'
});
```

--

# Object literals
### Methods and properties

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
