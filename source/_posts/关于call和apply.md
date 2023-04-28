---
title: 关于call和apply
date: 2023-04-27 18:04:08
tags:
---

`call()` 和 `apply()` 是 JavaScript 中两个常用的函数方法，它们可以用于改变函数的执行上下文和传入参数。<!--more-->

两者的区别在于传递参数的方式不同：

- `call()` 的第一个参数是要绑定给函数上下文的对象，后续参数是函数的参数列表，逐个列出。例如，`function.call(context, arg1, arg2, ...)`
- `apply()` 的第一个参数也是要绑定给函数上下文的对象，但是后续参数是以数组或类数组对象的形式传递的。例如，`function.apply(context, [arg1, arg2, ...])`

下面是一个例子，演示如何使用 `call()` 和 `apply()`：

```javascript
function greet(name) {
  console.log(`Hello, ${name}! I am ${this.name}.`);
}

const person1 = {
  name: 'Alice'
};

const person2 = {
  name: 'Bob'
};

greet.call(person1, 'Lily'); // 输出: Hello, Lily! I am Alice.
greet.apply(person2, ['John']); // 输出: Hello, John! I am Bob.
```

注意，`call()` 和 `apply()` 主要作用是用不同的对象来调用同一个函数，来改变函数内部的 `this` 指向。 如果不需要改变上下文，那么直接调用函数即可。
