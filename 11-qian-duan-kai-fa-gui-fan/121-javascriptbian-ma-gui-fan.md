### Object

* 杜绝使用var，用const和let替代

* object字面量简写

```js
// bad
const name = "david";
const obj = {
    name: name,
}

// good
const name = "david";
const obj = {
    name,
}
```

* 不要用引号包裹object属性名称除非属性名称含有特殊标识符。

```js
// bad
const obj = {
    'age': 10,
    'data-blah': 1,
}

// good
const obj = {
    age: 10,
    'data-blah': 1,
}
```

* 不要直接调用Object.prototype中的方法，如hasOwnProperty, isPrototypeOf等

  why? 一个对象有可能通过Object.create\(null\)生成，这样的对象中不含有Object的原型方法。

```js
// bad
console.log(object.hasOwnProperty(key));

// good
console.log(Object.prototype.hasOwnProperty.call(obj, key));
```

### Array

* 使用ES6扩展操作符做浅拷贝。

```js
// good
const itemsCopy = [...items];
```

* 对于array-like的对象，通过ES6扩展符将它转化为数组。

```js
const foo = document.querySelectorAll('.foo');

// bad
const nodes = Array.prototype.slice.call(foo);

// good
const nodes = Array.from(foo);

// best
const nodes = [...foo];
```

* 如果数组中有多行，在前括号后和后括号前都需要换行。

```js
// bad
const objectInArray = [{
  id: 1,
}, {
  id: 2,
}];

// good
const objectInArray = [
  {
    id: 1,
  },
  {
    id: 2,
  },
];
```

### ES6解构

* 使用ES6解构取得对象中的属性。

```js
// bad
function getFullName(user) {
  const firstName = user.firstName;
  const lastName = user.lastName;

  return `${firstName} ${lastName}`;
}

// good
function getFullName(user) {
  const { firstName, lastName } = user;
  return `${firstName} ${lastName}`;
}

// best
function getFullName({ firstName, lastName }) {
  return `${firstName} ${lastName}`;
}
```

* 数组中尽量通过解构获得item。

```js
const arr = [1, 2, 3, 4];

// bad
const first = arr[0];
const second = arr[1];

// good
const [first, second] = arr;
```

### String

* 用单引号包裹string。
* 用ES6 template合并字符串。

```js
// bad
function sayHi(name) {
  return 'How are you, ' + name + '?';
}

// bad
function sayHi(name) {
  return ['How are you, ', name, '?'].join();
}

// bad
function sayHi(name) {
  return `How are you, ${ name }?`;
}

// good
function sayHi(name) {
  return `How are you, ${name}?`;
}
```

* 代码中不允许使用eval\(\)。

### Function

* function的参数名不能是arguments，它会覆盖function本身的arguments造成意想不到的后果。

```js
// bad
function foo(name, options, arguments) {
  // ...
}

// good
function foo(name, options, args) {
  // ...
}
```

* 在方法体内不允许使用arguments，用rest syntax替代。

```js
// bad
function concatenateAll() {
  const args = Array.prototype.slice.call(arguments);
  return args.join('');
}

// good
function concatenateAll(...args) {
  return args.join('');
}
```

* 永远把有默认值的参数放到最后。

```js
// bad
function handleThings(opts = {}, name) {
  // ...
}

// good
function handleThings(name, opts = {}) {
  // ...
}
```

* 不要对参数重新赋值。

```js
// bad
function f1(a) {
  a = 1;
  // ...
}

function f2(a) {
  if (!a) { a = 1; }
  // ...
}

// good
function f3(a) {
  const b = a || 1;
  // ...
}

function f4(a = 1) {
  // ...
}
```

* 优先使用ES6扩展符调用多个参数。

```js
// bad
const maximum = Math.max.apply(null, [1,2,3,4,5]);

// good
const maximum = Math.max(...[1,2,3,4,5]);
```

* 尽量避免使用普通函数，并使用箭头函数。

  why？箭头函数可以保留外层this，从而解决了一些this指向不正确的问题，代码更加简洁。

```js
// bad
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});x

// good
[1, 2, 3].map(x => {
  const y = x + 1;
  return x * y;
});
```

### Modules

* 使用import加载模块，不要使用require\(\)。

* 不要export连写from。

```js
// bad
// filename es6.js
export { es6 as default } from './styleGuide';

// good
// filename es6.js
import { es6 } from './styleGuide';
export default es6;
```

* 不能重复加载同一个文件。

```js
// bad
import foo from 'foo';
import { named1, named2 } from 'foo';

// good
import foo, { named1, named2 } from 'foo';
```

* export的变量必须是const，不能是let。

```js
// bad
let foo = 3;
export { foo };

// good
const foo = 3;
export { foo };
```

* 如果只有一个export导出，使用export default。

```js
// bad
export function foo() {}

// good
export default function foo() {}
```

* 将所有的import放到文件最上面。

```js
// bad
import foo from 'foo';
foo.init();

import bar from 'bar';

// good
import foo from 'foo';
import bar from 'bar';

foo.init();
```

* 加载node\_module的import放到加载本地文件的import上面。

```js
// bad
import config from './config';
import path from 'path';

// good
import path from 'path';
import config from './config';
```



