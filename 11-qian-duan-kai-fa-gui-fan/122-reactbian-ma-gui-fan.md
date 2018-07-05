* 一个文件只能包含一个React组件。
* 使用 class XXX extends React.Component的方式创建组件。

```js
// bad
const Listing = React.createClass({
  // ...
  render() {
    return <div>{this.state.hello}</div>;
  }
});

// good
class Listing extends React.Component {
  // ...
  render() {
    return <div>{this.state.hello}</div>;
  }
}
```

* 无论是jsx还是js文件，都统一使用.js后缀名。

* jsx的文件的命名为帕斯卡(首字母大写)命名。

* 对齐方式。

```js
// bad
<Foo superLongParam="bar"
     anotherSuperLongParam="baz" />

// good
<Foo
  superLongParam="bar"
  anotherSuperLongParam="baz"
/>

// if props fit in one line then keep it on the same line
<Foo bar="bar" />

// children get indented normally
<Foo
  superLongParam="bar"
  anotherSuperLongParam="baz"
>
  <Quux />
</Foo>
```

* 所有JSX的属性用双引号引用，但是其他JS都用单引号（参考JavaScript编码规范）

```js
// bad
<Foo bar='bar' />

// good
<Foo bar="bar" />

// bad
<Foo style={{ left: "20px" }} />

// good
<Foo style={{ left: '20px' }} />
```

* Props命名为驼峰。

```js
// bad
<Foo
  UserName="hello"
  phone_number={12345678}
/>

// good
<Foo
  userName="hello"
  phoneNumber={12345678}
/>
```

* 如果Props是bool类型且值为true，省略值。

```js
// bad
<Foo hidden={true} />

// good
<Foo hidden />
```

* 如果jsx没有子元素，则必须自闭合。

```js
// bad
<Foo variant="stuff"></Foo>

// good
<Foo variant="stuff" />
```

* 如果jsx占多行，则闭合标签必须另起一行。

```js
// bad
<Foo
  bar="bar"
  baz="baz" />

// good
<Foo
  bar="bar"
  baz="baz"
/>
```

* 不要在jsx中使用bind(this), 使用es6 decorator的方式让bind(this更优雅), 参考miya-react-boilerplate.

```js
// bad
class extends React.Component {
  onClickDiv() {
    this.setState(...);
  }

  render() {
    return <div onClick={this.onClickDiv.bind(this)} />;
  }
}

// good
import autobind from 'autobind-decorator';

class extends React.Component {
  @autobind
  onClickDiv() {
    this.setState(...);
  }

  render() {
    return <div onClick={this.onClickDiv} />;
  }
}
```

* React组件中的方法用驼峰命名。

```js
// bad
class extends React.Component {
  _onClickSubmit() {
    // do stuff
  }

  // other stuff
}

// good
class extends React.Component {
  onClickSubmit() {
    // do stuff
  }

  // other stuff
}
```

* React组件的Props必须提供propType验证。

* React组件中在使用setState中不能调用this.state.xxx。setState可以接受一个方法作为参数，这个方法的第一个参数为之前的state。

```js
// bad
click() {
  this.setState({
    clickTimes: this.state.clickTimes + 1,
  });
}

// good
click() {
  this.setState(prev => ({
    clickTimes: prev.clickTimes + 1,
  }));
}
```
