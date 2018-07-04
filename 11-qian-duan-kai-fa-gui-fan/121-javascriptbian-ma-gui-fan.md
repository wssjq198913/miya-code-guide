* #### 杜绝使用var，用const和let替代
* #### object字面量必须简写

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

* 


