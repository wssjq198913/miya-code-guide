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



