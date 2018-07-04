###### 

## 该规范基于airbnb

1. var/let/const

        why? var没有块级作用域，容易引起难以注意的bug.

```
// bad
var a = 1;
var b = 2;

// good
const a = 1;
const b = 2;
```

### 

```
// bad
var count = 1;
if (true) {
    count += 1;
}
// good
let count = 1;
if (true) {
    count += 1;
}
```



