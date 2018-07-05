### 空格规范

* 使用2个空格来缩进，可以配置编辑器让tab变为2个空格以方便开发。

```js
// bad
function foo() {
∙∙∙∙let name;
}

// bad
function bar() {
∙let name;
}

// good
function baz() {
∙∙let name;
}
```
* 大括号前必须加一个空格

```js
// bad
function test(){
  console.log('test');
}

// good
function test() {
  console.log('test');
}
```

* 在条件控制语句(if, while。。。)中，小括号前面需要一个空格， 但是在方法名后面不要加空格。

```js
// bad
if(isJedi) {
  fight ();
}

// good
if (isJedi) {
  fight();
}

// bad
function fight () {
  console.log ('Swooosh!');
}

// good
function fight() {
  console.log('Swooosh!');
}
```

* 操作符两边都需要一个空格。

```js
// bad
const x=y+5;

// good
const x = y + 5;
```

* 所有文件末尾需要加一个且仅一个空行。

```js
// bad
import { es6 } from './AirbnbStyleGuide';
  // ...
export default es6;
// bad
import { es6 } from './AirbnbStyleGuide';
  // ...
export default es6;↵
↵
// good
import { es6 } from './AirbnbStyleGuide';
  // ...
export default es6;↵
```

* 小括号和中括号两边不要加空格。

```js
// bad
function bar( foo ) {
  return foo;
}
const foo = [ 1, 2, 3 ];

// good
function bar(foo) {
  return foo;
}
const foo = [1, 2, 3];
```

* 逗号前面不加空格，但是逗号后面需要一个空格。

```js
// bad
var arr = [1 , 2];

// good
var arr = [1, 2];
```

* 每一行的末尾不要加空格。

### 逗号规范

* 逗号不能放在属性名前面。

```js
// bad
const story = [
    once
  , upon
  , aTime
];

// good
const story = [
  once,
  upon,
  aTime,
];
```

* ES6 trailing comma, 属性最后需要加一个额外的逗号。
why? 更方便diff工具比较，加新属性的时候更加方便

```js
// bad
const hero = {
  firstName: 'Ada',
  lastName: 'Lovelace',
  birthYear: 1815,
  superPower: 'computers'
};

// good
const hero = {
  firstName: 'Ada',
  lastName: 'Lovelace',
  birthYear: 1815,
  superPower: 'computers',
};
```

### 分号规范

* 语句末尾需要加分号。

```js
// bad - raises exception
const luke = {}
const leia = {}

// good 
const luke = {};
const leia = {};
```

### 命名规范

* 不允许使用单个字母的命名，命名必须语义化。

```js
// bad
function q() {
  // ...
}

// good
function query() {
  // ...
}
```

* 命名变量，方法，示例的时候用驼峰拼写。

```js
// bad
const OBJEcttsssss = {};
const this_is_my_object = {};
function c() {}

// good
const thisIsMyObject = {};
function thisIsMyFunction() {}
```

* Class用帕斯卡(首字母大写)拼写。

```js
// bad
function user(options) {
  this.name = options.name;
}

const bad = new user({
  name: 'nope',
});

// good
class User {
  constructor(options) {
    this.name = options.name;
  }
}

const good = new User({
  name: 'yup',
});
```

* 命名不能出现下划线

```js
// bad
this.__firstName__ = 'Panda';
this.firstName_ = 'Panda';
this._firstName = 'Panda';

// good
this.firstName = 'Panda';
```

### 变量

* 永远使用const或者let来声明变量，不能用var。

```js
// bad
superPower = new SuperPower();
var superPower = new SuperPower();

// good
const superPower = new SuperPower();
```

* 每一个变量都必须有一个const或者let。

```js
// bad
const a = 1,
      b = 2,
      c = 3;

// good
const a = 1;
const b = 2;
const c = 3;
```

* 分组const和let，即const变量放一起，let变量放一起，不要穿插。

```js
// bad
let i;
const items = getItems();
let dragonball;
const goSportsTeam = true;
let len;

// good
const goSportsTeam = true;
const items = getItems();
let dragonball;
let i;
let length;
```

* 不要链式赋值

```js
// bad
const a = b = c = 1;

// good
const a = 1;
const b = 1;
const c = 1;
```

* 不能出现没有被调用的变量，也就是说，任何变量一旦被生命，它就应该被使用。

### 注释

* 多行注释用/** ... */， 单行注释用//

```js
// bad
// make() returns a new element
// based on the passed in tag name
//
// @param {String} tag
// @return {Element} element
function make(tag) {

  // ...

  return element;
}

// good
/**
 * make() returns a new element
 * based on the passed-in tag name
 */
function make(tag) {

  // ...

  return element;
}
```

* 在注释标志符和注释文本中间必须有一个空格。

```js
// bad
//is current tab
const active = true;

// good
// is current tab
const active = true;
```

### Object

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

* 不要在方法中保存this，用箭头函数替代。

```js
// bad
function foo() {
  const self = this;
  return function () {
    console.log(self);
  };
}

// good
function foo() {
  return () => {
    console.log(this);
  };
}
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



