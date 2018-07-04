* 杜绝使用var，用const和let替代

* object字面量必须简写

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
console.log(Object.prototype.hasOwnProperty.call(object, key));

// best
const has = Object.prototype.hasOwnProperty; // cache the lookup once, in module scope.
/* or */
import has from 'has'; // https://www.npmjs.com/package/has
// ...
console.log(has.call(object, key));
```



