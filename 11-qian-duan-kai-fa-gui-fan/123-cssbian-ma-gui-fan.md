* 使用2个空格来缩进，可以配置编辑器让tab变为2个空格以方便开发。

```css
// bad
.one {
color: red;
}

// good
.one {
  color: red;
}
```

* class命名使用"-"， 不要使用驼峰或下划线。

```css
// bad
.myBook {
  color: red;
}
.my_book {
  color: red;
}

// good
.my-book {
  color: red;
}
```

* 如过多个class共享同一个css规则，每一个class单独占一行。

```css
// bad
.one, .two, .three {
  // ...
}

// good
.one,
.two,
.three {
  // ...
}
```

* "{"前面必须要有一个空格。
* "}"必须单独占一行。
* 每一个css规则后面都需要一个空行来间隔。


