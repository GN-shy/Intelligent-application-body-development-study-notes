# js基础实战2-排错题-题目

==请说出以下代码都错在哪里，以及书写正确的代码==

## JS代码书写位置

```html
<script src="./02.js">
    alert('弹框出现')
</script>
```

分析错误：带 `src` 属性的 script 标签**内部不能写代码**，写了也会被忽略，属于语法规范错误。

正确写法：

```js
<script src="./02.js"><script>
<script>
    alert('弹框出现')
</script>
```





## 输出语句

```js
prompt(请输入您的姓名)
```

分析错误：`prompt` 的提示文字必须是**字符串，必须加引号**，不加会被当成变量，报未定义错误。

正确写法：

```js
prompt('请输入姓名')
```





## 变量01

```js
let age = 18
let age = 19
```

分析错误：`let` **不允许重复声明同一个变量**，会直接报错。

正确写法：

```
let age = 18
age = 19
```



## 变量02

```js
console.log(age)
let age = 18
```

分析错误：`let` 没有变量提升，**先使用后声明** 会报错（暂时性死区）。

正确写法：

```js
let age = 18
console.log(age)
```







## 字符串01

```js
let username = 张三
```

分析错误：字符串必须加引号，不加会被识别成变量，报未定义错误。

正确写法：

```js
let uname = '张三'
```







## 字符串02

```js
let uname = '张三"
```

分析错误：引号必须**成对且一致**，不能开头单引号、结尾双引号。

正确写法：

```js
let uname = '张三'
```







## 数组

```js
// 需求：取出 星期六 

let arr = ['星期一', '星期二', '星期三', '星期四', '星期五', '星期六', '星期日']
console.log(arr[6])
```

分析错误：数组索引**从 0 开始**，一共 6 个元素，最大索引是 5，arr [6] 是 undefined。

正确写法：

```js
let arr = ['星期一','星期二','星期三','星期四','星期五','星期六']
console.log(arr[5])
```









## 自增

```js
// 让num自身增加1

let num = 10

num + 1
```

分析错误：`num + 1` 只是计算，**没有赋值给 num**，num 永远不变。

正确写法：

```js
let num = 10
num++
console.log(num)
```









## switch分支

```js
let num = prompt('请输入一个数字')

switch (num) {
    case 1:
        alert('用户您输入的是数字1')
    case 2:
        alert('用户您输入的是数字2')
    case 3:
        alert('用户您输入的是数字3')
    default:
        alert('用户您输入的是非1、2、3的数字')
}
```

分析错误：`prompt` 返回**字符串**，case 是数字，类型不匹配，永远不执行

​                每个 case 后面**必须加 break**，否则会穿透

正确写法：

```js
let num = +prompt('输入数字')
switch (num) {
    case 1:
        alert('用户您输入的是数字1')
        break
    case 2:
        alert('用户您输入的是数字2')
        break
    case 3:
        alert('用户您输入的是数字3')
        break
    default:
        alert('用户您输入的是非1、2、3的数字')
        break
}
```







## while循环

```js
let num = 1
while (num <= 5) {
    document.write(`月薪过万不是梦<br/>`)
}
```

分析错误：循环条件永远成立（num 一直是 1），**没有写 num++，造成死循环**。

正确写法：

```js
let num = 1
while (num <= 5) {
    document.write(`月薪过万不是梦<br/>`)
    num++
}
```









## for循环

```js
for (let i = 1; i <= 3;) {
    document.write(`月薪过万不是梦 <br/>`)
}
```

分析错误：for 循环缺少**第三个表达式（i++）**，循环变量不递增，**死循环**。

正确写法：

```js
for (let i = 1; i <= 3; i++) {
    document.write(`月薪过万不是梦 <br/>`)
}
```







## 遍历数组

```js
// 需求：取出数组中的每一项

let arr = ['马超', '赵云', '张飞', '关羽', '黄忠', '小黑', '小红']

for (let i = 1; i < arr.length; i++) {
    console.log(arr[i])
}
```

分析错误：数组索引**从 0 开始**，i 从 1 开始会**漏掉第一个元素**

正确写法：

```js
let arr = ['马超', '赵云', '张飞', '关羽', '黄忠', '小黑', '小红']
for (let i = 0; i < arr.length; i++) {
    console.log(arr[i])
}
```







## 修改数组的项

```js
// 需求：将数组中的小白修改成 小灰灰
let arr = ['小黑', '小白', '小红']

arr = '小灰灰'
```

分析错误：直接给数组名赋值，会把**整个数组覆盖成字符串**，不是修改数组元素。

正确写法：

```js
let arr = ['小黑', '小白', '小红']
arr[1] = '小灰灰'
```







## 操作数组

```js
// 需求：在数组arr的最后面添加 blue

let arr = ['red', 'green']

arr.push = 'blue'
```

分析错误：`push` 是数组**方法**，必须**加括号调用**，不能直接赋值。

正确写法：

```js
let arr = ['red', 'green']
arr.push('blue')
```







## 对象

```js
// phone 手机对象

let phone = {
    size = 6.1
    play = function () {
        console.log('走起，吃鸡')
    }
}
```

分析错误：对象里**键值对必须用冒号 :**，不能用等号 `=`；属性之间要加逗号。

正确写法：

```js
let phone = {
    size: 6.1,
    play: function () {
        console.log('走起，吃鸡')
    }
}
```







## 遍历对象

```js
let obj = {
    uname: '小明',
    age: 18,
    sex: '男',
    height: 200,
}

// 遍历obj对象，取出对象的属性名和属性值
for (let k in obj) {
    console.log(k)
    console.log(obj.k)
}
```

分析错误：遍历对象必须用**方括号语法 obj[k]**，`obj.k` 会把 k 当作固定属性名，取不到值。

正确写法：

```js
let obj = {
    uname: '小明',
    age: 18,
    sex: '男',
    height: 200,
}
for (let k in obj) {
    console.log(k)
    console.log(obj[k])
}
```









