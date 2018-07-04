### Object

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
console.log(Object.prototype.hasOwnProperty.call(obj, key));
```

### Array

* 使用ES6扩展操作符做浅拷贝。

```js
// good
const itemsCopy = [...items];
```

* 对于array-like的对象，通过ES6扩展符将它转化为数组。

```

```



