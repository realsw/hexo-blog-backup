---
title: JavaScript笔记
date: 2023-02-05 22:42:15
tags:
---



> ## JavaScript 圣杯模式：
>
> 

```javascript
function inherit(Target,Origin){
    function F(){};
    F.prototype = Origin.prototype;
    Target.prototype = new F();
    Target.protype.constuctor = Target;
    Target.prototype.uber = Origin.prototype;
}
```

> ## JavaScript instanceof：
>
> 看 A 的对象原型链上有没有 B 的原型。

```javascript
A instanceof B
```

