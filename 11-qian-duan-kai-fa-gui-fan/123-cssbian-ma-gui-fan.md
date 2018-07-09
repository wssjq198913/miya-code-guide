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

* 冒号后面需要一个空格。
```css
// bad
.one {
  color:red;
}

// good
.one {
  color: red;
}
```

* 所有属性值后面都需要用分号结尾。

```css
.one {
  color: red
}

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

* "{"跟在选择器后面，而且它前面必须要有一个空格。

```css
// bad
.one{
  // ...
}

// good
.one {
  // ...
}
```

* "}"必须单独占一行。

```css
// bad
.one {
  // ... }

// good
.one {
  // ...
}
```

* 每一个css规则后面都需要一个空行来间隔。

```css
// bad
.one {
  // ... 
}
.two {
  // ...
}

// good
.one {
  // ...
}

.two {
  // ...
}
```

* css的命名在有语义的基础上越简洁越好。

```css
// bad
.navigation {}
.atr {}

// good
.nav {}
.author {}
```

* 避免在id或者class前面使用type选择器, 这会引起性能问题。

```css
// bad
ul#example {}
div.error {}

// good
#example {}
.error {}
```

* 使用css简写属性。

```css
// bad
.bad {
  font-family: palatino, georgia, serif;
  font-size: 100%;
  line-height: 1.6;
  padding-bottom: 2em;
  padding-left: 1em;
  padding-right: 1em;
  padding-top: 0;
}

// good
.good {
  font: 100%/1.6 palatino, georgia, serif;
  padding: 0 1em 2em;
}
```

* 没有border，不要使用none，应该用0.

```css
// bad
.one {
  border: none; 
}

// good
.one {
  border: 0;
}
```

* 规则按照位置，display/盒模型，颜色，文字，其它的顺序排列，具体如下。

```css
.good {
  /* Positioning */
  position: absolute;
  z-index: 10;
  top: 0;
  right: 0;

  /* Display & Box Model */
  display: inline-block;
  overflow: hidden;
  box-sizing: border-box;
  width: 100px;
  height: 100px;
  padding: 10px;
  border: 10px solid #333;
  margin: 10px;

  /* Color */
  background: #000;
  color: #fff
  
  /* Text */
  font-family: sans-serif;
  font-size: 16px;
  line-height: 1.4;
  text-align: right;

  /* Other */
  cursor: pointer;
}
```

* 长度如果为0，则省略单位。

```css
// bad
.bad {
  margin: 0px;
  padding: 0px;
}

// good
.good {
  margin: 0;
  padding: 0;
}
```

* 长度为零点几的时候，省略0。

```css
// bad
.bad {
  font-size: 0.5rem;
}

// good
.good {
  font-size: .5rem;
}
```

* css规则中使用单引号，url()里面不加引号。

```css
// bad
@import url("https://www.google.com/css/maia.css");

html {
  font-family: "open sans", arial, sans-serif;
}

// good
@import url(https://www.google.com/css/maia.css);

html {
  font-family: 'open sans', arial, sans-serif;
}
```





