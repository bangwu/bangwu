---
title: Javascript style guide
date: 2016-05-30 08:00:00
description: "作为一个前端的程序员，我们怎样才能写出最优雅的JavaScript。"
tags: JavaScript
category: 前端
---
写了这么长时间的JavaScript，总结一下如何写出优雅的JavaScript代码，本文章的内容很多来自[Airbab](https://github.com/airbnb/javascript)，如果想了解更过知识，请参考[Airbab](https://github.com/airbnb/javascript)

## 数据类型

### ***基本类型：***当你定义基本类型时，可以参考一下方式

* string
* number
* boolean
* null
* undefined

```
const foo = 1;
let bar = foo;

bar = 9;

console.log(foo, bar); // => 1, 9
```

### ***复合类型：***当你定义复合类型是你可以使用如下的方式

* object
* array
* function

```
const foo = [1, 2];
const bar = foo;

bar[0] = 9;

console.log(foo[0], bar[0]); // => 9, 9
```

## 参考

### 2.1 尽可能的使用`const`来定义你的引用，避免使用`var`	, 如果你使用`eslint`来检查你的代码，你可以尝试使用这些配置`prefer-const`, `no-const-assign`

> 这样可以确保你不会错误的对你的应用再次赋值，这样会导致一些bug并且使你的代码很难理解。

```
//bad
var a = 1;
var b = 2;

//good
const a = 1;
const b = 2;

```

### 2.2 如果你必须给你的引用重新赋值，你可以使用`let`而不是`var`。
> 他们的作用域不同，`let`是块级别的，`var`是function级别的

```
// bad
var count = 1;
if (true) {
  count += 1;
}

// good , use the let
let count = 1;
if (true) {
  count += 1;
}
```


### 注意`let`和`cont`都是块级别的作用域

```
// const and let only exist in the blocks they are defined in.
{
  let a = 1;
  const b = 1;
}
console.log(a); //ReferenceError
console.log(b); //ReferenceError
```