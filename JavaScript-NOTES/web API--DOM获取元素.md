# web API1--DOM获取元素

变量声明：const

- **let**：声明**可重新赋值**的变量
- **const**：声明**不可重新赋值**的常量（必须初始化）

有了变量先给const,如果发现后面要修改，再改为let

为什么const声明的对象可以修改里面的属性？

- 因为对象是引用类型，里面存储的是地址，只要地址不变，就不会报错
- 建议数组和对象使用 const 来声明

## 根据CSS选择器来获取DOM元素

**1.选择匹配的第一个元素**

语法：
```
document.querySelector('css选择器')
```

参数：有效的CSS选择器字符串

返回值：CSS选择器匹配的第一个元素，一个HTMLElement对象。如果没有匹配到，则返回null

核心特性：可以直接操作修改。返回的是单个真实DOM元素对象，可直接调用属性和方法修改元素。

示例代码：
```
const firstBox = document.querySelector('.box');
firstBox.style.backgroundColor = 'blue';
firstBox.textContent = '修改完成';
firstBox.classList.add('active');
```

**2.选择匹配的多个元素**

语法：
```
document.querySelectorAll('css选择器')
```

参数：有效的CSS选择器字符串

返回值：CSS选择器匹配的NodeList对象集合，是一个伪数组（有长度有索引号的数组，但是没有数组方法）想要得到里面每一个对象，则需要遍历（for)的方式获得

NodeList：

NodeList 是 document.querySelectorAll () 返回的结果，是匹配 CSS 选择器的所有 DOM 元素组成的集合，属于类数组对象，无法直接修改，必须遍历后操作集合内的单个元素。

核心特性：不能直接修改整个集合。返回的是类数组集合，无DOM元素专属属性，直接修改会报错。

正确修改方式：遍历集合，逐个修改元素

```
 const lis = document.querySelectorAll('.nav li')
// console.log(lis)
for (let i = 0; i < lis.length; i++) {
  console.log(lis[i]) // 每一个小li对象
}
```



## 其他获取DOM 元素的方法

```
// 根据id获取一个元素
document.getElementById('nav')
// 根据 标签获取一类元素  获取页面 所有div
document.getElementsByTagName('div')
// 根据 类名获取元素  获取页面 所有类名为 w的
document.getElementsByClassName('w')
```

